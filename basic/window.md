# Window对象

## 导航器对象

navigator | 返回
--------- | ----
appCodeName   | 浏览器的代码名
appName       | 浏览器的名称
appVersion    | 浏览器的平台和版本信息
cookieEnabled | 指明浏览器中是否启用cookie的布尔值
platform      | 运行浏览器的操作系统平台
userAgent     | 由客户端发送服务器的user-agent头部的值

## 显示器对象

screen | 返回
------ | ----
availHeight | 显示屏幕的可用高度
availWidth  | 显示屏幕的可用宽度
height      | 屏幕的像素高度
width       | 屏幕的像素宽度
colorDepth  | 屏幕颜色的位数

## 历史对象

history | 返回
------- | ----
back()    | 前一个URL
forward() | 下一个URL
go()      | 某个具体页面

## 位置对象

location属性 | 设置或返回
------------ | ----------
hash     | 从井号(`#`)开始的URL
host     | 主机名和当前URL的端口号
hostname | 当前URL的主机名
href     | 完整的URL
pathname | 当前URL的路径部分
port     | 当前URL的端口号
protocol | 当前URL的协议
search   | 从问好(`?`)开始的URL

location方法 | 功能
------------ | ----
assign(URL)     | 加载新的文档
reload()        | 重新加载当前页面
replace(newURL) | 用新的文档替换当前文档

## 文档对象

document集合 | 返回数组
------------ | --------
anchors[] | 锚点对象
images[]  | 图片对象
links[]   | 链接对象
forms[]   | 表单对象

document属性 | 返回
------------ | ----
cookie   | 设置或返回与当前文档有关的所有cookie
domain   | 当前文档的域名
referrer | 载入当前文档的文档的URL
title    | 当前文档的标题
URL      | 当前文档的URL

document方法 | 功能
------------ | ----
open()    | 打开一个新的文档，并擦除旧文档内容
close()   | 关闭文档输出流
write()   | 向当前文档追加写入文本
writeln() | 与`write()`相同，在`<pre>`中会追加换行

## 窗口控制

语法 | 功能
---- | ----
moveBy(水平位移量,垂直位移量) | 按照给定像素参数移动指定窗口
moveTo(x,y) | 将窗口移动到指定的坐标(x,y)处
resizeBy(水平,垂直) | 将当前窗口改变指定的大小(x,y)<br>当x、y的值大于0时为扩大<br>当x、y的值小于0时为缩小
resizeTo(水平宽度,垂直宽度) | 将当前窗口改变成(x,y)大小，x、y分别为宽度和高度
scrollBy(水平位移量,垂直位移量) | 将窗口中的内容按给定的位移量滚动<br>参数为正数时，正向滚动，否则反向滚动
scrollTo(x,y) | 将窗口中的内容滚动到指定位置

## 焦点控制

- `focus` 得到焦点
- `blur`  移出焦点

## 打开关闭窗口

语法 | 功能
---- | ----
open("URL","窗口名称","窗口风格") | 打开一个新的窗口，并在窗口中装载指定URL地址的网页
close() | 自动关闭浏览器窗口

### 窗口风格

Key | Value | Description
--- | ----- | -----------
height     | 数值   | 窗口高度   不能小于100
width      | 数值   | 窗口宽度   不能小于100
left       | 数值   | 窗口左坐标 不能为负值
top        | 数值   | 窗口上坐标 不能为负值
location   | yes/no | 是否显示地址栏
menubar    | yes/no | 是否显示菜单栏
resizable  | yes/no | 是否可以改变窗口大小
scrollbars | yes/no | 是否允许出现滚动条
status     | yes/no | 是否显示状态栏
toolbar    | yes/no | 是否显示工具栏

## 定时器

语法 | 功能
---- | ----
setTimeout(执行代码,毫秒数) | 当到了指定的毫秒数后，自动执行功能代码
clearTimeout(定时器) | 取消由setTimeout()设置的定时器
setInterval(重复执行的代码,毫秒数) | 按指定周期重复执行功能代码
clearInterval(时间间隔器) | 取消由setInterval()设置的时间间隔器

## 对话框

语法 | 功能
---- | ----
alert("提示字符串") | 弹出一个警告框，在警告框内显示提示字符串文本
confirm("提示字符串") | 显示一个确认框，在确认框内显示提示字符串<br>当用户点击“确定”按钮时该方法返回`true`<br>点击“取消”按钮时返回`false`
prompt("提示字符串","缺省文本") | 显示一个输入框，在输入框内显示提示字符串<br>在输入文本框显示缺省文本，并等待用户输入<br>当用户点击“确定”按钮时，返回用户输入的字符串<br>当点击“取消”按钮时，返回`null`值

## window属性

### 状态栏

- `defaultStatus` 改变浏览器状态栏的默认显示
- `status`        临时改变浏览器状态栏的显示

### 窗口位置

声明 | IE | !IE
---- | -- | ---
窗口的左上角的X坐标 | screenLeft | screenX
窗口的左上角的Y坐标 | screenTop  | screenY
当前文档向右滚动过的像素值 | document.body.screenLeft | pageXOffset
                           | document.documentElement.scrollLeft
当前文档向下滚动过的像素值 | document.body.screenTop | pageYOffset
                           | document.documentElement.scrollTop

FF属性 | 返回
------ | ----
innerHeight | 窗口的文档显示区的高度
innerWidth  | 窗口的文档显示区的宽度
outerHeight | 窗口的外部高度
outerWidth  | 窗口的外部宽度

### 其他属性

- `opener` 可以实现同域名下跨窗体之间的通讯，一个窗体要包含另一个窗口的`opener`
- `closed` 当前窗口关闭时返回`true`
- `name`   设置或返回窗口的名称
- `self`   返回对当前窗口的引用
