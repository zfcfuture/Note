### SSH连接虚拟机

问题：台式机连接wifi并开热点给笔记本，解决台式机用ssh远程工具连接笔记本ubuntu虚拟机问题

**（1）**

![img](file:///C:/Users/E0005175/Documents/WXWork/1688851187903851/Cache/Image/2021-08/d259696f-ad38-4ef8-8197-f06502b6c0a4.png)

**（2）**

![img](file:///C:/Users/E0005175/Documents/WXWork/1688851187903851/Cache/Image/2021-08/6c1f931c-7076-42db-8bd0-1fef3429c618.png)



**==Solution：==**

1.  检查**台式机**的无线网ip地址：192.168.137.1
2.  检查**笔记本**虚拟机地址：192.168.1.130
3.  检查**笔记本**无线网ip：192.168.137.198
4.  发现虚拟机ip与台式机ip不在同一网段
5.  解决办法两种：修改虚拟机ip或者修改虚拟机网络连接模式，本次解决方法选择后者
6.  点击编辑虚拟机设置-->网络适配器-->网络连接选择桥接模式，勾选复制物理网络连接状态-->确定
7.  开机，查看当前虚拟机ip地址：192.168.137.236
8.  台式机连接虚拟机，报错如下图：
9.  经排查，原因为ubuntu20为安全考虑，没有打开ssh权限，解决方法在第10步
10.  终端输入如下：
11.  再次ssh连接，成功

```shell
sudo apt update
sudo apt install openssh*
systemctl start sshd
lsof -i:22
systemctl status sshd
```

![img](file:///C:/Users/E0005175/Documents/WXWork/1688851187903851/Cache/Image/2021-08/企业微信截图_1629089623985.png)

