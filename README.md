# jquery拖拽jqdrage

效果如下：
![](images/img.gif)

all code:
```
<!DOCTYPE html>
<html lang="en">
<head>
	<meta charset="UTF-8">
	<title>拖拽</title>
	<style>
	*{margin:0px;padding: 0px;}
		.drage{width: 200px;height: 200px;background: red;position: absolute;cursor: move;}
	#coor {
		width: 10px;
		height: 10px;
		overflow: hidden;
		cursor: se-resize;
		position: absolute;
		right: 0;
		bottom: 0;
		background-color: #09C;
	}
	</style>
</head>
<body>
	<div class="drage">
		<div id="coor"></div>
	</div>
</body>
</html>
<script src="js/jquery-2.1.4.js"></script>
<script>
	$(function(){
		$('.drage').mousedown(function(ev) {
			var X = ev.pageX - $('.drage').offset().left;
			var Y = ev.pageY - $('.drage').offset().top;
			$(document).mousemove(function(ev) {
				$('.drage').css({'left':ev.pageX - X,'top':ev.pageY - Y})
			});
			$(document).mouseup(function(ev){
				$(document).unbind();
			});
		});
		/*		$("#coor").mousedown(function(ev){
		 var xstr=ev.pageX;
		 //            console.log(xstr);
		 $(document).mousemove(function(ev){
		 var xmov=ev.pageX;
		 var n=1-((xstr-xmov)/720);
		 console.log(xmov+":"+(xstr-xmov)+":"+(xstr-xmov/962).toFixed(2)+":"+n);
		 $(".drage").css({'transform':'scale('+n+')','left':0,'top':0});
		 })
		 })*/
	})

</script>
```
