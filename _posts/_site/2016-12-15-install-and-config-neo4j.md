# neo4j安装及配置


1. 从官网 https://neo4j.com/download/?ref=home 下载社区版，这里下载windows(exe)，貌似比较难下载，附上下载好的文件。

2. 一路默认安装即可见到如下界面：

	- 通过1选择要存储数据的位置；
	- 数据库初始配置修改，目前主要使用到两项功能需要修改：
		- load本地csv文件，注释掉`dbms.directories.import=import`，不然只能自己在1中目录下创建import目录放入本地文本。
		```
		# This setting constrains all `LOAD CSV` import files to be under the `import` directory. Remove or uncomment it to
		# allow files to be loaded from anywhere in filesystem; this introduces possible security problems. See the `LOAD CSV`
		# section of the manual for details.
		# dbms.directories.import=import
		```
		- Python连接数据库，改dbms.security.auth\_enabled为`false`，否则连接不上。
		```
		# Require (or disable the requirement of) auth to access Neo4j
		dbms.security.auth\_enabled=false
		```
3. 返回点击start启动服务，点击`http://localhost:7474/`会打开web界面，使用默认账户(neo4j)、密码(neo4j)即可登录。
4. 根据官方tutorial学习使用，本地已经整理该{-[tutorial](http://gitlab.gridsum.com/research/jd-category/issues/15)-}。














