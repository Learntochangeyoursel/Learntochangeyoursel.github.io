## 1. 简介

解释型语言，简单弱类型脚本语言，相对安全的脚本语言，依赖于浏览器本身，可以实现跨平台；是一种为网站添加互动以及自定义行为的客户端脚本语言。

### 2. 常见用法

一般引入写在文件末尾

## 3. 模块

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

## 4. 基本语法

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

## 5. DOM 获取

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

## 6. 数据类型

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

## 7. 延时和定时操作

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

## 8. 解构赋值

通俗易懂来讲就是在数据类型相同的情况下，名字相同就可以取出对应的值，可以理解为类比。

## 方法

定义方法的两种形式：

```javascript
function fun() {

}

//箭头函数
() => {

}
```

## 9. fetch

JavaScript 中处理响应的方法，代码示例

```javascript
fetch('url')
    //处理键值对数据
    .then(resp => {
        resp.json()
    })
    .then(date => {
        console.info("date")
    })
    .catch(erro => {
        console.error("error")
    });
```

## 10. 函数默认值

为函数设置默认值，避免因出现`unfinde`导致程序出错的情况

```javascript
//可以与解构赋值一起调用
function fun(x = 5) {
    console.info(x) //5
    x = 6
    console.info(x) //6
}
```

## 11. object类

两个比较运算符的区别

1. == 会自动转换数据类型
2. === 不会自动转换数据类型但是会出现 `-0 = +0`;NaN不等于自身。

Object.assign()用于对象合并，将源对象所有的可枚举属性复制到目标对象，第一个参数时目标对象，所有的参数对象都是源对象。

## 12. 变量的作用域

常用 `let` var 会造成变量提升

## 13. 对象

内置对象

常用的内置对象

1. Math.random()

```javascript
let num = Math.random() //返回一个0-1的随机数，左闭右开。
num.abs()   //返回一个数的绝对值
num.ceil()  //向上取整
num.floor() //向下取整
num.round() //四舍五入
num.pow()   //返回指定数的次幂
```

2. Date 处理的时格林时

```javascript
getFullYear()   //返回月份
getMonth()      //返回月份 0-11 0表示1月
getDate()       //返回月份日期
getDay()       //返回星期几 0-6 0表示星期一
getHours()     //返回小时 0-23 0表示凌晨12点
getMinutes()    //返回分钟
getSeconds()    //返回秒
getMilliseconds()   //返回毫秒
getTime()       //返回时间戳
```

## 14. 常用的交互事件

- 普通元素

1. onclick 鼠标点击事件
2. onmouseenter 鼠标进入事件
3. onmouseleave 鼠标离开事件

- 表单元素

1. onfocus //获得焦点
2. onblur //失去焦点
3. oninput //文本内容发生变化

- 键盘事件

## 15. 元素的添加 修改 删除

- 添加元素

```javascript
document.createElement() //创建新的 element 节点
node.appendChild()      //见创建好的节点同步网页
```

- 修改元素

```javascript
object.setAttribute()(attribute, value)  //设置元素属性
document.getElementById("id").style     //可获取元素在style中写的样式
```

- 删除元素

```javascript
removeChild()       //根据父节点删除子节点的元素
```

## 16. Web Storage

- storage 对象在创建时会有一个相应的键值对列表进行访问，属性方法具体如下：

1. length：返回当前对象保存键值对的数量；
2. key(index)：返回第(index)个key的名称；
3. getItem(key)：返回当前key对应的值；
4. removeItem(key)：根据key删除storage中的元素；
5. setItem(key,value)：先检测storage中是否存在该键值对列表是否存在，没有就添加，key存在就更新；
6. clear()：清空键值对的内容

## 17. 数组常用操作

- 添加

```javascript
// push unshift
let arr = [1, 2, 3];
arr.push(4, 5);
console.info(arr);      //[1,2,3,4,5]
arr.unshift(4, 5);
console.info(arr);       //[4,5,1,2,3,4,5]
```

- 删除

```javascript
//pop()删除数组最后一个元素
let arr = [1, 2, 3];
arr.pop();
console.info(arr);      //1，2
//shift 删除数组第一个元素
arr.shift();
console.info(arr);      //[2]
```

- 从数据中连续删除和插入数据

```javascript
//splice(1,2,3),1:起始下标，2：连续删除多少项，3：插入的数据(为0则不插入)，返回不删除的元素。
let arr = [1, 2, 3];
arr.splice(1, 1, "2") //在数组中下标为1开始添加1项元素，添加的内容为"2"
console.info(arr);  //[1,"2",2,3]
arr.splice(1, 1);    //从数组中下标为1开始删除1项元素
console.info(arr); //[1,2,3]
```

- 数组串联

```javascript
//join() 把数组中所有元素放入一个字符串中并返回一个字符串
let arr = [1, 2, 3];
console.info(arr.join("+"))     //1+2+3
```

- 数组排序

```javascript
//sort() 对数组元素进行排序
let arr = [20,120,38,15,64];
console.info(arr.sort());       // [15, 120, 20, 38, 64] 是将arr中的元素转换为Unicode码进行转换。
// 若想按照升序排序，需要添加一个比较函数
console.info(arr.sort((a,b)=>(a-b)))    //[15, 20, 38, 64, 120]
//字符串直接使用sort()进行排序，反序用reverse().
```

- 数组拆分与合并

```javascript
//slice(starting-Index,end-Position)
```