# 腾讯云CentOS 7上搭建WordPress

## 1.安装Apache web服务器

使用yum工具安装：

![](../img2/安装apacheweb服务器.png)

启动Apache web服务器

![](../img2/启动apacheweb服务器.png)

测试apache服务器是否成功运行

![](../img2/验证是否成功运行.jpg)

## 2.安装MySQL

安装mariaDB

![](../img2/安装mariadb.png)

启动mariadb

![](../img2/启动mariadb.png)

运行简单的安全脚本以移除潜在的安全风险，启动交互脚本

![](../img2/运行简单的安全脚本.png)

设置相应的root访问密码以及相关的设置

![](../img2/设置root访问密码以及相关设置.png)

置开机启动MariaDB

![](../img2/设置开机启动mariadb.png)

## 3.安装PHP

启用两个仓库

![](../img2/启用仓库.png)

![](../img2/启用仓库2.png)

启用PHP 7.2 Remi仓库

![](../img2/启用php7.2remi仓库.png)

安装PHP以及php-mysql

![](../img2/安装php和phpmysql.png)

查看安装的php版本

![](../img2/查看php版本.png)

重启Apache服务器以支持PHP

![](../img2/重启apache服务器以支持php.png)

安装PHP模块

![](../img2/yumsearchphp-为了更好的运行PHP需要启动PHP附加模块使用如下命令可以查看可用模块.png)



![](../img2/安装phpfpmwordpress.png)

重启Apache服务

![](../img2/重启apache服务.png)

## 4.测试PHP

利用一个简单的信息显示页面（info.php）测试PHP。创建info.php并将其置于Web服务的根目录（/var/www/html/）



![](../img2/sudovimvar那个.png)

该命令使用vim在/var/www/html/处创建一个空白文件info.php，我们添加如下内容：

![空白文件那个](../img2/空白文件那个.png)

完成之后，使用刚才获取的cvm的IP地址，在你的本地主机的浏览器中输入

![](../img2/完成phpcvmip的那个.jpg)

## 5.安装wordpress以及完成相关配置

### （1）为wordpress创建一个mysql数据库

以root用户登录MySQL数据库

![](../img2/以root用户登录mysql数据库.png)

为WordPress创建一个新的数据库

![](../img2/为wordpress创建数据库.png)

为WordPress创建一个独立的MySQL用户

![](../img2/为wordpress创建一个独立的mysql用户.png)

授权给wordpressuser用户访问数据库的权限

![](../img2/授权给wordpressuser用户访问数据库的权限.png)

刷新MySQL的权限

![](../img2/刷新mysql的权限.png)

### （2）安装wordpress

下载WordPress至当前用户的主目录

![](../img2/下载wordpress.png)

解压wordpress

![](../img2/解压wordpress.png)

将wordpress文件夹同步到apache服务器的根目录下

![](../img2/将wordpress文件夹同步到apache服务器的根目录下.png)

在Apache服务器目录下为wordpress创建一个文件夹来保存上传的文件并对Apache服务器的目录以及wordpress相关文件夹设置访问权限

![](../img2/在apache服务器目录下为wordpress创建一个文件夹来保存上传的文件并对apache服务器的目录以及wordpress相关文件夹设置访问权限.png)

### （3）配置wordpress

大多数的WordPress配置可以通过其Web页面完成，但首先通过命令行连接WordPress和MySQL。
定位到wordpress所在文件夹，然后，通过nano超简单文本编辑器来修改配置

![](../img2/大多数wordpress配置和wordpress配置以来和通过nano修改.png)

更改数据库名，数据库用户，和数据库密码为之前为WordPress创建的数据库的相关信息

![](../img2/将文件中的db.png)

### （4）通过web界面进一步配置wordpress

在浏览器中输入你的IP地址或者域名就会出现如下界面，注册登录侯

![](../img2/4通过web姐买你进一步配置wordpress输入ip地址出现的界面.png)

然后进入wordpress的控制面板就可以设计你的wordpress界面了

![](../img2/QQ截图20191027185121.png)



