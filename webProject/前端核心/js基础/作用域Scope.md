[toc]

## 作用域

- 作用域指一个变量的作用范围
- 在JS中一共有两种作用域



### 全局作用域

> 在页面的任意一个位置都能访问的到


```javascript
<script>
	console.log(a)
	var a = 3
</script>
```

变量的声明提前，如果前面有var 会被提取声明，但不会被赋值

如果没有var则不会被赋值

```javascript
<script>
 	fun()
	b()
    function fun(){
    	console.log(a)
	}
	var a = 3
    var b = function(){
        console.log(a)
    }
</script>
```

fun会打印undefined

而b()会报错，b不是一个函数，因只是被提前声明，而没有赋值

但是方法不同，会被提前加载。

## 函数作用域

