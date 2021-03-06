# 添加 FCP 存储

**概述**<br/>
EayunOS 平台通过从已存在的 LUN 组成的逻辑卷组创建存储域来支持 FCP
存储。同一时间，逻辑卷组和 LUN 都只能附加到一个数据域中。

EayunOS系统管理员需要对存储域的网络有个知识概念。SAN 使用光纤通到协议（FCP）为主机与共享外部存储域提供通信。所以这种存储被成为FCP存储。

>**注意**
>
>只能添加 iSCSI 存储域到类型为 iSCSI 的数据中心。

**添加 FCP 存储**

1. 点击**存储**标签，列出目前存在的所有存储域。

2. 点击**新建域**按钮打开**新建域**窗口，如图：

 ![添加FCP存储](../../images/storage-add-fcp.png)

 **添加 FCP 存储**

3. 输入存储域的**名称**。

4. 在**数据中心**下拉框选择一个 FCP
类型的数据中心，如果暂时没有该类型的数据中心，先选择 **(none)**。

5. 从**域功能/存储域类型**下拉菜单中选择 **Data/Fibre Channel**。选择**格式**。所选数据中心不匹配的存储域不会显示。

6. 在**使用主机**下拉菜单，选择适当的主机。

 > **重要**
 >
 > 与存储域的通信都通过所选择的*使用主机*而 不是通过 EayunOS
 > 系统本身。所以至少数据中心中必须有一台活动主机才能够配置存储。

7. 如果之前操作选择了 **Data/Fibre Channel** 存储类型，则新建域窗口会自动显示发现的 targets 中没有使用的  LUN。选择 **LUN ID** 复选框选择可用的 LUNs。

8. 另外，您还可以配置高级参数。

    * **点高级参数**。

    * 在**警告级低存储空间**项中输入一个百分比值。当存储域中的空闲空间低于这个值时，用户登录时就会显示一个警告信息。

    * 在**严重的空间操作限制阈值**项中输入一个值（以 GB 为单位）。当存储域中的空闲空间低于这个值时，用户登录时会显示一个错误信息，任何需要使用存储空间的操作（包括临时使用存储空间的操作）都会被限制。

    * 如果需要在删除虚拟磁盘后清除它上面的敏感数据，选择**删除后清除**选项。在域创建后，这个选项还可以被修改，但这不会改变已存在的、带有这个选项的存储的行为。

9. 点**确定**创建存储域并关闭窗口。

**结果**<br/>
**存储**标签列表中显示出了新建的 FCP 存储域，一开始是 **Locked** 状态的，准备就绪后将自动附加到数据中心上。


