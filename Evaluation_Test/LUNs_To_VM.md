# 给虚拟机分配LUNs

## 给虚拟机分配直接LUNs

在左侧树形面板中点击【系统】，在右侧的详细列表中点击选择【虚拟机】标签。
从显示的虚拟机列表中选择要分配直接LUN的虚拟机，点击该虚拟机的【磁盘】子标签。
点击【磁盘】子标签中的【添加】按键，在弹出的【添加虚拟磁盘】窗口中，选择【外部（直接LUN）】，填写别名、描述。
在下方的窗口中点击【发现目标】，填写iSCSI服务器的地址和端口（端口默认是3260，可以不改）。
点击【发现】。
在发现的iSCSI LUN窗口，点击要登录的target，点击【登录】。
点击目标旁的【+】按钮，展开target拥有的所有LUNs。
选择要使用的LUN。
点击【确定】，完成LUN的分配。
看到虚拟机的【磁盘】子标签下显示刚分配的LUN的信息，该磁盘有LUN的标记。

## 给虚拟机分配FC LUNs

  给虚拟机分配FC LUNs和给虚拟机分配直接LUN的操作步骤一样，只不过分配LUNs的时候不需要发现FC LUNs。
