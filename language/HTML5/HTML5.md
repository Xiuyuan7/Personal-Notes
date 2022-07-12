# 基本介绍

## 什么是HTML

**HTML：Hyper Text Markup Language（超文本标记语言）**

超文本包括：文字、图片、音频、视频、动画等

![image-20220226225937273](C:\Users\11151\AppData\Roaming\Typora\typora-user-images\image-20220226225937273.png)

## 发展史

![image-20220226230214666](C:\Users\11151\AppData\Roaming\Typora\typora-user-images\image-20220226230214666.png)

- HTML：Hyper Text Markup Language超文本标记语言。
- 超文本标记语言—在1993年6月互联网工程工作小组工作案发布（并非标准）。
- HTML2.0—1995年11月作为RFC1866发布，在RFC2854于2000年6月发布之后被宣布过。
- HTML3.2—1996年1月14日，W3C推荐标准。
- HTML4.0—1997年12月18日，W3C推荐标准。
- HTML4.01（微小改进）—1999年12月24日，W3C推荐标准，2000年5月15日发布基本严格的
  HTML4.01语法，是国标标准化组织和国际电工委员会的标准。
- XHTML1.0—发布于2000年1月26日，是W3C推荐标准，后来经过修订于2002年8月1日重新发布。
- XHTML1.1—2001年5月31日发布。
- XHTML2.0是W3C的工作草案，由于改动过大，学习这个新技术的成本过高而最终胎死腹中因
  此，现在最常用的还是XHTML1.0标准。
- 目前最新的版本为HTML5，它是2004年被提出，2007年被W3C接纳并成立新的HTML工作团队，2008年1月22日公布HTML5第一份正式草案，2012年12月17日HTML5规范正式定稿，2013年5月6日，HTML5.1正式草案公布。
- HTML 5作为最新版本，提供了一些新的元素和一些有趣的新特性，同时也建立了一些新的规则。这些元素、特性和规则的建立，提供了许多新的网页功能，如使用网页实现动态渲染图形、图表、图像和动画，以及不需要安装任何插件直接使用网页播放视频等。目前企业开发中也在增大使用HTML5的力度。

## 优势

**世界知名浏览器厂商对HTML5的支持**

通过对Internet Explorer、Google、Firefox、Safari、Opera等主要的Web浏览器发展策略调查，发现他们都在支持HTMl5上采取措施。

- 微软：2010年3月16日，微软于拉斯维加斯市举行的MIX10技术大会上宣布已推出IE9浏览器开发者预览版。此版本将更多的支持CSS3、SVG和HTML5等互联网浏览通用标准。
- Google：2010年2月19日，谷歌Gears项目经理伊安一费特通过博客宣布，谷歌将放弃对Gears浏览器插件项目的支持，以此重点开发HTML5项目。
- 苹果：2010年6月7日，苹果在开发者大会的会后发布了Safari 5，这款浏览器支持10个以上HTML5新技术，包括全屏播放、HTML5视频、HTML5地理位置、HTML5的形式验证等功能。
- Opera：2010年5月5日，Opera软件公司首席技术官Hakon Wium Lie先生在访华之际，接受中国软件资讯网等少数几家媒体采访，他认为HTML5和CSS3将是全球互联网发展的未来趋势。
- mozilla firefox：2010年7月，Mozilla基金会发布了Firefox 4浏览器的第一个测试版，从官方文档看，它对HTML5是完全级别的支持。

**市场的需求**

现在的市场已经迫不及待的要求有一个统一的互联网通用标准。HTML5之前的情况是，由于各浏览器之间的不统一，光是修改Web浏览器之间的由于兼容性而引起的bug就浪费了大量的时间。而HTML5的目标就是将Web带入一个成熟的应用平台，在HTML5平台上，视频、音频、图像、动画以及同电脑的交互都被标准化。

**跨平台**

HTML5可以做到跨平台开发，用户只用打开浏览器即可访问应用，PC网站、各种移动设备、插件等核心代码就可以不需要重复编写，极大的减少了开发人员的工作量。

## W3C标准

**W3C**

- World Wide Web Consortium（万维网联盟）
- 成立于1994年，Web技术领域最权威和具影响力的国际中立性技术标准机构
- http://www.w3.org/
- http://www.chinaw3c.org/

**W3C标准**

- 结构化标准语言（XHTML 、XML）
- 表现标准语言（CSS）
- 行为标准（DOM、ECMAScript ）

**常见的网页编辑工具IDE**

- 记事本
- NotePad++
- Sublime
- VsCode
- WebStorm
- HBuidler
- IDEA
- WebStorm

# 基本结构和标签

## 基本结构

```html
<!--tip：“ctrl + /”快速生成注释-->

<!--DOCTYPE告诉浏览器要使用什么规范-->
<!DOCTYPE html>

<!--html代表网页整体-->
<html lang="en">

<!--head代表网页头部-->
<head>
    <!--meta描述性标签，用来描述网站信息-->
    <!--meta一般用来做SEO-->
    <meta charset="UTF-8">
    <meta name="keywords" content="狂神说Java，西部开源">
    <meta name="description" content="来这个地方可以学习Java">

    <!--title代表网页标题-->
    <title>基本结构</title>
</head>

<!--body标签代表网页主体-->
<body>
    Hello，World！
</body>

</html>
```

## 基本标签

```html
<!--tip：“标签名称 + tab”快速生成标签-->

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>基本标签</title>
</head>
<body>

<!--标题标签-->
<h1>一级标签</h1>
<h2>二级标签</h2>
<h3>三级标签</h3>
<h4>四级标签</h4>
<h5>五级标签</h5>
<h6>六级标签</h6>

<!--段落标签-->
<p>两只老虎 两只老虎</p>
<p>跑得快 跑得快</p>
<p>一只没有耳朵 一只没有尾巴</p>
<p>真奇怪 真奇怪</p>

<!--水平线标签-->
<hr>

<!--换行标签-->
两只老虎 两只老虎 <br>
跑得快 跑得快 <br>
一只没有耳朵 一只没有尾巴 <br>
真奇怪 真奇怪 <br>

<!--粗体斜体-->
粗体：<strong>I love you</strong> <br>
斜体：<em>I love you</em> <br>

<!--特殊符号-->
空格：我的 世界 <br>
空格：我的&nbsp;世界 <br>
空格：我的&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;世界 <br>
大于：&gt; <br>
小于：&lt; <br>
版权符号：&copy; <br>

</body>
</html>
```

## 图像标签

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>图像标签</title>
</head>
<body>

<!--
图片标签：<img src="">
图片地址，相对地址（推荐使用），绝对地址：src="../resources/image/头像.jpg"
图片失效显示名字：alt="我的头像-失效"
图片悬停显示名字：title="我的头像-悬停"
宽度：width="300"
高度：height="300"
-->
<img src="../resources/image/头像.jpg" alt="我的头像-失效" title="我的头像-悬停" width="300" height="300">
    
</body>
</html>
```

## 链接标签

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>连接标签</title>
</head>
<body>

<!--使用name作为标记-->
<a name="top">顶部</a>

<!--
链接标签：<a href="">
跳转页面地址：href="1. 我的第一个网页.html"
窗口打开方式：target=""
    在新网页中打开 _blank 
    在现在的网页中打开 _self（默认属性）
-->
<a href="1. 我的第一个网页.html" target="_blank">点击我跳转到第一个网页</a>

<br>

<a href="https://www.baidu.com" target="_self">点击我跳转到百度</a>

<br>

<!--
锚链接：
    锚标记标签：<a name="top">
    跳转标签：<a href="#top">
-->
<a href="#top">回到顶部</a>
<a href="3. 图像标签.html#down">网页间跳转</a>

<!--
功能性链接：
	邮件链接标签：<a href="mailto:tom.xy.wang@outlook.com">
	QQ链接标签
-->
<a href="mailto:tom.xy.wang@outlook.com">点击给我发邮件</a> <br>

<a target="_blank" href="http://wpa.qq.com/msgrd?v=3&uin=&site=qq&menu=yes">
    <img border="0" src="http://wpa.qq.com/pa?p=2::53" alt="点击我领取小电影" title="点击我领取小电影"/>
</a>

</body>
</html>
```

## 行内元素和块元素

**行内元素**

- 内容撑开宽度，左右都时行内元素的可以排在一行，不会换行
- `<strong></strong>`
- `<em></em>`

**块元素**

- 无论内容多少，该元素独占一行，会换行
- `<p></p>`
- `<h1></h1>`

## 列表标签

**什么是列表**

列表就是信息资源的一种展示形式。它可以使信息结构化和条理化，并以列表的样式显示出来，以便浏览者能更快捷地获得相应的信息。

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>列表</title>
</head>
<body>

<!--
有序列表：<ol> ordered list
列表内容：<li> list
应用范围：试卷，问答 ...
-->
<ol>
    <li>Java</li>
    <li>Python</li>
    <li>运维</li>
    <li>前端</li>
    <li>C/C++</li>
</ol>

<hr>

<!--
无序列表：<ul> unordered list
列表内容：<li> list
应用范围：导航，侧边栏 ...
-->
<ul>
    <li>Java</li>
    <li>Python</li>
    <li>运维</li>
    <li>前端</li>
    <li>C/C++</li>
</ul>

<hr>

<!--
自定义列表：<dl> description list
列表名称：<dt> description term
列表内容：<dd> description content
应用范围：公司网站底部
-->
<dl>
    <dt>学科</dt>
    <dd>Java</dd>
    <dd>Python</dd>
    <dd>Linux</dd>
    <dd>C</dd>

    <dt>位置</dt>
    <dd>西安</dd>
    <dd>重庆</dd>
    <dd>新疆</dd>
</dl>

</body>
</html>
```

## 表格标签

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>表格</title>
</head>
<body>

<!--
表格：<table>
边框粗细：border="1px"
行：<tr> table row
跨行：rowspan="2"
列：<td> table data
跨列：colspan="4"
-->
<table border="1px">
    <tr>
        <td colspan="4">1-1</td>
    </tr>
    <tr>
        <td rowspan="2">2-1</td>
        <td>2-2</td>
        <td>2-3</td>
        <td>2-4</td>
    </tr>
    <tr>
        <td>3-1</td>
        <td>3-2</td>
        <td>3-3</td>
    </tr>
</table>

</body>
</html>
```

## 媒体标签

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>媒体</title>
</head>
<body>

<!--
视频标签：<video>
资源路径属性：src="../resources/video/ARK_ Survival Evolved 2021-05-25 18-01-49.mp4"
显示控制条：controls
自动播放：autoplay
-->
<video src="../resources/video/ARK_ Survival Evolved 2021-05-25 18-01-49.mp4" controls autoplay></video>

<!--
音频标签：<audio>
资源路径属性：src="../resources/audio/录音.m4a"
显示控制条：controls
自动播放：autoplay
-->
<audio src="../resources/audio/录音.m4a" controls autoplay></audio>

</body>
</html>
```

## 页面结构

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>页面结构</title>
</head>
<body>

<!--header：标题头部区域的内容（用于页面或页面中的一块区域）-->
<header>
    <h2>网页头部</h2>
</header>

<!--section：页面中的一块独立区域-->
<section>
    <h2>网页主体</h2>
    <!--article：独立的文章内容-->
    <article>
        列表就是信息资源的一种展示形式。它可以使信息结构化和条理化，并以列表的样式显示出来，以便浏览者能更快捷地获得相应的信息
    </article>
</section>

<!--aside：相关内容或应用（常用于侧边栏）-->
<aside>
    我的世界
</aside>

<!--nav：导航类辅助内容-->
<nav>
    嘿嘿嘿
</nav>

<!--footer：标记脚部区域的内容（用于整个页面或页面的一块区域）-->
<footer>
    <h2>网页脚步</h2>
</footer>

</body>
</html>
```

## 内联框架

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>内联框架</title>
</head>
<body>

<!--
内联框架标签：<iframe>
网页地址属性：src="https://www.bilibili.com"
框架线属性：frameborder="0"，0没有，1有
框架宽度：width="1300px"
框架高度：height="800px"
-->
<iframe src="https://www.bilibili.com" frameborder="0" width="1300px" height="800px"></iframe>

<!--
自定义名称属性：name="hello"
-->
<iframe src="" name="hello" frameborder="0" width="1300px" height="800px"></iframe>
<a href="https://www.bilibili.com" target="hello">点击跳转</a>

</body>
</html>
```

# 表单

## 表单标签

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>表单标签</title>
</head>
<body>

<h1>注册</h1>

<!--
表单标签：<form>
表单提交的位置属性，可以是网站，也可以是一个请求处理地址：action="1. 我的第一个网页.html"
表单提交方式属性：method="get"
    get方式提交：可以在url中看到提交信息，不安全但是高效
    post方式提交：无法在url中看到提交信息，比较安全，用来传输大文件
-->
<form action="1. 我的第一个网页.html" method="get">

    <!--文本输入框：<input type="text">-->
    <p>名字：<input type="text" name="username"></p>

    <!--密码框：<input type="password">-->
    <p>密码：<input type="password" name="password"></p>
    
    <p>
        <input type="submit">
        <input type="reset">
    </p>

</form>

</body>
</html>
```

## 文本框标签

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>文本框</title>
</head>
<body>

<form action="1. 我的第一个网页.html" method="get">

    <!--
    文本框标签：<input type="text">
    默认初始值属性：value="我的世界"
	组属性：name="username"
    最大输入长度属性：maxlength="8"
    文本框长度属性：size="30"
    -->
    <p>名字：<input type="text" value="我的世界" name="username" maxlength="8" size="30"></p>

</form>

</body>
</html>
```

## 密码框标签

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>密码框</title>
</head>
<body>

<form action="1. 我的第一个网页.html" method="get">

    <!--
	密码框标签：<input type="password">
	默认初始值属性：value="123456"
	组属性：name="password"
	-->
    <p>密码：<input type="password" value="123456" name="password"></p>

</form>

</body>
</html>
```

## 单选框标签

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>单选框</title>
</head>
<body>

<form action="1. 我的第一个网页.html" method="get">

    <!--
    单选框标签：<input type="radio">
    默认初始值属性：value="boy"
    组属性：name="gender"，同组单选，不同组多选
	默认选中：checked
    -->
    <p>性别：
        <input type="radio" value="boy" name="gender" checked>男
        <input type="radio" value="girl" name="gender">女
    </p>

</form>

</body>
</html>
```

## 多选框标签

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>多选框</title>
</head>
<body>

<form action="1. 我的第一个网页.html" method="get">
    
    <!--
    多选框标签：<input type="checkbox">
	默认初始值属性：value="sleep"
	组属性：name="hobby"
	默认选中：checked
    -->
    <p>爱好：
        <input type="checkbox" value="sleep" name="hobby">睡觉
        <input type="checkbox" value="coding" name="hobby" checked>敲代码
        <input type="checkbox" value="chat" name="hobby">聊天
        <input type="checkbox" value="game" name="hobby">游戏
    </p>

</form>

</body>
</html>
```

## 按钮标签

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>按钮</title>
</head>
<body>

<form action="1. 我的第一个网页.html" method="get">
    
    <!--
    按钮标签：
    	普通按钮：<input type="button">
    	图像按钮：<input type="image"> 点击可以提交表单
    	提交按钮：<input type="submit">
    	重置按钮：<input type="reset">
    -->
    <p>按钮：
        <input type="button" name="btn1" value="点击变长">
        <input type="image" src="../resources/image/头像.jpg">
        <input type="submit" value="提交">
        <input type="reset" value="清空表单">
    </p>

</form>

</body>
</html>
```

## 下拉框标签

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>下拉框</title>
</head>
<body>

<form action="1. 我的第一个网页.html" method="get">

    <!--
    下拉框标签：<select>
	组属性：name="国家名称"
    下拉选项标签：<option>
	默认初始值属性：value="china"
    默认选中：selected
    -->
    <p>国家：
        <select name="国家名称">
            <option value="china">中国</option>
            <option value="usa">美国</option>
            <option value="japan" selected>日本</option>
            <option value="india">印度</option>
        </select>
    </p>

</form>

    
</body>
</html>
```

## 文本域标签

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>文本域</title>
</head>
<body>

<form action="1. 我的第一个网页.html" method="get">

    <!--
    文本域标签：<textarea name="textarea">
    宽度属性：cols="30"
    长度属性：rows="10"
    -->
    <p>反馈：
        <textarea name="textarea" cols="30" rows="10">文本内容</textarea>
    </p>

</form>

</body>
</html>
```

## 文件域标签

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>文件域</title>
</head>
<body>

<form action="1. 我的第一个网页.html" method="get">

    <!--
    文件域标签：<input type="file">
    组属性：name="files"
    -->
    <p>
        <input type="file" name="files">
    </p>

</form>

</body>
</html>
```

## 简单验证

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>简单验证</title>
</head>
<body>

<form action="1. 我的第一个网页.html" method="get">

    <!--邮件验证-->
    <p>邮箱：
        <input type="email" name="email">
    </p>

    <!--URL验证-->
    <p>URL：
        <input type="url" name="url">
    </p>

    <!--数字验证-->
    <p>商品数量：
        <input type="number" name="number" max="100" min="0" step="1">
    </p>
    
    <!--滑块-->
    <p>音量：
        <input type="range" name="voice" max="100" min="0" step="2">
    </p>
    
    <!--搜索框-->
    <p>搜索：
        <input type="search" name="search">
    </p>

</form>

</body>
</html>
```

## 增强可用性

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>增强可用性</title>
</head>
<body>
    
<form action="1. 我的第一个网页.html" method="get">

    <!--只读-->
    <p>
        名字：<input type="text" name="username" value="admin" readonly>
    </p>

    <!--隐藏-->
    <p>
        密码：<input type="password" name="password" value="123456" hidden>
    </p>
    
    <!--禁用-->
    <p>
        <input type="submit" disabled>
        <input type="reset">
    </p>
    
    <!--
    增强鼠标可用性：<label for="mark">
    定位属性：id="mark"
    -->
    <p>
        <label for="mark">你点我试试</label>
        <input type="text" id="mark">
    </p>

</form>

</body>
</html>
```

## 初级验证

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>初级验证</title>
</head>
<body>

<form action="1. 我的第一个网页.html" method="get">

    <!--
	提示信息：placeholder="请输入用户名"
	非空判断：required
	-->
    <p>名字：<input type="text" name="username" placeholder="请输入用户名" required></p>

    <!--正则表达式：pattern="/^[_a-z0-9-]+(\.[_a-z0-9-]+)*@[a-z0-9-]+(\.[a-z0-9-]+)*(\.[a-z]{2,})$/"-->
    <p>自定义邮箱：
        <input type="text" name="diyemail" pattern="/^[_a-z0-9-]+(\.[_a-z0-9-]+)*@[a-z0-9-]+(\.[a-z0-9-]+)*(\.[a-z]{2,})$/">
    </p>
    
</form>

</body>
</html>
```

