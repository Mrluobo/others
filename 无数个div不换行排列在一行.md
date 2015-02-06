##无数个div不换行排列在一行
```
<!DOCTYPE html>
<html lang="en">
<head>
	<meta charset="UTF-8">
	<title>Document</title>
	<style>
		.test{
			width:200px;
			height:100px;
			background:red;
			display:inline-block;
		}
	</style>
</head>
<body>
<div style="white-space: nowrap;width:auto;position:absolute;">

	<div class="test"></div>
	<div class="test"></div>
	<div class="test"></div>
	<div class="test"></div>
	<div class="test"></div>
	<div class="test"></div>
	<div class="test"></div>
	<div class="test"></div>
	<div class="test"></div>
	<div class="test"></div>
</div>
</body>
</html>
```