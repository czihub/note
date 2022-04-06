# 1. JavaScript基础
	1. JavaScript基础
	
	0.1学习目标
		1、能够掌握js基本语法
		2、能够掌握js的基本数据类型
		3、能够掌握js常用的对象
	0.2 学习指南
		1.Js基本语法（重要） 
		2.Js基本数据类型（重要） 
		3.Js常用对象（重点） 



## JavaScript：

1. 概念：	
    	一门客户端脚本语言
      	 运行在客户端浏览器中的。每一个浏览器都有JavaScript的解析引擎
      	 脚本语言：不需要编译，直接就可以被浏览器解析执行了

2. 功能：
   	 可以来增强用户和html页面的交互过程，可以来控制html元素，让页	面有一些动态的效果，增强用户的体验。

3. JavaScript发展史：
    	1. 1992年，Nombase公司，开发出第一门客户端脚本语言，专门用于**表单的校验**。命名为 ： C--	，后来更名为：ScriptEase
    	2. 1995年，Netscape(网景)公司，开发了一门客户端脚本语言：LiveScript。后来，请来SUN公司的专家，修改LiveScript，命名为**JavaScript**
    	3. 1996年，微软抄袭JavaScript开发出**JScript**语言
    	4. 1997年，ECMA(欧洲计算机制造商协会)，制定出客户端脚本语言的标准：**ECMAScript**，就是统一了所有客户端脚本语言的编码方式。

* JavaScript = **ECMAScript** + JavaScript自己特有的东西(**BOM+DOM**）

  > 学习JavaScript的构成，学习内容

### ECMAScript

* ECMAScript：客户端脚本语言的标准

  1. 基本语法

     1. 与html结合方式

        1. 内部JS：

           * 定义<script>，标签体内容就是js代码
        2. 外部JS：
           				* 定义<script>，通过**src属性**引入外部的js文件
        
        * 注意：
        
          1. ```<script>```可以定义在html页面的任何地方。但是定义的位置会影响执行顺序。
        
             > 因此，为了获取html中的元素，script放在body后面
        
          2. ```<script>```可以定义多个。
     
  2. 注释
  
     1. 单行注释：```//注释内容```
     2. 多行注释：```/*注释内容*/```
  
  3. 数据类型：
  
     1. 原始数据类型(基本数据类型)：
  
        1. number：数字。 整数/小数/NaN(not a number 一个不是数字的数字类型)
  
        2. string：字符串。 字符串  "abc" "a" 'abc'
  
           > JavaScript中没有字符
  
        3.  boolean: true和false
  
        4. null：一个对象为空的占位符
  
           > 在JavaScript中认为是一个对象
  
        5. undefined：未定义。如果一个变量没有给初始化值，则会被默认赋值为undefined
  
     2. 引用数据类型：对象
  
  4. 变量
  
     1. 变量：一小块存储数据的内存空间
  
     2. Java语言是强类型语言，而JavaScript是弱类型语言。
  
        * 强类型：在开辟变量存储空间时，定义了空间将来存储的数据的数据类型。只能存储固定类型的数据
  
        * **弱类型**：在开辟变量存储空间时，不定义空间将来的存储数据类型，可以存放任意类型的数据。
  
     3.  语法
        * var 变量名 = 初始化值;
        * typeof运算符：获取变量的类型
        * 注：**null运算后得到的是object**
  
  5. 运算符
  
     1.  一元运算符
  
        ++，-- ， +(正号) 
  
        1. ++，-- ， +(正号) 
  
           * ++ --: 自增(自减)
           				 * ++(--) 在前，先自增(自减)，再运算
           	 * ++(--) 在后，先运算，再自增(自减)
  
        2. ++，-- ， +(正号) 
  
           1. 用于其他类型转number类型
           2. 注意：
              - 其他类型转number:
                 * string转number：按照字面值转换。如果字面值不是数字，则转为NaN（不是数字的数字）
                 * boolean转number：true转为1，false转为0
  
           ```javascript
                   var num = 3;
                   var a = ++ num ;
           
                   document.write(num);// 4
                   document.write(a); // 3 
                   document.write("<hr>");
           
                   var b = +"123abc";
                   document.write(typeof (b)); //number
                   document.write(b + 1); //124
                   document.write("<hr>");
           
                   var flag = + true;
                   var f2 = + false;
                   document.write(typeof (flag) + "<br>");//number
                   document.write(flag + "<br>");// 1
                   document.write(f2 + "<br>");// 0
           ```
  
     2. 算数运算符
  
        +- * / % ...
  
     3. 赋值运算符
  
        = += -+....
  
     4. 比较运算符
  
        ```>```< >= <= == ===(全等于)
  
        1. 类型相同：直接比较
                                 * 字符串：按照字典顺序比较。按位逐一比较，直到得出大小为止。
        2. 类型不同：先进行类型转换，再比较
                                 * ===：全等于。在比较之前，先判断类型，如果类型不一样，则直接返回false
  
        ```javascript
                document.write((3 > 4) +"<br>");//false
        
                document.write(("abc" < "acd") +"<br>");//true
        
        
                document.write(("123" == 123) +"<br>");//true
        
                document.write(("123" === 123) +"<br>");//false
        ```
  
     5. 逻辑运算符
  
        && || !
  
  6. 流程控制语句
