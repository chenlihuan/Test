#<!DOCTYPE html>
	<html>
	<head>
		<meta charset="UTF-8">
		<title></title>
		<style>
			*{padding: 0;margin: 0;}
			canvas{
				border: 1px solid #000;
				position: absolute;
				z-index: 2;
			}
			.prize{
				position:absolute;
				height: 150px;
				width: 300px;
				text-align: center;
				line-height: 150px;
				font-size: 30px;
				color: red;
				
			}
		</style>
	</head>
	
	<body>
		<canvas id="canvas" width="300" height="150"></canvas>
		<div class="prize">谢谢惠顾</div>
		<script>
			window.onload = function(){
				var canvas = document.getElementById("canvas");
				var ctx = canvas.getContext("2d");//开始绘制图形
			    	ctx.beginPath();//开始路径
			    	ctx.rect(0,0,300,150);//绘制矩形
			    	ctx.fillStyle="#c0c0c0";//填充颜色		    	
			    	ctx.fill();//填充
			    	ctx.closePath();//关闭路径
			    //鼠标按下去事件与鼠标滚动事件
			    canvas.onmousedown = function(evet){
			    	canvas.onmousemove= function(evet){
			    		var x = evet.clientX;
			    		var y = evet.clientY;
			    		console.log(x,y);
			    		ctx.clearRect(x,y,20,10);//清除
			    	}
			    };
			    //鼠标离开
			    canvas.onmouseup = function(){
			    	canvas.onmousemove = null;
			    }
			    //信息中的数据
			     var arr = ['一等奖学金','二等奖学金','三等奖学金','特等奖学金'];
			     var prise = document.querySelector(".prize");
			     var i =Math.floor(Math.random() * arr.length);
			     prise.innerHTML =  arr[i];
			}
	</script>
	</body>
	
</html>
