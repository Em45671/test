# CSS笔记



## id和Class选择器

1. id选择器,利用id属性

   ```html
   <!DOCTYPE html>
   <html>
   <head> 
   <meta charset="utf-8"> 
   <title>菜鸟教程(runoob.com)</title>
   <style>
       #paral{
           text-align:center;
           color:blue
       }
       #help{
           color:seagreen
       }
   </style>
   </head> 
   <body>
   <p id="paral">这是一个居中。颜色为蓝色的段落</p>
   <p id="help">注意：使用Id选择器需要在style中用"#"+id名</p>
   </body>
   </html>
   ```

   注意：id属性值不要用数字开头

2. class选择器

   ​       class选择器可以对class属性值相同的不同元素（p,h1,h2等)进行格式化。使用方法：在 CSS 中，类选择器以一个点 **.** 号显示。“**.**+class属性值{}”，对应在html元素中用设置元素class的值来设定。

   ​       class选择器可以对相同元素相同class属性值相同的元素进行处理。

   ```html
       
   <style>
           .test1 {
               text-align: center;
               color: blue
           }
   
           p.test2 {
               color: brown
           }
       </style>
   </head>
   
   <body>
       <!--不同元素相同的class属性值-->
       <h1 class="test1">这是一个class属性值为test1标题</h1>
       <p class="test1">这是一个class值为test1的段落</p>
       <!--同元素同class值-->
       <p class="test2">这是一个class值为test2的段落</p>
   </body>
   ```

   注意：class的值也不要用数字开头。

   

## CSS的创建

   插入样式表有三种方法

   - 外部样式表(External style sheet)

   - 内部样式表(Internal style sheet)

   - 内联样式(Inline style)

     三种样式的优先级是：内联样式>内部样式表>外部样式表。当优先级低和优先级高的样式表中有同一元素的样式定义且优先级低的样式表有对该元素更细致的样式定义，那么该元素的样式定义将会使用优先级高的样式表，同时把存在于低优先级样式表而不存在高优先级样式表中的样式定义抢走。

     ​     1.外部样式表

     ​      外部样式表用于多个页面的格式设置，使用外部样式表可以改变整个站点的样式。每个页面使用 <link> 标签链接到样式表。 <link> 标签在（文档的）头部：
     
     ```html
     <head>
     <link rel="stylesheet" type="text/css" href="mystyle.css">
     </head>
     ```

     ​     2.内部样式表
     
     ​     内联样式表用于单个页面的格式设置。在文档<head>中用style{}来设置页面格式。
     
     ```html
     <head>
     <style>
     hr {color:sienna;}
     p {margin-left:20px;}
     body {background-image:url("images/back40.gif");}
     </style>
     </head>
     ```
     
     ​     3.内联样式
     
     ​     内联样式将元素内容和样式一起设置。在元素中用style来设置。（不推荐使用）。
     
     ```html
     <p style="color:red;font-size:3"></p>
     ```



## CSS Background(背景)

背景属性如下：

|         属性          |                  作用及使用方法                  |
| :-------------------: | :----------------------------------------------: |
|   background-image    | 设置背景图像，background-image:url('图像的路径') |
|   background-repeat   |           设置图像是否重复以及如何重复           |
| background-attachment |    背景图像是否固定或者随着页面的其余部分滚动    |
|  background-position  |                设置图像的起始位置                |
|   background-color    |                   设置背景颜色                   |

## Text(文本)

|      属性       |                      作用                      |                             用法                             |
| :-------------: | :--------------------------------------------: | :----------------------------------------------------------: |
|      color      |                  设置文本颜色                  |                              /                               |
| letter-spacing  |                  设置字符间距                  |                              /                               |
|  word-spacing   |                  设置单词间距                  |                              /                               |
|   line-height   |                   设置行间距                   |                              /                               |
|    direction    |                  设置文本方向                  |                              /                               |
| text-transform  |         控制元素中的字母（大小写之类）         |                              /                               |
|   white-space   |      设置元素中空白的处理方式（如何换行）      | 一些元素会在其开始的时候自动换行,如<p>，设置为white-space:nowrap;时实现只有遇到<br>时才换行。[该属性的具体取值及作用](https://www.runoob.com/cssref/pr-text-white-space.html) |
| text-decoration | 规定添加到文本的修饰，下划线、上划线、删除线等 |                              /                               |
|   text-shadow   |                  设置文本阴影                  | text-shadow: h-shadow v-shadow blur color;分别为水平阴影的位置，垂直阴影的位置，模糊的距离，颜色。前两个必须 |
|   text-indent   |              缩进元素中文本的首行              |                              /                               |
|   text-align    |               设置文本的对齐方式               |                              /                               |
|  unicode-bidi   |            设置或返回文本是否被重写            |                              /                               |
| vertical-align  |           设置一个元素的垂直对齐方式           |   img{    vertical-align:text-top;}定义图像与文本上部对齐    |

## CSS Fonts(字体)

字体属性及作用

|     属性     |                             作用                             |                           使用注意                           |
| :----------: | :----------------------------------------------------------: | :----------------------------------------------------------: |
|     font     |                在font属性里设置全部的字体属性                |                              /                               |
|  font-size   |                        指定文本的大小                        | 可以通过以px或者em为单位来设置字体的大小，一般来说，默认的字体大小为16px,同时16px=1em。我们也可以设置默认字体的大小。在属性body中设置。还可以以body中的字体大小为参考（100%）用百分比来设置字体大小。 |
| font-family  |                      指定文本的字体系列                      | font-family 属性应该设置几个字体名称作为一种"后备"机制，如果浏览器不支持第一种字体，他将尝试下一种字体。多个字体系列是用一个逗号分隔指明。 |
|  font-style  |               指定文本字体的样式（斜体之类的）               | 有三个值。normal 正常,italic 斜体, oblique 斜体。一般用italic设置斜体。下面两种情况使用oblique。同时oblique可以设置斜体的角度。1.使用italic斜体之后文本不能使用其他属性2.oblique 是让没有斜体属性的文字倾斜， |
| font-weight  |                       设置文本加粗格式                       |          bord加粗，border超级加粗，还可以设置其他值          |
| font-variant | （值取small-caps）让字母变成大写，并且原本字母是大写的会比其他字母更大 |   原文本：SMall     处理后的文本：SMALL(而且SM的字体更大)    |

## CSS链接

链接的样式，可以用任何CSS属性（如颜色，字体，背景等）。

特别的链接，可以有不同的样式，这取决于他们是什么状态。

这四个链接状态是：

- a:link - 正常，未访问过的链接

- a:visited - 用户已访问过的链接

- a:hover - 当用户鼠标放在链接上时

- a:active - 链接被点击的那一刻

实例

```html
a.one:link{color:antiquewhite;text-decoration:underline;}
a.one:visited{color:aqua;text-decoration:line-through;}
a.one:hover{color:blueviolet;text-decoration:overline}
a.one:active{color:blue;text-decoration:wavy}
```

其中a.one指的是一个链接class值为one。

## CSS列表

列表属性及作用如下：

|        属性         |                  作用                  |                           使用注意                           |
| :-----------------: | :------------------------------------: | :----------------------------------------------------------: |
|     list-style      |         属性集合，用于属性简写         |                              /                               |
|  list-style-image   |         将图像设置为列表项标志         |                   list-style-image:url('')                   |
| list-style-position | 指示如何相对于对象的内容绘制列表项标记 | inside:列表项目标记放置在文本以内，且环绕文本根据标记对齐。outside:默认值。保持标记位于文本的左侧。列表项目标记放置在文本以外，且环绕文本不根据标记对齐 |
|   list-style-type   |         设置列表项标志的类型。         |                              /                               |

一个将图像设置为列表项标志的实例（在CSS内部样式表中设置）：

```html
ul
{
    list-style-type: none;
    padding: 0px;
    margin: 0px;
}
ul li
{
    background-image: url(sqpurple.gif);
    background-repeat: no-repeat;
    background-position: 0px 5px; 
    padding-left: 14px; 
}
```

例子解释：

- ul:

  - 设置列表类型为没有列表项标记
  - 设置填充和边距 0px（浏览器兼容性）

- ul 中所有 li:

  - 设置图像的 URL，并设置它只显示一次（无重复）

  - 您需要的定位图像位置（左 0px 和上下 5px）

  - 用 padding-left 属性把文本置于列表中

注意：list-style-type:none 属性可以用于移除小标记。默认情况下列表 <ul> 或 <ol> 还设置了内边距和外边距，可使用 `margin:0` 和 `padding:0` 来移除。

## CSS Table(表格)

对table的CSS设置的样式

```html
<style>
    table,th,td{
        /*这是对表格的表头和列元素的设置，一般是用来设置表头单元格和列单元格的边框*/
    }
    table{
        /*这是对表格的设置*/
    }
    th{
        /*这是对表头的设置*/
    }
    td{
        /*这是对列的设置*/
    }
</style>
```

- 表格边框（border属性）

  ```html
  table, th, td
  {
      border: 1px solid black;/*border:边框宽度，边框样式，边框颜色
  }
  ```

- 折叠边框：border-collapse 属性设置表格的边框是否被折叠成一个单一的边框或隔开

  ```html
  table
  {
      border-collapse:collapse;/*边框被折叠*/
  }
  table,th, td
  {
      border: 1px solid black;
  }
  ```

- 表格的高度和宽度

  使用width和height属性对单元格或者整个表格进行设置。

- 表格的文字对齐

  利用属性text-align实现表格文本的水平对齐，属性vertical-align实现文本元素的垂直对齐。

- 表格填充和表格的颜色

  如需控制边框和表格内容之间的间距，应使用td和th元素的填充属性：padding:80px。背景颜色用background-color实现。

- 表格标题的设置

  使用caption属性设置标题在表格中的位置。

  ```html
  <style>
  caption {caption-side:bottom;}
  </style>
  </head>
  <body>
      <table>
          <caption>Table 1.1</caption>
      </table>  
  </body>
  ```

  这个例子设置了一个位于表格底部的标题。
  
  一个完整的例子
  
  ```html
      <style>
          table,th{
              border:5px solid blue;
          }
          table{
              width:65%;
              
          }
          td{
              vertical-align:top;
              border:5px solid red;
              text-align:right;
              width:50px;
              padding:20px;
              background-color:yellow;
          }
          th{
              vertical-align:bottom;/*元素的垂直fa*/
              width:50px;
              height:50px;
              text-align:left;
              padding:50px;
              background-color:blueviolet;
          }
  
      </style>
  ```
  
  

## CSS盒子模型

所以的html元素都可以看作是盒子，CSS盒模型本质上是一个盒子，封装周围的HTML元素，它包括：边距，边框，填充，和实际内容。盒模型允许我们在其它元素和周围元素边框之间的空间放置元素。

下列是盒子模型。

![盒子模型](../../pr素材/box-model (1).gif)

- Margin(外边距) - 清除边框外的区域，外边距是透明的。

- Border(边框) - 围绕在内边距和内容外的边框。

- Padding(内边距) - 清除内容周围的区域，内边距是透明的。

- Content(内容) - 盒子的内容，显示文本和图像。

当您指定一个 CSS 元素的宽度和高度属性时，你只是设置内容区域的宽度和高度。要知道，完整大小的元素，你还必须添加内边距，边框和外边距。

举例：

```html
<style>
div.ex
{
width:220px;
padding:10px;
border:5px solid gray;
margin:0px;
}/*这个元素的宽度是250px宽*/
</style>

<body>
    <img src="250x250px.gif" width="250" height="250" />

    <div class="ex">上面的图片是250 px宽。
     这个元素的总宽度也是250 px。</div>
</body>
```

## CSS Border边框

|     属性      |                             作用                             |
| :-----------: | :----------------------------------------------------------: |
|    border     | 简写属性，用于把针对四个边的属性设置在一个声明。依次是border-width 边框宽度，border-style边框样式，border-color边框颜色。同时可以把三种设置分别拿出来设置。 |
|  border-top   | 简写属性，用于把针对上边框的属性设置在一个声明。依次是border-top-width 边框宽度，border-top-style边框样式，border-top-color边框颜色。同时可以把三种设置分别拿出来设置。 |
| border-bottom |                             同上                             |
|  border-left  |                             同上                             |
| border-right  |                             同上                             |
| border-radius |            把边框的直角变成圆角并且设置圆角的边框            |

border-style属性可以有1-4个值。不同个值下的作用如下。

border-style：属性1，属性2，属性3，属性4

上->右->下->左

border-style：属性1，属性2，属性3

上->左右->下

border-style：属性1，属性2

上下->左右

border-style：属性1

上下左右属性相同

不同的border-style属性值：

![](../../pr素材/border-style.png)

关于border-radius有如下实例

```html
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8"> 
<title>菜鸟教程(runoob.com)</title> 
<style> 
#example1
{
	border:2px solid #a1a1a1;
	padding:10px 40px; 
	background:#dddddd;
	width:300px;
	border-radius:25px;
}
#example2 {
  border: 2px solid red;
  padding: 10px;
  border-radius: 50px 20px;
}
</style>
</head>
<body>
<div id="example1">
  <p>border-radius 属性允许您为元素添加圆角边框！</p>
</div>
<br><br>
<div id="example2">
  <p>如果设置了两个值，第一个用于左上角和右下角，第二个用于右上角和左下角。</p>
</div>
</body>
</html>
```

## CSS outline轮廓

轮廓（outline）是绘制于元素周围的一条线，位于边框边缘的外围，可起到突出元素的作用。CSS outline 属性规定元素轮廓的样式、颜色和宽度。

下面是outline的位置。

![outline](../../pr素材/box_outline.gif)Outline

所有CSS 轮廓(outline）属性

|     属性      |              说明              |                              值                              |
| :-----------: | :----------------------------: | :----------------------------------------------------------: |
|    outline    | 在一个声明中设置所有的轮廓属性 | outline-color<br/>outline-style<br/>outline-width<br/>inherit |
| outline-color |          设置轮廓颜色          | *color-name<br/>hex-number<br/>rgb-number<br/>*invert<br/>inherit |
| outline-style |          设置轮廓样式          |                与上一节中border-style取值一样                |
| outline-width |         设置轮廓的宽度         | thin<br/>medium<br/>thick<br/>*length<br/>*inherit（或者em,px为单位） |

## CSS margin(外边距) 与padding（填充）

margin 没有背景颜色，是完全透明的。margin 可以单独改变元素的上，下，左，右边距，也可以一次改变所有的属性。

padding 定义元素边框与元素内容之间的空间，即上下左右的内边距。当元素的 padding（填充）内边距被清除时，所释放的区域将会受到元素背景颜色的填充。单独使用 padding 属性可以改变上下左右的填充。

下图为margin和padding 的示意图

![](../../pr素材/margin.png)

注意，padding和margin的距离都可以用cm(厘米)，em为单位设置大小还可以用%百分比来设置。

1.margin属性

|     属性      |                             说明                             |
| :-----------: | :----------------------------------------------------------: |
|    margin     | 简写属性。在一个声明中设置所有外边距属性.属性依次为margin-top,margin-right,margin-bottom,margin-left |
|  margin-top   |                     设置元素的上外边距。                     |
|  margin-left  |                     设置元素的左外边距。                     |
| margin-buttom |                     设置元素的下外边距。                     |
| margin-right  |                     设置元素的右外边距。                     |

2.padding属性

|      属性      |                             说明                             |
| :------------: | :----------------------------------------------------------: |
|    padding     | 简写属性。在一个声明中设置所有填充属性.属性依次为padding-top,padding-right,padding-bottom,padding-left |
|  padding-top   |                      设置元素的上部填充                      |
|  padding-left  |                      设置元素的左部填充                      |
| padding-buttom |                      设置元素的底部填充                      |
| padding-right  |                      设置元素的右部填充                      |

当margin/padding有不同个数的取值时

margin/padding:25px 50px 75px 100px;
上边距/填充为25px
右边距/填充为50px
下边距/填充为75px
左边距/填充为100px

margin/padding:25px 50px 75px;
上边距/填充为25px
左右边距/填充为50px
下边距/填充为75px

margin/padding:25px 50px;
上下边距/填充为25px
左右边距/填充为50px

margin:25px;
所有的4个边距/填充都是25px

##  CSS分组和嵌套

1.分组选择器

在样式表中有很多具有相同样式的元素,为了尽量减少代码，可以使用分组选择器。每个选择器用逗号分隔.

```html
h1,h2,p
{
    color:green;
}
```

2.嵌套选择器

它可能适用于选择器内部的选择器的样式.在下面的例子设置了四个样式：

- **p{ }**: 为所有 **p** 元素指定一个样式。

- **.marked{ }**: 为所有 **class="marked"** 的元素指定一个样式。

- **.marked p{ }**: 为所有 **class="marked"** 元素内的 **p** 元素指定一个样式。

- **p.marked{ }**: 为所有 **class="marked"** 的 **p** 元素指定一个样式.

  经测试值第三个嵌套选择器的优先级高于第二个

## CSS尺寸

  CSS 尺寸 (Dimension) 属性允许你控制元素的高度和宽度。同样，它允许你增加行间距。

通过控制min-height,max-height,min-width,max-width可以设置一个元素的范围有效位置,比如设置段落p的max-height,max-width就可以控制段落有效的样式设置尺寸大小.

尺寸属性

|    属性     |        作用        |
| :---------: | :----------------: |
|    width    |    设置元素宽度    |
|   height    |   设置元素的高度   |
| line-height |    设置元素行高    |
|  max-width  | 设置元素的最大宽度 |
| max-height  | 设置元素的最大高度 |
|  min-width  | 设置元素的最小宽度 |
| min-height  | 设置元素的最小高度 |

  注意,高度和宽度设置时可以用%百分比,px,em做单位的大小设置.

## CSS Display（显示）与Visibility（可见性）

display属性设置一个元素应如何显示，visibility属性指定一个元素应可见还是隐藏。

隐藏一个元素可以通过把display属性设置为"none"，或把visibility属性设置为"hidden"。但是请注意，visibility:hidden可以隐藏某个元素，但隐藏的元素仍需占用与未隐藏之前一样的空间。也就是说，该元素虽然被隐藏了，但仍然会霸占页面上的位置。display:none可以隐藏某个元素，且隐藏的元素不会占用任何空间。也就是说，该元素不但被隐藏了，而且该元素原本占用的空间也会从页面布局中消失。下面是设置元素不可见的例子。

```html
h1{
dispaly:none;
}
p{
visibility:hidden;
}
```

### CSS Display - 块和内联元素

块元素是一个元素，占用了全部宽度，在前后都是换行符。

块元素的例子：

h1

div

p

内联元素前后不带换行符，使用时不会出现换行。

内联元素的例子：

a

span（这是一个可以设置局部区域样式的元素）



我们可以通过display将块元素和内联元素实现转换，例如：

```html
li{
diaplay:inline;
}/*将块元素li(列表项)设置为内联元素*/
span{
display:block;
}/*将内联元素设置为块元素*/
```

display:inline-block

使元素变成行内元素，拥有行内元素的特性，即可以与其他行内元素共享一行，不会独占一行。能够改变元素的height，width的值。可以设置padding，margin的各个属性值，top，left，bottom，right都能够产生边距效果



我们还可以利用表格的collapse（折叠属性)来设置表格是否折叠。

举例如下：

```html
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8"> 
<title>菜鸟教程(runoob.com)</title> 
<style>
table, th, td {
    border: 1px solid black;
}

tr.collapse {
    visibility: collapse;
}
</style>
</head>
<body>

<table>
  <tr>
    <th>Firstname</th>
    <th>Lastname</th>
  </tr>
  <tr>
    <td>Peter</td>
    <td>Griffin</td>
  </tr>
  <tr class="collapse">
    <td>Lois</td>
    <td>Griffin</td>
  </tr>
</table>

<p><b>注意:</b> 利用collapse设置了表格class名为collapse的行元素的单元格是折叠的</p>

</body>
</html>

```



## CSS Position(定位)

### Potion属性

position 属性指定了元素的定位类型。

position 属性的五个值：

- static:默认值，静态定位不会受到top,right,left,bottom的大小影响。

- fixed:固定元素位置，元素的位置相对于浏览器窗口是固定位置。

  即使窗口是滚动的它也不会移动，Fixed定位使元素的位置与文档流无关，因此不占据空间。Fixed定位的元素和其他元素重叠。

- relative:相对位置，相对定位元素的定位是相对其正常位置。相对定位元素经常被用来作为绝对定位元素的容器块。会与其他元素重叠

- absolute:绝对定位，绝对定位的元素的位置相对于最近的已定位父元素，如果元素没有已定位的父元素，那么它的位置相对于<html>,absolute 定位使元素的位置与文档流无关，因此不占据空间

- stricky:粘性定位，

- sticky 英文字面意思是粘，粘贴，所以可以把它称之为粘性定位。

  **position: sticky;** 基于用户的滚动位置来定位。

  粘性定位的元素是依赖于用户的滚动，在 **position:relative** 与 **position:fixed** 定位之间切换。

  它的行为就像 **position:relative;** 而当页面滚动超出目标区域时，它的表现就像 **position:fixed;**，它会固定在目标位置。

  元素定位表现为在跨越特定阈值前为相对定位，之后为固定定位。

  这个特定阈值指的是 top, right, bottom 或 left 之一，换言之，指定 top, right, bottom 或 left 四个阈值其中之一，才可使粘性定位生效。否则其行为与相对定位相同。

  下面是该取值的案例：

  ```html
  <!DOCTYPE html>
  <html>
  <head>
  <meta charset="utf-8"> 
  <title>菜鸟教程(runoob.com)</title> 
  <style>
  div.sticky {
    position: -webkit-sticky;
    position: sticky;
    top: 0;
    padding: 5px;
    background-color: #cae8ca;
    border: 2px solid #4CAF50;
  }
  </style>
  </head>
  <body>
  
  <p>尝试滚动页面。</p>
  <p>注意: IE/Edge 15 及更早 IE 版本不支持 sticky 属性。</p>
  
  <div class="sticky">我是粘性定位!</div>
  
  <div style="padding-bottom:2000px">
    <p>滚动我</p>
    <p>来回滚动我</p>
    <p>滚动我</p>
    <p>来回滚动我</p>
    <p>滚动我</p>
    <p>来回滚动我</p>
  </div>
  
  </body>
  </html>
  
  
  ```

### 元素重叠

元素的定位与文档流无关，所以它们可以覆盖页面上的其它元素

z-index属性指定了一个元素的堆叠顺序（哪个元素应该放在前面，或后面）

一个元素可以有正数或负数的堆叠顺序。

```html
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8"> 
<title>菜鸟教程(runoob.com)</title> 
<style>
img
{
	position:absolute;
	left:0px;
	top:0px;
	z-index:-1;
}
</style>
</head>

<body>
<h1>This is a heading</h1>
<img src="w3css.gif" width="100" height="140" />
<p>因为图像元素设置了 z-index 属性值为 -1, 所以它会显示在文字之后。</p>
</body>
</html>
```

具有更高堆叠顺序的元素总是在较低的堆叠顺序元素的前面。

**注意：** 如果两个定位元素重叠，没有指定z - index，最后定位在HTML代码中的元素将被显示在最前面。

### 裁剪元素外形

使用clip来对元素大小进行裁剪，clip:rect(0px,0px,50px,50px),是指将元素裁剪掉左上角坐标为（0px,0px)右下角坐标为（50px,50px)的矩形。如下实例为给图像进行裁剪。

```html
img 
{
	position:absolute;
	clip:rect(0px,60px,200px,0px);
}
```

### 改变鼠标光标

利用style="cursor:(鼠标形状)"来设置当鼠标移动到这个元素时，鼠标光标的形状的样子。如下示例。

```html
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8"> 
<title>菜鸟教程(runoob.com)</title> 
</head>
<body>
<p>请把鼠标移动到单词上，可以看到鼠标指针发生变化：</p>
<span style="cursor:auto">auto</span><br>
<span style="cursor:crosshair">crosshair</span><br>
<span style="cursor:default">default</span><br>
<span style="cursor:e-resize">e-resize</span><br>
<span style="cursor:help">help</span><br>
<span style="cursor:move">move</span><br>
<span style="cursor:n-resize">n-resize</span><br>
<span style="cursor:ne-resize">ne-resize</span><br>
<span style="cursor:nw-resize">nw-resize</span><br>
<span style="cursor:pointer">pointer</span><br>
<span style="cursor:progress">progress</span><br>
<span style="cursor:s-resize">s-resize</span><br>
<span style="cursor:se-resize">se-resize</span><br>
<span style="cursor:sw-resize">sw-resize</span><br>
<span style="cursor:text">text</span><br>
<span style="cursor:w-resize">w-resize</span><br>
<span style="cursor:wait">wait</span><br>
</body>
</html>
```

## CSS布局-Overflow(溢出处理)

CSS overflow 属性可以控制内容溢出元素框时在对应的元素区间内添加滚动条。

overflow属性及说明：

|  属性   |                             说明                             |
| :-----: | :----------------------------------------------------------: |
| visible | 默认值，当元素溢出时内容不会被裁剪，但是溢出部分会显示在元素框外 |
| hidden  |                当元素溢出时，溢出部分会被裁剪                |
| scroll  |   内容会被修剪，但是浏览器会显示滚动条以便查看其余的内容。   |
|  auto   |   如果内容被修剪，则浏览器会显示滚动条以便查看其余的内容。   |
| inherit |           规定应该从父元素继承 overflow 属性的值。           |

如下示例

```html
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8"> 
<title>菜鸟教程(runoob.com)</title> 
<style>
div.ex1 {
    background-color: lightblue;
    width: 110px;
    height: 110px;
    overflow: scroll;
}

div.ex2 {
    background-color: lightblue;
    width: 110px;
    height: 110px;
    overflow: hidden;
}

div.ex3 {
    background-color: lightblue;
    width: 110px;
    height: 110px;
    overflow: auto;
}

div.ex4 {
    background-color: lightblue;
    width: 110px;
    height: 110px;
    overflow: visible;
}
</style>
</head>
<body>
<h1>overflow 属性</h1>

<p>如果元素中的内容超出了给定的宽度和高度属性，overflow 属性可以确定是否显示滚动条等行为。</p>

<h2>overflow: scroll:</h2>
<div class="ex1">菜鸟教程 -- 学的不仅是技术，更是梦想！！！菜鸟教程 -- 学的不仅是技术，更是梦想！！！菜鸟教程 -- 学的不仅是技术，更是梦想！！！菜鸟教程 -- 学的不仅是技术，更是梦想！！！</div>

<h2>overflow: hidden:</h2>
<div class="ex2">菜鸟教程 -- 学的不仅是技术，更是梦想！！！菜鸟教程 -- 学的不仅是技术，更是梦想！！！菜鸟教程 -- 学的不仅是技术，更是梦想！！！菜鸟教程 -- 学的不仅是技术，更是梦想！！！</div>

<h2>overflow: auto:</h2>
<div class="ex3">菜鸟教程 -- 学的不仅是技术，更是梦想！！！菜鸟教程 -- 学的不仅是技术，更是梦想！！！菜鸟教程 -- 学的不仅是技术，更是梦想！！！菜鸟教程 -- 学的不仅是技术，更是梦想！！！</div>

<h2>overflow: visible (默认):</h2>
<div class="ex4">菜鸟教程 -- 学的不仅是技术，更是梦想！！！菜鸟教程 -- 学的不仅是技术，更是梦想！！！菜鸟教程 -- 学的不仅是技术，更是梦想！！！菜鸟教程 -- 学的不仅是技术，更是梦想！！！</div>

</body>
</html>
```

## CSS Float（浮动）

浮动效果：元素的水平方向浮动，意味着元素只能左右移动而不能上下移动。

一个浮动元素会尽量向左（float:left)或向右(float:right)移动，直到它的外边缘碰到包含框或另一个浮动框的边框为止。

浮动元素之后的元素将围绕它。

浮动元素之前的元素将不会受到影响。

如果图像是右浮动，下面的文本流将环绕在它左边.

```html
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8"> 
<title>菜鸟教程(runoob.com)</title>
<style>
img 
{
	float:right;
}
</style>

</head>

<body>
<p>在下面的段落中，我们添加了一个 <b>float:right</b> 的图片。导致图片将会浮动在段落的右边。</p>
<p>
<img src="swing.gif" width="95" height="84" />
这是一些文本。这是一些文本。这是一些文本。
这是一些文本。这是一些文本。这是一些文本。
这是一些文本。这是一些文本。这是一些文本。
这是一些文本。这是一些文本。这是一些文本。
这是一些文本。这是一些文本。这是一些文本。
这是一些文本。这是一些文本。这是一些文本。
这是一些文本。这是一些文本。这是一些文本。
这是一些文本。这是一些文本。这是一些文本。
这是一些文本。这是一些文本。这是一些文本。
这是一些文本。这是一些文本。这是一些文本。
</p>
</body>

</html>
```

彼此相邻的浮动元素

如果把几个浮动元素放到一起，如果空间足够，她们就会彼此相邻。通常用图片廊使用float属性。

```html
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8"> 
<title>菜鸟教程(runoob.com)</title> 
<base href="https://www.runoob.com/">
<style>
.thumbnail 
{
	float:left;
	width:110px;
	height:90px;
	margin:5px;
}
</style>
</head>

<body>
<h3>图片库</h3>
<p>试着调整窗口,看看当图片没有足够的空间会发生什么。</p>
<img class="thumbnail" src="/images/klematis_small.jpg" width="107" height="90">
<img class="thumbnail" src="/images/klematis2_small.jpg" width="107" height="80">
<img class="thumbnail" src="/images/klematis3_small.jpg" width="116" height="90">
<img class="thumbnail" src="/images/klematis4_small.jpg" width="120" height="90">
<img class="thumbnail" src="/images/klematis_small.jpg" width="107" height="90">
<img class="thumbnail" src="/images/klematis2_small.jpg" width="107" height="80">
<img class="thumbnail" src="/images/klematis3_small.jpg" width="116" height="90">
<img class="thumbnail" src="/images/klematis4_small.jpg" width="120" height="90">
</body>
</html>
```



清除浮动（使用clear属性）

元素浮动之后，周围的元素会重新排列，为了避免这种情况，使用 clear 属性。

clear 属性指定元素两侧不能出现浮动元素。

```html
.text_line
{
    clear:both;
}
```

## 左侧菜单栏与上部菜单栏

左侧

```html
<!DOCTYPE html>
<html>

<head>
    <meta charset="utf-8">
    <title>菜鸟教程(runoob.com)</title>
    <style>
        .sidemenu {
            width: 25%;
        }

        .content {
            width: 75%;
        }

        .sidemenu ul {
            list-style-type: none;
            margin: 0;
            padding: 0;
        }

        .sidemenu li a {
            margin-bottom: 4px;
            display: block;
            padding: 8px;
            background-color: #eee;
            text-decoration: none;
            color: #666;
        }

        .sidemenu li a:hover {
            background-color: #555;
            color: white;
        }

        .sidemenu li a.active {
            background-color: #008CBA;
            color: white;
        }
    </style>
</head>

<body>
    <div class="column sidemenu">
        <ul>
            <li><a href="#flight">The Flight</a></li>
            <li><a href="#city" class="active">The City</a></li>
            <li><a href="#island">The Island</a></li>
            <li><a href="#food">The Food</a></li>
            <li><a href="#people">The People</a></li>
            <li><a href="#history">The History</a></li>
            <li><a href="#oceans">The Oceans</a></li>
        </ul>
    </div>


</body>

</html>
```



上部菜单栏

```html
<!DOCTYPE html>
<html>

<head>
    <meta charset="utf-8">
    <title>菜鸟教程(runoob.com)</title>
    <style>
        * {
            box-sizing: border-box;
          }
        body {
              margin: 0;
           }
        .topmenu {
            list-style-type: none;
            margin: 0;
            padding: 0;
            overflow: hidden;
            background-color: #777;
        }

        .topmenu li {
            float: left;

        }

        .topmenu li a {
            display: inline-block;
            color: white;
            text-align: center;
            padding: 16px;
            text-decoration: none;
        }

        .topmenu li a:hover {
            background-color: #222;
        }

        .topmenu li a.active {
            color: white;
            background-color: #4CAF50;
        }
    </style>
</head>

<body>
    <ul class="topmenu">
        <li><a href="#home" class="active">主页</a></li>
        <li><a href="#news">新闻</a></li>
        <li><a href="#contact">联系我们</a></li>
        <li><a href="#about">关于我们</a></li>
    </ul>
</body>

</html>
```





