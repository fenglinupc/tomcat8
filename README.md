# tomcat8
tomcat8源码编译，导入eclipse


安装ant
下载源码
进入到tomcat的源码目录
执行命令：ant ide-eclipse.会下载依赖的包
执行命令 ant

ant编译时有可能报错 the archive file.tar.gz doesn't exist
打开网址： https://repository.apache.org/content/repositories/snapshots/org/apache/commons/commons-dbcp2
修改对应的如下内容：

# ----- Commons DBCP, version 2.0 or later -----
#commons-dbcp.version=1.4
#commons-dbcp.home=${base.path}/commons-dbcp-${commons-dbcp.version}-src
#commons-dbcp-src.loc.1=${base-commons.loc.1}/dbcp/source/commons-dbcp-${commons-dbcp.version}-src.tar.gz
#commons-dbcp-src.loc.2=${base-commons.loc.2}/dbcp/source/commons-dbcp-${commons-dbcp.version}-src.tar.gz
commons-dbcp.version=_2.0.2-20141001.022814-10_
commons-dbcp.home=${base.path}/_commons-dbcp2-2.0.2_-SNAPSHOT-src
commons-dbcp-src.loc.1=https://repository.apache.org/content/repositories/snapshots/org/apache/commons/commons-dbcp2/_2.0.2-SNAPSHOT_/commons-dbcp2-${commons-dbcp.version}-src.tar.gz
commons-dbcp-src.loc.2=https://repository.apache.org/content/repositories/snapshots/org/apache/commons/commons-dbcp2/_2.0.2-SNAPSHOT_/commons-dbcp2-${commons-dbcp.version}-src.tar.gz

# ----- Commons Pool, version 2.1 or later -----
commons-pool.version=2.1
commons-pool.home=${base.path}/commons-pool2-${commons-pool.version}-src
commons-pool-src.loc.1=${base-commons.loc.1}/pool/source/commons-pool2-${commons-pool.version}-src.tar.gz
commons-pool-src.loc.2=${base-commons.loc.2}/pool/source/commons-pool2-${commons-pool.version}-src.tar.gz

打开eclipse。导入源码。
排除：
右键工程 -> build pathc -> configure build path -> Library
点击出错的位置 -> edit -> variable -> new 设置环境变量  
ANT_HOME： ant安装目录
TOMCAT_LIBS_BASE： build时下载的jar包目录

运行 org.apache.catalina.startup.Bootstrap 

完
