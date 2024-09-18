## [[Package Details: yay-bin 12.3.5-1](https://aur.archlinux.org/packages/yay-bin)](https://aur.archlinux.org/packages/yay-bin) 

随着 pacman 7 的更新，需要重建 yay，如果升级 pacman 而没有同时升级 yay，那么 yay 将无法运行。

重建方法为：

```bash
sudo pacman -Rns yay-bin yay-bin-debug
```

或

```bash
sudo pacman -Rns yay
```

卸载`yay`

```bash
sudo pacman -S --needed git base-devel
```

运行

```bash
sudo pacman -S --needed git base-devel
```

确保系统中有 `git` 和 `base-devel` 工具集，这些工具是从 AUR 构建包所必需的。

```bash
git clone https://aur.archlinux.org/yay.git
cd yay
makepkg -si
```

下载并安装yay，当然你也可以选择`yay-bin`

```bash
$ git clone https://aur.archlinux.org/yay-bin.git
$ cd yay-bin
$ makepkg -si
```

我遇到了构建过程中无法从 `https://proxy.golang.org/` 下载所需的 Go 模块文件的问题。具体原因是与 Golang 相关的依赖项在下载时发生了超时 (`i/o timeout`)，这通常是由网络连接问题引起的。

我使用的clash作为代理，终端中默认不使用系统代理，因此：

```bash
export https_proxy=127.0.0.1:7890
```

暂时将代理更换。

然后就能正常下载了。