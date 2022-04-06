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

  1. **基本语法**

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
     
           1. number：数字。 整数/小数/NaN(not a number 	一个不是数字的数字类型)
     
           2. string：字符串。 字符串  "abc" "a" 'abc'
     
              > JavaScript中没有字符
     
           3.  boolean: true和false
     
           4. null：一个对象为空的占位符
     
              > 在JavaScript中认为是一个对象
     
              1. undefined：未定义。如果一个变量没有给初始化值，则会被默认赋值为undefined
     
        2. 引用数据类型：对象
     
     4. 变量
     
        1. 变量：一小块存储数据的内存空间
     
        2. Java语言是强类型语言，而JavaScript是弱类型语言。
           * ​	强类型：在开辟变量存储空间时，定义了空间将来	存储的数据的数据类型。只能存储固定类型的数据	
             * **弱类型**：在开辟变量存储空间时，不定义空	间将来的存储数据类型，可以存放任意类型的	数据。
     
        3.  语法
     
           - var 变量名 = 初始化值;
     
           * typeof运算符：获取变量的类型
           * 注：**null运算后得到的是object**
     
     5. 运算符
     
        1.  一元运算符
     
           ++，-- ， +(正号) 
     
           1. ++，-- ， +(正号) 
                 1. ++ --: 自增(自减)
                       1. ++(--) 在前，先自增(自减)，再运算
                       2. ++(--) 在后，先运算，再自增(自减)
           2. ++，-- ， +(正号) 
              1. 用于其他类型转number类型
              2. 注意：
                  1. 其他类型转number:
                        1. string转number：按照字面值转换。	如果字面值不是数字，则转为NaN（不是数字的数字）
                        2. boolean转number：true转为1，false转为0
     
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
     
     6. 算数运算符
     
        +- * / % ...
     
     7. 赋值运算符
     
        = += -+....
     
     8. 比较运算符
     
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
     
     9. 逻辑运算符
     
        && || !
     
        1. 逻辑运算符：
     
           1. && ： 与（短路）
     
           2. || ： 或（短路）
     
           3. ！： 非
     
              - 其他类型转boolean
     
                1.  number：0或者NaN,其他为真
     
                2. string：除了空字符串（""）,其他都是true
     
                3. null&undefined：都是false
     
                4. 对象：所有对象都是true
     
                   > 因此在JavaScript中
                   >
                   > 判断时直接使用变量名可防止空指针
     
           ```javascript
           var flag = true;
           doucument.write(flag + "<br>")//true
           doucument.write(!flag+ "<br>")//fasle
           
           var num3 = NaN;
           doucument.write(num3 + "<br>")//false
           doucument.write(!num3+ "<br>")//true
           doucument.write(!!num3 + "<br>")//false
           
           var str1 = 'a';
           var str2 = '';
           doucument.write(!!str1 + "<br>")//true
           doucument.write(!!str2 + "<br>")//false
           
           var obj = null;
           var obj2;
           var obj3 = new Date();
           doucument.write(!!obj + "<br>");//false
           doucument.write(!!obj2 + "<br>")//false
           doucument.write(!!obj3 + "<br>")//true
           
           
           // 因此在JavaScript中直接使用变量名可防止空指针
           if(obj){//空类型都是false
               doucument.write("123");
           }
           ```
     
     10. 三元运算符：
     
        ？ ： 表达式
     
        ```javascript
        var a = 3;
        var b = 4;
        var c = a>b?1:0;//输出的值0
        ```
     
        * 语法：
          * 表达式？ 值1：值2；
          * 判断表达式的值，如果是true则取值1，如果是false则取值2；
     
     11. 流程控制语句
     
         1. if..else..
     
         2. switch
     
            1. 在java中，switch语句可以接受的数据类型：byte short int long；枚举（1.5版本之后），string（1.7）
            2. 在JavaScript中 
     
            ```JavaScript
            switch(变量名){
            	case 值:
            	break;
            }
            //在JavaScript中switch可以接受任意属性的值
            ```
     
         3. while
     
         ```javascript
         var sum=0;
         var num=1;
         while (num<=100){
             sum+=num;
             num++;
         }
         doucument.write(sum);
         ```
     
         
     
         1. do...while
         2. for
     
     12. JS特殊语法
     
         1. 语句以；结尾，如果一行只有一条语句则；可以省略
         2. 变量的定义使用var关键字，也可以不使用
            1. 用：定义的变量是局部变量
            2. 不用：定义的变量是全局变量（不建议使用）
     
         ```JavaScript
         var b;
         function fun(){
         	b=4;//如果在方法中间定义，则不能正常输出
         }
         fun();
         doucument.write(4);
         
         
         function fun(){
         	var b=4;//如果在方法中间定义，则不能正常输出
         }
         fun();
         doucument.write(4);//不输出
         
         function fun(){
         	b=4;//如果在方法中间定义，则不能正常输出
         }
         fun();
         doucument.write(4);//正常输出
         ```
     
     13. 九九乘法表
     
     ```javascript
         <style>
             td{
                 border: 1px solid
             }
         </style>
         <script>
             document.write("<table>")
             for(var i = 1; i <10;i++){
                 document.write("<tr>")
                 for(var j = 1; j <=i;j++){
                     document.write("<td>")
                     document.write(i+"*"+j+"="+i*j+"&nbsp&nbsp&nbsp")
                     document.write("</td>")
                 }
                 document.write("</tr>")
             }
             document.write("</table>")
         </script>
     ```

2. 基本对象

   - [function对象](https://www.w3school.com.cn/js/pro_js_functions.asp)

     1. 创建

        1.  ```javascript
            var fun = new Function(形式参数列表，方法体);
            var fun = new Function("a","b","c","alert(a);")//忘掉吧
            ```
   
        2. ```javascript
           function 方法名称（形式参数列表）{
               方法体
           }
           function fun2('a','b',"c"){
               alert(a)
           }
           ```

        3. ```javascript
           var 方法名称= function(形式参数列表){
           	方法体
           }
           var fun3 = function fun2('a','b',"c"){
               alert(a)
           }
           ```
   
     2. 方法：
   
     3. 属性：
   
        1. length:代表形式参数的个数
   
           ```javascript
           alert(fun2.length);//3
           ```
   
           
   
     4. 特点：
   
        1. 方法定义时，形式参数的类型不用写，返回值的类型也用写
   
           ```javascript
           function /* var可以不写 */ add('a','b'){
            	return a+b
           }
           var sum = add(2,2);//4
           ```
   
        2. 方法其实是一个对象，如果定义名称相同的方法，会覆盖
   
           ````javascript
           function add('a','b'){
            	return a+b
           }
           function add('a','b'){
            	return a-b
           }
           var sum = add(2,2);//0
           ````
   
        3. 在JS中方法的调用只与方法的名称有关，与方法的参数列表无关；
   
           ```javascript
           function fun2('a','b',"c"){
               alert(a)
           }
           fun2(1,2);//1
           fun2(1);//1
           fun2();//undefined
           fun2(1,2,3);//
           //与实际参数无关
           ```
   
        4. 在方法声明中有一个隐藏的内置对象（数组），arguments，封装所有的实际参数；
   
           ```javascript
           //因此可以求任意个数的和
           function fun(){
               var sum = 0;
               var count=0;
               while(count<arguments.length){
                   sum += arguments[count];
                   count++;
               }
               return sum;
           }
           var sum = add(1,2,3);//6
           ```
   
           
   
     5. 调用：
   
        方法名称（实际参数值）
   
   - [`Array](https://www.w3school.com.cn/jsref/jsref_obj_array.asp)
   
   - [Boolean](https://www.w3school.com.cn/jsref/jsref_obj_boolean.asp)
   
   - [Classe](https://www.w3school.com.cn/jsref/jsref_classes.asp)
   
   - [Date](https://www.w3school.com.cn/jsref/jsref_obj_date.asp)
   
   - [Error](https://www.w3school.com.cn/jsref/jsref_obj_error.asp)
   
   - [Global](https://www.w3school.com.cn/jsref/jsref_obj_global.asp)
   
   - [JSON](https://www.w3school.com.cn/jsref/jsref_obj_json.asp)
   
   - [Math](https://www.w3school.com.cn/jsref/jsref_obj_math.asp)
   
   - [Number](https://www.w3school.com.cn/jsref/jsref_obj_number.asp)
   
   - [RegExp](https://www.w3school.com.cn/jsref/jsref_obj_regexp.asp)
   
   - [String](https://www.w3school.com.cn/jsref/jsref_obj_array.asp)
   
   - [运算符](https://www.w3school.com.cn/jsref/jsref_operators.asp)
   
   - [语句](https://www.w3school.com.cn/jsref/jsref_obj_string.asp)
   - [javascript高级教程](https://www.w3school.com.cn/js/index_pro.asp)

