# Software Topics

# Paralellism & Concurrency
### Thread x Process:

#### 1.1 Process context Switching
https://www.geeksforgeeks.org/difference-between-thread-context-switch-and-process-context-switch/
Process Context switching is a switching from one process to another. It envolves switching all the resources from one process to another.
It has a high cost when compared to thread context switching, cause envolves memory addresses, cache from processor, kernel resources and others.

#### 1.2 Thread Context Switching
http://www.qnx.com/developers/docs/qnxcar2/index.jsp?topic=%2Fcom.qnx.doc.sat.user_guide%2Ftopic%2Fevents_Context_switch_time.html
https://courses.cs.duke.edu/spring01/cps110/slides/threadsync/sld004.htm
https://stackoverflow.com/questions/7439608/steps-in-context-switching
https://stackoverflow.com/questions/72367424/core-execution-flow-in-the-point-of-thread-context-switch-and-cpu-mode-switch
- envolves switching from one thread to another, after one blocks or yield to other. The kernel should save settings before switching the execution. There is a time to save the current state and restore another.
The thread context-switch is small compared to process switch, but could slow donw the CPU execution.
Sometimes a bunch of thread could sttay switching back and forth with a minimum set of instrutcions been executed.

## Multi-threads
https://ee.usc.edu/~redekopp/cs350/slides/Ch4_Threading.pdf
- Threads are part of process
- multi thread try to fill the gap of CPU idling

## Threads x Fiber
https://stackoverflow.com/questions/796217/what-is-the-difference-between-a-thread-and-a-fiber
Threads usually are preemtive. Current execution flow could be interrupted at any time. So, CPU could run multiple threads at same time and leaving to developer thing like the data integrity task. 
Fiber are cooperative: execution path is interrupted when they yield themself allowing other Fiber to run. Data integrity is grannted, cause you won't have another Fiber trying to modify the same data at same time. However, you won't have the advantage of multiple CPU core.
Fiber could be viewed as Green Thread. In computer programming, a green thread (virtual thread) is a thread that is scheduled by a runtime library or virtual machine (VM) instead of natively by the underlying operating system (OS).
https://stackoverflow.com/questions/74639116/what-is-the-difference-between-green-threads-and-virtual-threads


## Thread x async task
Async describe how individual threads are used. When a async task is executed, the thread where it belongs is released to be able to execute other bunch of tasks. When the async task is done, it is able to resume using the thread.
Let's say that a reading file task runs for 10 seconds. It been synchronous, the thread will do nothing for 10 seconds till it the reading is done. If it is executed as a async task, the thread will have 10 seconds to do another task other than be idle wainting.


