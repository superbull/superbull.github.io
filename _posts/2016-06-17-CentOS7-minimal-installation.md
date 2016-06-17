---
layout: post
title:  "CentOS 7 minimal 安装设置"
date:   2016-06-17 11:03:07 +0800
categories: CentOS 安装
---
我们首次安装好CentOS7 minimal后，可能无法连接到网络。这是因为Ethernet Interfaces默认为not enabled。

下面将介绍初次设置网络连接的步骤。

1. 运行`nmcli d`命令可以列出机器上安装的ethernet card。

    ![CentOS 7 network setup]({{ site.github.url }}/assets/img/2016-06/centos7-network-setup.png)

2. 运行`nmtui`命令打开网络管理界面。选择“**Edit a connection**”并点击“回车”。

    ![CentOS 7 network manager ui]({{ site.github.url }}/assets/img/2016-06/centos7-network-manager-ui.png)

3. 选择你的network interface并点击“**Edit...**”。

    ![Edit network interfaces]({{ site.github.url }}/assets/img/2016-06/edit-network-interfaces.png)

4. 设置“**IPv4 CONFIGURATION**”为“**Automatic**”,并选中“**Automatically connect**”。依次点击“OK”，“Quit”退出Network manager。

    ![Setup IP address via DHCP]({{ site.github.url }}/assets/img/2016-06/setup-ip-address-via-dhcp.png)

5. 运行命令`service network restart`重设网络服务。

6. 现在你的服务器将会由DHCP获得IP地址。

    ![check IP address]({{ site.github.url }}/assets/img/2016-06/centos7-check-ip-address.png)
