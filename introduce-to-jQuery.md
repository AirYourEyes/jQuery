## 一 什么是jQuery
- jQuery是一个JavaScript函数库

## 二 使用jQuery的好处
- jQuery支持CSS1到CSS3绝大多数选择器
- 兼容多种浏览器
- 支持连缀表达式
- 不用显示遍历元素
- 可与其他的框架共同使用

## 三 使用jQuery
1. 到[官网](https://jquery.com/)下载jQuery
2. 在head标签中引入jQuery，格式如下所示：`<script src="jquery-file-path" type="text/javascript"></script>`
3. 将代码编写在`$(document).ready(function(){// your code here});`，可以简写成以下的形式`$(function(){ // your code here});`

## 四 `$(document).ready(function(){});`与`window.onload`之间的区别
- 前者当页面加载完DOM之后即可执行（不必等到页面上的图片均加载完成），而后者需要等到整个页面（包括图片）完全加载
- 前者在页面中可以有多个，而后者只能有一个，若页面上有多个后者，只有最后一个起作用

## 五 原生DOM对象域jQuery对象
### 什么是原生对象
- 直接使用原生JavaScript获取的对象，如使用document的getElementById方法获取指定id的元素
### 什么是jQuery对象
- 使用$()制造出的对象都是jQuery对象
### 原生对象域jQuery对象之间的转换
- 使用`$()`将原生对象封装成jQuery对象
```jQuery
var box = document.getElementById("box");
$(box);                                 //将原生box对象封装成jQuery对象
```
- 通过中括号或者get方法获取原生对象
```jQuery
$(".box")[0];
等价于
$(".box").get(0);
```
### 注意事项：
- 原生对象不能使用jQuery对象中的属性与方法，反过来也一样

## 六 解决jQuery和其他库的冲突
### 冲突原因：
- 在jQuery中，$等价与jQuery对象
- 在其他库中，如prototype，也可能使用了$作为对象的简写，此时两个库产生了冲突

### jQuery库在其他库之后导入
- 此时jQuery拥有对$的控制权
- 可调用jQuery.noConfict()函数将对变量$的控制权交给其他的库，之后在需要使用jQuery的地方直接使用jQuery对象，即可解决冲突

### jQuery库在其他库之前导入
- 无需调用jQuery的noConflict方法
- 在需要使用jQuery的地方直接使用jQuery对象即可
