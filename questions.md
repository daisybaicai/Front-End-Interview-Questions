<!--
 * @Description: Interview-questions
 * @Author: Daisy
 * @LastEditors: Please set LastEditors
 * @Date: 2019-04-14 13:44:20
 -->
#  Front-End-Interview Questions & Answers

> Click :star:if you like the project. Pull Request are highly appreciated.

### Table of Contents


| No. | Questions |
|---- | ---------
|1| [说一下 http和  https](#说一下-http和-https) |
|==2==| [tcp三次握手](#tcp三次握手) |
|3| [TCP和UDP的区别](#TCP和UDP的区别) |
|4| [WebSocket的实现和应用](#WebSocket的实现和应用) |
|5| [HTTP请求的方式，HEAD方式](#HTTP请求的方式，HEAD方式)|
|6| [几个很实用的BOM属性对象方法](#几个很实用的BOM属性对象方法) |
|7| [说一下http2.0](#说一下http2.0) |
|8| [400和 401、403状态码](#400和401、403状态码) |
|9| [fetch发送 post 2次请求的原因](#fetch发送-post-2次请求的原因) |
|10| [Cookie、sessionStorage、localStorage的区别](#Cookie、sessionStorage、localStorage的区别) |
|11| [说一下web worker](#说一下web-worker) |
|12| [iframe是什么有什么缺点？](#iframe是什么有什么缺点？)|
|13| [Doctype作用?严格模式与混杂模式如何区分？它们有何意义?](#Doctype作用?严格模式与混杂模式如何区分？它们有何意义?) |
|14| [Cookie如何防范 XSS攻击](#Cookie如何防范-XSS攻击) |
|15| [一句话概括  RESTFUL](#一句话概括-RESTFUL) |
|==16==| [讲讲 viewport和移动端布局](#讲讲-viewport和移动端布局) |
|17| [click在  ios上有 300ms延迟，原因及如何解决？](#click在-ios上有300ms延迟，原因及如何解决？) |
|18| [addEventListener参数](#addEventListener参数) |
|19| [介绍知道的http返回的状态码](#介绍知道的http返回的状态码) |
|20| [http常用请求头](#http常用请求头) |
|20| [http常用请求头](#http常用请求头) |


1. ### 说一下 http和  https

http是**超文本传输协议**，信息**是明文**传输，https则是具有安全性的**ssl加密传输协议**。

Https协议需要**ca**证书，费用较高。

使用不同的链接方式，端口也不同，一般而言，http协议的端口为**80**，https的端口为**443**

http的连接很简单，是**无状态**的；HTTPS协议是由**SSL+HTT**P协议构建的可进行加密传输、
身份认证的网络协议，比http协议安全。

**Https协议工作原理**：
- 客户使用httpsurl访问服务器，则要求web服务器建立ssl链接。
- web服务器接收到客户端的请求之后，会将网站的证书（证书中包含了公钥），返回或者说
传输给客户端。
- 客户端和web服务器端开始协商SSL链接的安全等级，也就是加密等级。
- 客户端浏览器通过双方协商一致的安全等级，建立会话密钥，然后通过网站的公钥来加密会
话密钥，并传送给网站。
- web服务器通过自己的私钥解密出会话密钥。
- web服务器通过会话密钥加密与客户端之间的通信。

**Https优缺点：**

**优点：**

- 协议可以认证用户和服务器，保证数据正确发送
- **SSL+HTTP**协**议加密传输，身份认证**，更安全
- HTTPS加密的在**搜索引擎排名更高**

**缺点：**
- 但 HTTPS握手阶段比较**费时**
- 缓存**不如HTTP高效**
- SSL证书也需要**钱**
- SSL证书需要绑定IP，**不能在同一个IP上绑定多个域名**，ipv4接受不了这样的消耗。

2. ### tcp三次握手

3. ### TCP和UDP的区别

TCP | UDP
---|---
面向连接 | 无连接|
面向字节流 | 面向报文|
1对1 | 1对1，1对多|
首部20字节 | 首部8字节|
面向连接可靠性传输 | 不可靠 |


——

4. ### WebSocket的实现和应用

WebSocket是**HTML5**中的协议，支持**持久连续**，http协议不支持持久性连接。Http1、0和HTTP1、1都不支持持久性的链接，HTTP1、1中的**keep-alive**，**将多个http请求合并为1**个。

HTTP的生命周期通过**Request**来界定，也就是Request一个Response，那么在Http1、0协议中，这次Http请求就结束了。在Http1、1中进行了改进，是的有一个connection：Keep-alive，也就是说，在一个Http连接中，可以发送多个Request，接收多个Response。但是必须记住，**在Http中一个Request只能对应有一个Response，而且这个Response是被动的，不能主动发起**。

WebSocket是基于Http协议的，或者说借用了Http协议来完成一部分握手，在握手阶段与Http是相同的。我们来看一个websocket握手协议的实现，基本是2个属性，**upgrade，connection**。


5. ### HTTP请求的方式，HEAD方式

**head**：类似于get请求，只不过返回的响应中没有具体的内容，用户获取报头

**options**：允许客户端查看服务器的性能，比如说服务器支持的请求方式等等。


6. ### 几个很实用的BOM属性对象方法

什么是Bom?Bom是**浏览器对象**。有哪些常用的Bom属性呢？

(1)location对象

- location.href--返回或设置当前文档的URL
- location.search--返回URL中的查询字符串部分。例
如http://www.dreamdu.com/dreamdu.php?id=5&name=dreamdu返回包括(?)后面的内容?id=5&name=dreamdu
- location.hash--返回URL#后面的内容，如果没有#，返回空
- location.host--返回URL中的域名部分，例如www.dreamdu.com
- location.hostname--返回URL中的主域名部分，例如dreamdu.comlocation.pathname--返回URL的域名后的部分。例如http://www.dreamdu.com/xhtml/返回/xhtml/
- location.port--返回URL中的端口部分。例如http://www.dreamdu.com:8080/xhtml/返回8080
- location.protocol--返回URL中的协议部分。例如http://www.dreamdu.com:8080/xhtml/返回(//)前面的内容http:
- location.assign--设置当前文档的URL
- location.replace()--设置当前文档的URL，并且在history对象的地址列表中移除这个URL
- location.replace(url);
- location.reload()--重载当前页面

(2)history对象

- history.go()--前进或后退指定的页面数history.go(num);
- history.back()--后退一页
- history.forward()--前进一页

(3)Navigator对象
 
- navigator.userAgent--返回用户代理头的字符串表示(就是包括浏览器版本信息等的字符串)
- navigator.cookieEnabled--返回浏览器是否支持(启用)cookie

7. ### 说一下http2.0

简要概括：http2、0是基于1999年发布的http1、0之后的首次更新。
- **提升访问速度**（可以对于，请求资源所需时间更少，访问速度更快，相比http1、0）
- **允许多路复用**：多路复用允许同时通过单一的HTTP/2连接发送多重请求-响应信息。改善了：
在http1、1中，浏览器客户端在同一时间，针对同一域名下的请求有一定数量限制（连接数量），
超过限制会被阻塞。
- **二进制分帧**：HTTP2、0会将所有的传输信息分割为更小的信息或者帧，并对他们进行二进制编码
- **首部压缩**
- **服务器端推送**

8. ### 400和 401、403状态码

(1)400状态码：**请求无效**
产生原因：前端提交数据的字段名称和字段类型与后台的实体没有保持一致,前端提交到后台的数据应该是json字符串类型，但是前端没有将对象**JSON.stringify**转化.
(2)401状态码：当前请求**需要用户验证**
(3)403状态码：服务器已经**得到请求，但是拒绝执行**


9. ### fetch发送 post 2次请求的原因

用fetch的post请求的时候，导致fetch第一次发送了一个**Options**请求，询问服务器是否支持修改的请求头，如果服务器支持，则在第二次中发送真正的请求.


10. ### Cookie、sessionStorage、localStorage的区别

|cookie| sessionStorage| localStorage|
---|---|---
|同源|同源|同源|
|http请求中携带|不携带|不携带|
|限制cookie只属于某个路径|||
|4K|5M|5M|
|cookie只在设置的cookie过期时间之前一直有效，即使窗口或浏览器关闭|始终有效，窗口或浏览器关闭也一直保存|仅在当前浏览器窗口关闭前有效|
|同源窗口中都是共享|同源窗口中都是共享||
|保存用户登录状态，跟踪用户行为，定制页面|

11. ### 说一下web worker

JS**单线程**，需要等待执行完才可执行，web worker运行在后台JS，独立于其他脚本，不影响性能，通过**postMessage**将结果返回主线程，复杂操作也不会影响主线程。

**如何创建webworker：**
检测浏览器对于webworker的支持性
创建webworker文件（js，回传函数等）
创建webworker对象

12. ### iframe是什么有什么缺点？

13. ### Doctype作用?严格模式与混杂模式如何区分？它们有何意义?

14. ### Cookie如何防范 XSS攻击
- http-only
- secure
- 用户输入校验

15. ### 一句话概括 RESTFUL

url资源 http方法

16. ### 讲讲 viewport和移动端布局

17. ### click在  ios上有 300ms延迟，原因及如何解决？
fastClick

18. ### addEventListener参数


19. ### 介绍知道的http返回的状态码
**2XX 成功**

- 200 OK，表示从客户端发来的请求在服务器端被正确处理
- 204 No content，表示请求成功，但响应报文不含实体的主体部分
- 205 Reset Content，表示请求成功，但响应报文不含实体的主体部分，但是与 204 响应不同在于要求请求方重置内容
- 206 Partial Content，进行范围请求

**3XX 重定向**

- 301 moved permanently，永久性重定向，表示资源已被分配了新的 URL
- 302 found，临时性重定向，表示资源临时被分配了新的 URL
- 303 see other，表示资源存在着另一个 URL，应使用 GET 方法获取资源
- 304 not modified，表示服务器允许访问资源，但因发生请求未满足条件的情况
- 307 temporary redirect，临时重定向，和302含义类似，但是期望客户端保持请求方法不变向新的地址发出请求

**4XX 客户端错误**

- 400 bad request，请求报文存在语法错误
- 401 unauthorized，表示发送的请求需要有通过 HTTP 认证的认证信息
- 403 forbidden，表示对请求资源的访问被服务器拒绝
- 404 not found，表示在服务器上没有找到请求的资源

**5XX 服务器错误**

- 500 internal sever error，表示服务器端在执行请求时发生了错误
- 501 Not Implemented，表示服务器不支持当前请求所需要的某个功能
- 503 service unavailable，表明服务器暂时处于超负载或正在停机维护，无法处理请求

20. ### http常用请求头
|**通用字段**| **作用**|
---|---|---
|Cache-Control|控制缓存的行为|
|Connection	| 浏览器想要优先使用的连接类型，比如 keep-alive|
|Date|	创建报文时间|
|Pragma|	报文指令|
|Via|	代理服务器相关信息|
|Transfer-Encoding|	传输编码方式|
|Upgrade|	要求客户端升级协议|
|Warning|	在内容中可能存在错误|
|**请求字段**|	**作用**|
|Accept|	能正确接收的媒体类型|
|Accept-Charset|	能正确接收的字符集|
|Accept-Encoding|	能正确接收的编码格式列表|
|Accept-Language|	能正确接收的语言列表|
|Expect|	期待服务端的指定行为|
|From|	请求方邮箱地址|
|Host|	服务器的域名|
|If-Match|	两端资源标记比较|
|If-Modified-Since|	本地资源未修改返回 304（比较时间）|
|If-None-Match|	本地资源未修改返回 304（比较标记）|
|User-Agent|	客户端信息|
|Max-Forwards|	限制可被代理及网关转发的次数|
|Proxy-Authorization|	向代理服务器发送验证信息|
|Range|	请求某个内容的一部分|
|Referer|	表示浏览器所访问的前一个页面|
|TE|	传输编码方式|
|响应字段|	作用|
|Accept-Ranges|	是否支持某些种类的范围|
|Age|	资源在代理缓存中存在的时间|
|ETag|	资源标识|
|Location|	客户端重定向到某个 URL|
|Proxy-Authenticate|	向代理服务器发送验证信息|
|Server|	服务器名字|
|WWW-Authenticate|	获取资源需要的验证信息|
|实体字段|	作用|
|Allow|	资源的正确请求方式|
|Content-Encoding|	内容的编码格式|
|Content-Language|	内容使用的语言|
|Content-Length|	request body 长度||
|Content-Location|	返回数据的备用地址|
|Content-MD5|	Base64加密格式的内容 MD5检验值|
|Content-Range|	内容的位置范围|
|Content-Type|	内容的媒体类型|
|Expires|	内容的过期时间|
|Last_modified|	内容的最后修改时间|

21. ### 常见浏览器兼容性问题与解决方案？

(1)浏览器兼容问题一：**不同浏览器的标签默认的外补丁和内补丁不同** 
问题症状：随便写几个标签，不加样式控制的情况下，各自的margin 和padding差异较大。
碰到频率:100%
解决方案：**CSS里  * {margin:0;padding:0;}**
备注：这个是最常见的也是最易解决的一个浏览器兼容性问题，几乎所有的CSS文件开头都会用通配符*来设置各个标签的内外补丁是0。
(2)浏览器兼容问题二：**块属性标签float后，又有横行的margin情况下，在IE6显示margin比设置的大**
问题症状:常见症状是IE6中后面的一块被顶到下一行
碰到频率：90%（稍微复杂点的页面都会碰到，float布局最常见的浏览器兼容问题）
解决方案：**在float的标签样式控制中加入 display:inline**;将其转化为行内属性
备注：我们最常用的就是div+CSS布局了，而div就是一个典型的块属性标签，横向布局的时候我们通常都是用div float实现的，横向的间距设置如果用margin实现，这就是一个必然会碰到的兼容性问题。
(3)浏览器兼容问题三：**设置较小高度标签（一般小于10px），在IE6，IE7，遨游中高度超出自己设置高度** 
问题症状：IE6、7和遨游里这个标签的高度不受控制，超出自己设置的高度
碰到频率：60%
解决方案：给超出高度的标签设置**overflow:hidden**;或者设置行高**line-height** 小于你设置的高度。
备注：这种情况一般出现在我们设置小圆角背景的标签里。出现这个问题的原因是IE8之前的浏览器都会给标签一个最小默认的行高的高度。即使你的标签是空的，这个标签的高度还是会达到默认的行高。
(4)浏览器兼容问题四：**行内属性标签，设置display:block后采用float布局，又有横行的margin的情况，IE6间距bug**
问题症状：IE6里的间距比超过设置的间距
碰到几率：20%
解决方案 ： 在display:block;后面加入display:inline;display:table;
备注：行内属性标签，为了设置宽高，我们需要设置display:block;(除了input标签比较特殊)。在用float布局并有横向的margin后，在IE6下，他就具有了块属性float后的横向margin的bug。不过因为它本身就是行内属性标签，所以我们再加上display:inline的话，它的高宽就不可设了。这时候我们还需要在**display:inline后面加入display:talbe。**
(5) 浏览器兼容问题五：**图片默认有间距** 
问题症状：几个img标签放在一起的时候，有些浏览器会有默认的间距，加了问题一中提到的通配符也不起作用。
碰到几率：20%
解决方案：**使用float属性为img布局**
备注 ： 因为img标签是行内属性标签，所以只要不超出容器宽度，img标签都会排在一行里，但是部分浏览器的img标签之间会有个间距。去掉这个间距使用float是正道。（我的一个学生使用负margin，虽然能解决，但负margin本身就是容易引起浏览器兼容问题的用法，所以我禁止他们使用）
(6) 浏览器兼容问题六：**标签最低高度设置min-height不兼容** 
问题症状：因为min-height本身就是一个不兼容的CSS属性，所以设置min-height时不能很好的被各个浏览器兼容
碰到几率：5%
解决方案：如果我们要设置一个标签的最小高度200px，需要进行的设置为： **{min-height:200px; height:auto !important; height:200px; overflow:visible;}**
备注：在B/S系统前端开时，有很多情况下我们又这种需求。当内容小于一个值（如300px）时。容器的高度为300px；当内容高度大于这个值时，容器高度被撑高，而不是出现滚动条。这时候我们就会面临这个兼容性问题。
(7)浏览器兼容问题七：**透明度的兼容CSS设置** 
一般在ie中用的是filter:alpha(opacity=0);这个属性来设置div或者是块级元素的透明度，而在firefox中，一般就是直接使用opacity:0,对于兼容的，一般的做法就是在书写css样式的将2个都写上就行，就能实现兼容

22. ### CSS居中的几种方案
    1.absolute + 负margin
        .wp {
            position: relative;
        }
        .box {
            position: absolute;;
            top: 50%;
            left: 50%;
            margin-left: -50px;
            margin-top: -50px;
        }
    2.flex
        display: flex;
        justify-content: center;
        align-items: center;
    3.absolute + transform
        .wp {
            position: relative;
        }
        .box {
            position: absolute;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
        }
    4.absolute + calc
        .wp {
            position: relative;
        }
        .box {
            position: absolute;;
            top: calc(50% - 50px);
            left: calc(50% - 50px);
        }
    5.absolute + margin auto
        .wp {
            position: relative;
        }
        .box {
            position: absolute;;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            margin: auto;
        }
23. ### 清除浮动

- 父类div定义height
- 结尾空div clear:both
- 父类div定义伪类 :after和zoom
- 父类div定义overflow: hidden

24. ### 性能优化

- 降低请求量：合并资源，减少HTTP 请求数，minify / gzip 压缩，webP，lazyLoad。
- 加快请求速度：预解析DNS，减少域名数，并行加载，CDN 分发。
- 缓存：HTTP 协议缓存请求，离线缓存 manifest，离线数据缓存localStorage。
- 渲染：JS/CSS优化，加载顺序，服务端渲染，pipeline。

25. ### 页面经典布局

26. ### 从输入 URL 到页面加载完成的过程

（1）首先做 DNS 查询，如果这一步做了智能 DNS 解析的话，会提供访问速度最快的 IP 地址回来
（2）接下来是 TCP 握手，应用层会下发数据给传输层，这里 TCP 协议会指明两端的端口号，然后下发给网络层。网络层中的 IP 协议会确定 IP 地址，并且指示了数据传输中如何跳转路由器。然后包会再被封装到数据链路层的数据帧结构中，最后就是物理层面的传输了
（3）TCP 握手结束后会进行 TLS 握手，然后就开始正式的传输数据
（4）数据在进入服务端之前，可能还会先经过负责负载均衡的服务器，它的作用就是将请求合理的分发到多台服务器上，这时假设服务端会响应一个 HTML 文件
（5）首先浏览器会判断状态码是什么，如果是 200 那就继续解析，如果 400 或 500 的话就会报错，如果 300 的话会进行重定向，这里会有个重定向计数器，避免过多次的重定向，超过次数也会报错
（6）浏览器开始解析文件，如果是 gzip 格式的话会先解压一下，然后通过文件的编码格式知道该如何去解码文件
（7）文件解码成功后会正式开始渲染流程，先会根据 HTML 构建 DOM 树，有 CSS 的话会去构建 CSSOM 树。如果遇到 script 标签的话，会判断是否存在 async 或者 defer ，前者会并行进行下载并执行 JS，后者会先下载文件，然后等待 HTML 解析完成后顺序执行，如果以上都没有，就会阻塞住渲染流程直到 JS 执行完毕。遇到文件下载的会去下载文件，这里如果使用 HTTP 2.0 协议的话会极大的提高多图的下载效率。
（8）初始的 HTML 被完全加载和解析后会触发 DOMContentLoaded 事件
（9）CSSOM 树和 DOM 树构建完成后会开始生成 Render 树，这一步就是确定页面元素的布局、样式等等诸多方面的东西
（10）在生成 Render 树的过程中，浏览器就开始调用 GPU 绘制，合成图层，将内容显示在屏幕上了

输入url后，首先需要找到这个url域名的服务器ip,为了寻找这个ip，浏览器首先会寻找缓存，查看缓存中是否有记录，缓存的查找记录为：浏览器缓存-》系统缓存-》路由器缓存，缓存中没有则查找系统的hosts文件中是否有记录，如果没有则查询DNS服务器，得到服务器的ip地址后，浏览器根据这个ip以及相应的端口号，构造一个http请求，这个请求报文会包括这次请求的信息，主要是请求方法，请求说明和请求附带的数据，并将这个http请求封装在一个tcp包中，这个tcp包会依次经过传输层，网络层，数据链路层，物理层到达服务器，服务器解析这个请求来作出响应，返回相应的html给浏览器，因为html是一个树形结构，浏览器根据这个html来构建DOM树，在dom树的构建过程中如果遇到JS脚本和外部JS连接，则会停止构建DOM树来执行和下载相应的代码，这会造成阻塞，这就是为什么推荐JS代码应该放在html代码的后面，之后根据外部央视，内部央视，内联样式构建一个CSS对象模型树CSSOM树，构建完成后和DOM树合并为渲染树，这里主要做的是排除非视觉节点，比如script，meta标签和排除display为none的节点，之后进行布局，布局主要是确定各个元素的位置和尺寸，之后是渲染页面，因为html文件中会含有图片，视频，音频等资源，在解析DOM的过程中，遇到这些都会进行并行下载，浏览器对每个域的并行下载数量有一定的限制，一般是4-6个，当然在这些所有的请求中我们还需要关注的就是缓存，缓存一般通过Cache-Control、Last-Modify、Expires等首部字段控制。 Cache-Control和Expires的区别在于Cache-Control使用相对时间，Expires使用的是基于服务器 端的绝对时间，因为存在时差问题，一般采用Cache-Control，在请求这些有设置了缓存的数据时，会先 查看是否过期，如果没有过期则直接使用本地缓存，过期则请求并在服务器校验文件是否修改，如果上一次 响应设置了ETag值会在这次请求的时候作为If-None-Match的值交给服务器校验，如果一致，继续校验 Last-Modified，没有设置ETag则直接验证Last-Modified，再决定是否返回304

27. ### http2.0

http2.0的特性如下
1、内容安全，应为http2.0是基于https的，天然具有安全特性，通过http2.0的特性可以避免单纯使用https的性能下降

2、二进制格式，http1.X的解析是基于文本的，http2.0将所有的传输信息分割为更小的消息和帧，并对他们采用二进制格式编码，基于二进制可以让协议有更多的扩展性，比如引入了帧来传输数据和指令

3、多路复用，这个功能相当于是长连接的增强，每个request请求可以随机的混杂在一起，接收方可以根据request的id将request再归属到各自不同的服务端请求里面，另外多路复用中也支持了流的优先级，允许客户端告诉服务器那些内容是更优先级的资源，可以优先传输，

4.Header 压缩

在 HTTP 2.0 中，使用了 HPACK 压缩格式对传输的 header 进行编码，减少了 header 的大小。并在两端维护了索引表，用于记录出现过的 header ，后面在传输过程中就可以传输已经记录过的 header 的键名，对端收到数据后就可以通过键名找到对应的值。

5.服务器push

在 HTTP 2.0 中，服务端可以在客户端某个请求后，主动推送其他资源。

可以想象以下情况，某些资源客户端是一定会请求的，这时就可以采取服务端 push 的技术，提前给客户端推送必要的资源，这样就可以相对减少一点延迟时间。当然在浏览器兼容的情况下你也可以使用 prefetch 。

28. ### Flex布局

29. ### 三栏布局

30. ### 异步资源加载

31. ### JS防抖节流

32. ### JS垃圾回收

33. ### CMD,AMD

34. ### 对象深度克隆

35. ### 传入函数参数只执行一次

36. ### ajax 实现Promise

37. ### Object.defineProperty,Proxy

38. ### Event Loop