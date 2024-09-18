首先需要在苹果设备上下载 ssh 工具，经过筛选，我们选择使用 ISH 这个软件作为 ssh 工具。

刚下好的软件并没有 ssh 功能，只有基础的 Shell 功能，需要下载 ssh。

进入软件，我们可以在界面看到如下提示：

```text-plain
Welcome to Alpine!

You can install packages with: apk add <package>

You may change this message by editing /etc/motd.
```

这是一个 Alpine Linux 系统，我们需要使用 apk add 来下载软件，不过我们首先更新一下软件源

```text-plain
$ apk update
$ apk upgrade
```

我们需要下载 ssh 工具，从官网可以看到需要下载 openssh。

```text-plain
$ apk add openssh
```

这样 ssh 工具就下载好了，直接登陆即可。

```text-plain
$ ssh root@<你的ip地址>
```

然后会有确认选项，输入 `yes` 即可，之后输入你服务器的密码，我们就进入服务器了。

服务器我使用的是`Debian`系统，使用：

```text-plain
$ apt install gcc
$ apt install g++
```

即可下载C/C++编译工具。

然后使用Vim写一个简单的C语言代码，文件名为Hello.c，编译下一：

```text-plain
$ gcc -o Hello Hello.c #c语言用gcc,c++用g++
```

生成编译的Hello文件，运行一下：

```text-plain
$ ./Hello
```

即可看到运行结果。