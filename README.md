# linuxNote
<br>1.关于Linux:
<br>  关于Linux的优缺点:http://c.biancheng.net/view/709.html
<br> Linux相关的版本:
<br> A.Red Hat 公司的产品主要包括 RHEL（Red Hat Enterprise Linux，收费版本）和 CentOS（RHEL 的社区克隆版本，免费版本）、Fedora Core（由 Red Hat 桌面版发展而来，免费版本）。
<br>Linux 发行版本的选择
<br>Linux 的发行版本众多，在此不逐一介绍，下面给选择 Linux 发行版本犯愁的朋友一点建议：
<br>如果你需要的是一个服务器系统，而且已经厌烦了各种 Linux 的配置，只是想要一个比较稳定的服务器系统，那么建议你选择 CentOS 或 RHEL。
<br>如果你只是需要一个桌面系统，而且既不想使用盗版，又不想花大价钱购买商业软件，不想自己定制，也不想在系统上浪费太多时间，则可以选择 Ubuntu。
<br>如果你想深入摸索一下 Linux 各个方面的知识，而且还想非常灵活地定制自己的 Linux 系统，那就.
<br>如果你需要使用数据库高级服务和电子邮件网络应用，则可以选择 SuSE。
<br> Linux远程管理协议（RFB、RDP、Telnet和SSH）
<br>目前，常用的远程管理协议有以下 4 种：
<br>RDP（remote desktop protocol）协议：远程桌面协议，大部分 Windows 系统都默认支持此协议，Windows 系统中的远程桌面管理就基于该协议。
<br>RFB（Remote FrameBuffer）协议：图形化远程管理协议，VNC 远程管理工具就基于此协议。
<br>Telnet：命令行界面远程管理协议，几乎所有的操作系统都默认支持此协议。此协议的特点是，在进行数据传送时使用明文传输的方式，也就是不对数据进行加密。
<br>SSH（Secure Shell）协议：命令行界面远程管理协议，几乎所有操作系统都默认支持此协议。和 Telnet 不同，该协议在数据传输时会对数据进行加密并压缩，因此使用此协议传输数据既安全速度又快。
<br> 一般服务器的选择都不会选择图形界面,因为单纯的作为服务器没必要增加界面相关的内存消耗,所以一般是选择telnet或者SSH,但是SSH在数据传输的会进行加密压缩
<br> △Linux的FHS（Filesystem Hierarchy Standard），文件系统层次化标准，该标准规定了 Linux 系统中所有一级目录以及部分二级目录（/usr 和 /var）的用途。发布此标准的主要目的就是为了让用户清楚地了解每个目录应该存放什么类型的文件。
<br> linxu:挂载 http://c.biancheng.net/view/2859.html
<br> Linux 命令行格式 [root@localhost ~]# 命令[选项][参数] 命令的选项用于调整命令功能，而命令的参数是这个命令的操作对象
