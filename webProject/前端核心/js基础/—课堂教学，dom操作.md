[toc]

## 设置标签中的属性

setAttribute 方法 添加属性

className也可以设置属性

```javascript
	<style type="text/css">
		.green{
			color: aqua;
			background-color: rgb(200, 255, 0);
			width: 300px;
			margin: 0 auto;
		}
	</style>

<body>
	<div>设置元素的内容</div>
	<div>设置元素的内容</div>

	<script type="text/javascript">

		//align 不是 alien 获取元素然后设置样式表
		var div = document.querySelector('div')
		div.setAttribute('align','center')
		div.setAttribute('style','color:red;font-size:30px')

		// 对第二个div 设置样式 首先应该获取
		var div2 = document.getElementsByTagName('div')[1]
		div2.setAttribute('class','green')
		div2.className='green'
	</script>
</body>
```

- 删除属性 removeAttribute

```javascript
<script>
div2.setAttribute('class','green')
div2.removeAttribute('class')
</script>
```

- 为class 添加更多的属性

```javascript
div2.classList.add('big')// 删除也很简单  删除同理，remove方法
```



## 设置样式

classList 中的toggle 方法实现样式的切换

// 有则删除，没有则，添加

```javascript
<head>
	<meta charset="utf-8">
	<meta name="viewport" content="width=device-width, initial-scale=1">
	<title></title>
	<style type="text/css">
		.red{
			background-color: red;
			width: 200px;
			height: 100px;
			text-align: center;
		}
		.center{
			margin: 0 auto;
		}
	</style>
</head>
<body>
	<div class="red">设置样式</div>
	<input type="button" value ="center or not" onclick="change()">
	<script type="text/javascript">
		// class 中的toggle 方法实现样式的切换
		function change(){
			// 有则删除，没有则，添加
			var input = document.querySelector('div').classList.toggle('center')
		}
	</script>
</body>
```

## dom 事件\

- **设置下拉框的思路**

```javascript
<script type="text/javascript">
        //1.  获取要操作的元素节点
        var nav = document.querySelector('.nav')
        var lis = nav.children;// 获取nav节点的四个子节点  得到的是集合
        for(let i =0;i<lis.length;i++){
            lis[i].onmouseover = function () { // 执行调用一个匿名函数
                this.children[1].setAttribute('style','display:block')
            }
            lis[i].onmouseout = function () { // 执行调用一个匿名函数
                this.children[1].setAttribute('style','display:none')
            }
        }

</script>
```

- **切换选项卡的方法之一**

```javascript
   <script>
        //获取 需要操作的元素
        var lis = document.querySelector('.tab_head').getElementsByTagName('li') //   获取五个li的集合
        var divs = document.querySelector('.tab_body').getElementsByTagName('div') // 获取五个div
        for (let i = 0; i < lis.length; i++) {//为5个li添加单击事件
            lis[i].onclick = function() {
                for (let i = 0; i < divs.length; i++) {//分别设置五个模块的内容
                    if (lis[i] == this) { //判断是否是当前操作项目
                        //1、 设置当前项目的样式规则
                        divs[i].classList.add('currentbody')
                        lis[i].classList.add('current')
                    } else {
                        //2、 清除其他项规则
                        divs[i].classList.remove('currentbody')
                        lis[i].classList.remove('current')

                    }
                }
            }
        }
    </script>
```

