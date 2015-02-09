
转自党建cnblog http://www.cnblogs.com/dangjian/p/4281004.html
常见的CSS定义排序方式
1. 按类型分组排序
这种排序方式最复杂，却也是最合理的方式。国外著名的Web前端专家Andy Ford推荐过一种按照类型分组排序的方式，他把CSS属性分为7大类：显示与浮动（Diplay&Flow）、定位（Positioning）、尺寸（Dimensions）、边框相关属性（Margins、Padding、Borders、Outline）、字体样式（Typographic Styles）、背景（Backgrounds）、其他样式（Opacity、Cursors、Generated Content）。以此规则，Andy Ford给出了一个例子，基本包含了CSS2.1中所有的样式属性。可以通过浏览他的文章查看完整的例子代码。

随着CSS3的普及，CSS样式中也添加了很多新的属性，这些新的属性也可以按照如上的规则归类到不同的类别中，如：text- shadow可以归类到字体样式中；border-radius可以归类为边框相关属性等。
2. 按字母序排列
按字母序排列的方式也是CSS排序中使用较多的一种方式。相比较于前一种方式，这种方式的优点是排列规则简单。按字母序排列的规则是按照属性的首字母从A到Z排列，忽略浏览器前缀（如：-webkit-、-moz-、-o-以及-ms-）。如下是一个按照字母序排列的例子：
```css
#element {
    -webkit-border-radius: 4px;
    -moz-border-radius: 4px;
    border-radius: 4px;
    color: #FFF;  
    font-family: "Times New Roman", serif;  
    font-weight: bold;  
    height: 300px;  
    line-height: 20px;  
    top: 10px;  
    width: 100px;  
} 

```

3. 按定义长度排序
这种排序方式是使用较少的一种方式。和按照字母序排列的方式类似，这种方式是按照样式定义的字符长度排列。排列的方式可以从长到短，也可以是从短到长。如下的例子将按照定义由长到短排列：
```css
#element {
    font-family: "Times New Roman", serif;  
    -webkit-border-radius: 4px;
    -moz-border-radius: 4px;
    border-radius: 4px;
    font-weight: bold;  
    line-height: 20px;  
    height: 300px;  
    width: 100px;  
    color: #FFF;  
    top: 10px;  
} 
```

##插件的使用
csscomb