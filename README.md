# 树莓派开minecraft Server
## 1.安装JAVA环境

### 下载JDK安装包，也可以自己去官网下载(若没有 wget，请安装它 yum install wget)
```
wget https://img.zeruns.tech/down/jdk-8u261-linux-arm64-vfp-hflt.tar.gz
```
### 创建安装目录
```
mkdir /usr/local/java/
```
### 解压当前目录下的JDK压缩文件
```
tar -zxvf jdk-8u261-linux-arm64-vfp-hflt.tar.gz -C /usr/local/java/
```
### 设置环境变量(安装 VIM 输入 yum -y install vim)
```
vim /etc/profile
```
### 在末尾添加对应变量
Shift + Insert黏贴一下内容
```
export JAVA_HOME=/usr/local/java/jdk1.8.0_261
export JRE_HOME=${JAVA_HOME}/jre
export CLASSPATH=.:${JAVA_HOME}/lib:${JRE_HOME}/lib
export PATH=${JAVA_HOME}/bin:$PATH
```
### 应用修改后的环境变量
```
source /etc/profile
```
### 软链接程序到环境变量中
```
ln -s /usr/local/java/jdk1.8.0_261/bin/java /usr/bin/java
```
### 测试是否安装正常，显示 java version "1.8.0_261" 则为正常
```
java -version
```
## 2. 安装msc面板  

### Linux一行命令快速安装

### 手动安装
#### 切换到安装目录。如果不存在，请提前用'mkdir /opt/'创建它。
cd /opt/


#### 下载运行时环境（Node.js）。如果你已经安装了Node.js 14+，请忽略此步骤。
wget https://nodejs.org/dist/v14.19.1/node-v14.19.1-linux-x64.tar.gz

### 解压档案
tar -zxvf node-v14.19.1-linux-x64.tar.gz

### 添加系统环境变量
ln -s /opt/node-v14.19.1-linux-x64/bin/node /usr/bin/node
ln -s /opt/node-v14.19.1-linux-x64/bin/npm /usr/bin/npm


### 准备好安装目录
mkdir /opt/mcsmanager/
cd /opt/mcsmanager/

### 下载MCSManager
wget https://github.com/MCSManager/MCSManager/releases/latest/download/mcsmanager_linux_release.tar.gz
tar -zxf mcsmanager_linux_release.tar.gz


### 安装依赖库
./install-dependency.sh


### 请打开两个终端或屏幕
# 启动守护进程
./start-daemon.sh

### 启动面板前端(在第二个终端)
./start-web.sh
