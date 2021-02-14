Map
====
Map是一个接口，map是映射的意思，也是键值对，键不允许重复。
HashMap
=======
HashMap是Map接口的一个实现。  
注意实例化的时候：
```java
/*如果Map没有指定操作类型，之后的实例调用方法时会有警告产生，但不报错。*/
Map<int,String> m = new HashMap<int,String>();

```
##常用方法
###keySet
返回一个Set对象，为该HashMap对象多有键的集合。
