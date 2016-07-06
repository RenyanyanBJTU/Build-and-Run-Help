# Build-and-Run-Help

##编译环境搭建
1、首先，按照页面 "[Establishing a Build Environment](https://github.com/openthos/openthos/wiki/Establishing-a-Build-Environment%28lollipop-x86%29)" 来配置编译和运行环境。
<br><br>
2、使用下面的命令安装git，然后按照页面"[OTO](https://github.com/openthos/OTO)"下载源码进行编译。
```
sudo apt-get install git
#info：如果提示需要输入用户信息，使用git config命令进行配置，例如配置用户邮箱信息
git config --global user.email "your email address"
```
##安卓.iso镜像运行环境补充
1、首先，确保使用的机器支持虚拟化，输入如下命令,如果出现vmx或者svm等信息说明支持，如果没有信息则可能无法运行安卓镜像。
```
egrep '(vmx|svm)' /proc/cpuinfo
```
2、安装qemu和qemu-kvm
```
sudo apt-get install qemu
sudo apt-get install qemu-kvm
```
3、输入如下命令查询kvm模块是否加载成功，若出现kvm和kvm-intel(intel 为CPU类型，若是AMD的则显示kvm-amd）等说明成功
```
lsmod | grep kvm 
```
如果没有，则运行如下命令加载模块
```
sudo modprobe kvm
sudo modprobe kvm-intel 
```
如果还是不成功，则是机器支持虚拟化但没有开启虚拟化，可以重启机器,在bios里的虚拟化选项里开启。
<br><br>
4、运行安卓的镜像
```
qemu-system-x86_64 -enable-kvm -m 2G -cdrom xxx/android_x86_64_6.0.iso -vga std
#notice：镜像的路径和全称要正确。另外分配的内存如果太小会启动不起来镜像。
```
