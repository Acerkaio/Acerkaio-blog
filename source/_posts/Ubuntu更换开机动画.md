---
title: Ubuntu更换开机动画为Elaina
date: 2023-08-15 20:19:53
tags: 记录
categories: 记录
---
## 开始前


作者使用 **Ubuntu 22.04.3 LTS**，教程开始前请判断您的 Ubuntu 是否使用 **Plymouth**!


## 准备
作者已经帮您整合好 Elaina 主题，您需要下载其 [方式1](https://blog.acerkaio.top/download/Elaina.zip) | [方式2 (可能更快)](https://vercel.acerkaio.top/download/Elaina.zip)

## 更改文件夹权限

下载后，我们打开 /usr/share/plymouth/

为了方便，我们使用以下命令更改文件夹权限：

```
sudo chown -R <你的用户名>:<你的用户名> /usr/share/plymouth/themes/
```
## 具体操作

打开 themes 文件夹，将下载的 Elaina.zip 解压到这里为 Elaina 文件夹。

先使用：

```
sudo apt-get install plymouth-theme*
```

然后使用

```
sudo update-alternatives --install /usr/share/plymouth/themes/default.plymouth default.plymouth /usr/share/plymouth/themes/Elaina/ubuntu-gnome-logo.plymouth 150

```

接着使用以下命令并找到 Elaina 有关字段，填写编号。
```
sudo update-alternatives --config default.plymouth
```
最后生效（可能会等久一点）：

```
sudo update-initramfs -u
sudo update-grub
reboot
```

您也可以将其中的 PNG 文件做适当更改。