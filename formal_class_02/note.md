### 爬虫实战

awesome dataset--

爬虫一共十五个例子

什么是爬虫：
就是伪装人类的行为去寻找数据

爬虫的流程：
找到url-》请求（把网页的内容拿回来）-》解析-》 存储

工具（lib）：
- python - scrapy， pyspider
- java - Nutch（分布式爬虫） ，Crawler4j
- node.js - node-crawler
- 软件 ： 八爪鱼， hawk， 火车头

* 爬虫用的最多的语言是python

### 爬虫分类：
- 通用型 vs 定向／聚焦／垂直
通用型爬虫：百度，搜索引擎就是个爬虫 快照就是把数据库里面存储的东西拿出来。
这节课主要讲的是定向聚焦与垂直

- 单机 vs 分布式
分布式要处理很多问题。不要一开始就用分布式／先把单机搞明白

- dom解析 vs ajax vs 正则表达式
XHR就是AJAX请求，纯数据
（看源码1：command + option + u）

dom解析：aaron上课讲的
xpath： python里面用的多
网页里面- 万物皆块 js存在的意义就是调用这些块

正则表达式 匹配

后期讲怎么做chrome可视化插件


### sample 1 莆田系医院

网站的请求中是不能带中文的，必须转码

```js
var url = .........
decodeURI(url);
```

请求的返回：
url error： 没网
1xx
2xx

DATAV.GEOAtlas：查询adcode

- v3里面的filter
对象obj的好处：可以做索引

请求的堆积： 两秒钟返回，你设置成一秒，请求堆积，就会造成内存泄漏（memory leak），v4.js里面的请求模式解决这个问题
一个请求的函数，自己调用自己，ex：
```js
function a(){
  xxxx //请求的代码
  a（）//请求结束后在执行自己，有点像串联电路，一个一个排队走。

}
```
a
```
//范例代码的格式非常好，函数式编程。
```

要看的语法：nextQuery - v5
filter


- v6
解决不够快的问题
- v7
建立了请求池

- v9
text.replace(/ /g,'')

AJAX请求有可能是加密的， 在前段有些机制可以揭秘。
如何解决这类问题 ：npm install phantomjs -g
伪造一个浏览器，模拟用户登陆

var page = webpage.create();  相当于打开一个新tab
page.onResourceRequested = function(requestData, networkRequest) {//一个资源载入后，就触发这个函数 监听函数

- v14
把cookie存下来
为什么要cookie；cookie怎么用：

代理：怎么用代理
网站是用IP来封杀你的，所以可以用别的IP（代理），


### 生成URL
类比：通项公式和递进公式
就是分析怎么生成url，
社交网络：腾讯微博，从一个好友开始找五六层，就可以找到上百万的好友关系

自增id：通过加减乘除，遍历所有url
geohash： 分成一块一块的
bloom filter：把哈希简化的方式，做分布式时候，可以用bloom filter来做

移动app charles 加代理。AAP store有下载。
大致原理：但是明年苹果所有app要用https，无法截包，所以..... 时效性有问题


user-agent： 分析用了手机还是电脑。。。。浏览器幸好
reference： 你从什么网站过来的。
cookie：模拟登陆
content-type：请求的类别

请求的IP 如何改
x-forward-for
使用代理


反爬虫与反反爬虫
网站：
明杀404/验证码 && 暗杀

有一定流速控制：
3小时和一分钟检测 （实战才能发现）

所有的爬虫都是反向工程

要素伪造与发现：
假百度爬虫 user-agent 与IP穿帮
X-forward-for
是否访问了js，html （可能造一个伪造的按钮）

google -》执行js前后端校验

鼠标动式分析

### 优化：
dom解析
正则表达式解析

存取解析

分布式爬虫：scrapy engine
