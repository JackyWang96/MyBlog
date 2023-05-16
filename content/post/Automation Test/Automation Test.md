---
title: "Automation Test Note1"
date: 2023-05-16T22:05:21+10:00
draft: false
---

# Introduction
Starting today, I will begin my study of software testing. I will be documenting my notes after each learning session and sharing them as blog posts.
今天开始我将开始Java基础课程的教授。我会记录我每次备课的note并作为帖子发送至我的blog。



# Content
## 1. What is Cookie and Session? What's the different between Cookie, Session, Cache
在许多 web 应用中，session 信息会被储存在服务器端，而 cookie 中则储存一个 session ID，服务器通过这个 session ID 来识别特定用户

Session need to reply on cookie,cookie can live independently


### - **1.Cookie:**

1.1 Cookie，有时也用其复数形式Cookies。类型为“小型文本文件”，是某些网站为了辨别用户身份，进行Session跟踪而储存在用户本地终端上的数据

1.2 Reason: web程序是使用HTTP协议传输的，而HTTP协议是无状态的协议，对于事务处理没有记忆能力。
缺少状态意味着如果后续处理需要前面的信息，则它必须重传，这样可能导致每次连接传送的数据量增大。
另一方面，在服务器不需要先前信息时它的应答就较快。

1.3 Cookie有哪些缺陷 ？
1. 数量收到限制
2. 安全性问题
3. 浏览器可以禁用cookie




### - **2.Session:**

在计算机中，尤其是在网络应用中，称为“会话控制”。Session 对象存储特定用户会话所需的属性及配置信息。

**用户开一个浏览器，点击多个超链接，访问服务器多个web资源，然后关闭浏览器，整个过程称之为一个会话。**


2.1 Session的生命周期
根据需求设定，一般来说，半小时。举个例子，你登录一个服务器，服务器返回给你一个sessionID，
登录成功之后的半小时之内没有对该服务器进行任何HTTP请求，半小时后你进行一次HTTP请求，会提示你重新登录。


2.2 Session总结
Session是另一种记录客户状态的机制，不同的是Cookie保存在客户端浏览器中，而Session保存在服务器上。
客户端浏览器访问服务器的时候，服务器把客户端信息以某种形式记录在服务器上。这就是Session。客户端浏览器再次访问时只需要从该Session中查找该客户的状态就可以了。

2.3 cookie和session结合使用
1、存储在服务端：cookie仅存储一个session_id，然后具体的数据则是保存在session中。
如果用户已经登录，则服务器会在cookie中保存一个session_id，下次再次请求的时候，会把该session_id携带上来，服务器根据session_id在session库中获取用户的session数据。
就能知道该用户到底是谁，以及之前保存的一些状态信息。这种专业术语叫做server side session。

2、将session数据加密，然后存储在cookie中。这种专业术语叫做client side session。flask采用的就是这种方式，但是也可以替换成其他形式。


### - **3.cache:**

缓存是一种存储技术，其主要目标是提高数据获取的速度。缓存的工作原理是将一份数据的复制品存储在一个更快速访问的地方（如内存或本地硬盘上），
这样当再次需要这份数据时，系统就可以直接从缓存中获取，而不必再次从原始源（如远程服务器或数据库）获取。


3.1 浏览器可以从本地加载这些资源，而不是再次从服务器下载
Cache 是浏览器用于存储网页资源的地方，如图片、JavaScript文件和CSS样式表等，以便在用户下次访问相同的网页时，

3.2 cache的不同
Cache 主要关注的是资源，而不是用户信息。Cache 不会用于跟踪用户行为或存储用户的个人信息。

3.3 Lazy Loading
加载的工作原理是延迟对象的加载或初始化，直到真正需要它们时才进行。在网页开发中，懒加载通常用于图片或其他大型资源，
当用户滚动到这些资源的可视区域时，才开始加载它们。这可以减少网页的初始加载时间，提高用户体验。

**缓存关注的是快速访问已有数据，而懒加载关注的是延迟加载或初始化资源，直到真正需要它们时才进行。**