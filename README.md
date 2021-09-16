# README

xdu 晨午晚检/疫情通(健康卡) 自动填报



## 免责声明

​		此代码仅用于学习，请谨慎使用，所有与此代码相关的风险及损失均与代码作者无关。

​		希望大家做好防护，注意安全！



## 设置信息

​	    程序主入口有3个字典变量，xian_bei 代表定位信息在北校区（陕西省西安市雁塔区电子城街道西安电子科技大学北校区）；xian_nan代表定位信息在南校区（陕西省西安市长安区兴隆街道西安电子科技大学长安校区办公辅楼）; guangzhou代表定位信息在广研院（广东省广州市黄埔区九龙镇御禾田公寓广州绿地城）。如需添加用户，只需在对应校区内新增个人信息，格式为："学号" : "密码"。如：

```
    xian_bei = {
        "21xxxxxxxxx" : "***********",
    }
```



## 设置定时任务

​		如果没有服务器，相比于程序内循环判断，可以在电脑上（需要保证开机状态）设置定时任务，这里仅以windows中设置晨午晚检为例：

​			打开 控制面板→管理工具→任务计划程序，

![image-20210827232102811](https://github.com/40z0ng/xdu-cwwjNyqt/blob/main/images-folder/image-20210827232102811.png)

​			选择右侧“操作栏”中的“创建任务”，

![image-20210916144631804](https://github.com/40z0ng/xdu-cwwjNyqt/blob/main/images-folder/image-20210916144631804.png)

​			在常规选项卡中设置名称，（最好）选择“不管用户是否登录都要运行”，（可勾选“使用最高权限运行”）

![image-20210916145447769](https://github.com/40z0ng/xdu-cwwjNyqt/blob/main/images-folder/image-20210916145447769.png)

​			在触发器选项卡中设置想要执行程序的时间，

![image-20210916145946502](https://github.com/40z0ng/xdu-cwwjNyqt/blob/main/images-folder/image-20210916145946502.png)

​			在操作选项卡中，“程序或脚本"选择对应的bat脚本，同时设置“起始于”为bat脚本所在的文件夹，

![image-20210916150304695](https://github.com/40z0ng/xdu-cwwjNyqt/blob/main/images-folder/image-20210916150304695.png)

​			在设置选项卡，最下方的“如果此任务已经运行...”选项中，选择“并行运行新实例”，（由于默认为不运行新实例，因此不如下图设置可能会导致失败）

![image-20210916151228051](https://github.com/40z0ng/xdu-cwwjNyqt/blob/main/images-folder/image-20210916151228051.png)

​			最后点击确定即可。



## 其他

​		(1). 如果有服务器（最好是Linux），定时任务设置可见https://zhuanlan.zhihu.com/p/341901663。（个人体验下来，Linux的定时任务更加稳定）		

​		(2). 设置定时任务仅是一种使用方法，也可在程序内使用循环判断触发执行，只需将主函数中的submit函数放入循环内即可。

​		(3). **如果windows定时任务执行失败，可以试试换成“创建基本任务”，按提示创建完成后，双击进入任务，选择基本任务创建时不能设置的参数（尤其注意设置选项卡中选择”并行运行新实例“）。**
