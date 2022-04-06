# Java create classes and objects

## understand classes and objects

A class is a collection of objects with the same state and behavior. Variables store state and methods implement behavior.

> ![image-20220223155316795](C:\Users\19704\AppData\Roaming\Typora\typora-user-images\image-20220223155316795.png)

## Learn how to define classes and create objects of classes

```java
[Modifier[^fn1]] + class + class name{//define class
 	[modifier[^fn2]] + variable type + objects variable name;//create member state
    [modifier[^fn3]] + method return type + method name(parameter list){//create member behavior
        
    }
}
```

### Particular attention

> ![image-20220223162131726](C:\Users\19704\AppData\Roaming\Typora\typora-user-images\image-20220223162131726.png)
>
> ![image-20220223170923324](C:\Users\19704\AppData\Roaming\Typora\typora-user-images\image-20220223170923324.png)

## learn to access members of object (variable and method)

##  Understand the role of constructors and use constructors to initialize objects

### role

Build and initialize object

### how

```java
[modifier]+construct method name/*^same with calss*/(parameter list){//no return value
    //Constructor actuator(executable statement)
}
```

>  Attention![image-20220223163843722](C:\Users\19704\AppData\Roaming\Typora\typora-user-images\image-20220223163843722.png)
>
> none construction method = have none parameter constructor.
>
> have parameter constructor must have none parameter constructor.
>
> ![image-20220223164549679](C:\Users\19704\AppData\Roaming\Typora\typora-user-images\image-20220223164549679.png)
>
> ![image-20220223164636863](C:\Users\19704\AppData\Roaming\Typora\typora-user-images\image-20220223164636863.png)
>
> ![image-20220223170849134](C:\Users\19704\AppData\Roaming\Typora\typora-user-images\image-20220223170849134.png)
>
> ![image-20220223164713093](C:\Users\19704\AppData\Roaming\Typora\typora-user-images\image-20220223164713093.png)
>
> ![image-20220223165009057](C:\Users\19704\AppData\Roaming\Typora\typora-user-images\image-20220223165009057.png)
>
> ![image-20220223164758335](C:\Users\19704\AppData\Roaming\Typora\typora-user-images\image-20220223164758335.png)
>
> ![image-20220223165217931](C:\Users\19704\AppData\Roaming\Typora\typora-user-images\image-20220223165217931.png)
>
> 



## understand the store model of objects and the relationship between objects and reference variable

Object are stored in heap memory and are not accessible to java. Access by reference,manipulate objects.

### relationship

Reference variable are used to store the address of the object in the heap

> ![image-20220223170612560](C:\Users\19704\AppData\Roaming\Typora\typora-user-images\image-20220223170612560.png)
>
> ![img](https://img2020.cnblogs.com/blog/1820411/202007/1820411-20200730204322024-1206189447.jpg)

> ![image-20220223165835665](C:\Users\19704\AppData\Roaming\Typora\typora-user-images\image-20220223165835665.png)

[^fn1]: public abstract  final

[^ fn2 ]: public | protected | private | static | final 