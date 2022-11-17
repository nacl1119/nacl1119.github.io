# [Top Embedded Software Engineer Knowledge](https://www.interviewkickstart.com/interview-questions/embedded-software-engineer-interview-questions)

## Technical Embedded Software Engineer QnA
1. Q1. What is an embedded system?  
   Embedded system is defined by the purpose of it. Plus, embedded system is composed of specific hardware and software. System engineer designs embedded system based on the user's requirments. Select proper hardware component such assensor, actuator, RF module, etc. Embedded software engineer develops software to satisfy the requirments under the hardware restriction.

2. Q2. What is a spinlock?  
   Spinlock is one of the resource synchronization methods. It's very simple mechanism. When several threads try to access same resource, a thread that achieves the lock can access the resource first and other thread should wait in the loop such as "for" or "loop" There are other synchronization method like Mutex(wait/signal) and Semaphore. The difference between spinlock and others is User level or Kernel level. In spinlock, it doesn't need context switching

3. Q3. What do we mean by virtual memory?  
   Operating system provides virtual memory for each process. So, each process can think that it has full size of memory. For example, if there are 10 user level process with 16 gigabytes memory, every process can has 16 gigabytes size of memory. CPU manages the mapping between virtual memory and phisical memory using Memory Management Unit(MMU) for each process's real memory usage.  
   [what is paging and segmentation](https://bellog.tistory.com/159)
   
4. Q4. What is your approach for debugging any issue in an embedded system?  
   a. Understand the system  
   b. Reproduce the issue  
   c. Logging or instrumentation  
   d. Isolate the bug  
   e. Apply quick fix  

5. Q5. Describe the role of the watchdog timer.  
   Watchdog timer is hardware support timer. We can use watchdog timer to monitor system status. So, when the system occurs a critical malfunction, watchdog will be expired and a watchdog service routine will reset etire system to recover the system.  
   [watchdog and OS timer](https://www.edaboard.com/threads/comparison-of-watchdog-timer-and-hardware-timer.339482/)  
   [what is watchdog](https://gdnn.tistory.com/116)
6. Q6. What is a livelock, and how is it different from a deadlock?
7. Q7. What are the causes of the interrupt legacy?
8. Q8. What are static memory allocation and dynamic memory allocation?




https://www.interviewkickstart.com/interview-questions  
https://in.indeed.com/career-advice/interviewing/embedded-engineer-interview-questions


