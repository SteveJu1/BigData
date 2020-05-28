synchronized是给对象加锁，synchronized（this），synchronized（T.class）= synchronized方法,类对象加锁可重入（锁对象可调用同一锁对象），遇到异常会释放锁volatile可见性，不是原子性AtomXXX类本身方法都是原子性的，但不能保证多个方法连续调用是原子性的（CAS）不要锁字符串，#########Reentranlock 替代synchonized, 手动释放锁lock ,unlock，trylock（5） ，Lockinterruptibly，ReentrantLock lock=new ReentrantLock(true);公平锁wait();  等待，释放线程notifyall(); 不会释放线程
countdownlatch  await 等线程结束一个，减一，等于0
CyclicBarrier (20,new Runnable) 人满发车Phaser 阶段，重新onadvance（阶段，人数）， arriveAndAwaitAdvance arriveAndDeregister不进入下一个阶段ReadWriteLock读写锁，读的时候可以让别人读，不让写一种实现ReentrantReadWriteLock readLock共享锁，writeLock排他锁
semaphore（2）2个可同时执行，限流 信号灯，亮着才能执行 s.acquir()获取变成0，s.release()别人可以得到。和线程池的区别，这是做同步
forkjoin 分批发短信
exchanger :运行到exchange时阻塞，两线程之间交换数据


 ThreadLocal线程局部变量
**并发容器**concurrentLikedQueue: 替代vector（判断，操作是分离的），poll()方法（先取出在判断）offer有返回值，判断加成功,peekcountdownlatch countdownlatch latch=new Countdownlatch(1）latch,countDown();latch.await();替代wait和notify，不涉及锁定，count的值为零时当前线程继续运行concurrenthashmap();  segment分段锁16段，锁一段数据。1.8版本  node+CAS实现ConcurrentSkipListMap 调表 排好序。
TreeMap排好序

copy on wirter  copyonwriterList 写时复制，写的效率低，读的时候不加锁效率高，场景监听器

集合加锁的方法 collection.synchonizedList(list) ,把没加锁的对象传进去
hashtable 有锁

**Queue**
   ConrrentQueue 只有ConcurrentLinkedQueue //ArrayListQueue不好实现统一
   BlockingQueue（）；       LinkedBQ；       ArrayBQ；       transferQueue();  直接传给消费者，不传给服务队列，找不到消费者则阻塞。场景:游戏服务器       SynchonnizedQueue 容量为零，只能用put（），特殊的transferQueue
        add（）抛异常，   put（）满了会阻塞，offer（）返回boolean
   DelayQueue（） 执行定时任务 在compareto方法做定义顺序
**线程池**
Executor 接口，execute方法ExecutorService接口， submit方法
callable接口，call方法，有返回值
Executors工具类，
ThreadPool  service.shutdown();newFixedThreadpool（）Futuretask 拿到未来的返回值，f1=service.submit, f1.get（）阻塞
newCacheThreadPool（）.AliveTime默认60newSingleThreadExcutor
 newScheduledThread ,任务表 ，workSteling  的线程叫守护线程，后台线程ForkjoinPool，
大部分是通过ThreadpoolExecutor实现的
varhandle 原子性操作

idea setting-plugins-jclasslib Bytecode viewerview jclass