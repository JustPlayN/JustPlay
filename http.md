#### http(hyper text transfer protocal超文本传输协议)简介

定义：用于从万维网（www:world wide web）服务器传输超文本到本地浏览器的传输协议

http是基于TCP/IP通信协议来传输数据的

可传递的数据包括：html文件、图片、查询结果等

HTTP协议工作于客户端-服务端架构为上。浏览器作为HTTP客户端通过URL向HTTP服务端即WEB服务器发送所有请求。Web服务器根据接收到的请求后，向客户端发送响应信息

#### http特点

1. 简单快速：客户向服务器请求服务时，只需传送请求方法和路径。请求方法常用的有POST、GET、DELETE等。每种方法规定了客户与服务器联系的类型不同。由于HTTP协议简单，使得HTTP服务器的程序规模小，因而通信速度很快。
2. 灵活：HTTP允许传输任意类型的数据对象。正在传输的类型由Content-Type加以标记。
3. 无连接：无连接的含义是限制每次连接只处理一个请求。服务器处理完客户的请求，并收到客户的应答后，即断开连接。采用这种方式可以节省传输时间
4. 无状态：HTTP协议是无状态协议。无状态是指协议对于事务处理没有记忆能力。缺少状态意味着如果后续处理需要前面的信息，则它必须重传，这样可能导致每次连接传送的数据量增大。另一方面，在服务器不需要先前信息时它的应答就较快。
5. 支持B/S(brower/server)及C/S(client/serve)模式。(Client/Server是建立在局域网的基础上的.Browser/Server是建立在广域网的基础上的.)

#### uri和url

uri：http统一资源标示符，用来传输数据和建立连接

url：是一种特殊的uri，包含了用来查找某个资源的准确信息

#### http与https

1. HTTPS协议是由SSL+HTTP协议构建的可进行加密传输、身份认证的网络协议 
   要比http协议安全
2. Web服务器启用SSL需要获得一个服务器证书并将该证书与要使用SSL的服务器绑定。 http和https使用的是完全不同的连接方式,用的端口也不一样,前者是80,后者是443。
3. https协议需要到ca申请证书，一般免费证书很少，需要交费。
   http是超文本传输协议，信息是明文传输，https 则是具有安全性的ssl加密传输协议
   http和https使用的是完全不同的连接方式用的端口也不一样,前者是80,后者是443。
   HTTPS协议是由SSL+HTTP协议构建的可进行加密传输、身份认证的网络协议 要比http协议安全
4. **HTTPS 在保护用户隐私，防止流量劫持方面发挥着非常关键的作用，但与此同时，HTTPS 也会降低用户访问速度，增加网站服务器的计算资源消耗**。(详情：http://www.cnblogs.com/mylanguage/p/5635524.html)

#### post与get请求

1. get和post本质上都是tcp链接，并无差别。但是由于http的规定和服务器的限制，导致他们在应用过程中体现出了不同

2. get请求：浏览器会把header和data一并发出去，服务器响应200

3. post请求：浏览器先发送header，服务器响应100 continue，浏览器再发送data，服务器响应200

4. firefox浏览器post请求只发送一次

5. get请求会被浏览器主动缓存，post不会（需要手动设置）

6. get请求参数会被完整的保留在浏览器历史记录里，post的参数不会被保留

7. get请求可以被收藏为书签，post不能

8. post比get安全：get参数直接暴露在url上，post参数在http消息主体中，且post参数不会被保留在浏览器历史和web服务器日志中

9. get请求只有application/x-www-form-urlencoded编码格式

10. post有多种编码格式：application/x-www-form-urlencoded 或 multipart/form-data

11. get参数类型只接受ASCII字符，post没有限制，允许二进制

12. **GET**:特定浏览器和服务器对URL长度有限制，例如 IE对URL长度的限制是2083字节(2K+35)。对于其他浏览器，如Netscape、FireFox等，理论上没有长度限制，其限制取决于操作系 统的支持。

    **POST**:由于不是通过URL传值，理论上数据不受 限。但实际各个WEB服务器会规定对post提交数据大小进行限制，Apache、IIS6都有各自的配置。

