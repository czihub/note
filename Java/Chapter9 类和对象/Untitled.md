## 2022年4月4日16点09分

## 异常概述

---



| **Throwable** | Error         |                    |
| ------------- | ------------- | ------------------ |
|               | **Exception** | RuntimeException   |
|               |               | 非RuntimeException |

Error 不处理
Exception：异常类，程序本身可处理	

-   RuntimeException 编译期不检查，出问题后需要修改
  - jvm默认处理方式： 给出错误名称，错误原因，错误位置，然后终止程序
- 非RuntimeException 编译期就要处理，否则编译不通过

---



## 异常处理try -- catch

格式

```java
try{
    //异常代码  
}catch(/*异常类名 参数名*/ ){
    //处理代码
}//try -- catch配套出现，若无则程序终止
```

运行流程
从try中开始执行
出现异常，生成异常类对象，并提交给java运行系统
java运行系统接收到对象时，到catch中匹配异常类，执行异常处理
之后继续执行

---

## Throwable 成员方法



| 方法名                         | 说明                           |
| ------------------------------ | ------------------------------ |
| public String getMessage()     | 返回错误原因                   |
| public String toString()       | 名称：原因                     |
| public String printStacTrace() | 详细的名称：原因<br />错误地址 |

```java
try{
    int[] arr = {1,2,3}
    System.out.println(arr[3]);//new ArrayIndexOutOfBoundsException("xxx");
}catch(){
    System.our.println(e.getMessage());//调用Throwable方法
    e.printStackTrace();//调用Throwable方法
}
// 
puvlic class Throwable{
    private String detailMessage;//getMessage() 用到的成员变量
   	public Throwable(String message){//new ArrayIndexOutOfBoundsException("xxx");
        detailMessage=message;//xxx
    }
    public String getMessage(){
        return detailmessage;
    }
}
```

---

## 编译时异常和运行时异常

编译时异常

> 运行时有错误，处理后可正常运行

```java
try{//编译时异常
    String s = "2022-09-08";
    SimpleDateFormat sdf = new SimpleDateFormat(pattern:"yyyy-MM-dd");
    Date d = sdf.parse(d);//编译时错误，运行时无错误
}catch(ParseException se){
    e.printStackTrace();
}
```

运行时异常

> 数组下标越界

---

## 异常处理--throws

```java

public static void main(String[] args){
    System.out.println("开始");
    //抛出异常后处理异常
    
    try{
        method();
    }catch(ParseException e){
        e.printStackTrace();
    }  
}
//编译时异常
public static void method() throws ParseException{
    
    String s = "2022-09-08";
    SimpleDateFormat sdf = new SimpleDateFormat(pattern:"yyyy-MM-dd");
    Date d = sdf.parse(d);
    System.out.println(d);
}
//运行时错误
public static void method2() throws ArraysIndexOutOfBoundsException(){
    int[] i = {1,2,3};
    System.out.println(i[3]);
}
```

> 无论是编译异常还是运行异常
> 方法抛出异常并不是处理异常，后续依旧需要处理异常
> 只是把异常抛给了调用者

> 运行时异常，编译时不提醒，但是运行后需要更改