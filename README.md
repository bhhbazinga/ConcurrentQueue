# ConcurrentQueue
 ConcurrentQueue implemented in c++, the algorithms involved are also used in Java ConcurrentLinkedQueue (Java Platform SE 8 ).
## Feature
  * Thread-safe and Lock-free. 
  * Singly-linked list with a sentinel node.
  * Support Multi-producer & Multi-consumer.
  * Dynamic size.  
  * Dynamically allocate and deallocate nodes. 
  * Use [Hazard Pointer with RAII style](https://github.com/bhhbazinga/HazardPointer) to avoid ABA problems and manage memory.
## Benchmark
I've compared it with another ConcurrentLinkedQueue implematation [LockFreeQueue](https://github.com/bhhbazinga/LockFreeQueue), and their efficiency are almost the same.See [test](test.cc). 
## Build
```
make && ./test
```
## API
```C++
void Enqueue(const T& data);
void Enqueue(T&& data);
void Emplace(Arg&&.. args);
bool Dequeue(T& data);
size_t size() const;
```
## Reference
[1]Hazard Pointers: Safe Memory Reclamation for Lock-Free Objects. Maged M. Michael\
[2]Simple, Fast, and Practical Non-Blocking and Blocking Concurrent Queue Algorithms. Maged M. Michael Michael L. Scott
