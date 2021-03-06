# 虚拟机磁盘

|用例编号|测试目的|操作|预期结果|实际结果|备注|
|--------|--------|----|--------|--------|----|
|1|添加内部的虚拟机磁盘|<ol><li>在虚拟机标签列表下, 指定虚拟机</li><li>在该虚拟机详细面板下点击磁盘</li><li>点击菜单内的添加</li><li>设置大小, 描述, 点击确定</li></ol>|磁盘列表下显示新添加的磁盘.||||
|2|添加附加的虚拟机磁盘|<ol><li>点击磁盘标签</li><li>点击添加</li><li>在添加虚拟磁盘窗口, 设置大小, 别名(Disk1), 描述, 点击确定</li><li>在虚拟机标签列表下, 指定虚拟机</li><li>在该虚拟机详细面板下点击磁盘</li><li>点击菜单内的添加</li><li>勾选附加磁盘, 勾选 Disk1, 点击确定</li></ol>|磁盘列表下显示新添加的磁盘 Disk1||||
|3|添加外部的虚拟机磁盘|<ol><li>在虚拟机标签列表下, 指定虚拟机</li><li>在该虚拟机详细面板下点击磁盘</li><li>点击菜单内的添加</li><li>勾选外部(直接 LUN)</li><li>设置别名</li><li>点击发现目标, 填写 iSCSI 的地址, 和端口, 点击发现</li><li>在列出的目标列表中, 选择要登陆的目标, 点击登陆</li><li>点击登陆后的目标的【+】, 展开目标的 LUN</li><li>勾选要加入的 LUN, 点击确定</li></ol>|磁盘列表下显示新添加的 LUN.|||
|4|Move数据域之间磁盘迁移|<ul><li>前提：</li></ul><ol><li>该数据中心下至少有两个Data Domain</li></ol><ul><li>操作：</li></ul><ol><li>在虚拟机列表下，指定虚拟机（独立虚拟机并且非虚拟机池内分离出来的虚拟机状态为运行状态）</li><li>在该虚拟机详细面板下点击Disks</li><li>选中该列表显示的磁盘，点击菜单内的Move</li><li>在Move Disk（s）,下选择目标Data Domain</li><li>点击OK</li></ol>|迁移成功|||
|5|Move数据域之间磁盘迁移|<ul><li>前提：</li></ul><ol><li>该数据中心下至少有两个Data Domain</li></ol><ul><li>操作：</li></ul><ol><li>在虚拟机列表下，指定虚拟机（独立虚拟机并且非虚拟机池内分离出来的虚拟机状态状态为关闭状态）</li><li>在该虚拟机详细面板下点击Disks</li><li>选中该列表显示的磁盘，点击菜单内的Move</li><li>在Move Disk（s）,下选择目标Data Domain</li><li>点击OK</li></ol>|磁盘迁移成功|||
|6|Move数据域之间磁盘迁移|<ul><li>前提：</li></ul><ol><li>该数据中心下至少有两个Data Domain</li></ol><ul><li>操作：</li></ul><ol><li>在虚拟机列表下，指定虚拟机（虚拟机池内的虚 拟机状态为运行状态）</li><li>在该虚拟机详细面板下点击Disks</li><li>选中该列表显示的磁盘，点击菜单内的Move</li><li>在Move Disk（s）,下选择目标Data Domain</li><li>点击OK</li></ol>|虚拟机池内运行状态的虚拟机不能迁移|||
|7|Move数据域之间磁盘迁移|<ul><li>前提：</li></ul><ol><li>该数据中心下至少有两个Data Domain</li></ol><ul><li>操作：</li></ul><ol><li>在虚拟机列表下，指定虚拟机（虚拟机池内分离 的虚拟机状态为关闭状态）</li><li>在该虚拟机详细面板下点击Disks</li><li>选中该列表显示的磁盘，点击菜单内的Move</li><li>在Move Disk（s）,下选择目标Data Domain</li><li>点击OK</li></ol>|不能迁移，目标存储域为空且不能编辑|||
|8|Move数据域之间磁盘迁移|<ul><li>前提：</li></ul><ol><li>该数据中心下至少有两个Data Domain</li><ol><ul><li>操作：</li></ul><ol><li>在虚拟机列表下，指定虚拟机（虚拟机池内分离 的虚拟机状态为运行）</li></li>在该虚拟机详细面板下点击Disks</li><li>选中该列表显示的磁盘，点击菜单内的Move</li><li>在Move Disk（s）,下选择目标Data Domain</li><li>点击OK</li></ol>|不能迁移，运行虚拟机不能迁移||测试迁移磁盘功能 虚拟机池内分离的虚拟机状态为运行状态的虚拟机|
|9|Move数据域之间磁盘迁移|<ul><li>前提：</li></ul><ol><li>该数据中心下至少有两个Data Domain</li></ol><ul><li>操作：</li></ul><ol><li>在虚拟机列表下，指定虚拟机（模板创建的虚拟 机）</li><li>在该虚拟机详细面板下点击Disks</li><li>选中该列表显示的磁盘，点击菜单内的Move</li><li>在Move Disk（s）,下选择目标Data Domain</li><li>点击OK</li></ol>|磁盘迁移成功|||
|10|Move数据域之间磁盘迁移|<ul><li>前提：</li></ul><ol><li>该数据中心下至少有两个Data Domain</li></ol><ul><li>操作：</li></ul><ol><li>在虚拟机列表下，指定虚拟机（从快照创建的虚 拟机）</li><li>在该虚拟机详细面板下点击Disks</li><li>选中该列表显示的磁盘，点击菜单内的Move</li><li>在Move Disk（s）,下选择目标Data Domain</li><li>点击OK</li></ol>|迁移成功|||
|11|Edit 虚拟机磁盘|<ol><li>在虚拟机列表下，指定虚拟机</li><li>在该虚拟机详细面板下点击Disks</li><li>在Disk列表下选中Disk</li><li>点击菜单内的Edit，设置完毕后点击OK</li></ol>|磁盘编辑完成|||
|12|Remove虚拟机磁盘（关闭状态的虚拟机）|<ol><li>在虚拟机列表下，指定虚拟机</li><li>在该虚拟机详细面板下点击Disks</li><li>在Disk列表下选中Disk</li><li>点击菜单内的Remove，在Remove Disk（s）框选 中Remove permanently</li><li>点击OK</li></ol>|磁盘删除成功|||
|13|Active虚拟机磁盘（虚拟机磁盘为非Active状态）|<ol><li>在虚拟机列表下，指定虚拟机</li><li>在该虚拟机详细面板下点击Disks</li><li>在Disk列表下选中Disk</li><li>点击菜单内的Active</li></ol>|磁盘被激活|||
|14|Deactive虚拟机磁盘|</li><li>在虚拟机列表下，指定虚拟机</li><li>在该虚拟机详细面板下点击Disks</li><li>在Disk列表下选中Disk</li><li>点击菜单内的Deactive</li></ol>|使磁盘无效，标志变为Inactive|||
|15|Scan Alignment虚拟机磁盘|<ol><li>在虚拟机列表下，指定虚拟机</li><li>在该虚拟机详细面板下点击Disks</li><li>在Disk列表下选中Disk，将磁盘Deactive</li><li>右键该磁盘，选择菜单内的Scan Alignment</li></ol>|||不确定此功能在什么情况下使用 虚拟机关机磁盘变为Inactive状态下也不可点 目前只有数据中心宕掉后的虚拟机此项可点|
|16|磁盘热添加|<ol><li>在虚拟机列表, 指定运行的虚拟机</li><li>在该虚拟机详细面板下点击磁盘</li><li>点击添加</li><li>设置磁盘大小, 点击确定</li><li>选中添加的磁盘, 点击激活</li></ol>|在磁盘列表上多了一个磁盘, 登陆进虚拟机, 可以看到虚拟机里多了一个磁盘.|||
|17|磁盘热删除|<ol><li>在虚拟机列表, 指定运行的虚拟机</li><li>在该虚拟机详细面板下点击磁盘</li><li>选中待删除的磁盘, 点击取消激活</li><li>点击删除</li><li>在弹出的窗口上选中永久性的删除, 点击确定</li></ol>|在磁盘列表上该磁盘消失了, 登陆进虚拟机, 相关的磁盘显示被拔出.|||
|18|创建共享磁盘（Internal）|<ol><li>在虚拟机列表下，指定某一虚拟机</li><li>在该虚拟机详细面板下点击Disks</li><li>点击Add，选择Internal，填充磁盘大小，描述等信息，设置共享</li><li>点击OK，磁盘创建完成，会有一个小手的标志代表是共享磁盘</li><li>在虚拟机列表下，指定其他虚拟机</li><li>在该虚拟机详细面板下点击Disks</li><li>点击Add，在Add Virtual Disk，选中 Attach Disk，在显示磁盘列表下选中共享磁盘，点击OK</li><li>磁盘共享给该虚拟机</li></ol>|磁盘实现共享|||
|19|虚拟机关机下磁盘动态扩容|<ol><li>在虚拟机列表下，指定某一处于关机状态的虚拟机</li><li>在该虚拟机详细面板下点击 Disks</li><li>选中要扩容的磁盘, 点击编辑</li><li>在弹出的编辑窗口中, 在扩展大小(GB)中填写需要增加的磁盘容量</li><li>点击确定保存退出</li><li>在该虚拟机的磁盘列表下, 查看该磁盘的虚拟大小</li><li>打开虚拟机, 并登陆, 查看磁盘的大小(linux 可以用 fdisk 查看)</li></ol>|在磁盘列表下虚拟大小变为扩容后的大小, 登陆虚拟机查看磁盘大小变为扩容后的大小.||要想完整使用该功能, 必须在虚拟机内部使用分区扩容工具扩展磁盘分区(比如 linux 上的 resize2fs 和 gparted, windows 上的分区魔术师等)|
|20|虚拟机开机下磁盘动态扩容|<ol><li>在虚拟机列表下，指定某一处于开机状态的虚拟机</li><li>在该虚拟机详细面板下点击 Disks</li><li>选中要扩容的磁盘, 点击编辑</li><li>在弹出的编辑窗口中, 在扩展大小(GB)中填写需要增加的磁盘容量</li><li>点击确定保存退出</li><li>在该虚拟机的磁盘列表下, 查看该磁盘的虚拟大小</li><li>登陆虚拟机, 查看磁盘的大小(linux 可以用 fdisk 查看)</li></ol>|在磁盘列表下虚拟大小变为扩容后的大小, 登陆虚拟机查看磁盘大小变为扩容后的大小.||要想完整使用该功能, 必须在虚拟机内部使用分区扩容工具扩展磁盘分区(比如 linux 上的 resize2fs 和 gparted, windows 上的分区魔术师等)|

