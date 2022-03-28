#### 1、Collection和Collections的区别

Collection是一个集合接口（集合类的顶级接口），它提供了对于集合对象基本操作的通用接口方法，其意义是为各种集合提供最大化的统一操作方式。List、Set和Queue都继承于他。

Collections是一个集合工具类，里面有许多静态方法对集合进行查找、排序、线性安全等操作

#### 2、List、Set和Map的区别

![tt](https://pic4.zhimg.com/v2-065a248aa026cb73978ad6aec1b4237f_r.jpg)

#### 3、HashTable和HashMap的区别

hashtable是同步的，hashmap是非同步的，处理效率上hashmap更高；

hashtable的contains方法对应于hashmap的containsValue方法；

hashmap允许空键值对，hashtable不允许

