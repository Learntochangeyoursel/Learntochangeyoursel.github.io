## 简介

解释型语言，简单弱类型脚本语言，相对安全的脚本语言，依赖于浏览器本身，可以实现跨平台；是一种为网站添加互动以及自定义行为的客户端脚本语言。

### 常见用法

一般引入写在文件末尾

## 模块

3个：
ECMA：JavaScript基础语法
DOM：页面文档类型语言
BOM：浏览器对象模型

案例1:内嵌js

``` html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Title</title>
    <script>
        alert("弹窗")
        console.info("控制台打印")
    </script>
</head>
<body>
</body>
</html>
```

案例1：外联.js

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>js第一课</title>

</head>
<body>
<script src="demo01.js"></script>
//引入js，路径在当前目录下的demo01.js文件
</body>
</html>
```

```javascript
alert("弹窗")
console.info("控制台打印")
```

``` 

```

## 基本语法

1. 使用Unicode码编写，区分大小写，忽略空格，换行符和制表符。
2. 简单语句后面通常有分号
3. 注释 //

## 变量

JavaScript中变量命名方式有三个关键字：var let const，他们有一定的区别
                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         
1. var定义的变量会出现一种污染现象，俗称变量提升。
2. let是ES6后提出的定义变量的方法，用于定义局部变量，解决var的变量污染问题。
3. const声明的变量不可更改。

```javascript
var num1;
let num2;
const PI = 3.14;
```

ps:变量提升：JavaScript中var定义的变量会出现在变量未定义前也能被使用的现象

## DOM 获取

> JavaScript DOM（Document Object Model）是Web页面与脚本或编程语言交互的标准接口。它允许JavaScript访问和修改HTML和XML文档的内容、结构和样式。以下是DOM的一些基本概念和操作：
> 1. **节点（Node）**：
>- DOM将文档中的每个对象（元素、属性、文本等）都视为一个节点。
>- 节点有不同的类型，如元素节点、属性节点、文本节点等。
> 2. **元素（Element）**：
>- 元素是构成HTML文档的构建块，每个HTML标签都对应一个元素节点。
>- 元素节点可以包含子节点，比如文本节点或其它元素节点。
>3. **属性（Attribute）**：
> - HTML元素的属性也是节点，可以通过DOM进行访问和修改。
>4. **文本（Text）**：
>- 文本节点包含元素的文本内容。
>5. **DOM树**：
> - DOM将文档表示为树结构，树的每个节点代表文档的一部分。
> - 根节点是文档节点（document），它包含HTML文档的所有内容。
>6. **DOM操作**：
> - **创建新节点**：使用`document.createElement()`创建新元素。
>- **插入节点**：使用`appendChild()`或`insertBefore()`将新节点添加到DOM树中。
>- **删除节点**：使用`removeChild()`从DOM树中移除节点。
>- **查找节点**
   ：使用`getElementById()`, `getElementsByClassName()`, `getElementsByTagName()`, `querySelector()`, `querySelectorAll()`
   等方法查找节点。
>- **修改节点内容**：直接修改节点的属性或使用`textContent`和`innerHTML`属性修改元素的内容。
>7. **事件**：
> - DOM允许你为元素绑定事件处理器，以响应用户操作，如点击、键盘输入等。
>8. **样式**：
>- 可以通过DOM修改元素的样式，使用`style`属性来直接设置CSS样式。
>9. **遍历DOM树**：
>- 使用`parentNode`, `childNodes`, `firstChild`, `lastChild`, `nextSibling`, `previousSibling`等属性遍历DOM树。
>10. **DOM与BOM**：
>- DOM是浏览器提供的接口，用于操作文档。
>- BOM（Browser Object Model）是浏览器提供的另一组接口，用于操作浏览器窗口。
   > 通过DOM，JavaScript能够实现动态的网页内容更新，无需重新加载页面，这为创建交互式和动态的Web应用提供了基础。

常见函数用法用例

1. `getElementsByTagName()`

```angular2html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Title</title>

</head>
<body>
<div>张三</div>
<div>李四</div>
<div>王五😀</div>
<script>
    //getElementsByTagName()
    //document 获取div中的内容，返回类型是数组。
    var elementsByTagName = document.getElementsByTagName(`div`);
    //遍历数组elementsByTagName 用innerText获取其中的文本内容并在控制台打印
    for (let i = 0; i < elementsByTagName.length; i++) {
        console.info(elementsByTagName[i].innerText)
    }
</script>
</body>
</html>

```

## 数据类型

javaScript是一种弱类型语言，其数据类型只有三种分别为：String；Number；Boolean

```javascript
    var num = 123;
    var str = "123";
    //javaScript 中定义boolean数据类型有两种定义方式
    var b1 = flash;
    var b2 = Boolean(flash);
```
ps：特殊用法
1. infinity 、 -infinity JavaScript中有无穷大的表示方式，可以允许除数为零。
2. NaN：代表一个非数值。
3. isNaN：判断一个数据是否为number类型
4. parseInt 将string转换为number时，如果字符串以数字开头，就会返回开头的数字。
## 延时

```javascript
let element = document.getElementById("img-change");
let num = 0

function toBig() {
    // 获取当前的宽度值，去掉'px'并转换为数字
    let currentWidth = parseInt(element.style.width, 10);
    // console.log(currentWidth)
    // 在当前宽度的基础上增加30像素
    let newWidth = currentWidth + 30;
    // 将新的宽度值转换为字符串，并添加'px'单位
    let newWidthString = newWidth + "px";
    // 将新的宽度设置回元素的样式
    element.style.width = newWidthString;
}

function toSmall() {
    // 获取当前的宽度值，去掉'px'并转换为数字
    let currentWidth = parseInt(element.style.width, 10);
    // console.log(currentWidth)
    // 在当前宽度的基础上减少30像素
    let newWidth = currentWidth - 30;
    // 将新的宽度值转换为字符串，并添加'px'单位
    let newWidthString = newWidth + "px";
    // 将新的宽度设置回元素的样式
    element.style.width = newWidthString;
}

function inBig() {
    clearInterval(num)
    num = setInterval(() => {
        toBig()
    }, 1000)
}

function inSmall() {
    clearInterval(num)
    num = setInterval(() => {
        toSmall()
    }, 1000)
}

function inStop() {
    clearInterval(num);
}
```

## 元素的添加 修改 删除


