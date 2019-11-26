# Day：线程池的执行机制
1、工作线程数小于核心线程数时，直接新建核心线程执行任务；

2、大于核心线程数时，将任务添加进等待队列；

3、队列满时，创建非核心线程执行任务；

4、工作线程数大于最大线程数时创建失败，拒绝任务。

5、新建线程执行任务时，会首先执行firstTask，然后从工作队列中循环取出任务执行。

6、ThreadPoolExecutor构造方法参数有：

 * corePoolSize为核心线程池大小
 * maximumPoolSize为线程池允许的最大线程数
 * keepAliveTime为线程池的工作线程空闲后保持存活的时间
 * unit为线程保持存活的时间单位
 * workQueue为工作队列，线程池的工作线程都是从这个工作队列源源不断的取出任务执行
 * threadFactory为创建新的工作线程时使用的工厂类
 * handler为拒绝任务时的饱和策略

7、通常通过 Executors 类的如下几个静态方法来创建不同类型的线程池：

* newCachedThreadPool：可缓存线程池，无限大
* newFixedThreadPool：定长线程池
* newScheduledThreadPool：定长线程池，支持定时及周期性任务执行
* newSingleThreadExecutor：单个线程池