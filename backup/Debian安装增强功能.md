安装增强功能
------

安装必要的软件包
--------

首先用管理员权限下载`build-essential`、 `dkms`以及 `linux-headers-$(uname -r)`三个必要的软件包：`sudo apt-get install build-essential dkms linux-headers-$(uname -r)`

插入增强功能光盘映像
----------

在设备选项中点击安装增强功能

![zengqiang](https://github.com/dreamyunight/dreamyunight.github.io/blob/main/static/%E5%AE%89%E8%A3%85%E5%A2%9E%E5%BC%BA%E5%8A%9F%E8%83%BD/zengqiang.jpg?raw=true)

安装增强功能
------

然后我们点开`Files`可以看到`VBoxLinuxAdditions.run`，我们需要将该文件`cp`到`/tmp`文件夹中

![VBoxLinuxAdditions.run](https://github.com/dreamyunight/dreamyunight.github.io/blob/main/static/%E5%AE%89%E8%A3%85%E5%A2%9E%E5%BC%BA%E5%8A%9F%E8%83%BD/VBoxLinuxAdditions.jpg?raw=true)

c进入`/tmp`文件夹使用管理员权限运行安装脚本：`sudo ./VBoxLinuxAdditions.run`

重启电脑
----

执行`sudo reboot`重启电脑