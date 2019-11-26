# Cairo-Timer

集合`定时器`和`闹钟⏰`功能。
> 以前经常使用at脚本设置提醒，每次还要开终端，输入命令。这个单一执行文件，可以解决一般性的定时问题。
> 比如："*12分钟后提醒*"；"*5点45提醒*"。都是鼠标在同一界面操作。

GPL3 授权。gtk+-3.0下编译的，源码在其他仓库。当前Linux发行版本应该通用。其他平台不知道安装了gtk环境能跑不。

## 鼠标操作

![老界面](shot0.png) ![新界面](shot1.png)

* 圆心部分：
    * `1`键切换提醒开关，时间文字和定时指针会变颜色，指示开关的状态。
    * 滚轮设置以当前时间为基础，设置定时，每次正负一分钟。正向定时，会显示"+10"分钟这样的状态。
    * 其他鼠标按钮，关闭软件。
* 其他界面部分：
    * `1`拖动。
    * 滚轮缩放。
    * 其他鼠标按钮，点选定时，以五分钟为间隔。

## 提醒动作
* 缺省执行`/usr/bin/canberra-gtk-play -l 5 -i complete`，就是系统声音，连续响5次。如果不关闭提醒，大约会响一分钟。
* 如果有自定义脚本，`~/.config/time.script`，提醒动作就会执行它。不管shell格式。最好别设置`totem xxxx.mkv`这样的，软件会多次载入的，除非脚本里面自己搞定重载判断。因为提醒脚本是为了让人在没取消前，多次提醒。

## 新增参数
* 参数为 x, y, z, 0，或者无参数(缺省为z)。表示提醒时，摇摆的方向轴。


> 软件10秒激活一次，所以最大延时误差是10秒。

>虽然界面丑点，其实只是为了不调用任何外部资源。
