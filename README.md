# ORANGE'S 一个操作系统的实现---学习笔记  

## 编译安装bochs虚拟机  
1. 官网下载bochs源码
<pre><code>
$ wget https://nchc.dl.sourceforge.net/project/bochs/bochs/2.6/bochs-2.6.tar.gz
</code></pre>

2. 配置编译选项  
<pre><code>
$ ./configure --enable-debugger --enable-disasm --includedir=/usr/include/gtk-2.0/</code></pre>
> 若未安装gtklib2.0，需通过apt安装  

3. 修改Makefile文件 
<pre><code>
$ diff Makefile Makefile_modified 
92c92
< LIBS =  -lm -lgtk-x11-2.0 -lgdk-x11-2.0 -lpangocairo-1.0 -latk-1.0 -lcairo -lgdk_pixbuf-2.0 -lgio-2.0 -lpangoft2-1.0 -lpango-1.0 -lgobject-2.0 -lglib-2.0 -lfontconfig -lfreetype
---
> LIBS =  -lm -lgtk-x11-2.0 -lgdk-x11-2.0 -lpangocairo-1.0 -latk-1.0 -lcairo -lgdk_pixbuf-2.0 -lgio-2.0 -lpangoft2-1.0 -lpango-1.0 -lgobject-2.0 -lglib-2.0 -lfontconfig -lfreetype -lz -lrt -lpthread
</code></pre>

4. make编译  

5. sudo make install安装
