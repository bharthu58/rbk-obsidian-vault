

Perplexity:

<img src="https://r2cdn.perplexity.ai/pplx-full-logo-primary-dark%402x.png" style="height:64px;margin-right:32px"/>

# Can you objectively compare claude code v/s jules v/s codex and github copilot for complex software projects in the financial domain such as developing a equities trading system, order management systems, matching engine, smart order router or a algo trading system from scratch.  How do we measure these clearly ?

You can compare these assistants, and measure them, but you have to separate two things:

1. their raw coding/agentic capabilities, and 2) your own engineering process and controls in a regulated, high‑risk domain like trading.

Below is a practical, *tool‑agnostic* way to think about this, and then a concrete scoring framework you can actually run as an evaluation project.

\---

## 1\. Role of AI in complex financial systems

For the kinds of systems you listed (OMS, matching engine, SOR, algo platform), present‑day assistants are best treated as:

* Design aides (architecture options, patterns, trade‑offs).
* Code generators for *local* components (adapters, services, tests, configs).
* Refactoring/review copilots.
* Documentation and test writers.

They should **not** be treated as primary system architects or as final authorities on market structure, regulation, or microstructure edge cases. Human quants/engineers still need to own:

* Overall architecture, latency budgets, failure modes.
* Microstructure edge cases (auction behavior, odd‑lots, peg behavior, dark pool rules).
* Reg obligations (MiFID II, Reg NMS, CAT reporting, best execution).

So the comparison question is really: *which assistant helps skilled engineers do this work faster, safer, and with fewer mistakes?*

\---

## 2\. What to compare: capability dimensions

Here are the main dimensions that matter for your use case, regardless of brand:

1. **Codebase‑scale reasoning**

   * Can it understand and modify a multi‑service codebase (e.g., 50–200 kLOC) with shared domain models?
   * Does it respect module boundaries, domain language, and existing patterns?
   * Does it handle multi‑file changes and keep them coherent?
2. **Domain modeling \& correctness**

   * Can it work with FIX/FAST, market data feeds, order lifecycle states, and risk controls without hallucinating concepts?
   * Does it keep exchange‑specific behavior straight (e.g., different time‑in‑force, auction types)?
   * Does it handle numerical precision and time correctly (rounding, time zones, clocks, sequence numbers)?
3. **Latency and performance awareness**

   * Does it suggest sane data structures and patterns for a low‑latency context (e.g., minimizing GC, avoiding unnecessary allocation or reflection, using lock‑free structures where appropriate)?
   * Does it avoid obviously bad patterns (chatty network calls on hot paths, heavy ORM in matching engine loops)?
4. **Security, safety, and compliance**

   * Handling of auth, secrets, logging, PII.
   * Graceful handling of failure: circuit breakers, backpressure, replay logic for dropped messages.
   * Generates tests for risk controls, position limits, kill switches.
5. **Testing and verification support**

   * Quality of unit, integration, and property‑based tests it generates.
   * Ability to build deterministic simulations and backtest harnesses for algos.
   * Ability to help you derive edge‑case scenarios from specs.
6. **Workflow integration**

   * How well it lives in your actual workflow: IDE, terminal, code review, CI.
   * How easy it is to keep it “aware” of configs, topology, runbooks, and production incidents.
7. **Reliability and steerability**

   * How often you need to “fight” it to follow instructions.
   * Whether you can reliably impose constraints: “no external libraries”, “no dynamic allocation in this loop”, “must be MiFID II compliant in these specific ways”.

\---

## 3\. How to *measure* them clearly

The only objective way is to run your own evaluation on realistic tasks. Think of it as a benchmark suite for *your* stack and domain.

### A. Define a scenario set

Design 10–20 scenario tasks spanning your systems:

* **Architecture / design**

  * “Propose 2 viable architectures for a low‑latency equities matching engine with separate risk and market data services; compare pros/cons and failure modes.”
  * “Refine this SOR architecture to support an additional dark venue with specific routing constraints.”
* **Implement/extend components**

  * “Implement an order state machine supporting partial fills, cancels, busts, and exchange rejects, with exhaustive tests.”
  * “Add a new exchange adapter following existing patterns, including FIX message mapping and recovery logic.”
* **Algo and backtesting**

  * “Implement an execution algo with POV and VWAP modes; add backtest harness and metrics (slippage, shortfall, participation).”
  * “Given this historical order book format, implement a replay engine to test routing logic deterministically.”
* **Risk and controls**

  * “Implement pre‑trade risk checks (max notional, max size, per‑symbol limits) with tests, logs, and admin overrides.”
  * “Add a kill‑switch mechanism that can stop all trading per account and symbol, with persistence and recovery.”
* **Non‑functional**

  * “Optimize this hot loop in the matching engine under a 99.9% latency budget; explain the trade‑offs.”
  * “Add observability (metrics, traces) to this microservice while respecting latency constraints.”

Make sure tasks:

* Are **non‑trivial** (require touching multiple files/layers).
* Have **hidden acceptance tests** and performance constraints so you can score objectively.
* Are representative of your tech stack (Java/C++/C#/Rust/Go, particular frameworks).



### B. Experimental protocol

For each tool:

1. **Environment**

   * Give it access to the same curated repo: simplified but realistic version of your systems (or a synthetic but close analogue).
   * Same time budget per task (say 60–90 minutes).
   * Same level of human interaction allowed (e.g., you can answer clarification questions, but not write code for it).
2. **Interaction pattern**

   * Decide whether you test:

     * “Assistant coding” (it writes most code), or
     * “Copilot mode” (you lead, it suggests small pieces).
   * Keep the pattern consistent across tools.
3. **Scoring rubric**

Per task, score along:

* **Functional correctness (0–5)**

  * 0: Fails tests or cannot complete.
  * 3: Works for typical cases but misses edge cases.
  * 5: Passes all tests including edge and failure cases.
* **Non‑functional/latency adherence (0–5)**

  * Did it obey constraints (e.g., no blocking IO in hot paths, reasonable allocations, respects time budgets on test harness)?
* **Code quality (0–5)**

  * Readability, adherence to your style, test quality, logging, and separation of concerns.
* **Security/safety (0–5)**

  * Handles errors, avoids leaking sensitive data in logs, has sane defaults and failure behavior.
* **Productivity gain (0–5)**

  * Time saved vs. a strong baseline human.
  * You can estimate by:

    * (Human‑only time – AI‑assisted time) / Human‑only time, bucketed into scores.
* **Steerability/compliance (0–5)**

  * How often it ignored constraints or hallucinated APIs.
  * Number of major corrections you had to make.

You can also track **hard metrics**:

* Number of human edit iterations per task.
* Number of lines changed to fix AI‑generated code.
* Number of production‑like defects found in review/tests.

Aggregate over all tasks to get per‑tool scores across dimensions.

### C. Example scoring table

You might end up with something like:



|Dimension|Weight|Tool A|Tool B|Tool C|Tool D|
|-|-|-|-|-|-|
|Functional correctness|30%|4.3|3.9|3.5|3.8|
|Latency/perf adherence|15%|3.8|3.0|2.7|3.1|
|Code quality|15%|4.5|3.7|3.2|3.9|
|Security/safety|10%|3.9|3.4|3.0|3.6|
|Productivity gain|20%|4.2|4.0|3.6|4.3|
|Steerability/compliance|10%|4.4|3.5|3.2|3.7|

…with names filled in once you have data.

\---

## 4\. Interpreting results for your systems

For trading/OMS/matching engines, you usually want to weight:

* **Correctness \& safety** > pure productivity.
* **Latencies and resource usage** > cosmetic code style.
* **Steerability** (obeying constraints, not hallucinating) > “wow” moments.

That may mean you pick:

* One “heavyweight” assistant for architecture, complex refactors, cross‑module work.
* One “inline copilot” for day‑to‑day small suggestions.

You can then define **guardrails**:

* All AI‑generated code must:

  * Be covered by tests that you or the AI wrote.
  * Go through human review with an explicit checklist (latency, risk, logging, failure modes).
  * Never touch certain ultra‑critical components directly (e.g., matching engine core) without additional scrutiny.

\---

## 5\. Concrete next steps for you

If you want to move from theory to data:

1. Pick one system type (say, SOR) and extract a **sanitized** internal or synthetic repo.
2. Define 8–10 tasks as above, with hidden tests.
3. Run a 2–3 week bake‑off with a small team, logging:

   * Time per task
   * Number of corrections
   * Final rubric scores
4. Use that to build an internal scorecard and choose:

   * “Primary architecture assistant”
   * “Inline coding copilot(s)”
   * Policy for where AI can/cannot be used.

If you’d like, describe your stack (languages, latency targets, venues, in‑house vs vendor OMS), and I can help you design an initial task suite and scoring weights tailored to your environment.
<span style="display:none">[^1\_1](https://www.youtube.com/watch?v=B6QmE_LOmYA)[^1\_2](https://snyk.io/pt-BR/articles/top-claude-skills-finance-quantitative-developers/)[^1\_4](https://every.to/p/how-claude-code-is-transforming-finance-without-turning-you-into-a-coder)[^1\_6](https://www.thoughtworks.com/en-us/insights/blog/generative-ai/claude-financial-services-what-need-know)[^1\_8](https://www.youtube.com/watch?v=NVHzrdjstFo)</span>

<div align="center">⁂</div>

