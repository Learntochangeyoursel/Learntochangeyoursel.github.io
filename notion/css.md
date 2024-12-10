## CSS3
简介：翻译为层叠样式表，是用于控制或增强网页样式并允许将样式信息与网页内容分离的一种语言。使用css样式可以控制许多仅使用html无法控制的属性。
表现形式分为：
- 内联样式：在元素属性中设置样式。
- 嵌入样式：在文件档头定义样式。
- 外部样式：将所有的样式写在一个外部文件中，在文件档头引入。

```html
<link rel = "stylesheet" herf = "文件路径"
```

### 响应式
页面设计与开发要根据用户的行为和设备环境进行相应的响应和调整。响应式网页设计就是一个网站能否兼容多个终端，而不是为每个终端做一个特定的版本。

案列
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>响应式</title>
    <style>
        body{
        background-color: white;
        }
        @media screen and (min-width: 768px){
            body{
                background-color: red;
            }
        }

        @media screen and (min-width: 992px){
            body{
                background-color: purple;
            }
        }

        @media screen and (min-width: 1200px){
            body{
                background-color: yellow;
            }
        }
    </style>
</head>
<body>
<ul>
    <li>小于768时为白色</li>
    <li>768与992间时为红色</li>
    <li>992与1200间时紫色</li>
    <li>大于1200时为黄色</li>
</ul>

</body>
</html>

```

### 基础选择器

基础选择器是CSS中最基础、最常用的选择器，供web前端开发者快速地进行DOM元素查找与定位。基本语法如下：
``` 
选择器名字{
    属性：值；
    属性：值；
}
```
一个简单的选择器代码如下

``` 
<--! li 就是选择器中常见的类选择器-->
li{ 
    float : left;           <--!对页面标签向左浮动，css的选择器是以键值对的形式存储的-->
    padding:4px 5px 0 5px;
    list-style:none;
}

```
常见的几种选择器

| 选择器            | 名称       | 含义                    |
|----------------|----------|-----------------------|
| *              | 通用元素选择器  | 匹配任何元素                |
| E              | 标签选择器    | 匹配所有使用E标签的元素          |
| .info 或 E.info | class选择器 | 匹配所有class属性中包含info的元素 |
| #info后E#info   | ID选择器    | 匹配所有ID属性等于info的元素     |

案例
``` html
<!DOCTYPE html>
<html>
<head>
    <meta charset="utf8">
    <title>选择器</title>
    <style>
        /*通用选择器*/
        * {
            color: yellow;
        }

        /*标签选择器*/
        div {
            color: aqua;
        }

        /*class选择器*/
        .pink {
            color: pink;
        }

        /*ID选择器*/
        #green {
            color: green;
        }

    </style>
</head>
<body>
<div>我是div里面的文字</div>
<span class="pink">我是span里带pink类型的文字</span>
<p class="pink">我是p标签里带pink类型的文字</p>
<p id="green">我是p标签里带green ID的文字</p>
<div>这是第二个div的文字</div>
<p>没有class和id的p标签里面的文字</p>

</body>
</html>
```

