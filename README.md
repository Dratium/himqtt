# himqtt

#### 一 、介绍
himqtt是一款开源的高性能物联网防火墙，支持MQTT协议。

#### 二 、功能概述
开源版本没WEB管理，主要功能有: 	                           
      1. SSL安全加密反向带代理
	    2. 数据库SQL注入
	    3. 跨站脚本攻击（XSS)
	    4、DDOS攻击
	    5、密码暴力破解
	    6. TOPIC黑白名单
	    7. 兼容OWASP的ModSecurity的SQL注入/XSS攻击检测等规则
	    8. epoll模型多核数十万的并发连接
	    ..... 
	    商业版用机器学习+规则引擎+语义分析，识别未知攻击甚至0day漏洞。

#### 三、安装教程
支持Linux ，以root权限运行下面命令：

  1. 安装OpenSSL和libpcre
  CentOS : 
  	yum install openssl openssl-devel
  	yum install -y pcre pcre-devel 
  	
  Debian/Ubuntu:
  	sudo apt-get install openssl libssl-dev
  	apt-get install libpcre3 libpcre3-dev  
  
  2.编译
  解压到任意目录，make生成himqtt.
  
  3.规则
  规则放在和himqtt同一级的rules目录，注意后缀是.conf或.rule,更多规则支持商业版。

  
  4.运行
  默认himqtt前端运行1884（SSL 加密）端口，后端反向代理1883明文端口。
  ./himqtt默认读取当前目录下的confg.cfg文件， 或者./hihimqtt --config /dir/config.cfg
  具体请看config.cfg详细说明， 如果成功打印加载了rules目录下的规则，代表运行成功。
  
  5.MQTT.fx测试
   MQTT.fx配置SSL/TLSL里面打勾，选择TLSv1.2版本，如果选择第一项CA signed server certificate的话，请确认PEM格式的
   证书是CA信任机构签发的。
   具体看doc目录相关图片。

#### 四、商业版演示地址

商业版支持机器学习和WEB管理，也可以开源，地址 [http://59.110.1.135/iotpages/](http://59.110.1.135/iotpages/)

#### 五、商业源码部署请加微信号httpwaf

![](https://gitee.com/httpwaf/httpwaf/raw/master/img/wechat.png)

#### 六、来一张IOT攻击日志图

![](https://gitee.com/httpwaf/aimqtt/raw/master/doc/home.png)