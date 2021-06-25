###  1、 Java的HashMap是如何工作的？

HashMap是一个针对数据结构的键值，每个键都有有对应的值，关键是识别这样的值。

HashMap基于hashing原理，我们通过put()和get()方法存储和获取对象。当我们将键值对传递给put()方法时，它调用键对象的hashCode()方法来计算hashcode,然后找到bucket位置来存储存值对象。当获取对象时，通过对象的equals()方法找到正确的键值对，然后返回值对象。

HashMap使用linkedList来解决碰撞问题，当发现碰撞了，对象将会存储在linkedList的下个节点中，hashmap在每个linkedList节点存储键值对对象。

### 2、什么是快速失败的故障安全迭代？

快速失败的java迭代器可能会引发发ConcurrentModifcationException在底层集合迭代过程中被修改，故障安全作为发生在实例中的一个副本迭代是不会抛出任何异常的。快速失败的故障安全范例定义了当地遭遇故障时系统是如何反应的。例如，用于失败的快速迭代器ArrayList和用于故障安全的迭代器concurrenthashMap。

### 3、Java BlockingQueue是什么？

Java BlockingQueue是一个并发集合util包的一部分。BlockingQueue队列是一种支持操作，他等待元素变得用来时来检索，同样等待空间可用时来存储元素。

### 4、 什么时候使用concurrentHashMap?

在问题2中我们看到ConcurrentHashMap被作为故障安全迭代器的一个实例，它允许完整的并发检索和更新。当有大量的并发更新时，ConcurrentHashMap此时可以被使用。这非常类似于
Hashtable，但ConcurrentHashMap不锁定整个表来提供并发，所以从这点上ConcurrentHashMap的性能似乎更好一些。所以当有大量更新时ConcurrentHashMap应该被使用。

### 5、哪一个List实现了最快插入？

LinkedList和ArrayList是另个不同变量列表的实现。ArrayList的优势在于动态的增长数组，非常适合初始时总长度未知的情况下使用。LinkedList的优势在于在中间位置插入和删除操作，速度
是最快的。