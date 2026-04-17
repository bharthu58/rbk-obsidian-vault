For most C++ use cases, the widely accepted "best" implementation is **MoodyCamel's ConcurrentQueue**.

However, "best" depends heavily on your specific threading model (SPSC vs. MPMC) and constraints (latency vs. throughput).

Here is the breakdown of the top open-source implementations by use case.

### **1\. The Gold Standard (MPMC & General Use)**

**moodycamel::ConcurrentQueue**

This is widely considered the state-of-the-art for a general-purpose, lock-free queue in C++.

* **Best for:** Multi-Producer, Multi-Consumer (MPMC) scenarios.  
* **Key Features:**  
  * **Header-only:** Easy to drop into any project.  
  * **Fast:** Consistently outperforms boost::lockfree in benchmarks.  
  * **Allocation-friendly:** It handles memory dynamically but efficiently (blocks) to avoid the "fixed size" pitfall of traditional ring buffers, while still being lock-free.  
* **License:** Simplified BSD or MIT (very permissive).

### **2\. Best for Single-Producer Single-Consumer (SPSC)**

**moodycamel::ReaderWriterQueue**

If you *know* you only have one thread writing and one thread reading, do not use a generic MPMC queue. The synchronization overhead is unnecessary.

* **Why it wins:** It is a raw ring buffer designed specifically for SPSC. It is significantly faster than MPMC queues because it avoids atomic CAS (Compare-And-Swap) loops, relying instead on lighter memory fences.  
* **latency:** Extremely low.

### **3\. Best for Low-Latency / High-Frequency Trading (Fixed Size)**

**rigtorp::MPMCQueue**

If you cannot afford *any* dynamic allocation at runtime and need strict bounded latency (e.g., HFT, audio processing), Rigtorp's implementation is often preferred over MoodyCamel.

* **Best for:** Scenarios where you must pre-allocate the entire buffer upfront.  
* **Trade-off:** It is a strict ring buffer. If the queue fills up, you must either block or drop data (it cannot grow).  
* **Performance:** often beats MoodyCamel in throughput for fixed-size scenarios because of its simplicity and cache-friendliness.

### **4\. The "Standard" Choice (Boost)**

**Boost.Lockfree**

* **Best for:** Projects already heavily invested in the Boost ecosystem.  
* **Pros:** Battle-tested, stable API, part of a standard distribution.  
* **Cons:** Generally slower than the specialized libraries above. The boost::lockfree::queue has some limitations regarding payload types (must be trivially copyable for some operations).

### **5\. The "Big Tech" Component**

**Folly::ProducerConsumerQueue** (Facebook/Meta)

* **Best for:** SPSC scenarios if you are already using the Folly library.  
* **Pros:** Extremely optimized for cache locality.  
* **Cons:** Folly is a massive dependency. You shouldn't import Folly *just* for this queue; use MoodyCamel or Rigtorp instead if you want a lightweight solution.

### **Summary Table**

| Library | Type | Allocation | Best Use Case | Dependencies |
| :---- | :---- | :---- | :---- | :---- |
| **MoodyCamel Concurrent** | MPMC | Dynamic (Block) | General purpose, high throughput | None (Header-only) |
| **MoodyCamel RWQueue** | SPSC | Dynamic (Block) | 1:1 Threading, high speed | None (Header-only) |
| **Rigtorp** | MPMC/SPSC | Fixed (Static) | Ultra-low latency, Audio, HFT | None (Header-only C++11) |
| **Boost.Lockfree** | MPMC/SPSC | Fixed/Dynamic | Integration with Boost projects | Boost |

**Recommendation:** Start with **MoodyCamel** (Concurrent or ReaderWriter). It offers the best balance of "it just works" and extreme performance without requiring you to manage complex memory constraints manually.