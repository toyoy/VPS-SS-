可能大家有各种各样的理由需要科学上网，也有不同的科学上网的方法。但是对于一般非专业人士来说，主要还是通过现成的软件和应用，经常存在服务器不稳定、网速慢，价格贵等等的问题，那为什么我们不能自己去搭一个自己的服务器，把命运掌握在自己手上呢？今天就来解决这个问题，放心，没有想象中的困难，看下去就知道了。

**一、何为VPS（简单来说就是一个虚拟服务器，没兴趣的朋友可以跳过）**

**1、VPS**

VPS（Virtual Private Server虚拟专用服务器）可以理解成就是一台虚拟的服务器，他与服务器一样，有独立IP、内存、带宽等，可以安装不同的操作系统和运行软件。比较多用来做网站、跑OA、系统软件等等。 简单来说，VPS就是一种虚拟服务器。

**2、它跟云主机的区别**

VPS跟云服务器在虚拟化技术应用、资源配置和扩展能力上有明显不同，详细对比可以看这里：[https://yq.aliyun.com/articles/226730](https://yq.aliyun.com/articles/226730)
好了，理论知识先讲到这儿，接下来是关键的操作环节。

**二、如何购买VPS服务器**

首先说明一点，VPS是作为一种虚拟服务器，需要占用内存、带宽、硬盘这些资源，也就意味着需要花钱购买的，那要怎样选好的，怎样买到便宜的？

**1、VPS选购**

目前国内用的最多的是搬瓦工和Vultr这两家的VPS服务器。

Vultr官网：https://www.vultr.com/?ref=8089288-4F 

搬瓦工官网：www.bwh88.net

个人建议用Vultr，因为实在要更便宜。
Vultr首次充值10美元会送50美元（要通过这个链接进去注册才能送https://www.vultr.com/?ref=8089288-4F ），最便宜的服务器5美元一个月，跟搬瓦工最便宜的要年费59.99美元差不多，但是月付就灵活很多。

**2、注册Vultr**

购买Vultr的服务器之前要先在官网上（https://www.vultr.com/?ref=8089288-4F）注册账号，常规操作，用邮箱就可以！
注册完记得在邮箱里点认证。
![如何注册Vultr](https://upload-images.jianshu.io/upload_images/1985682-a33cba7749edbdd4.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

**3、充值**

邮箱验证完成之后，会自动跳转回在Vultr的个人主页，然后就可以充值了。Vultr现在已将支持支付宝、微信、信用卡和PayPal，充值方法还是很方便和简单。比如我们截图里面用支付宝充值10美金。
![如何充值.png](https://upload-images.jianshu.io/upload_images/1985682-fa7f295b61517751.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

首次充值10美金会额外送50美金，记得要点这里的连接进去注册才能送50美金的！https://www.vultr.com/?ref=8089288-4F

**4、选择VPS服务器**

充完钱，下一步就真正开始准备我们的VPS了。
![新增一个VPS服务器](https://upload-images.jianshu.io/upload_images/1985682-90a8a498251f823d.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

**a/选机房**

VPS作为虚拟服务器，也是要依托于实体的服务器的。所以这里就是要在哪里的服务器了。主要考虑的因素是速度（低延时）和稳定性，推荐用日本或者美国洛杉矶，日本机房选的人多，选美国的其实也不错，用过一段时间迈阿密的，也挺稳定的，所以看个人喜欢，没有固定的。
![选机房所在地](https://upload-images.jianshu.io/upload_images/1985682-3250e522de023e2f.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

**b/选系统和套餐**

这里默认选的系统是CentOS7 64位的，建议大家选Linux系统，比如Ubuntu，因为后面要讲解到如何安装流量转发软件（Shadowsocks）。
套餐配置其实选最低配，5美金一个月的，流量1T，个人用怎么都够了！有些服务器最低还有2.5美金的，自己选也行。
![选服务器系统和套餐配置](https://upload-images.jianshu.io/upload_images/1985682-592913651b4d3e7f.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

**c/其他选项**

其他选项如果没有特别需求，可以都不选，默认就行。最后点“Deploy Now”确认创建VPS。
![其它选项默认不选也行](https://upload-images.jianshu.io/upload_images/1985682-08741303888e764b.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

**5、查看VPS**
到这里，VPS服务器就购买好了，我们就看看自己的服务器吧。主要看服务器的信息，后续的远程连接要用到的。然后就可以把自己的项目部署到这台VPS上了。![查看VPS信息](https://upload-images.jianshu.io/upload_images/1985682-9c1e8fee49df242b.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

**三、安装ss软件**

这一步就到了接近完成的时候了。至于SS是啥，这里就不赘述了，自己查一下就明白了。
警告：本教程仅用于学习研究，请勿做任何危害gj的事情，大家热爱自己的zg！！！

**1、远程连接VPS**

首先我们要用远程连接的软件，比如新设立和putty（前者可以保存密码，后者右键直接粘贴），大家自己选择，网上都有，至于Mac电脑有自带的终端（terminal）可以连。
这里放一个xshell远程连接的案例：[https://www.zhujiceping.com/15879.html](https://www.zhujiceping.com/15879.html)

**2、一键安装SS**

远程连接好，登录到服务器之后，就开始安装SS了，直接原封不动复制下面的命令到远程连接里执行。
>wget --no-check-certificate -O shadowsocks.sh https://raw.githubusercontent.com/teddysun/shadowsocks_install/master/shadowsocks.sh
chmod +x shadowsocks.sh
./shadowsocks.sh 2>&1 | tee shadowsocks.log>

回车执行命令，然后运行一会儿就提示输入SS的密码、端口和加密方式。这些都是可以根据自己喜好设定的。
![SS设置](https://upload-images.jianshu.io/upload_images/1985682-d4e9ae5f64f38732.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

都确定好了，回车，就提醒再按一次回车，然后出现刚才设置的SS的信息，妥善保管。
到这里SS的安装就完成了。
![](https://upload-images.jianshu.io/upload_images/1985682-97d5d9ba0adbfe95.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

**四、连接SS**

这里就不提供SS的客户端了，请大家自行到网上搜索下载吧，Windows/MacOS/Android/iOS 的版本都有的，除了iOS的相对比较麻烦，其他都很简单其实。
主要就是把刚才的SS信息对应填到配置里，然后就可以连接了。

**注意**，这些设置好了之后，要测试一下连接情况怎么样，可能有些IP是被封掉了的，这时候就要在Vultr里面把原来的服务器取消掉，然后重新买一个新的VPS服务器，重复之后的步骤。所以买了VPS服务器之后，可以先看看IP，测试一下能不能连，在这个网址试试[http://ping.chinaz.com/](http://ping.chinaz.com/)， 能连的再装SS。

而且因为Vultr是按照使用时间收费的，虽然是月费5美金，但是不是一次性扣，是每天扣一点，一个月扣够5美金，所以即使如果买了一个服务器被封了，重买一个，也不会花什么钱，不用担心。

好了本教程就这么多了，是不是很简单，哈哈哈。互联网的精神是分享和探索，分享就到此结束了，接下来的实践和探索，就看你了。


