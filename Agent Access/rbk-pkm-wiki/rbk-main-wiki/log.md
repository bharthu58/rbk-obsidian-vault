# Wiki Operation Log

*Append-only. New entries go at the top.*

---

## [2026-04-17] ingest | DOCS/PKM LM/ (29 files → 3 pages)
Synthesised 3 wiki pages from 29 PKM reference files in DOCS/PKM LM/. Originals left in place (outside Agent Access/). Pages created: [[PKM — Note-Making Philosophy]] (meta/), [[Obsidian — Plugin Recommendations]] (obsidian/), [[Obsidian — Dataview Queries]] (obsidian/). Skipped: iOS/Drafts/iCloud-specific files (not applicable to WSL2+Windows setup), navigation stubs (General PKM, Task Management, Obsidian Setup, Productivity, Start Here — index files with no synthesisable content), writing/journaling-workflow files (secondary domain). Wiki now has 22 pages.

---

## [2026-04-17] restructure | domain subdirectories
Moved all 19 wiki pages from flat rbk-main-wiki/ into domain subdirectories: ai/ (6), cpp/ (3), devops/ (4), linux/ (2), python/ (1), obsidian/ (1), web/ (1), meta/ (1 — LLM Wiki Pattern). Updated index.md paths. Updated Overview.md v1.1. Infrastructure files (Overview.md, index.md, log.md) remain at root.

---

## [2026-04-16] ingest | Best C++ Lockfree Ring Buffers.md + vscode.md (gdoc exports) + MyLearn re-ingestions

New: Created [[C++ — Lock-Free Ring Buffers]] from Best C++ Lockfree Ring Buffers.md → ingested/notes/
New: Updated [[DevOps — IDE Comparison (Cursor vs VS Code)]] v1.1 with VS Code extensions section from vscode.md → ingested/notes/
Re-ingestions: 12 MyLearn files (content unchanged, no wiki updates) → ingested/notes/ and ingested/documentation/
Skipped: TargetRoles.docx → ingested/assets/ (user instruction)
Cleanup: raw/MyLearn/ folder deleted via PowerShell (broken WSL/GDrive state).
Wiki now has 19 pages.

## [2026-04-16] ingest | git-cheat-sheet-education.pdf (retry after poppler install)

Created [[DevOps — Git Cheat Sheet]] from MyLearn/DEVOPS/git-cheat-sheet-education.pdf. Index updated. Wiki now has 18 pages.

## [2026-04-16] ingest | MyLearn/ bulk ingest (13 pages, 6 domains)

Sources: MyLearn/AI/ (4 md + 9 images), MyLearn/C++/ (1 image), MyLearn/DEVOPS/ (2 md), MyLearn/Linux/ (1 md), MyLearn/Python/ (2 md), MyLearn/WEB/ (1 md), _assets/images/linux/ (1 image). Originals NOT moved (user instruction). Unreadable: 4 .gdoc files, 1 .docx, 1 .pdf (no poppler).

Pages created:
- [[AI — Learning Resources & Roadmap]]
- [[AI — 30-Day Mastery Mind Map]]
- [[AI — Agent Frameworks (N8N vs LangGraph)]]
- [[AI — Open Source RAG Stack]]
- [[AI — Coding Assistants for Financial Domain Evaluation]]
- [[AI — Claude Code Tips]]
- [[C++ — auto Type Deduction Reference]]
- [[DevOps — GitHub vs GitLab]]
- [[DevOps — Tool Version Management (mise)]]
- [[DevOps — IDE Comparison (Cursor vs VS Code)]]
- [[Linux — Commands Reference]]
- [[Linux — WSL2 Obsidian Vault Access]]
- [[Python — Package Management (uv and pipx)]]
- [[WEB — Markdown Reference]]

Index and Overview.md updated. Wiki now has 17 pages across 7 domains.

## [2026-04-16] crystallize | Wiki initialization session

Created [[Overview]] — session bootstrap page covering directory layout, current domains, operational notes from setup, and session checklist. Updated index.md. Updated Overview.md: N/A (this is the creation). Thread is the first session; continuing is fine.

## [2026-04-16] ingest | Lost in Modern C++ This Feature Map Shows Where Everything Fits (C++20–23).md + 5 image assets

Source: Medium article by Sagar (Towards Dev) clipped 2026-04-16. Companion images (Image.webp through Image 4.webp) read via vision — all 5 successful.
Created [[C++ — Modern Features Reference (C++20-23)]] — 10-category feature reference table + decision flowchart summary.
Markdown moved to ingested/clippings/; images moved to ingested/assets/. Index entry added under new section "C++ / Systems Programming".

## [2026-04-16] ingest | llm-wiki.md + Obsidian Google Docs plugin search

First ingest run. Wiki initialised (index.md, log.md created). Two sources processed from raw/web-clippings/:

- `llm-wiki.md` → synthesised into [[LLM Wiki Pattern]] → moved to ingested/clippings/
- `best community plugin for displaying google docs and word docs in obsidian - Google Search.md` → synthesised into [[Obsidian — Word and Google Docs Integration]] → moved to ingested/clippings/

Both pages cross-linked. Index entries added under two new sections: Knowledge Management & LLM Methodology, Obsidian Tooling.
