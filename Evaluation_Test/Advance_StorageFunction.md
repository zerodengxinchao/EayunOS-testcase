# 高级存储功能

|用例编号|操作|预期结果|实际结果|备注|
|--------|----|--------|--------|----|
|64|创建浮动磁盘.前提:<br/><br/>-   已经配置好了标准的 OVIRT 的环境, 或者至少配置好了最小化得 OVIRT 环境<br/><br/>-   已经配置好 OVIRT 环境, 并能利用该环境安装虚拟机<br/><br/>1.  在导航面板上点击磁盘标签<br/><br/>2.  点击导航面板左上角的添加按钮. 一个添加虚拟磁盘的 面板将会打开.<br/><br/>3.  在大小的输入框里, 输入10, 设置磁盘大小为 10GB.<br/><br/>4.  在别名输入框里, 输入 Alias.<br/><br/>5.  在描述输入框里输入相关的描述.<br/><br/>6.  其它设置保留默认.<br/><br/>7.  点击窗口又下角的确定创建虚拟磁盘.<br/><br/>|一个名为 Disk1 的浮动磁盘已经创建好了, 在虚拟机的磁盘列表上能正常显示.|||
|65|给虚拟机分配浮动磁盘<br/><br/>1.  在导航面板上点击虚拟机标签.<br/><br/>2.  从显示的虚拟机列表上选择待操作的虚拟机, 鼠标单击该虚拟机, 可以看到下<br/>    方的详细面板上将会显示该虚拟机的所有信息.<br/><br/>3.  在详细信息面板上, 点击磁盘, 将会显示附加到该虚拟机 上的所有磁盘.<br/><br/>4.  点击添加, 打开添加磁盘窗口.<br/><br/>5.  勾选附加磁盘, 将会列出所有浮动磁盘.<br/><br/>6.  选择上面创建的附加磁盘 Disk1.<br/><br/>7.  点击窗口又下角的确定给虚拟机分配浮动磁盘.<br/><br/>|将 Disk1 分配给了虚拟机, 能在虚拟机的磁盘列表上看到 Disk1.|||
|66|设置共享磁盘<br/><br/>1.  在导航面板上点击虚拟机标签.<br/><br/>2.  从显示的虚拟机列表上选择待操作的虚拟机, 鼠标单击该虚拟机, 可以看到下<br/>    方的详细面板上将会显示该虚拟机的所有信息.<br/><br/>3.  在详细信息面板上, 点击磁盘, 将会显示附加到该虚拟机 上的所有磁盘.<br/><br/>4.  点击Disk1.<br/><br/>5.  点击详细信息面板左上角的编辑, 打开编辑虚拟磁盘窗口.<br/><br/>6.  勾选编辑窗口右侧的是可共享的, 如图:<br/><br/>7.  点击窗口又下角的确定设置该磁盘为共享的.<br/><br/>|在虚拟机的磁盘列表上, Disk1 多了一个共享的图标.|||
|67|把共享磁盘分配给另外的虚拟机<br/><br/>1.  在导航面板上点击虚拟机标签.<br/><br/>2.  从显示的虚拟机列表上选择想要附加共享磁盘的虚拟机, 鼠标单击该虚拟机,<br/>    可以看到下方的详细面板上将会显示该虚拟机的所有信息.<br/><br/>3.  在详细信息面板上, 点击磁盘, 将会显示附加到该虚拟机 上的所有磁盘.<br/><br/>4.  勾选附加磁盘, 将会列出所有浮动磁盘. 和共享的磁盘,<br/>    可以看到我们的Disk1也在这里面.<br/><br/>5.  选择上面设置的共享磁盘 Disk1, 如图:<br/><br/>6.  点击窗口又下角的确定把该磁盘分配给虚拟机.<br/><br/>|将共享磁盘 Disk1 分配给了虚拟机, 在该虚拟机的磁盘列表上能看到.|||
|68|创建虚拟机的在线快照<br/><br/>1.  在导航面板上点击虚拟机标签.<br/><br/>2.  从显示的虚拟机列表上选择想要创建快照的虚拟机, 鼠标单击该虚拟机,<br/>    可以看到下方的详细面板上将会显示该虚拟机的所有信息.<br/><br/>3.  如果该虚拟机是处于关机状态, 则开启它<br/><br/>4.  在详细信息面板上, 点击快照, 将会显示该虚拟机 的所有快照.<br/><br/>5.  点击详细面板左上角的创建, 打开创建快照窗口, 输入快照的简单描述<br/>    snap1.<br/><br/>6.  点击窗口又下角的确定创建快照<br/><br/>|在虚拟机的快照列表下, 可以看到新创建的快照 snap1.同时快照可以正常使用|||
|69|快照恢复虚拟机<br/><br/>1.  在导航面板上点击虚拟机标签.<br/><br/>2.  从显示的虚拟机列表上选择刚才创建了快照的虚拟机, 鼠标单击该虚拟机,<br/>    可以看到下方的详细面板上将会显示该虚拟机的所有信息.<br/><br/>3.  在详细信息面板上, 点击快照, 将会显示该虚拟机 的所有快照.<br/><br/>4.  鼠标单击需要的快照, 然后点击克隆, 打开从快照克隆虚拟机窗口<br/><br/>5.  输入需要的名称, 描述(可选), 注释(可选)<br/><br/>6.  点击窗口又下角的确定克隆虚拟机.<br/><br/>|新创建的虚拟机显示在虚拟机列表中.|||
|70|给虚拟机直接分配 LUN<br/><br/>1.  在导航面板上点击虚拟机标签.<br/><br/>2.  从显示的虚拟机列表上选择需要分配 LUN 的虚拟机, 鼠标单击该虚拟机,<br/>    可以看到下方的详细面板上将会显示该虚拟机的所有信息.<br/><br/>3.  在详细信息面板上, 点击磁盘.<br/><br/>4.  勾选添加, 弹出添加虚拟磁盘窗口.<br/><br/>5.  点击外部.<br/><br/>6.  填写描述.<br/><br/>7.  在下面的窗口上, 点击发现目标, 填写 iSCSI 服务器的地 址和端口<br/><br/>8.  点击发现.<br/><br/>9.  在发现的 iSCSI LUN 窗口, 选择要登陆的 target, 点击登陆.<br/><br/>10. 点击目标旁的+按钮, 展开该 target 拥有的 LUNs.<br/><br/>11. 选中需要使用的 LUN.<br/><br/>12. 点击确定, 完成 LUN 的分配.<br/><br/>|在虚拟机的磁盘列表上看到分配给该虚拟机的 LUN.|||
|71|给虚拟机直接分配 FC LUNs<br/><br/>给虚拟机知己分配 FC LUNs 和给虚拟机直接分配 iSCSI LUNs 的操作步骤一样, 只不过分配 LUNs 的时候不需要发现 FC LUNs.|在虚拟机的磁盘列表上看到分配给该虚拟机的 FC LUN.|||<br/><br/>> **Note**<br/>><br/>> 其他注意事项：
