小Tips
======
##数组
在声明一个数组的时候，中括号内不写数字。  
数组变量至少要new两次：
* 第一次，new一下，确定数组大小
* 然后，数组中每一个元素要new一下，实例化一个对象

##关于继承
子类实例化的时候一定需要调用父类的构造函数。如果在子类构造函数中，没有用super指定的话，会默认调用父类的无参构造函数，但是如果此时父类没有无参的构造函数，子类的构造函数会报错。  
super如果存在，那么一定要出现在构造方法的第一条语句。
##自定义异常
Java中自定义的异常类（继承Exception）都是不可被忽略的异常。而系统实现的异常当中存在可以忽略的异常。
##方法传递的参数
方法传递的参数并非C++中的引用。
```java
public class Test {
	public void change(String a){
		a="123";
	}
	public static void main(String[]args){
		String a="abc";
		Test t = new Test();
		t.change(a);
		System.out.println(a);
	}
}
```
结果是： abc
##Java参数传递
一般情况下，当参数是一个对象的时候，是传递的引用，但是String是例外，String对象传递的是值，而非引用。
