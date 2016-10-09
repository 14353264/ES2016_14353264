#配置DOL的实验报告
*姓名：石梦涵*  
*学号：14353264*  
*班级：14M3*
### 一、DOL框架描述
>分布式操作层（DOL）是一个程序的并行应用软件开发框架。DOL允许指定基于计算Kahn进程网络模型的应用范围和特点，基于SystemC仿真引擎。此外，劳工部提供了基于XML规范的格式来描述一个多处理器系统上的并行应用程序的实现，包括结合和映射。
### 二、DOL安装步骤
1. 安装Ubuntu
2. 安装必要的环境  
$	sudo apt-get update  
$	sudo apt-get install ant  
$ 	sudo apt-get install openjdk-7-jdk  
$	sudo apt-get install unzip
3. 解压文件  
$	sudo mkdir dol //新建dol文件夹  
$	sudo unzip dol_ethz.zip -d dol //将压缩包解压  
$	sudo tar -zxvf systemc-2.3.1.tgz //解压systemc
4. 编译systemc  
$	cd systemc-2.3.1 //解压后进入systemc-2.3.1的目录下  
$	sudo mkdir objdir //新建一个临时文件夹objdir 
$	cd objdir //进入该文件夹objdir  
$	sudo ../configure CXX=g++ --disable-async-updates //运行configure(能根据系统的环境设置一下参数，用于编译)  
$	sudo make install  
$	sudo pwd  
5. 编译dol  
$	cd ../dol //进入dol文件夹  
修改build_zip.xml文件  
**修改为:**
![](http://p1.bpimg.com/567571/ea8fdc3def39ade9.png)
$	sudo ant -f build_zip.xml all //编译
运行第一个例子，测试安装是否成功

### 三、实验心得  
配置过程中遇到的主要问题是一开始的openjdk-7-jdk环境安装fail了导致后面的编译不成功，在不明白原因的情况下花了大量的时间重装了两遍环境也还是不行，最后解决方法是更改了源，将默认的美国的源换成了阿里巴巴的aliyun。所以遇到问题不能慌乱盲目尝试，要仔细分析找到问题再对症下药，反而事半功倍。  
**报错截图：**
![](http://p1.bpimg.com/567571/8ac57cdc6c20cb6a.png)