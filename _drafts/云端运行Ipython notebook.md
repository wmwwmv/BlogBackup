title: 云端运行Ipython notebook
date: 2016/8/1 6:23:44
categories: 笔记
tags:
comments: true
fancybox:
---



conda的使用
Anaconda多环境多版本python配置指导
http://www.jianshu.com/p/d2e15200ee9b


每次重新接入需要运行
export PATH="/root/anaconda3/bin:$PATH"

安装后加入变量
$ export PATH=/root/home/qy/anaconda/bin:$PATH
保存后source ~/.bash_profile（立即执行）

外部访问
http://essun.blog.51cto.com/721033/1712773

使用conda实现的完整教程
https://zhuanlan.zhihu.com/p/20226040

https://ask.hellobi.com/blog/seng/3084
https://ask.hellobi.com/blog/seng/3154
加入后少一句
$ exec $SHELL -l
参考
http://www.jianshu.com/p/1b0b50d1cd24

需要先安装Python


输入`ipython`
密码 lsc47442426

Out[2]: 'sha1:9a898266dbd7:2d1523682ef4609c2a87756130da269705b020f1'

输入exit退出

# Set options for certfile, ip, password, and toggle off browser auto-opening
c.NotebookApp.certfile = u'/root/.jupyter/mycert.pem'
c.NotebookApp.keyfile = u'/root/.jupyter/mykey.key'
# Set ip to '*' to bind on all interfaces (ips) for the public server
c.NotebookApp.ip = '*'
c.NotebookApp.password = u'sha1:9a898266dbd7:2d1523682ef4609c2a87756130da269705b020f1'
c.NotebookApp.open_browser = False

# It is a good idea to set a known, fixed port for server access
c.NotebookApp.port = 10011

https://45.32.255.216:10011/ipython/tree#notebooks

中间如果有科学计算包安装不上的话需要升级一下pip`pip install --upgrade pip`
`matplotlib`这个包安装会有点慢，需要耐心等待


Anacodna之conda与 virtualenv对比使用教程，创建虚拟环境
https://segmentfault.com/a/1190000005828284




查看系统是否开启ipv6
a）通过网卡属性查看
命令：ifconfig
注释：有 “inet6 addr：。。。。。。。“ 的表示开启了ipv6功能
b）通过内核模块加载信息查看
命令：lsmod | grep ipv6
ipv6关闭方法
在/etc/modprobe.d/dist.conf结尾添加
alias net-pf-10 off
alias ipv6 off
