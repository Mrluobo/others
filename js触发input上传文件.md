##js触发input文件上传
今天学到的感觉很有用的技巧
下附代码：
```
<form action="test">
		<input type="file" id="file" style="display:none">
		<input type="file" id="filename" style="display:none">
	</form>
	<div onclick="tt()" style="width:100px;height:100px;background:red;	">test</div>
	<script>
	function tt(){ 
			var ie=navigator.appName=="Microsoft Internet Explorer" ? true : false; 
		if(ie){ 
			document.getElementById("file").click(); 
			document.getElementById("filename").value=document.getElementById("file").value;
		}else{
			var a=document.createEvent("MouseEvents");//FF的处理 
			a.initEvent("click", true, true);  
			document.getElementById("file").dispatchEvent(a); 
		} 
		}
	</script>
```

##学习的内容：
创建事件对象：
```
var eve = document.createEvent("事件类型");
```
事件类型如下：

|参数|事件接口|初始化方法|
| ---- |-------| -----|
|HTMLEvents|HTMLEvent|initEvent()|
|MouseEvents| MouseEvent | initMouseEvent()|
|UIEvents | UIEvent | initUIEvent()|
初始化事件对象：
```
eve.initEvent("要触发的事件名：click...","是否可以冒泡","是否阻止事件的默认操作");
```
触发事件：
```
dom.dispatchEvent(eve);
```

###IE兼容
IE浏览器并不支持`createEvent()`但是其自身有一个propertychange事件，既属性发生改变就出发的事件。所以可以通过将自定义事件塞到propertychange事件里。如下：
首先先给dom随便搞一个属性：
```
dom.pro = "100";
```
然后把要自定义的事件处理方法塞到propertychange事件里：
```
dom.attachEvent("onpropertychange", function(e) {
    if (e.propertyName == "evtAlert") {
        fn.call(this);
    }
});
```
当常需要触发的时候：
```
dom.pro = Math.random();
```