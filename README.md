# DOL开发环境配置
----------------
## 在虚拟机中打开**terminal**，输入指令
<pre><code>
$  sudo apt-get updata
$  sudo apt-get install ant
$  sudo apt-get installopenjdk-7-jdk
$  sudo apt-get install unzip
</code></pre>
## 用命令行下载文件到虚拟机中(TA给出文件中已经有了需要下载的文件可进行复制粘贴)
<pre><code>
$  sudo wget http://www.accellera.org/images/downloads/standards/systemc/systemc-2.3.1.tgz
sudo wget http://www.tik.ee.ethz.ch/~shapes/downloads/dol_ethz.zip
</pre></code>
## 解压文件
<pre><code>
$  mkdir dol                       //新建dol的文件夹
$  unzipdol_ethz.zip -d dol        //将dolethz.zip解压到 dol文件夹中
$  tar -zxvf systemc-2.3.1.tgz     //解压systemc
</code></pre>
## 编译systemc
<pre><code>
$  cdsystemc-2.3.1                //解压后进入systemc-2.3.1的目录下
$  mkdir objdir                   //新建一个临时文件夹objdir
$  cdobjdir                       //进入该文件夹objdir
$  ../configure CXX=g++--disable-async-updates    //运行configure
$  sudo make install            //编译
$  pwd                          //输出当前所在路径，需记录当前的工作路径
</code></pre>
![效果图](http://a2.qpic.cn/psb?/V10xhQuy3m7suY/8crmW08XMCmp7prJj0WxMBbIE4bEbG9QHBWIomPGaec!/b/dOUAAAAAAAAA&bo=.QG2AAAAAAADAGs!&rf=viewer_4)
![效果图](http://a2.qpic.cn/psb?/V10xhQuy3m7suY/Nni7oaiZk7Q7EndU6idcdJgxR1cz5zGTvjdwaRzhe74!/b/dG8BAAAAAAAA&bo=LgJWAAAAAAADAF8!&rf=viewer_4)
### 编译DOL

* cd ../dol
* 找到下面这两句话，修改build_zip.xml文件

><propertyname="systemc.inc" value="pwd输出的工作路径/include"/>
><propertyname="systemc.lib" value="pwd输出的工作路径/lib-linux/libsystemc.a"/>

* 最后编译 $  ant -f runexample.xml -Dnumber=1   

### 如果成功显示build successful
![效果图](http://a1.qpic.cn/psb?/V10xhQuy3m7suY/29lsXa.MVwI6POr*w14gOidiysIkhgw8L0CaEAfbO4A!/b/dHcBAAAAAAAA&bo=LgKpAQAAAAADAKE!&rf=viewer_4)
