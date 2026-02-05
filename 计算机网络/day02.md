# HTTP请求报文和响应报文是怎样的，有哪些常见的字段？  
HTTP报文分为请求报文和响应报文。  
(1) 请求报文  
请求报文主要由请求行、请求头、空行、请求体构成。 
1. 请求行包括如下字段：  
     方法（Method）：指定要执行的操作，如 GET、POST、PUT、DELETE 等。  
     资源路径（Resource Path）：请求的资源的URI（统一资源标识符）。// URL(统一资源定位符)  
     HTTP版本（HTTP Version）：使用的HTTP协议版本，如 HTTP/1.1 或 HTTP/2.0。 
2. 请求头的字段较多，常使用的包含以下几个：
  Host：请求的服务器的域名。  
  Accept：客户端能够处理的媒体类型。   
  Accept-Encoding：客户端能够解码的编码类型。  
  Authorization：用于认证的凭证信息，比如token数据。 
  Content-Length：请求体的长度。 
  Content-Type：请求体的媒体类型。 
  Cookie：存储在客户端的cookie数据。 
  If-None-Match：资源的ETag值，用于缓存控制。  
  Connection：管理连接的选项，如 keep-alive。  
3. 空行是请求头部和请求主体之间的空行，用于分隔请求头部和请求主体。
4. 请求体通常用于 POST 和 PUT 请求，包含发送给服务器的数据。
  
(2) 响应报文
一个标准的HTTP响应报文通常包含状态行、响应头、空行、响应体。  
1. 状态行包含HTTP版本、状态码和状态消息
2. 响应头主要字段有
   Content-Type：指定响应主体的媒体类型。
   Content-Length：指定响应主体的长度（字节数）。
   Server：指定服务器的信息。
   Expires: 响应的过期时间，之后内容被认为是过时的。
   ETag: 响应体的实体标签，用于缓存和条件请求。
   Last-Modified： 资源最后被修改的日期和时间。
   Location：在重定向时指定新的资源位置。
   Set-Cookie：在响应中设置Cookie。
   Access-Control-Allow-Origin: 跨源资源共享（CORS）策略，指示哪些域可以访问资源。
3. 空行用于分隔请求头部和请求主体。
4. 响应体是服务端实际传输的数据，可以是文本、HTML页面、图片、视频等，也可能为空
# http有哪些请求方式 
1. GET：请求指定的资源。  
2. POST：向指定资源提交数据进行处理请求（例如表单提交）。  
3. PUT：更新指定资源。  
4. DELETE：删除指定资源。  
5. HEAD：获取报文首部，不返回报文主体。  
6. OPTIONS：查询服务器支持的请求方法。  
7. PATCH：对资源进行部分更新。
# GET请求和POST请求的区别  
1. 用途：GET请求通常用于获取数据，POST请求用于提交数据。
2. 数据传输：GET请求将参数附加在URL之后，POST请求将数据放在请求体中。
3. 安全性：GET请求由于参数暴露在URL中，安全性较低；POST请求参数不会暴露在URL中，相对更安全。
4. 数据大小：GET请求受到URL长度限制，数据量有限；POST请求理论上没有大小限制。
5. 幂等性：GET请求是幂等的，即多次执行相同的GET请求，资源的状态不会改变；POST请求不是幂等的，因为每次提交都可能改变资源状态。
6. 缓存：GET请求可以被缓存，POST请求默认不会被缓存。
   

