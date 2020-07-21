# meta 

## 定义
`<meta>` 元素表示那些不能由其它HTML元相关元素 (`<base>`, `<link>`, `<script>`, `<style>` 或 `<title>`) 之一表示的任何元数据信息。

`meta` 元素定义的元数据的类型包括以下几种：

- 如果设置了 `name` 属性，`meta` 元素提供的是文档级别（_document-level_）的元数据，应用于整个页面。
- 如果设置了 `http-equiv` 属性，`meta` 元素则是编译指令，提供的信息与类似命名的HTTP头部相同。
- 如果设置了 `charset` 属性，`meta` 元素是一个字符集声明，告诉文档使用哪种字符编码。
- 如果设置了 `itemprop` 属性，`meta` 元素提供用户定义的元数据。

## 常见功能

### 帮助主页被各大搜索引擎登录

`meta`标签的一个很重要的功能就是设置关键字，来帮助你的主页被各大搜索引擎登录，提高网站的访问量。在这个功能中，最重要的就是对`keywords`和`description`的设置。因为按照搜索引擎的工作原理，搜索引擎首先派出机器人自动检索页面中的`keywords`和`description`，并将其加入到自己的数据库，然后再根据关键词的密度将网站排序。因此，我们必须设置好关键字，来提高页面的搜索点击率。下面我们来举一个例子供大家参考：
```html
<meta name="keywords" content="政治，经济，科技，文化，卫生，情感，心灵，娱乐，生活，社会，企业，交通">
<meta name="description" content="政治，经济，科技，文化，卫生，情感，心灵，娱乐，生活，社会，企业，交通">
```
设置好这些关键字后，搜索引擎将会自动把这些关键字添加到数据库中，并根据这些关键字的密度来进行合适的排序。

### 定义页面的使用语言

这是meta标签最常见的功能，在制作网页时，我们在纯HTML代码下都会看到它，它起的作用是定义你网页的语言，当浏览者访问你的网页时，浏览器会自动识别并设置网页中的语言，如果你网页设置的是GB码，而浏览者没有安装GB码，这时网页只会呈现浏览者所设置的浏览器默认语言。同样的，如果该网页是英语，那么charset=en。下面就是一个具有代表性的例子：
```html
<meta http-equiv="content－Type" content="text/html; charset=gb2312">
```
该代码就表示将网页的语言设置成国标码。

### 自动刷新并指向新的页面

如果你想使您的网页在无人控制的情况下，能自动在指定的时间内去访问指定的网页，就可以使用meta标签的自动刷新网页的功能。下面我们来看一段代码：
```html
<meta http-equiv="refresh" content="2; URL=">
```
这段代码可以使当前某一个网页在2秒后自动转到页面中去，这就是meta的刷新作用，在content中，2代表设置的时间（单位为秒），而URL就是在指定的时间后自动连接的网页地址。

### 动画效果

使用meta标签，我们还可以在进入网页或者离开网页的一刹那实现动画效果，我们只要在页面的html代码中的`<head></head>`；标签之间添加如下代码就可以了：
```html
<meta http-equiv="Page-Enter" content="revealTrans(duration=5.0,transition=20)">
```
一旦上述代码被加到一个网页中后，我们再进出页面时就会看到一些特殊效果，这个功能其实与FrontPage2000中的Format/Page Transition一样，但我们要注意的是所加网页不能是一个Frame页； RevealTrans动态滤镜
Duration表示滤镜特效的持续时间（单位：秒）
Transition滤镜类型。表示使用哪种特效，取值为0-23:
|值|效果|值|效果|
|---|---|---|---|
|0 |矩形缩小|1 |矩形扩大|
|2 |圆形缩小|3 |圆形扩大|
|4 |下到上刷新|5 |上到下刷新|
|6 |左到右刷新|7 |右到左刷新|
|8 |竖百叶窗|9 |横百叶窗|
|10| 错位横百叶窗|11| 错位竖百叶窗|
|12| 点扩散|13| 左右到中间刷新|
|14| 中间到左右刷新|15| 中间到上下|
|16| 上下到中间|17| 右下到左上|
|18| 右上到左下|19| 左上到右下|
|20| 左下到右上|21| 横条|
|22| 竖条|23| 以上22种随机选择一种|

### 申明编码

```html
<meta charset='utf-8' />
```

### 优先使用 IE 最新版本和 Chrome

```html
<meta http-equiv="X-UA-Compatible" content="IE=edge,chrome=1" />
<!-- 关于X-UA-Compatible -->
<meta http-equiv="X-UA-Compatible" content="IE=6" ><!-- 使用IE6 -->
<meta http-equiv="X-UA-Compatible" content="IE=7" ><!-- 使用IE7 -->
<meta http-equiv="X-UA-Compatible" content="IE=8" ><!-- 使用IE8 -->
```

### 浏览器内核控制

国内浏览器很多都是双内核（webkit和Trident），webkit内核高速浏览，IE内核兼容网页和旧版网站。而添加meta标签的网站可以控制浏览器选择何种内核渲染。
```html
<meta name="renderer" content="webkit|ie-comp|ie-stand">
```

### 禁止浏览器从本地计算机的缓存中访问页面内容
```html
<meta http-equiv="Pragma" content="no-cache">
```

### 控制页面缓冲
meta标签可以设置网页到期的时间，也就是说，当你在Internet Explorer 浏览器中设置浏览网页时首先查看本地缓冲里的页面，那么当浏览某一网页，而本地缓冲又有时，那么浏览器会自动浏览缓冲区里的页面，直到meta中设置的时间到期，这时候，浏览器才会去取得新页面。例如下面这段代码就表示网页的到期时间是2001年1月12日18时18分18秒。
```html
<meta http-equiv="expires" content="Friday,12-Jan-2001 18:18:18 GMT">
```

### 控制网页窗口
我们还可以使用meta标签来控制网页显示的窗口，只要在网页中加入下面的代码就可以了：
```html
<meta http-equiv="window-target" content="_top">
```
这段代码可以防止网页被别人作为一个Frame调用。

### 移动设备
#### viewport

能优化移动浏览器的显示。如果不是响应式网站，不要使用`initial-scale`或者禁用缩放。大部分4.7-5寸设备的`viewport`宽设为360px；5.5寸设备设为400px；iphone6设为375px；ipone6 plus设为414px。
```html
<meta name="viewport" content="width=device-width, initial-scale=1.0,maximum-scale=1.0, user-scalable=no"/>

<!-- `width=device-width` 会导致 iPhone 5 添加到主屏后以 WebApp 全屏模式打开页面时出现黑边  -->
```
- width：宽度（数值 / device-width）（范围从200 到10,000，默认为980 像素）
- height：高度（数值 / device-height）（范围从223 到10,000）
- initial-scale：初始的缩放比例 （范围从>0 到10）
- minimum-scale：允许用户缩放到的最小比例
- maximum-scale：允许用户缩放到的最大比例
- user-scalable：用户是否可以手动缩 (no,yes)
- minimal-ui：可以在页面加载时最小化上下状态栏。（已弃用）

注意，很多人使用`initial-scale=1`到非响应式网站上，这会让网站以100%宽度渲染，用户需要手动移动页面或者缩放。如果和`initial-scale=1`同时使用`user-scalable=no`或`maximum-scale=1`，则用户将不能放大/缩小网页来看到全部的内容。

#### WebApp全屏模式

伪装app，离线应用。
```html
<meta name="apple-mobile-web-app-capable" content="yes" /> <!-- 启用 WebApp 全屏模式 -->
```
  
#### 更多
```html
<!-- 忽略数字自动识别为电话号码 -->
<meta content="telephone=no" name="format-detection" />
<!-- 忽略识别邮箱 -->
<meta content="email=no" name="format-detection" />
<!-- 添加智能 App 广告条 Smart App Banner：告诉浏览器这个网站对应的app，并在页面上显示下载banner -->
<meta name="apple-itunes-app" content="app-id=myAppStoreID, affiliate-data=myAffiliateData, app-argument=myURL">
<!-- 针对手持设备优化，主要是针对一些老的不识别viewport的浏览器，比如黑莓 -->
<meta name="HandheldFriendly" content="true">
<!-- 微软的老式浏览器 -->
<meta name="MobileOptimized" content="320">
<!-- uc强制竖屏 -->
<meta name="screen-orientation" content="portrait">
<!-- QQ强制竖屏 -->
<meta name="x5-orientation" content="portrait">
<!-- UC强制全屏 -->
<meta name="full-screen" content="yes">
<!-- QQ强制全屏 -->
<meta name="x5-fullscreen" content="true">
<!-- UC应用模式 -->
<meta name="browsermode" content="application">
<!-- QQ应用模式 -->
<meta name="x5-page-mode" content="app">
<!-- windows phone 点击无高光 -->
<meta name="msapplication-tap-highlight" content="no">
```
  
### 其他
```html
<meta name="author" content="author name" /> <!-- 定义网页作者 -->
<meta name="google" content="index,follow" />
<meta name="googlebot" content="index,follow" />
<meta name="verify" content="index,follow" />
```

## 相关资料
[meta元素文档](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/meta)