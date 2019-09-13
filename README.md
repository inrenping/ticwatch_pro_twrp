## TicWatch Pro
TicWatch Pro 是出门问问于2018年5月发布的一款基于 Google Wear OS 的智能手表。

国行版的系统是特别定制的，没有 Google Play ，应用商店基本没用。可是我只能买到国行版……

想想大不了刷了机嘛。手机路由器都刷过来了，手表应该是可行的。

可行是可行，不过是多踩几个坑……

一上来没有备份就把系统给双清了，所有的指令都是红色大感叹号。一脸懵逼，默默打开了京东的售后页面……

死马当活马医，最后参考 [xda-developers 论坛的帖子](https://forum.xda-developers.com/smartwatch/other-smartwatches/rom-kernel-t3821013)，刷了国际版,还是基于其他型号魔改的版本，因为硬件存在差异，使用起来还是有一些问题，时常卡的一逼,但是其他的方法都不行，暂时只能这样了……

[官方论坛]()居然还是打不开的，只能用 Google 的缓存来看，官网也没有提供 ROM 下载,给我一种这家公司已经倒闭跑路的感觉……

## adb => Bootloader=> TWRP
[下载 adb](https://dl.google.com/android/repository/platform-tools_r29.0.3-windows.zip)

[下载 ROM](https://mega.nz/#F!1IsjVCII)

密码 `McNNTt-c4e78cTOidKHhpA`


使用USB线缆(充电底座)连接你的手表和电脑，在你的手表上开启ADB调试。
在手表中，进入设置-系统-关于-点击7次版本号，开启开发者模式，返回设置，进入开发者选项-打开adb调试。

检查已经连接上的设备
~~~
adb devices
adb reboot bootloader
fastboot devices
fastboot oem unlock
fastboot boot recovery.img
~~~

直接启动`TWRP-Recovery`

建议进行完全抹除操作(4清) - 抹除data/执行恢复出厂设置

在recovery中选择Wipe - Advanced Wipe-全部勾选然后Wipe，然后返回首个界面选择Reboot-Recovery，或执行Wipe - Factory Reset

在recovery中选择Install，选择ROM的zip包刷入。

完成，我没有`root`。

## 体验

- 可以正常开机。
- 续航能力下降，耗电速度肉眼可见加快。
- 预装的Google系列应用，可以上Google Play 下应用
- 不再预装中国版的应用(微信和支付宝) ~~反正我也不用~~
- NFC 没法用 ~~反正我也不用~~
- 不知道是不是初始化的缘故， Google Play 下载安装其他软件的时候整个手表就会奇卡无比……
- 据说是中国版Pro硬件差异导致的。

总之，就当玩具吧，不建议刷机，更不建议入手……

## 参考

[了解一下什么是 Bootloader](https://sspai.com/post/38319)

[台湾少年的开箱测评](https://www.bilibili.com/video/av47884656/)

[哔站的刷机视频](https://www.bilibili.com/video/av26414053/)

[xda-developers论坛的帖子](https://forum.xda-developers.com/smartwatch/other-smartwatches/rom-kernel-t3821013)

[~~官方论坛的刷机指南帖 (打不开)~~](https://bbs.chumenwenwen.com/forum.php?mod=viewthread&tid=409801)

[官方论坛的刷机指南帖的缓存](https://webcache.googleusercontent.com/search?q=cache:RZaf7lQCPmkJ:https://bbs.chumenwenwen.com/forum.php%3Fmod%3Dviewthread%26tid%3D409801+&cd=6&hl=zh-CN&ct=clnk&gl=jphttps://bbs.chumenwenwen.com/forum.php?mod=viewthread&tid=409801)

[Nike+ Run Club For Wear OS ](https://www.youtube.com/watch?v=W-za4-nIYZY)