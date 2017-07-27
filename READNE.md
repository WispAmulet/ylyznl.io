# README

1. 购买 VPS 服务器，比如 [bandwagonhost]()

   进入 Control Panel，可以在自带的 root shell 中输入命令，也可以通过 [PUTTY]() 远程连接 VPS

   为了同时使用 ss，就不安装 CentOS-7 了😅

2. 安装 [Node.js]()

   首先安装 gcc

    ```code
    yum -y install gcc make gcc-c++ openssl-devel wget
    ```

   通过源码安装 Node.js：

   ```code
   // 进入想要安装的目录
   cd /usr/local

   // 下载 Node.js
   wget https://nodejs.org/dist/v8.2.1/node-v8.2.1.tar.gz

   // 解压，会自动生成文件夹
   tar zxvf node-v8.2.1.tar.gz

   // 进入生成的 node-v8.2.1/ 文件夹，配置并编译
   cd node-v8.2.1

   ./configure
   make

   // 安装
   make install
   ```

   结果提示：
   ```code
   WARNING: C++ compiler too old, need g++ 4.8 or clang++ 3.4.2 (CXX=g++)
   ```

   根据此[文章](http://www.cjjjs.com/paper/czxt/2017222114137150.html)所述升级 gcc 版本，提示：

   ```code
   configure: error: cannot run /bin/sh ../config.sub
   ```

   转用 yum 安装

   ```code
   wget -qO- https://rpm.nodesource.com/setup_8.x | bash -
   yum install -y nodejs
   ```

   检查是否安装成功

   ```code
   node -v
   ```
