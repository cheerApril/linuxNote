-# linuxNote(这份笔记是我看了:http://c.biancheng.net/linux_tutorial/ 入门教程之后的笔记而已,偶尔看到这个的话,可以进去学习下)
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
<br> Linux 命令行格式 [root@localhost](这里因为GitHub相关的格式问题所以需要不是准确的命令行格式)命令[选项][参数] 命令的选项用于调整命令功能，而命令的参数是这个命令的操作对象 http://c.biancheng.net/view/720.html
<br> 硬链接 软链接 http://c.biancheng.net/view/740.html
<br>这就是硬链接的原理。硬链接的特点如下：
<br>--不论是修改源文件（test 文件），还是修改硬链接文件（test-hard 文件），另一个文件中的数据都会发生改变。
<br>--不论是删除源文件，还是删除硬链接文件，只要还有一个文件存在，这个文件（inode 号是 262147 的文件）都可以被访问。
<br>--硬链接不会建立新的 inode 信息，也不会更改 inode 的总数。
<br>--硬链接不能跨文件系统（分区）建立，因为在不同的文件系统中，inode 号是重新计算的。
<br>--硬链接不能链接目录，因为如果给目录建立硬链接，那么不仅目录本身需要重新建立，目录下所有的子文件，包括子目录中的所有子文件都需要建立硬链接，这对当前的 Linux 来讲过于复杂。
<br> ------------------------------------
<br> ---软链接的特点（软链接的特点和 Windows 中的快捷方式完全一致）。
<br>--不论是修改源文件（check），还是修改硬链接文件（check-soft)，另一个文件中的数据都会发生改变。
<br>--删除软链接文件，源文件不受影响。而删除原文件，软链接文件将找不到实际的数据，从而显示文件不存在。
<br>--软链接会新建自己的 inode 信息和 block，只是在 block 中不存储实际文件数据，而存储的是源文件的文件名及 inode 号。
<br>--软链接可以链接目录。
<br>--软链接可以跨分区。
<br>---------------------------
<br> 软链接和硬链接在原理上最主要的不同在于：硬链接不会建立自己的 inode 索引和 block（数据块），而是直接指向源文件的 inode 信息和 block，所以硬链接和源文件的 inode 号是一致的；而软链接会真正建立自己的 inode 索引和 block，所以软链接和源文件的 inode 号是不一致的，而且在软链接的 block 中，写的不是真正的数据，而仅仅是源文件的文件名及 inode 号。
<br> basic -------Linux命令权限相关的命令 重要方面------------------------------------
<br> Linux权限位
<br> -rw-r--r--.1 
<br>第 1 位代表文件类型。Linux 不像 Windows 使用扩展名表示文件类型，而是使用权限位的第 1 位表示文件类型。虽然 Linux 文件的种类不像 Windows 中那么多，但是分类也不少，详细情况可以使用"info ls"命令查看。笔者在这里只讲一些常见的文件类型。
<br>-"-"：普通文件。
<br>-"b"：块设备文件。这是一种特殊设备文件，存储设备都是这种文件，如分区文件 /dev/sda1 就是这种文件。
<br>-"c"：字符设备文件。这也是特殊设备文件，输入设备一般都是这种文件，如鼠标、键盘等。
<br>-"d"：目录文件。Linux 中一切皆文件，所以目录也是文件的一种。
<br>-"l"：软链接文件。
<br>-"p"：管道符文件。这是一种非常少见的特殊设备文件。
<br>-"s"：套接字文件。这也是一种特殊设备文件，一些服务支持 Socket 访问，就会产生这样的文件。
<br>第2-4 位代表文件所有者的权限。
<br>-r:代表 read，是读取权限。
<br>-w:代表 write，是写权限。
<br>-x:代表 execute，是执行权限。
<br>如果有字母，则代表拥有对应的权限；如果是"-"，则代表没有对应的权限。
<br>第 5~7 位代表文件所属组的权限，同样拥有"rwx"权限。
<br>第 8~10 位代表其他人的权限，同样拥有"rwx"权限。
<br> 设置权限命令: 修改文件或目录的权限
<br> chmod [选项] 权限模式 文件名
<br> 权限模式(这里只是基本权限,不包括特殊权限)
<br>权限模式
<br>chmod 命令的权限模式的格式是"[ugoa] [[+-=] [perms]]"，也就是"[用户身份][[赋予方式][权限]]"的格式，我们来解释一下。

<br>用户身份：
<br>-u：代表所有者(user)。
<br>-g：代表所属组(group)。
<br>-o：代也人(other)。
<br>-a：代表全部身份(all)。

<br>赋予方式：
<br>-+：加入权限。
<br>--：减去权限。
<br>-=：设置权限。

<br>权限：
<br>-r：读取权限(read)。
<br>-w：写权限(write)。
<br>-x：执行权限(execute)。

<br>数字权限 自我感觉这个最好用,而且B格高点就用了
<br>权限的赋予方式是最简单的，但是不如之前的字母权限好记、直观。
<br>我们来看看这些数字权限的含义,
<br>4：代表"r"权限。
<br>2：代表"w"权限。
<br>1：代表"x"权限。
<br> chomd 755 [某个文件的文件名] 755 表示该文件所有者拥有RWX读写操作权限(4+2+1),权限组跟其他用户拥有读写权限(4+1=5);
