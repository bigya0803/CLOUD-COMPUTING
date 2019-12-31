虚拟机安装4个centos7，最小安装，只有命令函界面

进入系统后用ip add查询系统ip，然后用xshell连接

##### **给所有节点**

添加用户并配置sudo权限

![添加用户](../img4/添加用户.png)

![](../img4/配置sudo.png)

然后安装配置ntp服务

![](../img4/安装配置ntp服务.png)

![安装配置ntp服务2](../img4/安装配置ntp服务2.png)

禁用selinux

![](../img4/禁用selinux.png)

防火墙设置

![](../img4/防火墙设置.png)

《1》主控结点防火墙

![主控节点防火墙](../img4/主控节点防火墙.png)

《2》mon1结点防火墙

![](../img4/mon1防火墙.png)

《3》普通结点防火墙

![普通节点防火墙](../img4/普通节点防火墙.png)

#### 准备工作

主控结点添加如下配置

![](../img4/添加配置.png)

设置免密登录ssh并添加配置

![](../img4/免密登录与添加配置.png)

使用ssh-copy-id命令将ssh密钥添加到所有结点

![](../img4/使用sshcopyid命令将ssh密钥添加到所有节点.png)

测试连接其他各个结点

![](../img4/测试连接其他节点.png)

ceph-deploy安装

在每个结点下方执行以下内容

![在每个节点执行下方命令1](../img4/在每个节点执行下方命令1.png)

![在每个节点执行下方命令2](../img4/在每个节点执行下方命令2.png)

![](../img4/在每个节点执行下方命3.png)

添加ceph仓库

sudo vi /etc/yum.repos.d/ceph.repo

![](../img4/在ceph仓库添加如下配置.png)

在mon1结点执行，修改主机名为mon1

![](../img4/修改mon1节点主机名.png)

为osd守护进程创建目录

![](../img4/守护进程目录osd2.png)

![为osd守护进程创建目录osd1](../img4/为osd守护进程创建目录osd1.png)

检查集群状态

![](../img4/结果.png)

![结果2](../img4/结果2.png)