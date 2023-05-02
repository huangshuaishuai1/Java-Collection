# 常见的集合
### Collection接口下
#### LinkedList vs ArrayList
* 二者都是线程不安全的。
* 在底层的实现中，LinkedList使用的是双向链表，ArrayList使用的是数组。
* 由于底层数据结构的不同，在操作它们的时候，面临的复杂度是不同的。
* ArrayList实现了RandomAccess接口，支持随机访问。
* 二者都会有一些空间的浪费，具体的：
  * LinkedList需要保存前驱和后继。
  * ArrayList数组在没存满的时候也存在内存的浪费。
* 一般来说，无脑使用ArrayList，它的性能会更好一些。
#### ArrayList的扩容原理
* 在使用空参构造器初始化ArrayList的时候，它的初始容量为0。
* 当向其中插入一条数据的时候，容量变为10。
* 之后每当要插入而容量不够的时候，就触发扩容：
  * 每次都扩容到原来长度的1.5倍（创建一个新的数组）。
  * 将老数组中的数据拷贝到新数组中。
  * 将要插入的数据放在新数组的尾部。
  * 完成扩容。
#### Vector vs ArrayList
* Vector是线程安全的，在方法上都加了同步锁
* 二者的扩容机制不同，Vector扩容到原来长度的2倍，而ArrayList是原来的1.5倍->ArrayList比Vector更省内存。
#### Queue vs Deque
* 二者都是队列
* Queue是单端的，只支持一端进，另一端出，Deque是双端的，两端都可以进行出队和入队。
#### HashSet vs TreeSet
* TreeSet底层基于TreeMap，除了具备存放不重复数据的功能，还可以排序。
### Map结构下
#### HashMap底层数据结构
* jdk1.7时底层的数据结构是数组+链表
* jdk1.8时底层的数据机构是数组+链表+红黑树
#### HashMap解决hash冲突的办法
* jdk1.7时，冲突的时候进行拉链
* jdk1.8的时候，为了防止链表过长，当数组长度>=64且链表长度>=8的时候，就会将链表转换为红黑树。




