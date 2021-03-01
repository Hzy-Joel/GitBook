### 1、阻断崩溃链接、忽略该崩溃

https://www.infoq.cn/article/NxlcJikbFaoTeACHxMQk

由FinalizerWatchdogDaemon触发的TimeoutException超时

```
Thread.setDefaultUncaughtExceptionHandler(new Thread.UncaughtExceptionHandler() {
    @Override
    public void uncaughtException(Thread t, Throwable e) {
        if (t.getName().equals("FinalizerWatchdogDaemon") && e instanceof TimeoutException) {
        			//忽略捕捉
             //ignore it
        } else {
            defaultUncaughtExceptionHandler.uncaughtException(t, e);
        }
    }
})；
```



### 2、手动停止FinalizerWatchdogDaemon线程：

 https://github.com/AndroidAdvanceWithGeektime/Chapter02

