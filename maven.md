<h4> <central>maven安装指南</central> </h4>

1. 首先到[官网](http://maven.apache.org/download.cgi)下载Maven文件, 如apache-maven-3.2.3-bin.tar.gz
2. 到Maven下载的目录下,将Maven文件解压  

	`wanghuan@WangHuan-PC-Ubuntu:~/Downloads/Maven$ tar -xvzf apache-maven-3.2.3-bin.tar.gz`  
3. 在安装目录旁创建一个平行的符号链接,方便日后的升级(如下,给解压后的文件apache-maven-3.2.3创建一个符号链接为maven)  

	`wanghuan@WangHuan-PC-Ubuntu:~/Downloads/Maven$ ln -s apache-maven-3.2.3 maven`

	执行wanghuan@WangHuan-PC-Ubuntu:~/Downloads/Maven$ ls -l, 后看可看到如下:  
		`total 6804`  
		`drwxrwxr-x 6 wanghuan wanghuan    4096 11月  3 23:02 apache-maven-3.2.3`  
		`-rw-r----- 1 wanghuan wanghuan 6956162 10月 18 11:23 apache-maven-3.2.3-bin.tar.gz`  
		`lrwxrwxrwx 1 wanghuan wanghuan      18 11月  3 23:05 maven -> apache-maven-3.2.3(看到此条记录,证明符号链接创建成功)`
4. 设置环境变量M2_HOME指向符号链接maven, 并把Maven安装目录下的/bin文件加到系统环境变量PATH中  

	`wanghuan@WangHuan-PC-Ubuntu:~/Downloads/Maven$ export M2_HOME=/home/wanghuan/Downloads/Maven/apache-maven-3.2.3`  
	`wanghuan@WangHuan-PC-Ubuntu:~/Downloads/Maven$ export PATH=$PATH:$M2_HOME/bin`

5. 使用gedit ~/.bashrc, 将上述两条命令加到系统shell脚本中.这样,每次启动一个终端,这些配置就能自动启动执行.  
6. 至此安装完成.运行一下两条指令,检查Maven安装.  

	`指令1: wanghuan@WangHuan-PC-Ubuntu:~/Downloads/Maven$ echo $M2_HOME`  

	显示:
	`/home/wanghuan/Downloads/Maven/apache-maven-3.2.3`  

	`指令2:  wanghuan@WangHuan-PC-Ubuntu:~/Downloads/Maven$ mvn -v`

	显示:  
	`Apache Maven 3.2.3 (33f8c3e1027c3ddde99d3cdebad2656a31e8fdf4; 2014-08-12T04:58:10+08:00)`
	`Maven home: /home/wanghuan/Downloads/Maven/apache-maven-3.2.3`  
	`Java version: 1.8.0_25, vendor: Oracle Corporation`  
  `Java home: /usr/lib/jvm/java-8-oracle/jre`  
	`Default locale: en_US, platform encoding: UTF-8`  
	`OS name: "linux", version: "3.13.0-39-generic", arch: "amd64", family: "unix"`  
