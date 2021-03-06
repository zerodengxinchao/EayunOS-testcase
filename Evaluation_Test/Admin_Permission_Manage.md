# 系统管理员不同权限的层级管理

|  用例编号  |  测试目的  |  操作  |  预期结果  |  实际结果  |  备注  |
|------------|------------|--------|------------|------------|--------|
|50          |为存储域分配存储管理角色|<ol><li>在OVIRT管理平台树形面板先点击【展开所有】（按键，在默认的数据中心下的默认集群，点击【存储】，在【存储】标签下将展现出所有的存储域</li><li>选择您要为用户*tangyan*分配权限的存储域，点击【权限】子标签（本实验采用的例子存储域名叫*local\_iso*）</li><li>点击【添加】按键，弹出【为用户添加权限】对话框，在【搜索】文本框中输入*tangyan*，然后点击【执行】按钮</li><li>选中搜索结果中的*tangyan*，在【要分配的角色】下拉列表框中选择【StorageAdmin】</li><li>点击【确认】，用户的信息（头像、用户以及角色）等会自动显示在【权限】子标签中</li></ol>|为*tangyan*成功赋予【StorageAdmin】角色|            |        |
|51          |虚拟机管理员|<ol><li>在OVIRT管理平台树形面板先点击【展开所有】（按键，在默认的数据中心下的默认集群，点击【虚拟机】，在【虚拟机】标签下将展现出所有的虚拟机</li><li>选择要赋予某用户的虚拟机，然后点击下方【权限】子标签，此例选择的虚拟机叫做*Publican*</li><li>点击【添加】按钮，弹出【为用户添加权限】对话框，在【搜索】文本框中输入*tangyan*，然后点击【执行】</li><li>选中搜索结果中的*tangyan*，在【要分配的角色】下拉列表框中选择【PowerUserRole】点击【确认】</li><li>用户的信息（头像、用户以及角色）等会自动显示在【权限】子标签中</li></ol>|成功为用户*tangyan*赋予虚拟机*Publican*为【PowerUserRole】角色|            |        |
|52          |存储管理角色的权限验证|<ol><li>使用*tangyan*用户登录到管理门户</li><li>在OVIRT管理平台树形面板先点击【展开所有】（按键，在默认的数据中心下的默认集群，点击【存储】，在【存储】标签中将展现出所有的存储域</li><li>选中*local\_iso*，在细节项中，点击【数据中心】子标签，并点击菜单中的【维护】按键，此时ISO域的状态为Inactive</li><li>再次选中ISO域，在细节项中，点击【数据中心】子标签，并点击【激活】按键，此时ISO域的状态为Active</li></ol>|存储域*local\_iso*是可以操作的|            |        |
|53          |存储管理角色的权限验证|<ol><li>使用*tangyan*登录到管理门户中</li><li>在OVIRT管理平台树形面板先点击【展开所有】（按键，在默认的数据中心下的默认集群，点击【存储】，在【存储】标签下将展现出所有的存储域</li><li>选中*local\_iso*，在细节项中，点击【数据中心】子标签，并点击菜单中的【维护】按键，此时ISO域的状态为Inactive</li><li>选中数据存储域，在细节项中，选中【数据中心】子标签下数据存储域之一（数据存储域不是只有一个），并点击子标签菜单中的【维护】按钮</li></ol>|数据中心下数据存储域不是只有一个时，数据存储域是可以做维护激活等操作|            |        |
|54          |虚拟机管理角色的验证|<ol><li>使用用户*tangyan*登录管理门户</li><li>在OVIRT管理平台树形面板先点击【展开所有】（按键，在默认的数据中心下的默认集群，点击【虚拟机】，在【虚拟机】标签下将展现出所有的虚拟机</li><li>选中虚拟机*Publican*，如果它正在运行，则尝试关闭它；如果它没有运行，则启动它，这些均是可以成功的</li></ol>|用户*tangyan*可以正常关闭或启动虚拟机|            |        |
|55          |虚拟机管理角色的验证|<ol><li>使用用户*tangyan*登录管理门户</li><li>在OVIRT管理平台树形面板先点击【展开所有】（按键，在默认的数据中心下的默认集群，点击【虚拟机】，在【虚拟机】标签下将展现出所有的虚拟机</li><li>选中其他任意虚拟机，如果它正在运行，则尝试关闭它；如果它没有运行，则启动它，这次OVIRT会弹出错误的消息框：“没有授权用户执行这个动作。”这说明*tangyan*仅有操作虚拟机*Publican*的权限，而对其它虚拟机则无效</li></ol>|用户不可操作其他的任何虚拟机|            |        |
|56          |创建自定义角色|<ol><li>在OVIRT管理门户的右上角，点击【配置】，在【配置】的对话框中，默认会列出所有的用户和管理员角色，以及自定义的（如果有的话）</li><li>点击菜单中的【新建】，在弹出的对话框中输入和选择相应的信息</li><li>为新的角色命名及简要的描述信息</li><li>选择一个账户类型：用户或管理员</li><li>点击【展开所有】，查看所有的可以赋予权限的对象</li><li>针对每一个对象，根据你希望的角色选择可以进行的操作</li><li>点击【确认】，新的角色出现在角色的列表中</li></ol>|可以成功创建自定义角色|        |

**Note**<br/>><br/>> 其他注意事项：

