# 分布式系统与云计算结课报告
## 作业一 虚拟机
### 问题1 安装虚拟机操作系统
下载Oracle VM VirtualBox软件，新建虚拟电脑，命名为test。
在 [Ubuntu网站](http://releases.ubuntu.com/20.04/)下载操作系统，将.ios文件分配到test，

### 问题2 配置虚拟机网络为桥接
将网络设置由网络地址转换改为桥接网卡


### 问题3 ping
在host主机中ping通虚拟机内的guest主机，在guest主机的命令行中输入ifconfig命令，查看guest主机的IP地址为192.168.1.29。在host主机的命令行中输入命令：ping 192.168.1.29,得到下图的结果：
ifconfig
ping 192.168.1.29


### 问题4 开通http server服务
在guest主机中安装Git，然后将仓库克隆下来：
sudo apt install git
git clone https://github.com/zxuqian/html-css-examples.git

