# ideapad-720s-13IKB
我买的日版机，CPU是i5 8250u，其它参数可看鲁大师导出的配置单，所有文件来自https://github.com/dragonflylee/Yoga-730-hackintosh  我只改了layoutid为22，并去掉了原项目里我暂时用不到的opencore文件。

### 使用方法：
用黑果小兵提供的10.15.1镜像，刻录一个安装盘，用此处的EFI替换安装U盘里的EFI，然后安装系统。
系统安装完成后，用此处的EFI替换系统盘里的EFI，即可脱离u盘启动。然后config.plist里改声卡layoutid为22。

### 可用项目
1. 触摸板已驱动
2. intel power gadget有变频，电池电量显示正常，并调整系统设置去掉睡眠，怕出问题，不用时关机就好了
3. 亮度快捷键可调
4. 声卡正常
5. 显卡正常
6. 自带网卡蓝牙暂时不管，需更换才行，目前暂用的USB迷你网卡comfast cf-811ac，官方提供驱动安装包，点击安装即可。


### 发现问题
目前发现触摸板在闲置一段时间，如5分钟多点，就会不响应，像完全没驱动一样，必须重启才可以正常，可能需要自己定制DSDT(或许voodooi2c本身有bug)，但我不会，这里有这个教程，我看了几遍还不太懂，有需要的去看看吧，参考教程：https://www.penghubingzhou.cn/2019/01/06/VoodooI2C%20DSDT%20Edit/ 

### 其它说明
有问题需要讨论可去 http://bbs.pcbeta.com/forum.php?mod=viewthread&tid=1817262&highlight=720s  我只是看到讨论里用这个EFI可以,就用了,其它不懂。



### 20191119关于网卡更新
鉴于USB网卡占用宝贵的USB口，我最终还是买了dw1820a，但是系统就是识别不出来，无论win下还是mac下，开始以为是网卡问题，就又买了bcm94360cs2加仕和技术的m2转苹果网卡那个延长线，把电池拿下来去掉扬声器，可以很好的放入这个网卡，但是遇到同样的问题，依然无论win还是mac都识别不到，后来群里有人说换网卡前要先屏蔽wifi，我就先bios里屏蔽wifi进系统，然后再解开屏蔽进系统，居然成功识别出来了，bcm94360cs2直接免驱，可以把相关驱动删了(AirportBrcmFixup.kext、
BT4LEContinuityFixup.kext、BrcmBluetoothInjector.kext)，另外，dw1820a应该也是一样需要先bios屏蔽才识别吧，拆装比较麻烦就没再试了。
