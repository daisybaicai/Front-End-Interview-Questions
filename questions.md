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
