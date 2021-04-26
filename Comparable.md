Comparable接口
============
用于实现某一类的两个对象之间的大小比较。  
只要实现了这个接口，就能用>、<、=符号来比较大小
##接口原型
```java
package java.lang;

public interface Comparable{
    public int compareTo(Object o);
}
```
compareTo的返回值对应不同的大小关系

|返回值|对象的大小关系
|:----:|:------:
|负整数|<
|0|=
|正整数|>
>String和Date类都实现了这一接口

##用法
###方法内
```java
public class Max{
    public static Comparable max(Comparable o1,Comparable o2){
        if(o1.compareTo(o2)>0)
            return o1;
        else 
            return o2;
    }
}
```
```java
public class Max{
    public static Comparable max(Object o1,Object o2){
        if(((Comparable)o1).compareTo(o2)>0)
            return o1;
        else 
            return o2;
    }
}
```
