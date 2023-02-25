## css选择器

### 基础的选择器

#### 通配符选择器

*通配符选择器可以选择页面所有元素*

``` html	
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>通配符选择器</title>
    <style>
        * {
            color: #ddd;
        }
    </style>
</head>
<body>
<p>我是p标签中的文字</p>
<p>我是p标签中的文字1</p>
<p>我是p标签中的文字2</p>
<div><span>我是span元素中的文字1</span><span>我是span元素中的文字2</span><span>我是span元素中的文字3</span><label
        for="ipt">1<input type="text" id="ipt">11111</label>
</div>
</body>
</html>
```

![通配符选择](C:\Users\Administrator\Desktop\截图\css选择器\通配符选择器\通配符选择.png)

#### 标签选择器

*标签选择器,可以指定具体标签的样式*

``` html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Title</title>
    <style>
        p{
            color: #7A7C7A;
        }
        span {
            color: #626BAA;
        }
        label {
            color: red;
        }
        input {
            color: #2ed573;
        }
    </style>
</head>
<body>
<p>我是p标签中的文字</p>
<p>我是p标签中的文字1</p>
<p>我是p标签中的文字2</p>
<div><span>我是span元素中的文字1</span><span>我是span元素中的文字2</span><span>我是span元素中的文字3</span><label
        for="ipt">1<input type="text" id="ipt" placeholder="input的文字">11111</label>
</div>
</body>
</html>
```

![image-20230221213050607](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20230221213050607.png)

#### 类选择器

*可以在html标签上指定具体的class属性.*

``` html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>类选择器</title>
    <style>
        p.p-no1 {
            color: #ff7f50;
        }

        p.p-no2 {
            color: #ff6b81;
        }

        p.p-no3 {
            color: #ffa502;
        }
    </style>
</head>
<body>

<p class="p-no1">我是p标签中的文字</p>
<p class="p-no2">我是p标签中的文字1</p>
<p class="p-no3">我是p标签中的文字2</p>
</body>
</html>
```

![类选择器](C:\Users\Administrator\Desktop\截图\css选择器\类选择器\类选择器.png)

#### id选择器

*id选择器优先级最高,id属性在页面中是唯一的，所以id选择器只能选取一个元素*

``` html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>id选择器</title>
  <style>
    #id-p {
      color: #55a532;
    }
    .p {
      color: red;
    }
    /*类选择没有覆盖id选择器,*/
  </style>
</head>
<body>
<p>我是p标签中的文字</p>
<p>我是p标签中的文字1</p>
<p class="p" id="id-p">我是p标签中的文字2</p>
</body>
</html>
```

![id选择器](C:\Users\Administrator\Desktop\截图\css选择器\id选择器\id选择器.png)

*css通配符选择器 粒度更大,可以选择页面所有元素*

*标签选择器粒度适中 可以控制相同标签的样式*

*类选择器粒度更小 可以选择相同标签,不同class的元素*

*id选择器优先级最高*

### 结构选择器

#### 后代选择器

*后代选择器,可以选择所有的后代元素 以空格分割*

``` html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>后代选择器</title>
    <style>
        /*main下面所有的p标签都会被选中*/
        main p {
            color: red;
        }
    </style>
</head>
<body>
<main>
    <div>
        我是div中的文字
        <p>我是div-p中的文字</p>
    </div>
    <p>我是main-p中的文字<span>我是p-span中的文字</span></p>
    <span>我是main-span中的文字</span>
</main>
<main>
    <div>
        我是div中的文字
        <p>我是div-p中的文字</p>
    </div>
    <p>我是main-p中的文字<span>我是p-span中的文字</span></p>
    <span>我是main-span中的文字</span>
</main>
</body>
</html>
```

![后代选择器-1](C:\Users\Administrator\Desktop\截图\css选择器\后代选择器\后代选择器-1.png)

*选择器可以组合使用,例如类选择组合后代选择器可以选中某一块区域*

``` html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>后代选择器组合使用</title>
    <style>
        .main p {
            color: red;
        }
    </style>
</head>
<body>
<!--指定类名-->
<main class="main">
    <div>
        我是div中的文字
        <p>我是div-p中的文字</p>
    </div>
    <p>我是main-p中的文字<span>我是p-span中的文字</span></p>
    <span>我是main-span中的文字</span>
</main>
<hr>
<main>
    <div>
        我是div中的文字
        <p>我是div-p中的文字</p>
    </div>
    <p>我是main-p中的文字<span>我是p-span中的文字</span></p>
    <span>我是main-span中的文字</span>
</main>
</body>
</html>
```

![后代选择器组合使用](C:\Users\Administrator\Desktop\截图\css选择器\后代选择器\后代选择器组合使用.png)

#### 子元素选择器

*子组合器（>）是一种 CSS 组合器，它用来选择元素的直接子元素，即第一层后代元素,不会选择孙元素*

![子元素选择器](C:\Users\Administrator\Desktop\截图\css选择器\子元素选择器\子元素选择器.png)

#### 相邻兄弟选择器

*相邻兄弟组合器（+）：选择前一个元素的下一个兄弟元素，即同级且相邻的元素(不会选择上面相邻的元素,会从本身向下找),且只会选择一个。*

``` html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>相邻兄弟选择器</title>
    <style>
        .main>p + span {
            color: red;
        }
    </style>
</head>
<body>
<main class="main">
    <div>
        我是div中的文字
        <p>我是div-p中的文字</p>
    </div>
    <p>我是main-p中的文字<span>我是p-span中的文字</span></p>
    <span>我是main-span中的文字</span>
    <span>我是main-span中的文字2</span>
</main>
<hr>
<main>
    <div>
        我是div中的文字
        <p>我是div-p中的文字</p>
    </div>
    <p>我是main-p中的文字<span>我是p-span中的文字</span></p>
    <span>我是main-span中的文字</span>
</main>
</body>
</html>
```

#### 分组选择器

*可以用逗号分隔多个选择器，然后统一应用一些样式规则*

``` html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>分组选择器</title>
    <style>
        .main > span, .main p {
            color: #DD4A68;
        }
    </style>
</head>
<body>
<main class="main">
    <div>
        我是div中的文字
        <p>我是div-p中的文字</p>
    </div>
    <p>我是main-p中的文字<span>我是p-span中的文字</span></p>

    <span>我是main-span中的文字</span>
    <span>我是main-span中的文字-1</span>
</main>

</body>
</html>
```

![组合选择器](C:\Users\Administrator\Desktop\截图\css选择器\组合选择器\组合选择器.png)

### 属性选择器

*属性选择器可以根据元素的属性及属性值来选取元素,有不同的属性选择器，例如[attr\]、[attr=val]、[attr~=val]等*

``` html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>属性选择器</title>
    <style>
        div[class=div] {
            color: red;
        }

        p[class=p]{
            color: red;
        }
    </style>
</head>
<body>
<main class="main">
    <div class="div">
        我是div中的文字
        <p>我是div-p中的文字</p>
    </div>
    <p>我是main-p中的文字<span>我是p-span中的文字</span></p>
    <span>我是main-span中的文字</span>
    <span>我是main-span中的文字2</span>
</main>
<p>我是p+</p>
<hr>
<main>
    <div>
        我是div中的文字
        <p>我是div-p中的文字</p>
    </div>
    <p class="p">我是main-p中的文字<span>我是p-span中的文字</span></p>
    <span>我是main-span中的文字</span>
</main>
</body>
</html>
```

![属性选择器](C:\Users\Administrator\Desktop\截图\css选择器\属性选择器\属性选择器.png)

### 伪类选择器

*伪类选择器包括超链接伪类,:target,:root,:empty等*

*:link是一个css伪类选择器，用于定义未访问过的链接的样式*

``` html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>link</title>
    <style>
        a:link{
            color: red;
        }

        a {
            text-decoration: none;
            color: inherit;
        }

    </style>
</head>
<body>
<a href="#">链接</a>
<a href="#">链接</a>
<a href="#">链接</a>
</body>
</html>
```

![link](C:\Users\Administrator\Desktop\截图\css选择器\链接伪类\link.png)

*:visited用于定义已访问过的链接的样式*

``` html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>visited</title>
    <style>
        a:visited {
            color: #2ed573;
        }
    </style>
</head>
<body>
<a href="#">链接</a>
</body>
</html>
```

![visited](C:\Users\Administrator\Desktop\截图\css选择器\链接伪类\visited.png)

*:hover用于定义鼠标经过时的样式*

``` html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>hover</title>
  <style>
    a:hover {
      color: lawngreen;
    }
  </style>
</head>
<body>
<a href="">链接</a>
</body>
</html>
```

![hover](C:\Users\Administrator\Desktop\截图\css选择器\链接伪类\hover.png)

*:active 用来定义鼠标点击时的状态*

``` html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>active</title>
    <style>
    a:active{
        color: #DD4A68;
    }
    </style>
</head>
<body>
<a href="#">链接</a>
</body>
</html>
```

![active](C:\Users\Administrator\Desktop\截图\css选择器\链接伪类\active.png)

*链接伪类最好按照lvha的顺序编写样式，即先写a:link，再写a:visited，再写a:hover，最后写a:active 否则容易冲突 样式不生效*

*:target 用于定义当前活动的锚点目标元素的样式,可以配合a标签使用 点击a标签时让锚点元素产生动态的样式转变*

``` html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>target</title>
    <style>
        div:target {
            color: #DD4A68;
        }
        div {
            width: 200px;
            height: 200px;
            border: 1px seagreen solid;
        }
    </style>
</head>
<body>
<a href="#div">点击我,使div的样式发生动态变化</a>
<br>
<div id="div">我可以变色</div>
</body>
</html>
```

*默认的样式为:*

![target](C:\Users\Administrator\Desktop\截图\css选择器\链接伪类\target.png)

*点击a标签时 div样式动态产生变化*

![target-1](C:\Users\Administrator\Desktop\截图\css选择器\链接伪类\target-1.png)

#### 结构伪类

*E:first-child 可以选择父元素下面第一个E元素*

#### 表单伪类

#### 字符伪类







