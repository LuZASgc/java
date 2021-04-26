Cloneable接口
=============
##接口原型
```java
package java.lang;

public interface Cloneable{
}
```
是空接口。**空接口又称为标记接口**。标记接口即不包括常量、也不包括方法。  
Cloneable用来标记类为可克隆的，而且它的对象可以使用在**Object类中定义的clone方法克隆**。
