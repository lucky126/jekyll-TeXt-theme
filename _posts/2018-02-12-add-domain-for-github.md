---
layout: post
title: 给github page加上域名
key: 20180212
tags:
  - 域名
  - domain
  - github
lang: zh-Hans
---

## 给github page加上域名

继昨天成功完成了建站工作以后，甚是高兴。突发奇想，手里不是正好有一堆可以使用的域名么。拿出来一个用上，岂不是更好，总比github给的二级域名好记忆吧。
<!--more-->
于是，继续从度娘上寻找相关文章，这次很简单，只需要去域名服务商那里修改cname和@两个设置即可，cname指向username.github.io即可，@指向这个域名通过ping得到的ip即可。

可是就是这么简单的事情还是出现了一些状况。配置好了，提交后生效了。访问那个.com的域名，发现github给了个错误页面，我去，这是咋回事？检查一下设置吧，ping了一下两个域名，ip是一样的呀。看来dns这里没有设置错误。再请教一下度娘吧，发现问题了，原来github的repo上面有个setting的选项叫做custom domain，在这里将.com域名加上就好了。

果真没错，一切终于正常了。