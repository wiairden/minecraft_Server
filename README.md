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
### 安装14.17.0 以上的NODEJS
```
apt-get install nodejs
```
### Linux一行命令快速安装

// 国内专用 gitee 加速源
```
wget -qO- https://gitee.com/mcsmanager/script/raw/master/setup_cn.sh | bash
```
// 原始源（科学上网）
```
wget -qO- https://raw.githubusercontent.com/mcsmanager/Script/master/setup.sh | bash
```
脚本适用于 x86_64 架构 Ubuntu/Centos/Debian/Archlinux 系统
执行完成后，使用 systemctl start mcsm-{web,daemon} 即可启动面板服务。
面板代码与运行环境自动安装在 /opt/ 目录下。
