# configurable thresholds for storage space per domain

  from: [https://bugzilla.redhat.com/show_bug.cgi?id=1185839](https://bugzilla.redhat.com/show_bug.cgi?id=1185839)
#为每一个存储配置阀值

**简要说明**：每个存储应该存在一个对于存储的限制。当存储域的剩余存储低于设定后，系统将会组织此操作并发出警告

|用例编号|测试目的|操作|预期结果|实际结果|备注|
|--------|--------|----|--------|--------|----|
|01200002|可以为每个存储都配置阀值|<ol><li>点击<b>存储</b>面板下的<b>新建域</b>创建NFS域(命名nfs-export)</li><li>在存储详细面板中可以看到域信息，nfs-export域的空闲域为42G</li><li>选中创建好的域，点击<b>编辑域</b>选择高级参数</li><li>设置警告级低磁盘空间与严重的空间操作限制阀值，设置阀值为42G(方便实现结果)</li><li>在储存下创建磁盘，使用dd指令在磁盘中创建一个大的空文件</li></ol> |在**存储**的详细面板下的**事件**报告中提>示错误|在这个存储详细面板的事件中提示错误并组织次操作，错误提示：<code>Critical,Low disk space .nfs-export domain has 40 GB of free space</code>|测试完成|

