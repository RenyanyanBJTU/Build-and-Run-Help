#Ubuntu 16.04 LTS 运行环境
<h4> 1、基本信息</h4>
Linux版本：Ubuntu 16.04 LTS  64位<br>
内核版本：4.4.0-21-generic <br>
内存大小：编译需要至少4G <br>
gcc版本：version 5.3.1 <br>
<h4> 2、安装编译时所需的各个版本信息（搭建编译环境的命令） </h4>
```
sudo apt-get install -y git-core gnupg flex bison gperf build-essential zip curl libc6-dev libncurses5-dev x11proto-core-dev libx11-dev libreadline6-dev libgl1-mesa-dev g++-multilib schedtool tofrodos python-markdown pngquant libxml2-utils xsltproc zlib1g-dev libxext-dev openjdk-7-jdk gettext bc mtools lib32z1 lib32ncurses5 python-pip libyaml-dev python-dev squashfs-tools
sudo pip install prettytable Mako pyaml dateutils --upgrade
```
缺少git时可以用下列命令安装
```
sudo apt-get install git
```
这时安装的git版本是 2.7.4
<h4>3、安装运行时所需的软件（搭建运行环境的命令）</h4>
```
sudo apt-get install qemu
```
安装的qemu的版本是QEMU emulator version 2.5.0
