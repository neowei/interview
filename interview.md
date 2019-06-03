算法题:
快速排序 归并排序

数据结构题:
链表 队列 二叉树 红黑树 B树

java基础题:
string stringbuffer stringbuilder intern原理及区别
set list map 有哪些实现集合 常用的那些 原理是啥
arrayset treeset
arralist linkedlist
hashmap treemap
concurrenthashmap 线程安全实现原理 volatile cas synchronized 原理slot局部加锁
类加载器 双亲委派

java 设计模式:
单例模式 工厂模式 适配器模式 代理模式 观察者模式

java线程题:
线程池 需要设置哪些参数
corePoolSize maximumPoolSize keepAliveTime timeUnit blockingQueue threadFactory rejectedHandler
blockingQueue:
ArrayBlockingQueue // 定长的队列
LinkedBlockingQueue // 单链表队列 有oom风险
LinkedBlockingDeque // 双向链表的队列
DelayQueue // 延时队列
PriorityBlockingQueue // 排序队列 优先级
LinkedTransferQueue // SynchronousQueue升级 有等待进队列 没有则直接运行 避免锁操作
SynchronousQueue // 等待队列
ConcurrentLinkedQueue LinkedBlockingQueue 区别在于ConcurrentLinkedQueue的API原来.size()是要遍历一遍集合的 在线程池经常要判断size 所以在线程池不用


拒绝模式:
AbortPolicy // 抛异常
DiscardPolicy // 啥都不做
DiscardOldestPolicy // 移除队列头元素 在塞进去
CallerRunsPolicy // 直接当前线程做
自定义

线程工厂那些参数需要设置 (threadgroup,threadname,isDeman,priority)


有哪些线程池 
ForkJoinPool(fork join模式的线程池) ScheduledExecutorService(定时任务的线程池) ExecutorCompletionService(有返回值的线程池)

java线程安全:
volatile 关键词 强制工作内存变量到主内存并不可进入寄存器 但只保证可见性 不能保证原子性
synchronized 关键词 保证只有一个线程可运行 非公平锁    可配合wait notify用
原理: 简单说就是 自旋获取锁 获取不到就进竞争队列 等待下次再自旋锁 如果竞争队列过多会进入到等待队列 等获取锁释放再从等待队列中拉入竞争队列
CompareAndSwap 调用native内核cpu的方法 基于cas的有 Atomic AQS Semaphore
threadLocal 线程自带变量 内部弱引用 线程隔离的形式的线程安全访问
ReentrantLock ReentrantReadWriteLock 基于AQS CAS  支持线程重进入 可设置非公平锁 公平锁
StampedLock 不支持线程重入 乐观锁策略
CopyAndWriteArrayList/Set 写时加锁拷贝 避免读取锁
 
spring相关问题
spring 底层原理 反射
事务注解 原理及使用方式
springboot的好处

java nio/aio:
处理大文件 用FileChannel AsynchronousFileChannel RandomAccessFile(MappedByteBuffer)
nio非阻塞(多路复用原理) aio内核原理 reactor模式 proactor模式 

jvm原理:
程序计数器 本地方法区 方法区 堆 栈 metaspace(类文件 类加载器)
分代垃圾回收
Minor GC (年轻代gc) Major GC(老年代gc) Full GC(清理整个堆空间)之间的区别
对象何时回收 强引用 软引用 弱引用 虚引用

缓存:
redis 原子性命令有哪些

数据库
mysql innodb 表空间原理 索引原理
mysql的事务四大特性
mysql的事务隔离级别 原理
如何实现乐观锁 MVCC原理(XtraDB)
mysql 有哪些悲观锁 行锁的命令有几种 何时会表锁? 
数据量过大 分区分表分库 原理 原因
sharding jdbc 分库分表原理

消息中间件:
rabbitmq rocketmq kafka区别
集群模式 实现高可用
发送原理 补偿机制原理 事务原理

搜索引擎:
lucene实现原理 倒排索引
elasticsearch 高可用方案

日志:
elk架构

服务器:
http/s原理 tomcat原理 nginx反向代理
docker k8s 相关题
springcloud相关 注册中心 熔断容错 网关


其他题:
进程线程协程区别
分布式事务实现
zookeeper原理及实现
全链路实现方案 skywalking

场景业务题:
新浪微博 微信好友圈 实现原理 推 拉 区别
电商 业务逻辑及抢购实现原理
