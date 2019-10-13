---
layout: post
title: "HTTP 响应状态码"
description: "了解一下 HTTP 响应状态码的姿势."
date: 2019-10-11
tags: [提高姿势水平]
comments: true
share: true
---

> 了解一下 HTTP 响应状态码的姿势.

了解一下 HTTP 响应状态码. 别除了 200、404 剩下都是一脸懵逼. 就算不全知道起码知道属于哪个大类也行吧😂

* TOC
{:toc}

## 阅读资料

可以看这个网页: [HTTP response status codes](https://developer.mozilla.org/en-US/docs/Web/HTTP/Status), 肯定比网上东抄西抄自己都没学过的那种二手资料或是不知道怎么翻译出来的垃圾要好一点儿...

更纯正的原材料可以看:

* [RFC 2616 - Hypertext Transfer Protocol -- HTTP/1.1](https://tools.ietf.org/html/rfc2616): IETF 的, 排版还可以, 所有各章节都在一个页面上.
* [Hypertext Transfer Protocol -- HTTP/1.1](https://www.w3.org/Protocols/rfc2616/rfc2616.html): W3C 的, 就有个首页, 想看哪个还得跳转到其他页.

这里我们看下 [HTTP response status codes](https://developer.mozilla.org/en-US/docs/Web/HTTP/Status) / [HTTP 响应代码 - HTTP | MDN](https://developer.mozilla.org/zh-CN/docs/Web/HTTP/Status) 这个页面的开头:

> HTTP response status codes indicate whether a specific HTTP request has been successfully completed. Responses are grouped in five classes:<br/>
> 1. Informational responses (`100`–`199`),
2. Successful responses (`200`–`299`),
3. Redirects (`300`–`399`),
4. Client errors (`400`–`499`),
5. and Server errors (`500`–`599`).


也就是说, 和五五队有五个人(童比大雄、西野霞、源静萱、御坂美琪、藤浦焕)、IPv4 地址可划分为 A、B、C、D、E 五类 ——

<table class="mtable tab">
<tr> <th style="width:11%">Class</th> <th style="width:30%">Address range</th> <th style="width:59%">Supports</th> </tr>
<tr class="tcw"> <td><b>Class A</b></td><td>0.0.0.0 to 127.255.255.255</td><td>Supports 16 million hosts on each of 127 networks.</td></tr>
<tr class="tcw"> <td><b>Class B</b></td><td>128.0.0.0 to 191.255.255.255</td><td>Supports 65,000 hosts on each of 16,000 networks.</td></tr>
<tr class="tcw"> <td><b>Class C</b></td><td>192.0.0.0 to 223.255.255.255</td><td>Supports 254 hosts on each of 2 million networks.</td></tr>
<tr class="tcw"> <td><b>Class D</b></td><td>224.0.0.0 to 239.255.255.255</td><td>Reserved for <a href="/jargon/m/multicast.htm">multicast</a> groups.</td></tr>
<tr class="tcw"> <td><b>Class E</b></td><td>240.0.0.0 to 255.255.255.255</td>
<td>Reserved for future use, or research and development purposes.</td></tr>
</table>

的道理一样, HTTP 响应状态码也有五种.

插一句, 注意一下被 reserve 的那些 IPv4 地址: 

* *127.0.0.0* through *127.255.255.255* are reserved for loopback addresses. Although reserved, they are still part of the class A address group.
* *255.255.255.255* is reserved as the IPv4 Broadcast address.
* The blocks numerically at the start and end of classes A, B and C were originally reserved for special addressing or future features, i.e., *0.0.0.0/8* and *127.0.0.0/8* are reserved in former class A; *128.0.0.0/16* and *191.255.0.0/16* were reserved in former class B but are now available for assignment; *192.0.0.0/24* and *223.255.255.0/24* are reserved in former class C. While the *127.0.0.0/8* network is a Class A network, it is designated for loopback and cannot be assigned to a network.

数学不好智商不够等等总之不会划子网的可以看看 [IPv4 subnetting reference](https://en.wikipedia.org/wiki/Classless_Inter-Domain_Routing#IPv4_CIDR_blocks). 当然了, 以前贝老经理给我讲过所以我会划, 虽然我现在去写代码了. 而且你光划个子网没二层 VLAN 乃至没三层路由表卵用没有😂

## 笔记 & 科普

面试划重点的话, 似乎是该看 200、206、301、302、304、400、403、404、500、501、502、503 这些.

总之, 能找到就行, 你看个英语还不容易么...

### 1. [Informational 1xx](https://tools.ietf.org/html/rfc2616#section-10.1)

This class of status code indicates a provisional response, consisting only of the Status-Line and optional headers, and is terminated by an empty line. There are no required headers for this class of status code. Since HTTP/1.0 did not define any 1xx status codes, servers MUST NOT send a 1xx response to an HTTP/1.0 client except under experimental conditions.

A client MUST be prepared to accept one or more 1xx status responses prior to a regular response, even if the client does not expect a 100 (Continue) status message. Unexpected 1xx status responses MAY be ignored by a user agent.

Proxies MUST forward 1xx responses, unless the connection between the proxy and its client has been closed, or unless the proxy itself requested the generation of the 1xx response. (For example, if a  proxy adds a "Expect: 100-continue" field when it forwards a request, then it need not forward the corresponding 100 (Continue) response(s).)

### 2. [Successful 2xx](https://tools.ietf.org/html/rfc2616#section-10.2)

This class of status code indicates that the client's request was successfully received, understood, and accepted.

#### [200 OK](https://tools.ietf.org/html/rfc2616#section-10.2.1)

The request has succeeded. The information returned with the response is dependent on the method used in the request, for example:

<!-- 此处有 HTML 表格. -->
<table>
  <tr>
    <td>GET</td>
    <td>an entity corresponding to the requested resource is sent in the response</td>
  </tr>
  <tr>
    <td>HEAD</td>
    <td>the entity-header fields corresponding to the requested resource are sent in the response without any message-body</td>
  </tr>
  <tr>
    <td>POST</td>
    <td>an entity describing or containing the result of the action</td>
  </tr>
  <tr>
    <td>TRACE</td>
    <td>an entity containing the request message as received by the end server</td>
  </tr>
</table>

举例: 和楼下的 204 放在一起了.

#### [204 No Content](https://tools.ietf.org/html/rfc2616#section-10.2.5)

The server has fulfilled the request but does not need to return an entity-body, and might want to return updated metainformation. The response MAY include new or updated metainformation in the form of entity-headers, which if present SHOULD be associated with the requested variant.

If the client is a user agent, it SHOULD NOT change its document view from that which caused the request to be sent. This response is primarily intended to allow input for actions to take place without causing a change to the user agent's active document view, although any new or updated metainformation SHOULD be applied to the document currently in the user agent's active view.

The 204 response MUST NOT include a message-body, and thus is always terminated by the first empty line after the header fields.

举例 (200 + 204 的例子放在一起):

访问 [Seal Lee 的 YTB](https://www.youtube.com/channel/UC5ibEE0btMSv_D9A6ZllY4A) 可以看到:

![200-204](https://i.ibb.co/tXRQ5Pb/200-204.png) 

### 3. [Redirection 3xx](https://tools.ietf.org/html/rfc2616#section-10.3)

This class of status code indicates that further action needs to be taken by the user agent in order to fulfill the request.  The action required MAY be carried out by the user agent without interaction with the user if and only if the method used in the second request is GET or HEAD. A client SHOULD detect infinite redirection loops, since such loops generate network traffic for each redirection.

> Note: previous versions of this specification recommended a maximum of five redirections. Content developers should be aware that there might be clients that implement such a fixed limitation.

#### [304 Not Modified](https://tools.ietf.org/html/rfc2616#section-10.3.5)

If the client has performed a conditional GET request and access is allowed, but the document has not been modified, the server SHOULD respond with this status code. The 304 response MUST NOT contain a message-body, and thus is always terminated by the first empty line after the header fields.

The response MUST include the following header fields:

- Date, unless its omission is required by [section 14.18.1](https://tools.ietf.org/html/rfc2616#section-14.18.1)

If a clockless origin server obeys these rules, and proxies and clients add their own Date to any response received without one (as already specified by [&#x5b;RFC 2068&#x5d;, section 14.19](https://tools.ietf.org/html/rfc2068#section-14.19)), caches will operate correctly.

- ETag and/or Content-Location, if the header would have been sent in a 200 response to the same request
- Expires, Cache-Control, and/or Vary, if the field-value might differ from that sent in any previous response for the same variant

If the conditional GET used a strong cache validator (see [section 13.3.3](https://tools.ietf.org/html/rfc2616#section-13.3.3)), the response SHOULD NOT include other entity-headers. Otherwise (i.e., the conditional GET used a weak validator), the response MUST NOT include other entity-headers; this prevents inconsistencies between cached entity-bodies and updated headers.

If a 304 response indicates an entity not currently cached, then the cache MUST disregard the response and repeat the request without the conditional.

If a cache uses a received 304 response to update a cache entry, the cache MUST update the entry to reflect any new field values given in the response.      

举例:

![304](https://upload.cc/i1/2019/10/11/FWLO6z.png)

访问 RFC 2616 标准的材料的一个网站 [https://tools.ietf.org/html/rfc2616](https://tools.ietf.org/html/rfc2616) 时碰到的.

### 4. [Client Error 4xx](https://tools.ietf.org/html/rfc2616#section-10.4)

The 4xx class of status code is intended for cases in which the client seems to have erred. Except when responding to a HEAD request, the server SHOULD include an entity containing an explanation of the error situation, and whether it is a temporary or permanent condition. These status codes are applicable to any request method. User agents SHOULD display any included entity to the user.

If the client is sending data, a server implementation using TCP SHOULD be careful to ensure that the client acknowledges receipt of the packet(s) containing the response, before the server closes the input connection. If the client continues sending data to the server after the close, the server's TCP stack will send a reset packet to the client, which may erase the client's unacknowledged input buffers before they can be read and interpreted by the HTTP application.

#### [403 Forbidden](https://tools.ietf.org/html/rfc2616#section-10.4.4)

The server understood the request, but is refusing to fulfill it. Authorization will not help and the request SHOULD NOT be repeated. If the request method was not HEAD and the server wishes to make public why the request has not been fulfilled, it SHOULD describe the reason for the refusal in the entity.  If the server does not wish to make this information available to the client, the status code 404 (Not Found) can be used instead.

举例:

![403](https://i.ibb.co/s6hhgdn/403.png)

场景是这样: 

我用了这个脚本: [使用 PHP 去掉富文本中的尖角括号标签](https://liujunyi271828.github.io/2019-10-08/strip-tags-in-text/#正则表达式手法), 目标 URL 是: [https://tools.ietf.org/html/rfc2616](https://tools.ietf.org/html/rfc2616). 跑了这个脚本之后(注意把 `$fileHeaders` 给 `var_dump()` 出来)就 403 了.

#### [404 Not Found](https://tools.ietf.org/html/rfc2616#section-10.4.5)

The server has not found anything matching the Request-URI. No indication is given of whether the condition is temporary or permanent. The 410 (Gone) status code SHOULD be used if the server knows, through some internally configurable mechanism, that an old resource is permanently unavailable and has no forwarding address. This status code is commonly used when the server does not wish to reveal exactly why the request has been refused, or when no other response is applicable.

举例:

![404](https://i.ibb.co/tLTW7d1/404.png)

场景是这样: 

我访问了如下地址: [http://liujunyi271828.github.io/test](http://liujunyi271828.github.io/test). 然后就 404 了.

另外在 ThinkPHP 5.1 框架中, 可以通过 [MISS 路由](https://www.kancloud.cn/manual/thinkphp5_1/353972) 的方式来实现添加一个 404 页面. 注意: <span style="color:red">一旦设置了 MISS 路由, 相当于开启了强制路由模式.</span>

### 5. [Server Error 5xx](https://tools.ietf.org/html/rfc2616#section-10.5)

Response status codes beginning with the digit "5" indicate cases in which the server is aware that it has erred or is incapable of performing the request. Except when responding to a HEAD request, the server SHOULD include an entity containing an explanation of the error situation, and whether it is a temporary or permanent condition. User agents SHOULD display any included entity to the user. These response codes are applicable to any request method.

#### [500 Internal Server Error](https://tools.ietf.org/html/rfc2616#section-10.5.1)

The server encountered an unexpected condition which prevented it from fulfilling the request.

举例: ![500](https://i.ibb.co/T4FNDJ9/500.png)

场景是这样: 

还是用的这个脚本: [使用 PHP 去掉富文本中的尖角括号标签](https://liujunyi271828.github.io/2019-10-08/strip-tags-in-text/#正则表达式手法), 目标 URL 是: [https://www.ccyp.com/ccypContents?content_id=115628](https://www.ccyp.com/ccypContents?content_id=115628). 跑了这个脚本之后(也是把 `$fileHeaders` 给 `var_dump()` 出来)就 403 了.

#### [504 Gateway Timeout](https://tools.ietf.org/html/rfc2616#section-10.5.5)

The server, while acting as a gateway or proxy, did not receive a timely response from the upstream server specified by the URI (e.g. HTTP, FTP, LDAP) or some other auxiliary server (e.g. DNS) it needed to access in attempting to complete the request.

> Note: Note to implementors: some deployed proxies are known to return 400 or 500 when DNS lookups time out.

举例: 

![504](https://i.ibb.co/DGP6ytZ/504.png)

访问 [sm.ms](sm.ms) 即可得到.