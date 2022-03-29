#### 1、Collection和Collections的区别

Collection是一个集合接口（集合类的顶级接口），它提供了对于集合对象基本操作的通用接口方法，其意义是为各种集合提供最大化的统一操作方式。List、Set和Queue都继承于他。

Collections是一个集合工具类，里面有许多静态方法对集合进行查找、排序、线性安全等操作

#### 2、List、Set和Map的区别

![tt](https://pic4.zhimg.com/v2-065a248aa026cb73978ad6aec1b4237f_r.jpg)

#### 3、HashTable和HashMap的区别

hashtable是同步的，hashmap是非同步的，处理效率上hashmap更高；

hashtable的contains方法对应于hashmap的containsValue方法；

hashmap允许空键值对，hashtable不允许

#### 4、如何决定使用HashMap还是TreeMap

对于插入、删除和定位操作，hashmap是一个不错的选择

假如要对有序的key集合进行遍历，将map换为TreeMap进行有序key的遍历

#### 5、Hashmap原理

拉链法，计算hash值，如果这个桶位置没有，直接加入，有的话就拉链

JDK1.8，拉链中个数超过8个转为红黑树提高查询效率

#### 6、HashSet原理

底层原理就是hashmap

hashmap的key来存储，无序

value设置为PRESENT

#### 7、ArrayList和LinkedList

一个底层实现是数组，一个是双向链表

可随机访问和不可随机访问；0（1）和0（n）

#### 8、数组和List转换

asList方法和toArray方法

#### 9、ArrayList和Vector区别

Vector线程同步，安全

ArrayList更快，不同步

ArrayList更加通用，因为我们可以使用Collections工具类轻易地获取同步列表和只读列表

#### 10、Array和ArrayList

Array可以是基本类型也可以是对象类型，ArrayList必须是对象类型

Array是指定大小的，ArrayList空间是动态增长的

ArrayList有比Array更多的方法

#### 11、 在 Queue 中 poll()和 remove()有什么区别

poll如果没有会返回一个null

remove如果没有会抛出异常

#### 12、哪些集合类是线程安全的

Vector

HashTable

stack

enumeration

#### 13、迭代器 Iterator 是什么

Iterator是一种设计模式，是一个对象用来实现对集合类的遍历，进而降低耦合，轻量级，其缺点是每增加一个集合类就要多增加对应的迭代器方法

#### 14、迭代器 Iterator 怎么使用以及特点

先根据集合创建迭代器对象，while循环，若hasNext，取next，操作，然后继续循环直到最后一个，可以使用remove把就近返回的元素进行移除；

特点如下：

不允许修改集合类中的元素，负责会抛出异常

可以通过remove方法移除前一次循环的得到的next

迭代器必须依赖于集合类对象而存在，本身没有装载数据对象的能力

next方法通过游标指向的形式返回下一个元素

#### 15、Iterator和ListIterator

所有集合类、List以及它的子类

正向、正向逆向都可遍历

不可修改、可修改集合元素

没有add方法、有add方法

不可定位当前索引的位置、可以定位当前索引的位置

