# Kuaipan Uploader

前段时间dropbox在国内没法用了，国内的网盘在linux下又没有一个轻量简洁的同步工具，于是动了自己操刀写一个的想法，终于在一个下大雨的周末诞生了Kuaipan Uploader :)

PS：其实我的本意是基于百度云盘写一个上传下载的脚本，但是写了一半发现百度云盘不开放API了，真是悲剧。。。

=============

**1.依赖项**

使用此程序需要你的Linux或者Cygwin支持如下命令

`curl sed awk basename date grep tr od openssl base64`



**2.配置**

首先注册一个金山快盘账号，然后到这里[地址](http://www.kuaipan.cn/developers)创建一个你自己的应用并把得到的
consumer_key、consumer_secret填写到脚本相应位置。


**3.赋予脚本执行权限并执行**

`chmod a+x kuaipan_uploader.sh`

`./kuaipan_uploader.sh`

然后根据提示完成API的授权流程，得到授权Token。脚本会自动保存得到的授权信息



**4.使用说明**

下载：

 `git clone https://github.com/wujiwh/kuaipan_uploader.git`
 
 `cd kuaipan_uploader`
 
 `chmod a+x kuaipan_uploader.sh`
 
 `./kuaipan_uploader.sh`
 

	Usage: ./kuaipan_uploader.sh COMMAND [PARAMETERS]...

	Commands:
	         upload   [local file]  <remote file>
	         download [remote file] <local file>
	         delete   [remote file/remote dir]
	         list     <remote dir>
	         info
	         relink

	For more informations, please visit  http://wangheng.org.


`其中[XXX]内的为必填参数，<XXX>内的为可选参数`

比如执行 `./kuaipan_uploader.sh upload a.txt`

后面的`<remote file>`可以不填，不填写的话，默认上传到网盘根目录或者应用程序根目录的同名文件。
(跟你创建应用的时候选择的选项有关)

其他，下载和删除都是类似如上...

- *注意：如果上传到远程某个目录内的话，请务必保证此目录已存在！*

执行 `./kuaipan_uploader.sh info` 可以查看网盘的用户名，总容量和可用容量。

执行 `./kuaipan_uploader.sh list` 可以查看网盘内已经存在的文件以及目录(非结构化)。

执行 `./kuaipan_uploader.sh relink` 可以删除网盘授权信息并重新授权


**5、安装卸载**

此工具为绿色软件，使用时候复制到执行目录并赋予执行权限即可。

如果想卸载删除此工具，请连带删除 `CONFIG_FILE` 变量后面的配置文件，默认为 `~/.kuaipan_upload.conf`


**6.关于**

此工具为开源软件，基于GPL 协议发布，请尊重作者知识产权，遵守软件协议！

任何问题欢迎来我的[博客](http://wangheng.org)交流互相学习，我将很高兴认识大家：http://wangheng.org

或者给我写邮件：wujiwh@gmail.com 


##TODO

1、list可以区分目录和文件，并显示目录结构。


##赞助

如果您想支持此项目，您可以考虑以下方式赞助：

- 支付宝扫码支付

![image](http://wangheng.org/images/alipay.png "")

##许可证

Kuaipan Uploader 基于GPL第二版或以后版本发布。详见LICENSE文件
