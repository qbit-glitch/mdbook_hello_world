# Deadlocks

- A deadlock is a situation in concurrent computing when two or more processes or goroutines are unable to proceed because each is waiting for the other to release resources. This results in a state where none of the processes or goroutines can make progress.

- Deadlocks can cause programs to hand or freeze, leading to unresponsive systems and poor user experience. Understanding and preventing deadlocks is crucial for reliable and efficient concurrent systems.

- Causes of Deadlocks: Four Conditions for Deadlocks :

    - Mutual Exclusion: at least one resource is held in a non-shareable mode. Only one process or goroutine can use the resource at a time.

    - Hold and Wait: process or goroutine holding at least one resource is waiting to acquire additional resources held by other processes or goroutines.

    - No Preemption: resources cannot be forcibly taken away from processes or goroutines. They must be released voluntarily.

    - Circular Wait: a set or processes or goroutines are waiting for each other in a circular chain, with each holding a resource that the next one in the chain is waiting for.

- Detecting Deadlocks:
    - Deadlock Detection Strategies
        - Static Analysis
        - Dynamic Analysis
    - Deadlock Detection Tools

- A blank select statement waits indefinitely for the goroutines to finish.
    ```go
    select {}
    ```

- `mutex.Lock()` is blocking in nature.

- Deadlock happens when two locked mutexes try to access each other's values/ each other's mutex.

- Consitent lock order helps us avoid deadlocks. If we do not follow a consistent lock order then we might have a deadlock. So by acquiring locks in a consistent order accross all goroutines, we can avoid the deadlock scenario and ensure that the program runs smoothly.

- Best Practices for avoiding deadlocks:
    - Lock Ordering
    - Timeouts and Deadlock Detection
    - Resource Allocation Strategies

- Best Practices and Patterns :
    - Avoid nested locks
    - Use lock-free data structures
    - Keep critical sections short

- Practical Consierations:
    - Complex Systems
    - Testing for Deadlocks
    - Code Reviews

