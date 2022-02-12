---
title: HTML学习笔记
date: 2022-02-02 21:23:59
tags:
cover: https://s2.loli.net/2022/02/02/UOlfPaLdhGJq9T2.jpg
---

## 目录

### 1、html定义

### 2.video标签

### 3.下载资源及audio标签

### 4.img标签

### 5.标签、超链接

### 6：h标签

### 7：meta标签

### 8：div标签:

### 9:span标签

### 10：pre标签

### 11：p标签

### 12：center标签

### 13：form（形式、表格、表单）标签

### 14：单选、复选、下拉、上传标签

### 15：u标签

### 16：table（表格）标签

### 17:frameset（框架页）标签

### 18：iframe（n. 内嵌框架；内联框架）标签

### 19:属性

### 20:hr标签（横线）

### 21:html实体编码、转义、特殊符号

1、html定义


2、HTML文档展示



 

代码解释：

1）<!DOCTYPE html>

声明/告诉 浏览器：以下 文档/代码 为html 代码

@<~~~~>为开始标签   </~~~~>为结束标签   

2）HTML头部<head>标签

里边定义一些元信息（描述信息的信息<给浏览器看的>），给浏览器/搜索引擎 看的 读者看的内容多在<body>里

3）<meta charset="utf-8">

meta表示标签，charset表示标签属性名， =   “（属性值）”

代码含义：表示浏览器在进行渲染时要用“utf-8”编码显示（因为写代码时用的编码形式为utf-8）确保不会出现乱码

4）<!--注释内容（浏览器渲染时不会显示出来）-->

5）<meta keywords=“微信，即使通讯”>      标签含义：搜索引擎中的关键字



注意：

1）<html>   <head>开始结束标签是必须写的

2）代码（此时为txt文本形式）用记事本打开可能会出现乱码，此处用Notepad++打开，语言选择H--->HTML(方便检查）

3.HTML展示步骤



 1）将txt后缀改为html（用浏览器打开）



 左上角为文档标题

2）查看源代码



2.video标签


 不使用flash愿意：手机发烫、安全性问题

3.下载资源及audio标签
<audio controls>
        <!--audio:音频-->
        <source src="test.mp3">
        <!--不能加type="mp3/m4a"，否则不能播放-->
        您的浏览器不支持audio标签
    </audio>
4.img标签
 <img src="好看1/1.png">
    <!--当前目录的好看1文件夹中的1.png图片-->
    <img src="../好看1/1.png">
    <!--当前目录的好看1文件夹上一层文件夹中的1.png图片(每上一层多一个../)-->
    <img src="https://img1.baidu.com/it/u=2285020071,1228316245&fm=253&fmt=auto&app=138&f=JPEG?w=500&h=341">
    <!--原文件为网址链接时，若链接没有图片后缀，不用自己添加-->
    <img src="C:\Users\13912\Desktop/hei.jpg">
    <!--绝对路径-->
    <!--原图片直接复制路径（要补充图片名）则为\，如果在windows下建议用\\，或者用/代替正\-->
    <!--<img src="C:/Users/13912/Desktop/hei.jpg">-->
    <!--还可以加上协议：<img src="file:\\\C:\Users\13912\Desktop/hei.jpg">，file：\\表示协议名-->
    <!--直接用html携带图片方法：图片转base64,缺点：图片不易维护、修改-->
5.<a>标签、超链接
 <a href="https://kannikanyun.github.io">点我跳转Kanyun's Blog</a>
    <!--href:超文本引用、超链接地址指向（hypertext reference<参考、引用>-->
    <br>
    <br>
    <a href="https://kannikanyun.github.io" target="_blank">点我跳转Kanyun's Blog</a>
    <!--
        arget的所有取值以及它们的含义：

        _blank：在新窗口中打开；

        _self：默认。在相同的框架中打开；

        _parent：在父框架集中打开；

        _top：在整个窗口中打开；
        -->
    <br>
    <br>

    <a href="C:\Users\13912\Desktop\html学习\笔记文件\target測試\白.html">点我跳转白.html</a>
    <br>
    <br>
    <a href="C:\Users\13912\Desktop\html学习\笔记文件\target測試\白.html" target="_blank">点我跳转白.html</a>
    <!--使用时注意路径选择-->

    <!--


    -->
    <br>
    <br>
    <a href="mailto:1391205637@qq.com">点我弹出邮箱客户端发送邮件</a>
    <!--mailto后可以写更多参数-->
    <br>
    <br>

    <a href="javascript:alert('别灰心')">点我试试看</a>
    <!--在javascript中，alert的用法是“alert(在对话框中显示的纯文本)”。-->
    <br>
    <br>

    <!--


    -->
    <!--锚标记-->
    <a href="#标记">点我</a>
    <br>
    <br>
    <div id="标记1">定位到这里1</div>
    <!--
        在网址后跟  #标记  ，则自动定位到该标记所在位置
    -->
    <br>
    <br>
    <div id="标记" style="position: absolute; top: 9000px;">通过”点我“您来到了这里</div>
    <!--div可理解为：显示文本标签，“position：absolute”是绝对定位的意思，
        单纯的使用absolute属性并不会其效果，
        需要配合“top bottom left right ”属性才能看到效果。
    -->
6：h标签
<h1>第1句话</h1>
    <h2>第2句话</h2>
    <h3>第3句话</h3>
    <h4>第4句话</h4>
    <h5>第5句话</h5>
    <h6>第6句话</h6>
    <h7>第7句话</h7>
    <!--
        h后的数字超过6后，文本均为普通文本
    -->
    <br>
    <br>
7：meta标签
<!--
        6：meta标签之keywords：为文档定义了一组关键字，某些搜索引擎在遇到这些关键字时，
        会用这些关键字对网站的网页进行分类

    -->
    <meta name="keywords" content="嘻嘻哈哈，数码宝贝，世界值得">

    <!--
        7：meta标签之description
        对网站页面进行描述，方便搜索引擎展示给用户，使用户了解网站性质

    -->
    <meta name="description" content="你才这个网站是干嘛的？">
8：div标签:
 <!--
        8:div标签:用来控制、布局的，包裹文本或别的标签
        每一个div标签会自动换行
    -->
    <div style="color: aqua;">看看我的颜色吧</div>
    <br>
9:span标签
<!--
        9:span标签:用来控制、布局的，包裹文本或别的标签
        每一个div标签不会会自动换行
    -->
    <span style="color: red">我是小红</span>
    &nbsp;
    <!--转义字符：表示英文空格-->
    <br />
    <br />
    <!--<br/>标签标准写法，（无开始和结束的标签后可以加上/-->
10：pre标签
<!--
        10：pre标签：pre 元素可定义预格式化的文本。
         被包围在 pre 元素中的文本通常会保留空格和换行符。
    -->
    <pre>
        你  不知道 你，

        所以 你 是你。
    </pre>
11：p标签
<!--
        11：p标签：表示段落（自动换行且间距大
    -->
    <p>
        &nbsp; &nbsp;&nbsp;&nbsp;《悟》
    <p>
        <br />
        悟道休言天命，
        <br />

        修行勿取真经。
        <br />

        一悲一喜一枯荣，
        <br />

        哪个前生注定？
        <br />

    </p>
    <p>
        袈裟本无清净，
        <br />

        红尘不染性空。
        <br />

        幽幽古刹千年钟，
        <br />

        都是痴人说梦。
    </p>
    <br />
12：center标签
 <!--
        12：center标签：使内容水平居中
    -->
    <center>
        <div>修为成佛，在求。</div>
        <div>悟为明性，在知。</div>
        <div>修行以行制性，悟道以性施行，觉者由心生律，修者以律制心。</div>
        <div>不落恶果者有信无证，住因住果、住念住心，如是生灭。</div>
        <div>不昧因果者无住而住，无欲无不欲，无戒无不戒，如是涅槃。</div>
    </center>
    <br />
13：form（形式、表格、表单）标签
<!--
        13：form（形式、表格、表单）标签
    -->

    <input type="text" value="此处输入不会提交奥">
    <br />
    <br />

    <input type="text" placeholder="占位文本且不提交">
    <br />
    <br />

    <!--placeholder:n,占位符、占位文本-->

    <input type="button" value="我只是一个按钮">
    <br />
    <br />

    <input type="submit" value="我是一个可以提交的按钮（如果在form表单中的话,haha)">
    <!--
        如果在form表单中：submit按钮可以将所有输入内容都提交给服务器
                         如果是button按钮，则需要给button重新定义一个事件
    -->
    <br />
    <br />
    <button>我是一个单纯的按钮类型</button>
    <br />
    <br />
    <!--
        在url中能看到的方式传参：get传参（我们的值通过http协议传给服务器）
    -->
    <!--
        https://www.baidu.com/s?wd=我爱的人
        ？前为url，？后为参数、参数之间用&分隔
        wd――查询的关键词(Keyword) 
    -->
    <form action="https://www.baidu.com/s" target="_blank" method="get">
        <input type="text" name="wd">

        <input type="submit" value="点我提交内容到百度">
    </form>
    <!--
        eage的url关键字参数为wd，所以要用name=”wd”
        target可要可不要
    -->
    <br />
    <br />
    <pre>
    用户名：  <input type="text"/>
        <br/>
    用户密码：<input type="password"/>
    <!--如果password中有值，则可以F12源代码中Elements中将password修改为text
        （源代码经浏览器渲染后，内存里的代码的一个状态《动态执行后的代码》
    如果直接右键，则显示的是真正源代码-->
    </pre>
    <br/>
    <br/>
    <input type="hidden" value="能看到我吗?">
    <!--
        隐藏域
        注重功能能上的使用，却又不想让用户看到的参数
    -->
    <br/>
    <br/>
    <input type="hidden" type="text" value="看不到我吧"/>
    <!--
        html中：当属性冲突时会以第一个为准
    -->
    <br/>
14：单选、复选、下拉、上传标签
 <!--
        14：单选、复选、下拉、上传标签
    -->

    <!--checkbox标签：复选框
        复选框用的value 指的是这个复选框的值
    -->
    <input type="checkbox"/>何必再说
    <input type="checkbox"/>看你看云
    <input type="checkbox"/>忘了那片海
    <br/>
    <br/>
    <!--radio标签：单选框
        单选框用的value 和复选框一样
        在后台如果你想得到复选框的内容 就是value 来取
        当你在接收表单数据的页面中获取数据时，
        得到的就是value的值
    -->
    <!--单选框情况1-->
    请选择：
    <input type="radio" name="gender" value="1" />男
    <input type="radio" name="gender" value="1" />女
    </br>
    </br>
    请选择：

    <!--单选框情况2-->
    <input type="radio" name="sex" />男
    <input type="radio" name="sex" />女
    <br/>
    <br/>
    <!--单选框情况3:默认选择一个-->
    默认选择一个1
    <input type="radio" name="a" />男
    <!--此方法失效，不清楚原因@_@
        问题解决：各组选项之间name不能相同
    -->
    <input type="radio" name="a" checked/>女
    <br/>
    <br/>
    默认选择一个2
    <!--单选框情况4:默认选择一个-->
    <input type="radio" name="b" checked="true"/>男
    <input type="radio" name="b" />女
    <!--单选框情况3:默认选择一个-->
    <br/>
    <br/>
    默认选择一个3
    <input type="radio" name="c"/>男
    <input type="radio" name="c" checked="checked"/>女
    <br/>
    <br/>
    <!--下拉框/（标签）select
        选项给浏览者看的
        给计算机看的是value中的值
    -->
    <select>
        <option>--请选择--</option>
        <option value="1">葡萄</option>
        <option value="橘子">橘子</option>
        <option>香蕉</option>
        <option>柠檬</option>
        <option>香水</option>
    </select>
    <br/>
    <br/>
    <!--文本域textarea
        rows：行数（即高度）
        cols：列数（即宽度）
    -->
    <textarea rows="1" cols="50">
        你是朵夜云，在我梦幻的天空浮泛
    </textarea>
    <br/>
    <br/>
    <!--上传标签file-->
    <input type="file">
    <br/>
    <br/>
15：u标签
<!--15：u标签-->
    <ul>
        <li>john</li>
        <li>yohn</li>
        <li>smith</li>
    </ul>
    
    <br/>
    <br/>
    <ul type="circle">
        <li>john</li>
        <li>yohn</li>
        <li>smith</li>
    </ul>
    <br/>
    <br/>
    <ul type="disc">
        <li>john</li>
        <li>yohn</li>
        <li>smith</li>
    </ul>
    <br/>
    <br/>
16：table（表格）标签
<!--16：table（表格）标签
        table：（桌子）、表格
        border：边框（像素为1？）
        thead：表格头
        tr：表格行
        th：表格头中的列
        td：表格列
        colspan：标签属性（合并列《跨列数》）数字为合并的列数
        rowspan：合并行（跨行数）
        align：对齐
        提示：外层标签（head、body、foot）可以不要，效果一样
    -->
    <table border="1">
        <thead>
            <tr>
                <th colspan="2" align="center">理想与现实的距离</td>
            </tr>
            
        </thead>
        <tbody>
            <tr>
                <th>理想</th>
                <th>当下</th>
            </tr>

            <tr>
                <td>距离</td>
                <td>little</td>
            </tr>

            <tr>
                <td>时间</td>
                <td>little</td>
            </tr>
        </tbody>

        <tfoot>
            <tr>
                <td>求和</td>
                <td>max</td>
            </tr>
        </tfoot>
17:frameset（框架页）标签
<!doctype html>
<!--文档类型声明 html-->
<html>

<!--17：frameset标签
        frameset:n.框架型 框架的 框架页 框架集
        frame：n. 框架，边框；
    -->
<!----混合框架---->
<frameset rows="50%,50%">
    <frame src="frame框架1.html"></frame>
    <frameset cols="50%,50%">
        <frame src="frame框架2.html"></frame>
        <frame src="frame框架3.html"></frame>
    </frameset>
</frameset>

</html>
18：iframe（n. 内嵌框架；内联框架）标签
<!--
        18：iframe（n. 内嵌框架；内联框架）标签
        作用：在当前页面中嵌套
        src中可以是：图片、html、网址等....
        1:vh就是当前屏幕可见高度的1%，也就是说
        height:100vh == height:100%;
        2:vw就是当前屏幕宽度的1%
        3:scorlling:n、v：滚动、卷动

        注意：一些老的浏览器不支持iframe
                如果得不到支持，iframe是不可见的
    -->
    <br/>
    <br/>
        <iframe src="https://www.4399.com/" style="width: 100vw; height:100vh" frameborder="0" scorlling="no"></iframe>
    <!--
        <iframe src="https://www.baidu.com" style="width: 100vw; height:100vh frameborder="0" scorlling="no";></iframe>
        这个网站不能嵌入，尚未解决（请求被拒绝）
    -->
    我在iframe之外奥
    <br/>
    <br/>
19:属性
 <!--
        19:属性
        每一个html标签，都有自己的属性，通过设置属性的值，达到想要的外观或功能性效果
        当然，也可以在标签上通过name="value"的方式写自定义的属性，以共自己调用
        常见的属性；
        width、height、id（唯一,相当于给每一个标签起唯一的一个标识）、name（可相同）、
        src（img、iframe等标签中）、value（值）、type、align（文本对齐方式）
    -->
20:hr标签（横线）
<!--
        20:hr标签（横线）
    -->
    下面有一条横线
    <hr>
    滴
    <hr>
    上面也有一条横线
    <br/>
    <br/>
21:html实体编码、转义、特殊符号
<!--
        21:html实体编码、转义、特殊符号
    -->
    M<sup>2</sup>

    <pre>HTML特殊转义字符对照表</pre>
    https://tool.oschina.net/commons?type=2

    <pre>HTML 中有用的字符实体</pre>
    https://www.w3school.com.cn/html/html_entities.asp

    <pre>URL 编码参考手册</pre>
    https://www.runoob.com/tags/html-urlencode.html

    <pre>URL 汉字转html实体符号 中文转&#开头的字符编码</pre>
    https://seo.juziseo.com/tools/entity/ html实体编码
    <h1 style="color: lawngreen;" align="center">html see you soon</h1>

​
