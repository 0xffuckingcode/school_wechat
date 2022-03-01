## 0x00 致敬

原项目地址：

`https://github.com/oubingbing/school_wechat`

`https://github.com/oubingbing/wechatAlliance`

原作者的技术水平及开源精神令人敬佩，本版本只是在原版本的基础上做了点微小的debug和美化工作

## 0x01 前言
校园小情书是一个微信小程序的表白墙，主要功能有表白（匿名表白和短信表白）、卖舍友、情侣脸对比、以及步数旅行。适合大学校园内运营，建立自己学校的表白墙社区。


<font color=red>**PS：该小程序属于【社区/论坛】类，微信规定【社区/论坛】类的小程序在微信公众平台上线的话，必须需要企业或者个体工商户资质才可以。同时，还得需要该资质下的一个备案域名。**</font>

## 0x02 效果图
![在这里插入图片描述](https://img-blog.csdnimg.cn/20201015001336927.jpg?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzM1Nzk1NDE4,size_16,color_FFFFFF,t_70#pic_center)

## 0x03 注册管理后台
1、首先登录校园小情书的后台站点进行注册：`https://mp.wx-union.cn`

2、注册成功后会提示发送一封激活邮件到您的邮箱，点击邮件中的激活链接进行账户激活。

3、激活账户后登录会跳转到小程序的建立页面，小程序的名字必须和你微信注册的名称一模一样

![在这里插入图片描述](https://img-blog.csdnimg.cn/20191206093107217.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzM1Nzk1NDE4,size_16,color_FFFFFF,t_70)

4、在后台注册好小程序，这时管理后台就注册完成了。

![在这里插入图片描述](https://img-blog.csdnimg.cn/20210220191639992.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzM1Nzk1NDE4,size_16,color_FFFFFF,t_70)


## 0x04 在微信公众平台绑定服务端的域名
![在这里插入图片描述](https://img-blog.csdnimg.cn/202102201918188.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzM1Nzk1NDE4,size_16,color_FFFFFF,t_70)

request合法域名
```
https://mp.wx-union.cn 			    //后台域名
https://apis.map.qq.com             //地图api
```


uploadFile合法域名
```
https://up-z2.qbox.me                       //七牛
https://mp.wx-union.cn          			//后台地址
https://img.wx-union.cn         			//七牛oss地址
```

downloadFile合法域名
```
https://img.wx-union.cn          			//七牛云存储的域名
https://mp.wx-union.cn          			//后台域名
https://wx.qlogo.cn                         //微信头像
https://thirdwx.qlogo.cn					//微信头像
```

**PS：以上地址都不用改，直接复制上就可以**

## 0x05 配置小程序
用微信开发者工具打开源码后在项目根目录的`config.js`进行如下配置。

![在这里插入图片描述](https://img-blog.csdnimg.cn/20210220192359328.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzM1Nzk1NDE4,size_16,color_FFFFFF,t_70)

这里的`alliance_key`是后台生成的，去后台找到然后替换掉就OK了，以及在腾讯地图开放平台注册一个账号，把开发者`ID`粘贴到`TX_MAP_KEY`就可以了。

此外，我们还需要用到一个叫**七牛传图**的第三方插件用于上传图片，把这个插件添加到我们的小程序里面。

![在这里插入图片描述](https://img-blog.csdnimg.cn/20191206101816391.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzM1Nzk1NDE4,size_16,color_FFFFFF,t_70)
对比一下插件版本号，看看是否是最新的版本，如果不是就在`app.json`里面填上最新的版本号即可。

![在这里插入图片描述](https://img-blog.csdnimg.cn/20191206101919437.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzM1Nzk1NDE4,size_16,color_FFFFFF,t_70)

到这里客户端基本上配置就完成了

清除全部缓存，然后再点编译，项目应该就没问题可以运行了。

上传代码到微信公众平台，然后提交审核，审核过了即可发布上线。
