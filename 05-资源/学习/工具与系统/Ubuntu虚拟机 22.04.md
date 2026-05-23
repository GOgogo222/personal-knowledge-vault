
# 1_2

### 安装

[VMware中安装配置Ubuntu（2024最新版 超详细）_vmware安装ubuntu-CSDN博客](https://blog.csdn.net/air_729/article/details/143105854)

网络类型选择了 **NAT**

### 网络连接失败

虚拟网络编辑器-重启网络配置 ---》***成功！！！***

### 无法正常复制

~~~
sudo apt update
sudo apt install open-vm-tools open-vm-tools-desktop
sudo reboot
~~~

**注意**，其他的下载进程会影响**terminal**中的下载

这个tools还自带了**自适应收缩**功能
### 虚拟机暗装VS code

[Linux环境下的Ubuntu虚拟机安装VScode超详解-CSDN博客](https://blog.csdn.net/qq_45009309/article/details/136577582)

### 虚拟机的NAT模式

edit-visual network editor
新建一个适用于NAT模式的VMnet8网卡
配置这个网卡为NAT模式，并：
- 勾选 connect a host。。。
- 勾选 host-only 。。。

**记住**，VMnet0适用于brige模式，VMnet8适用于NAT模式

这也是我的DHCP Service和NAT Service总是有“毛病”的原因（这两个Service只服务于NAT模式！而NAT模式又需要勾选特定的选项！）

最后成功连上外网

# 1_5

Ctrl+' " ' = @

[ubuntu22.04无法实现复制粘贴的解决方法_ubuntu里的u盘不能粘贴-CSDN博客](https://blog.csdn.net/m0_59228082/article/details/148627354)
---》下载后可以使用“C+V”复制粘贴

[Ubuntu 22.04.3 常用软件和配置_ubuntu常用软件-CSDN博客](https://blog.csdn.net/xunyan6234/article/details/136054399)
---》总结得非常详细


代理的 **虚拟网卡模式** 不能随便开！！！
代理的 **虚拟网卡模式** 不能随便开！！！
代理的 **虚拟网卡模式** 不能随便开！！！

