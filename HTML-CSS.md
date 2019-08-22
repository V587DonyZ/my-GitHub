# HTML知识



## 1. html概念

```html
html全称HyperText Markup Language，翻译为超文本标记语言，它不是一种编程语言，是一种描述性的标记语言，用于描述超文本内容的显示方式。比如字体、颜色、大小等。

超文本：音频，视频，图片称为超文本。
标记 ：<英文单词或者字母>称为标记，一个HTML页面都是由各种标记组成。
作用：HTML是负责描述文档语义的语言。

注意：HTML语言不是一个编程语言(有编译过程)，而是一个标记语言(没有编译过程)，HTML页面直接由浏览器解析执行。
 
HTML只是负责描述文档语义的语言,在html中，除了语义，其他什么都没有。
```

## 2. 网络术语

```html
网页 ：由各种标记组成的一个页面就叫网页。
主页(首页) : 一个网站的起始页面或者导航页面。
标记： <p>称为开始标记 ，</p>称为结束标记，也叫标签。每个标签都规定好了特殊的含义。
元素：<p>内容</p>称为元素.
属性：给每一个标签所做的辅助信息。
```

## 3. HTML规范

```html
HTML是一个弱势语言
区分大小写
页面的后缀名是html或者htm(有一些系统不支持后缀名长度超过3个字符，比如dos系统)
HTML的结构：
    声明部分：主要作用是用来告诉浏览器这个页面使用的是哪个标准。是HTML5标准。
    head部分：将页面的一些额外信息告诉服务器。不会显示在页面上。
    body部分：我们所写的需要显示出来的代码必须放在此标签內。
```

编写规范

```html
1. 所有标记元素都要正确的嵌套，不能交叉嵌套。正确写法举例：<h1><font></font></h1>
2. 所有的标记都必须小写。
3. 所有的标记都必须关闭。
    双边标记：<span></span>
    单边标记：<br> 转成 <br /> <hr> 转成 <hr />，还有<img src=“URL” />
4. 所有的属性值必须加引号。<h1 id="head"></h1>
5. 所有的属性必须有值。<input type="radio" checked="checked" />
```

HTML基本语法特征

```
1. html对换行,tab不敏感
2. 空白折叠现象
3. 标签要严格封闭
```

## 4. HTML结构

```html
<!doctype html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport"
          content="width=device-width, user-scalable=no, initial-scale=1.0, maximum-scale=1.0, minimum-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>Document</title>
</head>
<body>

</body>
</html>
```





------



# head

## 1. 文档声明头

```html
<!DOCTYPE html> 是一个声明，表示该文档是由 HTML5 进行编写的。
<!DOCTYPE> DocType Declaration，简称DTD,声明必须是 HTML 文档的第一行，位于 <html> 标签之前。
<!DOCTYPE> 声明，这样可告知浏览器文档使用哪种 HTML 或 XHTML 规范。
```

## 2. head  头标签

```html
<head> 标签用于定义文档的头部，它是所有头部元素的容器。
这些标签可用在 head 部分：<base>, <link>, <meta>, <script>, <style>，<title>。
    
<base> : 用来设置一个基准 URL，让 HTML 文档中的相对链接在此基础上进行解析。  
<link>：定义文档与外部资源的关系,最常见的用途是链接样式表。
<meta>：标签用于描述页面内容，关键词，作者，最新修订时间以及其它元信息。
<script> : 标签用于在 HTML 文档中加入脚本（例如 JavaScript）   
<style>:定义内部样式表与网页的关系
<title>：指定整个网页的标题，在浏览器最上方显示。
```

#### base

```html
<base> : 用来设置一个基准 URL，让 HTML 文档中的相对链接在此基础上进行解析。  
<base> 标签必须位于 <head> 标签内部，并尽量靠前，以便随后的元素中的相对 URL 可以用上其设置的基准 URL。
```

| 属性   | 值                                      | 描述                                                         |
| ------ | --------------------------------------- | ------------------------------------------------------------ |
| href   | URL                                     | 指定该 HTML 文档中所有相对链接的基准 URL。                   |
| target | _blank、_parent、_self、_top、framename | 指定在何处打开超链接。 _blank：在新窗口中打开 _parent：在当前的父窗口中打开，如果不存在父窗口，此选项的行为方式与 _self 等同 _self：当前窗口打开（默认） _top：在整个窗口中打开 framename：在指定的框架中打开 |

实例

```html
<!doctype html>
<html lang="zh_cn">
<head>
    <base href="../img/" target="_blank">
    <meta charset="UTF-8">
    <title>标题</title>
</head>
<body>
    <img src="壁纸.jpg"><br>
    <p><a href="http://www.baidu.com">百度一下</a></p>
    <p>请注意，链接会在新窗口中打开，即使链接中没有 target="_blank" 属性。<br>这是因为 base 元素的 target 属性已经被设置为 "_blank" 了。</p>
</body>
</html>
```

#### b. link

```html
<link>：定义文档与外部资源的关系,最常见的用途是链接样式表。
link 元素定义了 6 个属性，其中 rel 属性是必选的，它说明了当前文档与被链接资源之间的关系。
```

| 属性                                                        | 值                                                           | 描述                                     |
| ----------------------------------------------------------- | ------------------------------------------------------------ | ---------------------------------------- |
| href                                                        | URL                                                          | 指定被链接资源的 URL。                   |
| hreflang                                                    | language_code                                                | 指定被链接资源使用的语言。               |
| sizes                                                       | HeightxWidth                                                 | 指定图标的大小（比如 `sizes="16x16"`）。 |
| [`media`](https://man.ilovefishc.com/pageHTML5/media1.html) | media_query                                                  | 指定被链接的资源将被显示到什么设备上。   |
| [`rel`](https://man.ilovefishc.com/pageHTML5/rel.html)      | alternate、author、help、icon、licence、next、pingback、prefetch、prev、search、sidebar、stylesheet、tag | 指定当前文档与被链接资源之间的关系。     |
| [`type`](https://man.ilovefishc.com/pageHTML5/type1.html)   | MIME_type                                                    | 规定被链接文档的 MIME 类型。             |

实例

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>这是标题</title>
    <link rel="stylesheet" type="text/css" href="css3.css" >
</head>
<body>
    <h1>我通过外部样式表进行格式化。</h1>
    <p>我也一样！</p>
</body>
</html>


放在同级目录css文件内的fishc.css:
body{
    color: green;
}
```

## 3. meta

```html
<meta>：标签用于描述页面内容，关键词，作者，最新修订时间以及其它元信息。
标签的内容不会显示在网页中，但经常被机器（比如网页爬虫）解析。针对搜索引擎和更新频度的描述和关键词。
```

```html
content 属性必须和 name 或 http-equiv 属性共存亡。
为了让网页尺寸实现自适应，你应该在 HTML 文档中加入下面代码：
<meta name="viewport" content="width=device-width, initial-scale=1.0">
```

| 属性       | 值                                                           | 描述                                                         |
| ---------- | ------------------------------------------------------------ | ------------------------------------------------------------ |
| charset    | character_set                                                | 指定 HTML 文档的编码。                                       |
| content    | text                                                         | 指定与 `http-equiv` 或 `name` 属性相关的值。                 |
| http-equiv | content-type、default-style、refresh                         | content-type：另一种声明 HTML 文档作用字符编码的方法（`<meta http-equiv="content-type" content="text/html charset=UTF-8">`）。 default-style：指定页面优先使用的样式表。 refresh：以秒为单位指定一个时间间隔，在此时间过去之后将从服务器重新载入当前页面。也可以另行指定一个 URL 让浏览器载入。 |
| name       | application-name、author、description、generator、keywords、viewport | application-name：当前页所属 Web 应用系统的名称。 author：当前页的作者名。 description：当前页的内容描述。 generator：用来生成 HTML 的软件名称。 keywords：当前页的关键词。 viewport：网页尺寸自适应。 |

实例

实例一 : 指定网页编码

```html
<meta charset="UTF-8">
<meta http-equiv="Content-Type" content="text/html;charset=utf-8" />
```

实例二：为搜索引擎提供关键词

```html
<meta name="keywords" content="网页前端学习">
```

实例三：描述网页内容

```html
<meta name="description" content="这是一个学习前端html的网页">
```

实例四：定义网页的作者

```html
<meta name="author" content="donyz">
```

实例五：设置网页尺寸自适应

```html
<meta name="viewport" content="width=device-width, initial-scale=1.0">
```

实例六：每 5 秒刷新一下浏览器并跳转到指定页面

```html
<meta http-equiv="refresh" content="5;http://baidu.com">
```





------



# body

## 1. 输入框

```html
1. <input type="text" value="默认内容" >	// 实色文字,可以删除
2. <input type="text"  placeholder="请输入用户名">	//提示信息半透明,且光标到输入框提示信息消失
3. <input type="password" placeholder="请输入密码">	//密文显示
4. <input type="date">	// 选择日期
5. <input type="color">	//选择颜色
6. <input type="file" >	//选择文件
7. <input type="checkbox">	//复选框
8. <input type="radio">	// 单选框
```

## 2. a标签

```html
1. <a href="#">百度一下</a>	// 跳转到当前页面
2. <a href="http://baidu.com" title="这是百度链接">百度一下</a>	// title 鼠标移动到文字提示的内容
```

```html
图片链接到网址
<a href="http://baidu.com" title="这是百度链接">
    <img src="https://wx2.sinaimg.cn/mw690/9b6feba7ly1g5l6z42v5zj24lz3gg1l1.jpg" alt="章若楠">
</a>
```

```html
<a href="http://baidu.com" title="这是百度链接" target="_blank">百度一下</a>	// 
新标签打开 : _blank
```

**target 属性**

| 值          | 描述                                 |
| :---------- | :----------------------------------- |
| _blank      | 在新窗口中打开被链接文档。           |
| _self       | 默认。在相同的框架中打开被链接文档。 |
| _parent     | 在父框架集中打开被链接文档。         |
| _top        | 在整个窗口中打开被链接文档。         |
| *framename* | 在指定的框架中打开被链接文档         |

## 3. 锚点跳转

```html
<body>
    <a href="#middle">中间</a>
    <a href="#finally">末尾</a>
    
    <p id="middle">这是中间部分</p>
    <hr>
    <p id="finally">这是尾部部分</p>
</body>
```

**tips**

```
随机生成内容:
lorem + 想要生成内容的字数   tab后生成英文内容
```

## 4. 媒体

### audio 音频

```html
方式一 :
<audio src="audio/爱的就是你-刘佳.mp3" controls='controls'>浏览器不支持</audio>
controls 声音控制, 如果浏览器不支持则会显示后面的文字
方式二 :
    <audio controls='controls'>
        <source src="audio/爱的就是你-刘佳.mp3">  <!-- 只播放第一个 -->
        <source src="audio/斧头舞.mp4">
    </audio>
```

###  背景音乐

```html
<audio src="http://music.163.com/song/media/outer/url?id=518076141.mp3" autoplay="autoplay" loop="loop">
```

| 属性                                                         | 值       | 描述                                                         |
| :----------------------------------------------------------- | :------- | :----------------------------------------------------------- |
| [autoplay](https://www.w3school.com.cn/tags/att_audio_autoplay.asp) | autoplay | 如果出现该属性，则音频在就绪后马上播放。                     |
| [controls](https://www.w3school.com.cn/tags/att_audio_controls.asp) | controls | 如果出现该属性，则向用户显示控件，比如播放按钮。             |
| [loop](https://www.w3school.com.cn/tags/att_audio_loop.asp)  | loop     | 如果出现该属性，则每当音频结束时重新开始播放。               |
| [muted](https://www.w3school.com.cn/tags/att_audio_muted.asp) | muted    | 规定视频输出应该被静音。                                     |
| [preload](https://www.w3school.com.cn/tags/att_audio_preload.asp) | preload  | 如果出现该属性，则音频在页面加载时进行加载，并预备播放。如果使用 "autoplay"，则忽略该属性。 |
| [src](https://www.w3school.com.cn/tags/att_audio_src.asp)    | *url*    | 要播放的音频的 URL。                                         |

### video 视频

```html
<video src="video/斧头舞.mp4" controls='controls'height="360px";width="540x">浏览器不支持</video>
```

| 属性                                                         | 值       | 描述                                                         |
| :----------------------------------------------------------- | :------- | :----------------------------------------------------------- |
| [autoplay](https://www.w3school.com.cn/tags/att_video_autoplay.asp) | autoplay | 如果出现该属性，则视频在就绪后马上播放。                     |
| [controls](https://www.w3school.com.cn/tags/att_video_controls.asp) | controls | 如果出现该属性，则向用户显示控件，比如播放按钮。             |
| [height](https://www.w3school.com.cn/tags/att_video_height.asp) | *pixels* | 设置视频播放器的高度。                                       |
| [loop](https://www.w3school.com.cn/tags/att_video_loop.asp)  | loop     | 如果出现该属性，则当媒介文件完成播放后再次开始播放。         |
| [muted](https://www.w3school.com.cn/tags/att_video_muted.asp) | muted    | 规定视频的音频输出应该被静音。                               |
| [poster](https://www.w3school.com.cn/tags/att_video_poster.asp) | *URL*    | 规定视频下载时显示的图像，或者在用户点击播放按钮前显示的图像。 |
| [preload](https://www.w3school.com.cn/tags/att_video_preload.asp) | preload  | 如果出现该属性，则视频在页面加载时进行加载，并预备播放。如果使用 "autoplay"，则忽略该属性。 |
| [src](https://www.w3school.com.cn/tags/att_video_src.asp)    | *url*    | 要播放的视频的 URL。                                         |
| [width](https://www.w3school.com.cn/tags/att_video_width.asp) | *pixels* | 设置视频播放器的宽度。                                       |

## 5. 列表

### 有序/无序列表

```html
    <ul>
        <li>无序列表</li>
        <li>无序列表</li>
    </ul>

    <ol>
        <li>有序列表</li>
        <li>有序列表</li>
    </ol>

	<ol start="10" reversed type="I">  <!--倒叙-->
        <li>有序列表</li>
        <li>有序列表</li>
    </ol>
```

有序列表

| 属性     | 值                            | 描述                             |
| -------- | ----------------------------- | -------------------------------- |
| reversed | reversed                      | 规定列表顺序为降序。(9, 8, 7, …) |
| start    | number                        | 规定有序列表的起始值。           |
| type     | 1、A、a、I、i、suqare、circle | 规定在列表中使用的标记类型。     |

### 定义列表

 **dt dl dd**

```html
<dt> 标签用于定义列表中的项目（即术语部分）。
<dl> 标签定义了一个包含术语定义以及描述的列表。
<dd> 标签用于定义列表中项目的描述部分。
```

**实例**

```html
<body>
    <h2>一个定义列表：</h2>
    <dl>
        <dt>计算机</dt>
        <dd>用来计算的仪器 ... ...</dd>
        <dt>显示器</dt>
        <dd>以视觉方式显示信息的装置 ... ...</dd>
    </dl>
</body>
模拟显示效果:
计算机
	用来计算的仪器.. ...
显示器
	以视觉方式显示信息的装置 ... ...
```

## 6.表单标签 

```html
<body>
    <form action="http://127.0.0.1:9966">   <!--提交的服务器地址和端口-->
        <label>用户名</label>
        <input type="text" id="user" placeholder="请输入用户名">
        <br>
        <br>
        <label>密 码</label>
        <input type="password" placeholder="请输入密码">
        <br>
        <br>
        <label>性①别</label>   <!--下拉选择-->
        <select name="sex">
            <option value="男">男</option>
            <option value="女">女</option>
        </select>
        <br>
        <br>
        <label>性②别</label>   <!--单选-->
        <input type="radio" name="sex" value="1">男
        <input type="radio" name="sex" value="2">女
        <br>
        <br>
        <input type="checkbox" name="hobby" value="1">唱
        <input type="checkbox" name="hobby" value="2">跳
        <input type="checkbox" name="hobby" value="3">rap
        <br>
        <br>
        <label>个人介绍</label>
        <textarea name="info" id="" cols="30" rows="10"></textarea>
        <br>
        <br>
        <input type="hidden">    <!--隐藏-->
        <input type="date">     <!--选择日期-->
        <input type="file">     <!--文件上传-->
        <input type="submit" value="提交">
        <input type="reset">    <!--重置-->
        <br>
        <br>
        <!-- for属性,点击lable中的内容,让for标示的id对应的元素获得焦点-->
        <label for="use">用户名</label>
        <input type="text" name='username' id="use" >
    </form>
```

## 7. 样式(CSS)/节

### 1.  导入css

方式一 : 行内引入

```css
<body>  
    <div style ='color:red'>asdfg</div>
</body>
```

方式二 : 内联引入

```css
<head>
	<style>
        div{
            color:aqua;
        }
    </style>
</head>
<body>  
    <div>asdfg</div>
    <div>asdfg</div>
</body>
```

方式三 : 外链引入

```css
<!doctype html>
<html lang="en">
<head>
    <link rel="stylesheet" href="index.css">
</head>
<body>
    <div>asdfg</div>
</body>
</html>


index.css :
div{
    color: darkorange;
}
```

方式四 : 导入式

```css
<head>
    <style>
        @import "index.css";
		/*@import url("index.css");*/
    </style>
</head>
<body>
    <div>asdfg</div>
</body>
```

### 2. 节标签

#### div-独占一行

#### span

### 3. 语义化标签

```html
<header>	//对主页的介绍
<section>	//文档中的区段
<footer>	//文档中的页脚部分
<arcticle>	//文档的内容
<nav>		// 标签定义导航链接的部分。
```

## 8. 设置浏览器标签图标

### favicon.ico

```css
1. favicon.ico一般用于作为缩略的网站标志，它显示在浏览器的地址栏、浏览器标签上或者在收藏夹上，是展示网站个性的缩略logo标志
2. favicon.ico也可以说是网站头像,目前主要的浏览器都支持favicon.ico图标，如果要让网站看起来更专业、更美、更有个性，favicon.ico是必不可少的
```

### 在线制作

```
http://www.faviconico.org/
```

### 设置图标

```css
方式1. 将制作好的图片放到项目的根目录
方式2. 在head当中添加以下标签图标:
	在<head>加:
	 <link rel="shortcut icon" href="favicon.ico" type="image/x-icon">
```

## 9. 清除网页外边距

```html
<body style="margin: 0;">
```





------



# CSS

## 1. 引入方式

```css
行内样式 style="color:red;height:200px"
内接样式 
<style>
  div{
      color:red;
  }
</style>
外接样式1.(链接式,导入式)
	<link href='xxxx.css'>
	<link rel="stylesheet" href="index.css">
外接样式2.
	<style>
		@import url('地址')
	</style>
```

## 2. 选择器

```
什么是选择器 :
	对指定的标签设置样式，要把指定的标签选择出来
```

### 2.1 通用选择器

```css
通用选择器，可以同时选中页面中的所有元素。
`语法
*{ }
```

### 2.2 标签选择器

```css
<style>
	div{
	color: darkorange;
        }
</style>
```

### 2.3  类选择器

```css
    <style>
        .div{	/* 用点'.'+类名引用	*/
            color: darkorange;
        }
        .div1{	
            color: orange;
            font-size: 100px;
        }
    </style>
</head>
<body style="margin: 0;">
    <div class="div">设置类选择器01</div>	/* div是类名 */
    <div class="div div1">设置类选择器02</div>  /* 一个标签可以设置多个类名 */
	<div class="div1">设置类选择器03</div>
</body>
```

### 2.4 ID选择器

**ID是唯一的**

```css
    <style>
        #div1{
            font-size: 100px;
            background-color:darkturquoise;
        }
        #div2{
            color: greenyellow;
		   font-weight: bold;
        }
    </style>
</head>
<body style="margin: 0;">
    <div id="div1">设置ID选择器01</div>
    <div id="div2">设置ID选择器02</div>
</body>
```

### 2.5 复合选择器

```css
    <style>
        div.test1{
            font-size: 50px;
        }
        p.test2{
            color: #f30c65;
        }
    </style>

</head>
<body style="margin: 0;">
    <div class="test1">这个是div标签01</div>
    <div>这个是div标签02</div>
    <hr>
    <p>这是p段落标签1</p>
    <p class="test2">这是p段落标签2</p>
    <hr>
    <span class="test3">这是span标签01</span>
    <span>这是span标签02</span>
</body>
```

### 2.6 群组选择器

**群组选择器，可以同时使用多个选择器，多个选择器将被同时应用指定的样式。**

```css
        div, span,p{
            background-color: #deff3b;
        }
    </style>

</head>
<body style="margin: 0;">
    <div class="test1">这个是div标签01</div>
    <div>这个是div标签02</div>
    <hr>
    <p>这是p段落标签1</p>
    <p class="test2">这是p段落标签2</p>
    <hr>
    <span class="test3">这是span标签01</span>
    <span>这是span标签02</span>
</body>
```

### 2.7 后代选择器

```css
    <style>
       #main p{			/* 只找main下p标签这一层  */
           color: #ff5a17;
       }
    </style>
</head>
<body style="margin: 0;">
    <div id="main">
        <p>div中的p标签		/* 变 */
        <div>div-p-div标签</div>  /* 不变 */
        </p>
        <span>
            <div><p>span中的p标签</p></div>  /* 变 */
        </span>
    </div>
    <p>外面的p标签</p>		/* 不变 */
</body>
```

### 2.8 直接后代选择器

```css
    <style>
       #main>p{			/* 只找main下的第一层p */
           color: #ff5a17;
       }
    </style>
</head>
<body style="margin: 0;">
    <div id="main">
        <p>div中的p标签
        <div>div-p-div标签</div>
        </p>
        <span>
            <div><p>span中的p标签</p></div>
        </span>
    </div>
    <p>外面的p标签</p>
</body>
```

### 2.9 兄弟选择器

**拿到下面的一个元素**

```css
    <style>
       div+p{
           color: #ff5a17;
       }
    </style>
</head>
<body style="margin: 0;">
    <p>批标签</p>
    <p>批标签</p>
    <div></div>
    <p>皮标签</p>		/* 变色 */
    <p>皮标签</p>
</body>
```

**查找下面的所有兄弟**

```css
    <style>
       div~p{
           color: #ff5a17;
       }
    </style>
</head>
<body style="margin: 0;">
    <p>批标签</p>
    <p>批标签</p>
    <div></div>
    <p>皮标签</p>	/* 变色 */
    <p>皮标签</p>	/* 变色 */
</body>
```

### 2.10 属性选择器

```css
属性选择器可以挑选带有特殊属性的标签 :
[属性名]
[属性名="属性值"]
[属性名~="属性值"]
[属性名|="属性值"]
[属性名^="属性值"]
[属性名$="属性值"]
[属性名*="属性值"]
```

```css
    <style>
       p[name_p]{
           color: #ff5a17;
       }
    </style>
</head>
<body style="margin: 0;">
    <p name_p="pp">批标签</p>	/* 变色 */
    <p name_p="ss">皮标签</p>	/* 变色 */
    <p>皮标签</p>
</body>
```

```css
    <style>
       p[name_p='ss']{
           color: #ff5a17;
       }
    </style>
</head>
<body style="margin: 0;">
    <p name_p="pp">批标签</p>
    <p name_p="ss">皮标签</p>	/* 变色 */
    <p>皮标签</p>
</body>
```

```css
    <style>
       p[name_p][age_p]{
           color: #ff5a17;
       }
    </style>
</head>
<body style="margin: 0;">
    <p name_p="pp" age_p="18">批标签</p>	/* 变色 */
    <p name_p="ss">皮标签</p>
    <p>皮标签</p>
</body>
```

### 2.11 伪类和伪元素

```css
":after" 伪元素可以在元素的内容之后插入新内容 :
在每个 <h1> 元素后面插入一幅图片：
h1:after
  {
  content:url(logo.gif);
  }
```

```css
":before" 伪元素可以在元素的内容前面插入新内容 :
在每个 <h1> 元素前面插入一幅图片：
	h1:before
  {
  content:url(logo.gif);
  }
```



```
"first-line" 伪元素用于向文本的首行设置特殊样式。
"first-letter" 伪元素用于向文本的首字母设置特殊样式：
```

```
注释："first-letter" 伪元素只能用于块级元素。
注释：下面的属性可应用于 "first-letter" 伪元素：
font   color   background   margin   padding   border   text-decoration
vertical-align(仅当loat为none时)   text-transform
line-height   float   clear
```

```css
    <style>
       p:first-line{
           color: #ff5a17;
       }
    </style>
</head>
<body style="margin: 0;">
    <p >批标签中华人民共和国</p>	/* 第一个字变色 */
    <p >皮标签中华人民共和国</p>	/* 第一个字变色 */
    <p>皮标签中华人民共和国</p>	/* 第一个字变色 */
</body>
```

### 2.12. hover 选择器

**选择鼠标指针浮动在其上的元素，并设置其样式：**

```css
a:hover
{ 
background-color:yellow;
}
```

### 2.13. focus 选择器

**选择获得焦点的输入字段，并设置其样式：**

```css
    <style>
        input:focus{
            width: 500px;
            height: 50px;
            background-color:yellow;
        }
    </style>
</head>
<body style="margin: 0;">
    <input type="text">
</body>
```

### 2.14. 否定伪类

**否定伪类可以帮助我们选择不是其他标签的某个标签。**

```
比如div:not(.box)表示选择所有的div元素但是class为box的除外。
```

### 2.15. 序号选择器

#### 1. 不区分类型

```
:first-child	选中同级别中第一个标签
:last-child		选中同级别中最后一个标签
:nth-last-child(n)	选中同级别中倒数第n个标签
:nth-child(n)	选中同级别中第n个标签
:only-child		选中同级别中唯一子元素标签
```

```css
    <style class="">
        li:nth-child(odd){
            color:aqua;
        }
    </style>
</head>
<body>
    <ul class="">
        <li class="">1</li>
        <li class="">2</li>
        <li class="">3</li>
        <li class="">4</li>
        <li class="">5</li>
        <li class="">6</li>
        <li class="">7</li>
    </ul>
```



#### 2. 区分类型

```
:first-of-type
		选中同级别中同类型第一个标签
:last-of-type
		选中同级别中同类型最后一个标签
:nth-of-type(n)
		选中同级别中同类型第n个标签
:nth-last-of-type(n)
		选中同级别中同类型倒数第n个标签
:only-of-type
		选中同级别中唯一同类型子元素标签
```

#### 3. 奇偶选择

```
:nth-child(odd)
		选中级别中所有奇数
:nth-child(even)
		选中同级别中所有的偶数
:nth-child(xn+y)
		x,y是用户自定义的 n为计数器,从0开始递增选择,  到元素的总个数停止
```



------



## 3. html标签分类

### 3.1块元素

**特点**

```css
1. 自己单独占一行，就像一个段落
2. 能随时设置宽度和高度
```

**常见块元素**

```
ul	li	form	h1-h6	hr	p	div
```

### 3.2. 内联(行内)元素

**特点**

```css
1. 不会自己独立占一行，就好像一个单词，一直往后排
2. 宽度(width)、高度(height)、内边距的top/bottom(padding-top/padding-bottom)和外边距的top/bottom(margin-top/margin-bottom)都不可改变
```

**常见内联元素**

```
a  br	em	img	label	span
```

### 3.3. 内联(行内)-块级元素

**特点**

```css
1. 多个内联(行内)-块级元素可以在一行
2. 能设置宽度和高度
```

**常见块级元素**

```
input	select	textarea
```

### 3.4.  块元素与内联元素相互转换

**把内联 (行内) 元素转成块元素**

```
display:block  -- 显示为块级元素
display:none -- 隐藏
```

**把块元转成内联 (行内) 元素**

```
display:inline  -- 显示为内联元素
display:none -- 隐藏
```

**转为内联块元素**

```
dipslay:inline-block -- 显示为内联块元素，表现为同行显示并可修改宽高内外边距等属性
```

## 4. 盒子模型

- 网页上的每一个标签就是一个盒子
- 每一个盒子都有四个属性

### 4.1 内容 - content

- 盒子里装的东西 - 网页中通常是指文字和图片

- | 属性       | 描述               |
  | ---------- | ------------------ |
  | height     | 设置元素高度       |
  | max-height | 设置元素的最大高度 |
  | min-height | 设置元素的最下高度 |
  | width      | 设置元素宽度       |
  | max-width  | 设置元素的最大宽度 |
  | min-width  | 设置元素的最小宽度 |

### 4.2 填充 (padding,内边距)

- padding 是盒子与内容之间的距离

- | 属性           | 描述               |
  | -------------- | ------------------ |
  | padding-top    | 设置元素的顶内边距 |
  | padding-right  | 设置元素的右内边距 |
  | padding-bottom | 设置元素的下内边距 |
  | padding-left   | 设置元素的左内边距 |

  

- ```css
  设置上右下左内边距分别为 :10px 5px 15px 20px
  padding : 10px 5px 15px 20px
  ```

- ```css
  设置上下内边距都为10px,左右内边距都为5px :
  padding : 10px 5px
  ```

- ```css
  设置上边距10px , 左右内边距5px , 下边距15px
  padding : 10px 5px 15px
  ```

- ```css
  设置四个内边距都是10px
  padding : 10px
  ```

- 

### 4.3. 边框 - border :盒子本身

**border 简写属性在一个声明设置所有的边框属性。**

| 值             | 描述                                                         |
| :------------- | :----------------------------------------------------------- |
| *border-width* | 规定边框的宽度。(px)  可以这样 :border-width:20px 10px 20px 10px ; |
| *border-style* | 规定边框的样式。<br />点线 ：dotted ；        <br />实线 ：solid ； <br />双实线 ： double  ；<br />虚线 ：dashed <br />可以这样 ：border-style:dotted solid double dashed; |
| *border-color* | 规定边框的颜色。可以这样 ：border-color:red green blue pink; |
| inherit        | 规定应该从父元素继承 border 属性的设置。                     |

| 值                     | 描述                                        |
| ---------------------- | ------------------------------------------- |
| border-top             | 设置元素的上边框                            |
| border-right           | 设置元素的右边框                            |
| border-bottom          | 设置元素的下边框                            |
| border-left            | 设置元素的左边框                            |
| border-radius          | 设置边框圆角    50% 为圆形  数值px 或 数值% |
| border-top-left-radius | 设置左上角圆角   数值px 或 数值%            |

```css
可以这样 :
border:fuchsia dashed 5px;

width: 200px;
height:200px;
border:fuchsia solid 10px;
border-top-left-radius: 50%;
border-bottom-right-radius:50%;
```

### 4.2 边界 - margin  : 外边界

**盒子之间的距离称为margin**  - 从边框开始往外的距离

| 属性          | 描述                           |
| ------------- | ------------------------------ |
| margin        | 在一个声明中设置所有外边距属性 |
| margin-top    | 设置元素的上外边距             |
| margin-right  | 设置元素的右外边距             |
| margin-bottom | 设置元素的下外边距             |
| margin-left   | 设置元素的左外边距             |

```css
设置上右下左外边距分别是 :10px 5px 15px 20px;
margin:10px 5px 15px 20px;
```

```css
设置上10px , 左右5px , 下15px
margin : 10px 5px 15px
```

```css
设置上下10px , 左右5px
margin : 10px 5px
```

```css
设置所有外边距都为10px
margin : 10px
```

## 5. 浮动 - float

**在 CSS 中，任何元素都可以浮动。浮动元素会生成一个块级框，而不论它本身是何种元素。**

| 值      | 描述                                                 |
| :------ | :--------------------------------------------------- |
| left    | 元素向左浮动。                                       |
| right   | 元素向右浮动。                                       |
| none    | 默认值。元素不浮动，并会显示在其在文本中出现的位置。 |
| inherit | 规定应该从父元素继承 float 属性的值。                |

```css
把图像向右浮动：
img{float:right;}
```

## 6. 标签居中

### 6.1 水平居中

**行内标签水平居中**

```css
text-align:center
```

**块级标签水平居中**

```css
margin:0 auto
```

### 6.2 垂直居中

**行内标签垂直居中**

```css
line-height:height;
```

**块级标签垂直居中**

```
定位
```

### 6.3. vertical-align - 垂直对齐方式

**vertical-align 属性设置元素的垂直对齐方式。**

```
	该属性定义行内元素的基线相对于该元素所在行的基线的垂直对齐。允许指定负长度值和百分比值。这会使元素降低而不是升高。在表单元格中，这个属性会设置单元格框中的单元格内容的对齐方式。
```

| 值          | 描述                                                         |
| :---------- | :----------------------------------------------------------- |
| baseline    | 默认。元素放置在父元素的基线上。                             |
| sub         | 垂直对齐文本的下标。                                         |
| super       | 垂直对齐文本的上标                                           |
| top         | 把元素的顶端与行中最高元素的顶端对齐                         |
| text-top    | 把元素的顶端与父元素字体的顶端对齐                           |
| middle      | 把此元素放置在父元素的中部。                                 |
| bottom      | 把元素的顶端与行中最低的元素的顶端对齐。                     |
| text-bottom | 把元素的底端与父元素字体的底端对齐。                         |
| length      |                                                              |
| %           | 使用 "line-height" 属性的百分比值来排列此元素。允许使用负值。 |

```css
设置行内标签的文字和图片在在基线轴的中部
父级样式和img标签都要设置 vertical-align

<style class="">
        #box{
            background-color:cyan;
            width:800px;
            height:600px;
            text-align:center;
            line-height:600px;
            vertical-align:middle;
        }
        span{
            background-color: orange;
        }
        img{
            vertical-align:middle;
        }
    </style>
</head>
<body>
    <div id="box">
        <span class="">行内标签1</span>
        <img src="http://img3.imgtn.bdimg.com/it/u=4200179912,1171200473&fm=15&gp=0.jpg" alt="" class="">
        <span class="">行内标签2</span>
    </div>
</body>
```

## 7. css常见属性

### 7.1  visibility - 可见性

```
visibility 属性规定元素是否可见。
提示：即使不可见的元素也会占据页面上的空间。请使用 "display" 属性来创建不占据页面空间的不可见元素。
```

| 值      | 描述                   |
| :------ | :--------------------- |
| visible | 默认值。元素是可见的。 |
| hidden  | 元素是不可见的。       |

```css
使h2不可见 :
h2
  {
  visibility:hidden;
  }
```

### 7.2. cursor - 光标指针

**该属性定义了鼠标指针放在一个元素边界范围内时所用的光标形状**

| 值        | 描述                                                         |
| :-------- | :----------------------------------------------------------- |
| *url*     | 需使用的自定义光标的 URL。注释：请在此列表的末端始终定义一种普通的光标，以防没有由 URL 定义的可用光标。 |
| default   | 默认光标（通常是一个箭头）                                   |
| auto      | 默认。浏览器设置的光标。                                     |
| crosshair | 光标呈现为十字线。                                           |
| pointer   | 光标呈现为指示链接的指针（一只手）                           |
| move      | 此光标指示某对象可被移动。                                   |
| e-resize  | 此光标指示矩形框的边缘可被向右（东）移动。                   |
| ne-resize | 此光标指示矩形框的边缘可被向上及向右移动（北/东）。          |
| nw-resize | 此光标指示矩形框的边缘可被向上及向左移动（北/西）。          |
| n-resize  | 此光标指示矩形框的边缘可被向上（北）移动。                   |
| se-resize | 此光标指示矩形框的边缘可被向下及向右移动（南/东）。          |
| sw-resize | 此光标指示矩形框的边缘可被向下及向左移动（南/西）。          |
| s-resize  | 此光标指示矩形框的边缘可被向下移动（南）。                   |
| w-resize  | 此光标指示矩形框的边缘可被向左移动（西）。                   |
| text      | 此光标指示文本。                                             |
| wait      | 此光标指示程序正忙（通常是一只表或沙漏）。                   |
| help      | 此光标指示可用的帮助（通常是一个问号或一个气球）。           |

```css
此光标指示程序正忙(通常是一只表或沙漏）:
cursor:wait;
```

### 7.3. color - 字体

**为不同元素设置文本颜色**

**三种书写格式**

```css
  {
  color:red;
  }
h1
  {
  color:#00ff00;
  }
p
  {
  color:rgb(0,0,255);
  }
```

### 7.4. font - 字体

**font 简写属性在一个声明中设置所有字体属性**

| 值                      | 描述                                                         |
| :---------------------- | :----------------------------------------------------------- |
| *font-style*            | 规定字体样式:<br/>normal :正常(默认)<br/>italic :斜体<br/>oblique:倾斜 |
| *font-weight*           | 规定字体粗细<br/>bold :粗体<br/>bolder :更粗<br/>lighter :更细<br/>100-900 :定义由粗到细,400=normal,700=bold |
| *font-size/line-height* | 规定字体尺寸和行高。                                         |
| *font-family*           | 规定字体系列。<br/>Arial , Helvetica , sans-serif<br/>浏览器会优先使用第一个，如果没有找到则使用第二个，以此类推。 |
| caption                 | 定义被标题控件（比如按钮、下拉列表等）使用的字体。           |
| icon                    | 定义被图标标记使用的字体。                                   |
| menu                    | 定义被下拉列表使用的字体。                                   |
| message-box             | 定义被对话框使用的字体。                                     |
| small-caption           | caption 字体的小型版本。                                     |
| status-bar              | 定义被窗口状态栏使用的字体。                                 |

### 7.5. text-decoration - 文本的修饰

**text-decoration 属性规定添加到文本的修饰。**

| 值           | 描述                     |
| :----------- | :----------------------- |
| none         | 默认。定义标准的文本。   |
| underline    | 定义文本下的一条线。     |
| overline     | 定义文本上的一条线。     |
| line-through | 定义穿过文本下的一条线。 |
| blink        | 定义闪烁的文本。         |

### 7.6. text-indent -首行文本缩进

**该样式需要指定一个长度，并且只对第一行生效。**

| 值       | 描述                               |
| :------- | :--------------------------------- |
| *length* | 定义固定的缩进。默认值：0。        |
| *%*      | 定义基于父元素宽度的百分比的缩进。 |

### 7.7. text-align - 文本水平的对齐方式

| 值      | 描述                                     |
| :------ | :--------------------------------------- |
| left    | 把文本排列到左边。默认值：由浏览器决定。 |
| right   | 把文本排列到右边。                       |
| center  | 把文本排列到中间。                       |
| justify | 实现两端对齐文本效果。                   |

### 7.8. text-transform - 控制文本大小写

| 值         | 描述                                           |
| :--------- | :--------------------------------------------- |
| none       | 默认。定义带有小写字母和大写字母的标准的文本。 |
| capitalize | 文本中的每个单词以大写字母开头。               |
| uppercase  | 定义仅有大写字母。                             |
| lowercase  | 定义无大写字母，仅有小写字母。                 |

### 7.9. list-style -type - 列表属性样式

**list-style-type**

| 值                   | 描述                                                        |
| :------------------- | :---------------------------------------------------------- |
| none                 | 无标记。                                                    |
| disc                 | 默认。标记是实心圆。                                        |
| circle               | 标记是空心圆。                                              |
| square               | 标记是实心方块。                                            |
| decimal              | 标记是数字。                                                |
| decimal-leading-zero | 0开头的数字标记。(01, 02, 03, 等。)                         |
| lower-roman          | 小写罗马数字(i, ii, iii, iv, v, 等。)                       |
| upper-roman          | 大写罗马数字(I, II, III, IV, V, 等。)                       |
| lower-alpha          | 小写英文字母The marker is lower-alpha (a, b, c, d, e, 等。) |
| upper-alpha          | 大写英文字母The marker is upper-alpha (A, B, C, D, E, 等。) |
| lower-greek          | 小写希腊字母(alpha, beta, gamma, 等。)                      |
| lower-latin          | 小写拉丁字母(a, b, c, d, e, 等。)                           |
| upper-latin          | 大写拉丁字母(A, B, C, D, E, 等。)                           |

### 7.10. overflow - 元素框溢出事件

| 值      | 描述                                                     |
| :------ | :------------------------------------------------------- |
| visible | 默认值。内容不会被修剪，会呈现在元素框之外。             |
| hidden  | 内容会被修剪，并且其余内容是不可见的。                   |
| scroll  | 内容会被修剪，但是浏览器会显示滚动条以便查看其余的内容。 |
| auto    | 如果内容被修剪，则浏览器会显示滚动条以便查看其余的内容。 |

### 7.11. line-height - 设置行高

| 值       | 描述                                                 |
| :------- | :--------------------------------------------------- |
| normal   | 默认。设置合理的行间距。                             |
| *number* | 设置数字，此数字会与当前的字体尺寸相乘来设置行间距。 |
| *length* | 设置固定的行间距。                                   |
| *%*      | 基于当前字体尺寸的百分比行间距。                     |

### 7.12. box-sizing - 定义匹配某个区域

```
	box-sizing 属性允许您以特定的方式定义匹配某个区域的特定元素。
	例如，假如您需要并排放置两个带边框的框，可通过将 box-sizing 设置为 "border-box"。这可令浏览器呈现出带有指定宽度和高度的框，并把边框和内边距放入框中。
```

| 值          | 描述                                                         |
| :---------- | :----------------------------------------------------------- |
| content-box | 这是由 CSS2.1 规定的宽度高度行为。宽度和高度分别应用到元素的内容框。在宽度和高度之外绘制元素的内边距和边框。 |
| border-box  | 为元素设定的宽度和高度决定了元素的边框盒。就是说，为元素指定的任何内边距和边框都将在已设定的宽度和高度内进行绘制。通过从已设定的宽度和高度分别减去边框和内边距才能得到内容的宽度和高度。 |

## 8. position - 定位

**position 属性规定元素的定位类型。**

```
	这个属性定义建立元素布局所用的定位机制。任何元素都可以定位，不过绝对或固定元素会生成一个块级框，而不论该元素本身是什么类型。相对定位元素会相对于它在正常流中的默认位置偏移。
```

| 值       | 描述                                                         |
| :------- | :----------------------------------------------------------- |
| absolute | 生成绝对定位的元素，相对于 static 定位以外的第一个父元素进行定位。元素的位置通过 "left", "top", "right" 以及 "bottom" 属性进行规定。 |
| fixed    | 生成绝对定位的元素，相对于浏览器窗口进行定位。元素的位置通过 "left", "top", "right" 以及 "bottom" 属性进行规定。 |
| relative | 生成相对定位的元素，相对于其正常位置进行定位。因此，"left:20" 会向元素的 LEFT 位置添加 20 像素。 |
| static   | 默认值。没有定位，元素出现在正常的流中（忽略 top, bottom, left, right 或者 z-index 声明）。 |

### 8.1 .相对定位 - relative

```css
1. 开启元素的相对定位后，如果不设置偏移量元素不会发生任何变化
2. 相对定位元素相对于其自身在文档流中的位置来定位
3. 相对定位的元素不会脱离文档流
4. 相对定位不会改变元素的性质，块元素还是块元素，内联元素还是内联元素
5. 相对定位的元素会提升一个层级
```

**实例**

```css
        img{
            position:relative;
            left:100px;
            top:100px;
        }
```

### 8.2.  绝对定位 -

```css
1. 元素设置绝对定位以后，如果不设置偏移量，元素的位置不会发生变化
2. 绝对定位的元素是相对于距离他最近的开启了定位的祖先元素进行定位，如果所有的祖先元素都没开启定位，则相对于浏览器窗口进行定位。
3. 绝对定位的元素会完全脱离文档流
4. 绝对定位会改变元素的性质。内联变块，块的高度和宽度都被内容撑开，并且不独占一行
5. 绝对定位会使元素提升一个层级
```

### 8.3. 固定定位 - fixed

```css
1.  固定定位是一种特殊的绝对定位，它的特点大部分都和绝对定位一样
2.  不同的是，固定定位的元素永远都是相对于浏览器窗口进行定位的。并且他不会随滚动条滚动
```

### 8.4. 层级关系

**z-index**	            `z-index:999;`

```css
1. z-index 属性设置元素的堆叠顺序。拥有更高堆叠顺序的元素总是会处于堆叠顺序较低的元素的前面
2. Z-index 仅能在定位元素上奏效（例如 position:absolute;）
```

## 9. background - 背景

### 9.1. background

**background 简写属性在一个声明中设置所有的背景属性。**

| 值                      | 描述                                             |
| :---------------------- | :----------------------------------------------- |
| *background-color*      | 规定要使用的背景颜色。                           |
| *background-position*   | 规定背景图像的位置。                             |
| *background-size*       | 规定背景图片的尺寸。                             |
| *background-repeat*     | 规定如何重复背景图像。默认平铺  不平铺:no-repeat |
| *background-origin*     | 规定背景图片的定位区域。                         |
| *background-clip*       | 规定背景的绘制区域。                             |
| *background-attachment* | 规定背景图像是否固定或者随着页面的其余部分滚动。 |
| *background-image*      | 规定要使用的背景图像。                           |

### 9.2. background-position

| 值                                                           | 描述                                                         |
| :----------------------------------------------------------- | :----------------------------------------------------------- |
| top lefttop centertop rightcenter leftcenter centercenter rightbottom leftbottom centerbottom right | 如果您仅规定了一个关键词，那么第二个值将是"center"。默认值：0% 0%。 |
| x% y%                                                        | 第一个值是水平位置，第二个值是垂直位置。左上角是 0% 0%。右下角是 100% 100%。如果您仅规定了一个值，另一个值将是 50%。 |
| xpos ypos                                                    | 第一个值是水平位置，第二个值是垂直位置。左上角是 0 0。单位是像素 (0px 0px) 或任何其他的 CSS 单位。如果您仅规定了一个值，另一个值将是50%。您可以混合使用 % 和 position 值。 |

### 9.3. repeat

```
repeat:
		默认值，背景图片会平铺显示
		沿x轴和y轴双方向重复
no-repeat:
		背景图片不重复
repeat-x:
		背景图片沿水平方向重复
repeat-y:
		背景图片沿垂直方向重复
```

### 9.4. background-size

| *length*     | 设置背景图像的高度和宽度。第一个值设置宽度，第二个值设置高度。如果只设置一个值，则第二个值会被设置为 "auto"。 |
| ------------ | ------------------------------------------------------------ |
| *percentage* | 以父元素的百分比来设置背景图像的宽度和高度。第一个值设置宽度，第二个值设置高度。如果只设置一个值，则第二个值会被设置为 "auto"。 |
| cover        | 把背景图像扩展至足够大，以使背景图像完全覆盖背景区域。背景图像的某些部分也许无法显示在背景定位区域中。 |
| contain      | 把图像图像扩展至最大尺寸，以使其宽度和高度完全适应内容区域。 |

### 9.5. background-attachment

**用来设置背景是否随页面滚动**

```css
可选值:
1. scroll :
	默认值，背景图片会随页面一起滚动
2. fixed :
	1. 背景图片不随页面滚动，会固定在页面的指定位置
	2. 设置该属性的背景，则背景会永远相对于浏览器窗口进行定位
	3. 一般这种背景都会设置给body
```





## 10. opacity - 不透明度

**值 : 0~1**

```
div
{
opacity:0.5;
}
```



------

# 常用CSS属性

## 1. transform 属性

**transform 属性向元素应用 2D 或 3D 转换。该属性允许我们对元素进行旋转、缩放、移动或倾斜。**

## 2. 移动 - translate

| 值                       | 描述                            |
| ------------------------ | ------------------------------- |
| translate(*x*,*y*)       | 定义 2D 转换。                  |
| translate3d(*x*,*y*,*z*) | 定义 3D 转换。                  |
| translateX(*x*)          | 定义转换，只是用 X 轴的值。     |
| translateY(*y*)          | 定义转换，只是用 Y 轴的值。     |
| translateZ(*z*)          | 定义 3D 转换，只是用 Z 轴的值。 |

**例子**

```css
    <style class="">

        div{
            background-color: deeppink;
            width:100px;
            height:100px;
            transition:all 0.5s ease-out;
        }
        div:active{
            transform:translate(100px)
        }
    </style>
</head>
<body>
    <div class=""></div>
</body>
```

## 3. transition-timing-function 属性

**以相同的速度从开始到结束的过渡效果**

| linear                        | 规定以相同速度开始至结束的过渡效果（等于 cubic-bezier(0,0,1,1)）。 |
| ----------------------------- | ------------------------------------------------------------ |
| ease                          | 规定慢速开始，然后变快，然后慢速结束的过渡效果（cubic-bezier(0.25,0.1,0.25,1)）。 |
| ease-in                       | 规定以慢速开始的过渡效果（等于 cubic-bezier(0.42,0,1,1)）。  |
| ease-out                      | 规定以慢速结束的过渡效果（等于 cubic-bezier(0,0,0.58,1)）。  |
| ease-in-out                   | 规定以慢速开始和结束的过渡效果（等于 cubic-bezier(0.42,0,0.58,1)）。 |
| cubic-bezier(*n*,*n*,*n*,*n*) | 在 cubic-bezier 函数中定义自己的值。可能的值是 0 至 1 之间的数值。 |

```css
    <style class="">

        div{
            background-color: deeppink;
            width:100px;
            height:100px;
            transition:all 0.5s ;
            transition-timing-function:ease-out;
        }
        div:active{
            transform:translate(100px)
        }
    </style>
</head>
<body>
    <div class=""></div>
</body>
```

## 4.  缩放 - scale

| 值                   | 描述                                  |
| -------------------- | ------------------------------------- |
| scale(*x*,*y*)       | 定义 2D 缩放转换。                    |
| scale3d(*x*,*y*,*z*) | 定义 3D 缩放转换。                    |
| scaleX(*x*)          | 通过设置 X 轴的值来定义缩放转换。     |
| scaleY(*y*)          | 通过设置 Y 轴的值来定义缩放转换。     |
| scaleZ(*z*)          | 通过设置 Z 轴的值来定义 3D 缩放转换。 |

```css
    <style class="">

        div{
            background-color: deeppink;
            width:100px;
            height:100px;
            margin:200px auto;
             /* 过渡效果 */
            transition:all 0.5s ease-out;
            /* 改变中心点 */
            transform-origin:left top;            
        }
        div:hover{
            transform:scale(1.5)
        }
    </style>
</head>
<body>
    <div class=""></div>
</body>
```

## 5. transform-origin - 改变中心点

| 值     | 描述                                                         |
| :----- | :----------------------------------------------------------- |
| x-axis | 定义视图被置于 X 轴的何处。可能的值：leftcenterright*length**%* |
| y-axis | 定义视图被置于 Y 轴的何处。可能的值：topcenterbottom*length**%* |
| z-axis | 定义视图被置于 Z 轴的何处。可能的值：*length*                |

## 6. rotate - 旋转

| rotate(*angle*)               | 定义 2D 旋转，在参数中规定角度。 |
| ----------------------------- | -------------------------------- |
| rotate3d(*x*,*y*,*z*,*angle*) | 定义 3D 旋转。                   |
| rotateX(*angle*)              | 定义沿着 X 轴的 3D 旋转。        |
| rotateY(*angle*)              | 定义沿着 Y 轴的 3D 旋转。        |
| rotateZ(*angle*)              | 定义沿着 Z 轴的 3D 旋转。        |

```css
<style class="">

        div{
            background-color: deeppink;
            width:100px;
            height:100px;
            margin:200px auto;
            transition:all 0.5s ease-out;

            /* 改变中心点 */
            /* transform-origin:left top; */
        }
        div:hover{
            /* z方向顺时针旋转90° */
            transform:rotatez(90deg);
        }
    </style>
</head>
<body>
    <div class=""></div>
</body>
```

# 网页favicon.ico图标设置

## 第一种方式：放在根目录

```html
这种方法最简单，在服务器根目录下放一个 favicon.ico 的文件，浏览器发现后就会使用。
注：这种方式，ico文件的名称一定要叫：favicon
```

## 第二种方法：link标签

**在head里面加入代码：**

```html
<link rel="shortcut icon" href="ico文件url">
或
<link rel="icon" href="../favicon.ico">
或
<link rel="shortcut icon" href="../favicon.ico" type="image/x-icon">

```

**favicon的格式一定是ico格式吗？**

```
favicon的格式不一定是ico格式，它可以是png，jpg甚至是gif，不过ico格式是所有浏览器都支持的。

favicon.ico的尺寸有16×16、32×32、48×48，在添加到桌面、任务栏小尺寸的图标就不是很理想了，这就需要多种尺寸兼容各种设备和情况。
```

