# 线程

线程是cpu调度，或者说是程序执行的最小单位。


线程之间的通信比较方便。统一进程下的线程共享数据（比如全局变量，静态变量），通过这些数据来通信不仅快捷而且方便，当然如何处理好这些访问 的同步与互斥正是编写多线程程序的难点【"互斥锁"（Mutual exclusion，缩写 Mutex），防止多个线程同时读写某一块内存区域，"信号量"（Semaphore），用来保证多个线程不会互相冲突】。而进程之间的通信只能通过 进程通信(共享内存模式、消息传递模式、共享文件模式) 的方式进行。


- 多线程同步和互斥有几种实现方法
线程间的同步方法大体可分为两类：用户模式和内核模式。顾名思义，内核模式就是指利用系统内核对象的单一性来进行同步，使用时需要切换内核态与用户态，而用户模式就是不需要切换到内核态，只在用户态完成操作。
用户模式下的方法有：原子操作（例如一个单一的全局变量），临界区。内核模式下的方法有：事件，信号量，互斥量。