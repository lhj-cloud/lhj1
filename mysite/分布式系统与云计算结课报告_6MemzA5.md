# 分布式系统与云计算结课报告
分布式系统与云计算结课报告,包括作业一虚拟机与作业二云盘。

## 作业一 虚拟机
### 问题1 安装虚拟机操作系统
下载Oracle VM VirtualBox软件，新建虚拟电脑，命名为test。
在 [Ubuntu网站](http://releases.ubuntu.com/20.04/)下载操作系统，将.ios文件分配到test。
![在这里插入图片描述](https://img-blog.csdnimg.cn/20210109171731320.png)


### 问题2 配置虚拟机网络为桥接
将网络设置由网络地址转换改为桥接网卡
![在这里插入图片描述](https://img-blog.csdnimg.cn/20210109171756805.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQ0NzY0MzY2,size_16,color_FFFFFF,t_70)

### 问题3 ping
在host主机中ping通虚拟机内的guest主机：在guest主机的命令行中输入ifconfig命令，查看guest主机的IP地址为192.168.1.29。在host主机的命令行中输入命令：ping 192.168.1.29,得到下图的结果：

```python
ipconfig
ping 10.196.12.198
```

![主机](https://img-blog.csdnimg.cn/20210109172048616.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQ0NzY0MzY2,size_16,color_FFFFFF,t_70)

![在这里插入图片描述](https://img-blog.csdnimg.cn/2021010917254992.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQ0NzY0MzY2,size_16,color_FFFFFF,t_70)


在虚拟机终端中输入以下命令：
```python
sudo apt install net-tools
ifconfig
ping 10.196.13.51
```

![在这里插入图片描述](https://img-blog.csdnimg.cn/20210109172449680.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQ0NzY0MzY2,size_16,color_FFFFFF,t_70)
![在这里插入图片描述](https://img-blog.csdnimg.cn/20210109172503945.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQ0NzY0MzY2,size_16,color_FFFFFF,t_70)

![在这里插入图片描述](https://img-blog.csdnimg.cn/2021010917281822.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQ0NzY0MzY2,size_16,color_FFFFFF,t_70)


### 问题4 开通http server服务
在guest主机中安装Git，然后将仓库克隆下来：

```python
sudo apt install git
git clone https://github.com/zxuqian/html-css-examples.git
```
![在这里插入图片描述](https://img-blog.csdnimg.cn/20210109173026726.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQ0NzY0MzY2,size_16,color_FFFFFF,t_70)

![在这里插入图片描述](https://img-blog.csdnimg.cn/20210109173054140.png)
在host主机中通过浏览器访问guest主机中的http服务中的html文件,结果如下图演示:
![在这里插入图片描述](https://img-blog.csdnimg.cn/20210109173250755.png)
![在这里插入图片描述](https://img-blog.csdnimg.cn/20210109173235632.png)
host主机中的浏览器页面：
![在这里插入图片描述](https://img-blog.csdnimg.cn/20210109173449642.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQ0NzY0MzY2,size_16,color_FFFFFF,t_70)




## 作业二  使用django开发一个云盘系统
### 问题1 配置运行环境
下载Git Bash，Vscode软件并完成配置

### 问题2 新建Django工程
在GitHub服务器上新建一个仓库，在本地git bash命令行中运行以下命令，再
将生成的密钥配置到GitHub的ssh密钥中：

```bash
ssh-keygen
cat ~/.ssh/id_rsa.pub
```

克隆仓库地址：git clone 仓库地址
进入仓库名目录：cd 仓库名
在仓库目录运行命令新建Django工程，再进入新建工程的目录：

```bash
 django-admin startproject yunpan 
cd yunpan
```

创建yunpan工程的app，命名为miaochuan：

```bash
python manage.py startapp miaochuan 
```

使用以下命令在网址https://127.0.0.1:8000中验证app是否创建成功：

```bash
python manage.py runserver
```



### 问题3 完善前端界面
在VScode中克隆仓库，增加一个.gitignore 文件，将所有不需要提交到仓库的sqlite3文件和pyc文件过滤：

![在这里插入图片描述](https://img-blog.csdnimg.cn/20210109174002975.jpg)
克隆修改代码，创建superuser之后展示页面如下：

![在这里插入图片描述](https://img-blog.csdnimg.cn/20210109194818751.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQ0NzY0MzY2,size_16,color_FFFFFF,t_70)

![在这里插入图片描述](https://img-blog.csdnimg.cn/20210109194927770.jpg?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQ0NzY0MzY2,size_16,color_FFFFFF,t_70)
文件提交界面：
![在这里插入图片描述](https://img-blog.csdnimg.cn/2021011119091426.jpg?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQ0NzY0MzY2,size_16,color_FFFFFF,t_70)

![在这里插入图片描述](https://img-blog.csdnimg.cn/20210111191336361.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQ0NzY0MzY2,size_16,color_FFFFFF,t_70)






