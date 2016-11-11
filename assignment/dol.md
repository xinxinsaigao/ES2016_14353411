#DOL实例分析&编程
----------------------
##example中各文件的含义：
-----------------------------
<pre>
src文件夹：各进程（生产者，消费者，处理模块等）的功能定义；文件夹内包含.c和.h两种  
文件，就是实现的模块，即*.dol的框架的功能描述；  
.xml文件：系统架构即模块连接方式定义；定义模块与模块之间的连接方式；其中proces是  
框架，sw_channal是线，connection就是连线的脉络。
</pre>
----------------------------------------------------------------------------------------------------
##exmaple1分析：

生产者和消费者只是发送和接受信号，其中的处理过程在square中做；所以example1只需要在square中处理即可；
一开始example1的迭代次数为2，square中改动迭代次数即可；
##example2分析： 
进程定义与example1很类似，只是这里有3个square；因此处理的思路也很清晰，只需要在.xml文件将迭代次数N减1即可；  
如图：  
可以看到N==2，即迭代次数为2；i^4不为i^8;  

--------------------------------------------------------------
##example运行结果：
----------------------
### 在虚拟机中打开**terminal**，输入指令:  
<pre><code>
$	cd dol
$	cd build/bin/main
$	ant -f runexample.xml -Dnumber=1
$	ant -f runexample.xml -Dnumber=2
</code></pre>
**在每次改动example之后要删除build并重新编译一次build.zip.xml**

-------------------------------------------------------------------------
##得到最终结果
<p>example1结果图</p>
![example1结果图](http://a2.qpic.cn/psb?/V10xhQuy3m7suY/BDkEbTw2VTMLAEvw44t.YWbd2XB6QQmWIrQmGfpBXZU!/b/dI0BAAAAAAAA&bo=RAGlAQAAAAADAMQ!&rf=viewer_4)    
---------------------------------------------------------------------------------------------
<p>example2结果图</p>
![example2结果图](http://a1.qpic.cn/psb?/V10xhQuy3m7suY/cbAR7HcKefgLg3b105Ej4Ba*PAkvOjU108w9hu5fcCo!/b/dHcBAAAAAAAA&bo=SAGcAQAAAAADAPE!&rf=viewer_4)  
<p>example1 dot图</p>
![dot1](http://a2.qpic.cn/psb?/V10xhQuy3m7suY/MCRtxxtLIzr8zdb5nWmvuuedoBZxOapC0y11yArRuFM!/b/dAkBAAAAAAAA&bo=NAJ5AQAAAAADAGs!&rf=viewer_4)
<p>example2 dot图</p>
![dot2](http://a3.qpic.cn/psb?/V10xhQuy3m7suY/zZOX8SqZRTv78tYG24F9hNeUJb88SqQJ8M29ArKLIGU!/b/dAoBAAAAAAAA&bo=lwI6AQAAAAADAIs!&rf=viewer_4)  
##实验感想  
-------------  

这次实验不是很难，只需要改少量代码即可。主要是理解代码每部分的作用，生产者和消费者之间的关系。在嵌入式的框架上也是老师讲过的，实验的处理方法和终端的运行TA上课和课件也有很详细的说明，难度不大；但对于dol的编程有了更深的理解。  

----------------------------------------------------------------------------------------------------









