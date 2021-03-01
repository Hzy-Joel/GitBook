1、查看主线程的堆栈，判断是否是锁等待导致。

2、查看ANR 日志中 iowait、CPU、GC、system server 等信息，确定是否是 I/O 问题、 CPU 竞争问题，还是由于大量 GC 导致卡死