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
可以用`+=`连接，也可以用conact方法连接。  
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
equals方法可以比较两个字符串的内容是否相同
###compareTo
compareTo方法返回的值是比较的两个字符串从左到右数第一个不同字符之间的距离（ascii码之差）。   
String类型不能用>、>=、<、<=这样的比较运算符来比较两个字符串的字典序。
##长度
length方法
##定位
###charAt
通过索引定位字符：提取字符串中的某个特定字符用charAt方法。
```java
String s = "Hello World";
char c = s.charAt(0);
```
charAt的参数是字符串元素的索引。该索引的值在0~s.length()-1之间。
###indexOf/lastIndexOf
通过字符获得索引：indexOf是从左到右查找，lastIndexOf是从右到左查找
String类提供了几个重载的方法：
```java
"Welcome to Java".indexOf('o')//返回4
"Welcome to Java".indexOf('o',5)//返回9
"Welcome to Java".indexOf("come")//返回3
"Welcome to Java".indexOf("Java",5)//返回11
"Welcome to Java".indexOf("java")//找不到返回-1

"Welcome to Java".lastIndexOf('o')//返回9
"Welcome to Java".lastIndexOf('o',5)//返回4
"Welcome to Java".lastIndexOf("come")//返回3
"Welcome to Java".lastIndexOf("Java")//返回11
"Welcome to Java".lastIndexOf("Java",5)//返回-1
```
凡是找不到都会返回-1。  
部分重载方法参数里面的整数，如：
* indexOf('o',5)指的是从索引为5的位置之后（包括5）开始查找。
* lastIndexOf('o',5)指的是从索引为5的位置之前（包括5）开始查找。

##获取子串
使用substring方法。该方法的格式为：
```java
String substring(beginIndex )
String substring(beginIndex , endIndex)
```
索引同样是从0开始算起。
注意，实际获取到的子串是原字符串的索引beginIndex到endIndex-1位置的子串。  
第一个substring的缺省endIndex就是字符串的长度，即截取到字符串结尾。  
>注意，求子串的方法substring并不会对原字符串做出改变，它只是把子串作为返回值返回。

##字符串的替换、分割
###普通做法
该部分功能的方法如：

|返回值|方法名|参数|描述
|-----|-----|----|----
|String|toLowerCase||返回一个将所有字母转换成小写后到新字符串
|String|toUpperCase||返回一个将所有字母转换成大写后到新字符串
|String|trim||返回一个去掉首尾两端空白字符的新字符串
|String|replace|char oldChar,char newChar|返回一个用新的字符替换所有匹配字符的新串
|String|replaceFirst|String oldStr,String newStr|返回一个用新子串替换第一个匹配子串的新串
|String|replaceAll|String oldStr,String newStr|返回一个用新子串替换所有匹配子串的新串
|String[]|split|String delimiter|返回一个用定界符delimiter分割出来的字符串数组
###模式匹配法
####matches
该方法的参数是一个支持正则表达式的字符串。
####其他
replace的三个方法和split方法都支持真正表达式匹配串（分别对应旧串和定界符串）。
##字符串的转换
###valueOf
静态方法valueOf可以将其他类型转换为字符串。它所支持的类型有：
* char
* char[]
* double
* float
* int
* long
* boolean

###逆向操作
将字符串转换成其他类型。比如Double.parseDouble(str),将str转换成double类型。
每种基本类型的包装类都有对应的静态`parse*`方法。
##格式化
静态format方法。格式为：
```java
String.format(format,item1,item2,...itemk);
//比如：
String s = String.format("5.2f",45.556);
```
类似与printf方法，只不过printf方法将结果打印到屏幕，而format方法是作为返回值返回。
