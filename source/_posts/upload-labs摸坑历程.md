---
title: upload-labs摸坑历程
date: 2022-02-08 13:44:44
tags: 
cover: https://s2.loli.net/2022/02/08/mfnMdVakLjGXFYA.png
---
## 前言
希望你能够快乐依旧啊！！！~

## pass-01-页面js绕过
说做题，其实是骗人的哈哈，连burp suite都还不太会用（此处省略**字查询过程，==心累哇==）

言归正传，学习记录还是要记录一下的。
1.提示：
![图片.png](https://img-blog.csdnimg.cn/img_convert/0e498cf203125b3adfec79f4f568c4fe.png)
途中大致了解到：这种文件上传检测大致分为前端和后端？且检测分为白名单与黑名单。
此处可以尝试对数据进行抓包，但是啥也抓不到哈哈，
因此：判断是在前端js处进行的----->故，查看F12--->查看js代码.
![图片.png](https://img-blog.csdnimg.cn/img_convert/46137a645675ce6edb82f71c129debad.png)
有一个chickfile（）函数，其实就是判断文件类型函数，直接删去！
![图片.png](https://img-blog.csdnimg.cn/img_convert/340f6aae265fed78bda8652b77289890.png)好的，pass-01通过

## pass-02-文件类型绕过
pass-02第一种方法不可行了，查看提示：
*本pass在服务端对数据包的MIME进行检查！*
查询MIME：* web服务器使用MIME来说明发送数据的种类*
服务端检测可：对请求的数据MIME类型进行修改
**步骤**：1：bp抓包---------->2：修改类型EXE.application/octet-stream，==为==JPG.image/jpeg
![图片.png](https://img-blog.csdnimg.cn/img_convert/6fbd0fcf4c4bb20cdb79ec0b623bebd0.png)
此处犯了个毛病（==累==）filename与content-Type都要修改才能绕过！！
![图片.png](https://img-blog.csdnimg.cn/img_convert/2b2e5aae23603a16bbf607832772a02e.png)
**成功！！**==！==

## pass-03-文件其他可解析类型绕过
先看一下直接传php![图片.png](https://img-blog.csdnimg.cn/img_convert/9fb3c5b2c86bb20b7891167475de372d.png)
应该是黑名单？
这里可以试试.php7/.PHP5（之前看过一个文章，貌似系统会忽略文件后缀的大小写、空格以及后缀后面还可以跟==....==,都会被略去？
**.php5**成功上传==！==

### 依旧，听首歌再溜吧！
``下方为大佬传送门``

[请qiao这里](https://www.bilibili.com/video/BV1rc411h7ZQ).
