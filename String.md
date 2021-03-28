String
=======
##构造字符串
常见的方法
```java
//用双引号内的字符串序列构造
String message = new String("Welcome to Java");
//字符串直接量
String message = "Welcome to Java";
//用字符数组构造字符串
char[] charArray = {'G','o','o','d',' ','d','a','y',};
String message = new String(charArray);
```
具有相同字符串直接量（双引号包裹的字符串序列）使用的是同一个实例。如：
```java
String s1 = "Welcome to Java";
String s2 = new String("Welcome to Java");
String s3 = "Welcome to Java";
System.out.println("s1 == s2 is "+(s1 == s2));
System.out.println("s1 == s3 is "+(s1 == s3));
```
打印的是：
```
s1 == s2 is false
s1 == s3 is true
```
##连接
可以用`+=`连接，也可以用contact方法连接。  
注意：
```java
i = 1;
j = 2;
//注意一下输出语句
System.out.println("i + j is "+i+j);//输出结果为i + j is 12
System.out.println("i + j is "+(i+j));//输出结果为i + j is 3
```
##比较
###==
==只能比较两个字符串是不是指向同一个对象，它不会告诉你他们的内容是否相同。
###equals

