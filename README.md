# 树莓派开minecraft Server
## 1.安装JAVA环境

### 下载JDK17安装包，也可以自己去官网下载(若没有 wget，请安装它 yum install wget)
```
wget https://download.oracle.com/java/17/latest/jdk-17_linux-aarch64_bin.tar.gz
```
### 创建安装目录
```
mkdir /usr/local/java/
```
### 解压当前目录下的JDK压缩文件
```
tar jdk-17_linux-aarch64_bin.tar.gz -C /usr/local/java/
```

## 2. 安装msc面板  
### 手动安装
#### 切换到安装目录。如果不存在，请提前用'mkdir /opt/'创建它。
```
cd /opt/
```

#### 下载运行时环境（Node.js）。如果你已经安装了Node.js 14+，请忽略此步骤。
```
wget https://nodejs.org/dist/v14.19.1/node-v14.19.1-linux-x64.tar.gz
apt install npm
```
重新链接 npm 到 Node.js：
有时候手动安装 npm 后可能需要手动重新链接到 Node.js。可以尝试运行以下命令重新链接 npm 到 Node.js：
```
sudo ln -s /usr/bin/nodejs /usr/bin/node
```

### 解压档案
```
tar -zxvf node-v14.19.1-linux-x64.tar.gz
```
### 添加系统环境变量
```
ln -s /opt/node-v14.19.1-linux-x64/bin/node /usr/bin/node
ln -s /opt/node-v14.19.1-linux-x64/bin/npm /usr/bin/npm
```

### 准备好安装目录
```
mkdir /opt/mcsmanager/
cd /opt/mcsmanager/
```
### 下载MCSManager
```
wget https://github.com/MCSManager/MCSManager/releases/latest/download/mcsmanager_linux_release.tar.gz  
```
```
tar -zxf mcsmanager_linux_release.tar.gz
```

### 安装依赖库
```
./install-dependency.sh
```
### 3. 启动mcs面板
### 请打开两个终端或屏幕
# 启动守护进程
```
./start-daemon.sh
```
### 启动面板前端(在第二个终端)
```
./start-web.sh
```
### 启动命令为:
```
你的java路径/bin/java -jar 你的服务器jar文件名称.jar nogui
```
### foege安装参考
```
https://www.rainyun.com/docs/guide/Minecraft/mc-forge/
```
