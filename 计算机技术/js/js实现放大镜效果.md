# js实现放大镜效果

#### js部分：

```js
var small = document.getElementById('small');
var big = document.getElementById('big');
var mark = document.getElementById('mark');

//鼠标移入到小图，镜头和大图显示
small.onmouseover = function(){
	big.style.display = 'block';
	mark.style.display = 'block';
}
// 鼠标离开小图 大图和镜头隐藏
small.onmouseout = function(){
	big.style.display = 'none';
	mark.style.display = 'none';
}
// 监视鼠标在小图上的移动行为
small.onmousemove = function(event){
	//console.log(this.parentNode.offsetLeft);//小图的父节点(main)距离左边的距离
	//console.log(mark.offsetWidth); //镜头的宽度
	var ev = event || window.event;
	var x = ev.clientX - this.parentNode.offsetLeft - mark.offsetWidth/2;
	var y = ev.clientY - this.parentNode.offsetTop - mark.offsetHeight/2;

	//console.log('X'+x,'Y'+y);
	//防止镜头出界
	if (x <= 0) {	//控制左
		x = 0;
	}
	if (y <= 0) {	//控制上
		y = 0;
	}
	if (x >= this.offsetWidth - mark.offsetWidth) {	//控制右
		x = this.offsetWidth - mark.offsetWidth;
	}
	if (y >= this.offsetHeight - mark.offsetHeight) {	//控制下
		y = this.offsetHeight - mark.offsetHeight;
	}

	//让镜头的坐标等于鼠标的坐标
	mark.style.left = x + 'px';
	mark.style.top = y + 'px';

	//通过镜头移动的比例，计算大图移动的距离
	//镜头移动的距离 / 总长度 == 大图移动的距离 / 大图可以移动的总长度
	//mark.offsetLeft / (this.offsetWidth - mark.offsetWidth) == bigLeft / (bigImg.offsetWidth - big.offsetWidth);
	var bigImg = big.getElementsByTagName('img')[0];//big节点找到大图
	var bigLeft = mark.offsetLeft / (this.offsetWidth - mark.offsetWidth) * (bigImg.offsetWidth - big.offsetWidth);
	var bigTop = mark.offsetTop / (this.offsetHeight - mark.offsetHeight) * (bigImg.offsetHeight - big.offsetHeight);

	/*var bl = mark.offsetLeft / (this.offsetWidth - mark.offsetWidth);//计算出比例是多少
	var bigLeft = bl * (bigImg.offsetWidth - big.offsetWidth); //通过比例计算出大图到左侧的距离*/

	//先定位布局，才能移动
	bigImg.style.position = 'absolute';
	bigImg.style.left = -bigLeft + 'px'; //要反方向移动用负数 - 
	bigImg.style.top = -bigTop + 'px'; //要反方向移动用负数 -
}
```

#### html部分：

```html
<!DOCTYPE html>
<html>
<head>
	<meta charset="utf-8">
	<title>放大镜效果</title>
	<link rel="stylesheet" type="text/css" href="./css/1.css">
	
</head>
<body>
	<div id="main">
		<!-- 小图 -->
		<div id="small">
			<img src="./small.jpg">
			<!-- 镜头-阴影部分 -->
			<div id="mark"></div>
		</div>
		<!-- 大图 -->
		<div id="big">
			<img src="./big.png">
		</div>
	</div>

</body>
<script type="text/javascript" src="./js/1.js"></script>
</html>
```

#### css部分：

```css
body,div,img{margin: 0;padding: 0}
#main{width: 323px;height: 323px;margin: 50px; border: 1px solid #666; position: relative;}
#small{width:100%;}
#small img{width: 323px; height: 323px;}
#big{width: 100%;height: 323px; overflow: hidden;position: absolute;left: 350px;top: 0;display: none;}
#mark{width: 80px;height: 80px;background-color: #ccc;opacity: 0.8;position: absolute;left: 0;top: 0;display: none;}
```

