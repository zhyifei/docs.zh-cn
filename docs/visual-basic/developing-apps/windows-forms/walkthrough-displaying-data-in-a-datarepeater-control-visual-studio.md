---
title: 演练：在 DataRepeater 控件中显示数据 (Visual Studio)
ms.date: 07/20/2015
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataRepeater, walkthrough
ms.assetid: 65dcdb95-6c3e-47cc-987d-190000f71653
ms.openlocfilehash: 8e64a819e9670a29e97140a32c81f5ff9006f83e
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/01/2018
ms.locfileid: "43388547"
---
# <a name="walkthrough-displaying-data-in-a-datarepeater-control-visual-studio"></a>演练：在 DataRepeater 控件中显示数据 (Visual Studio)
本演练提供了在 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> 控件中显示绑定数据的完整基本方案。  
  
## <a name="prerequisite"></a>必备组件  
 本演练需要 Northwind 示例数据库。  
  
 如果在开发计算机上没有此数据库，您可以从 Microsoft 下载中心下载它。 有关说明，请参阅[下载示例数据库](../../../framework/data/adonet/sql/linq/downloading-sample-databases.md)。  
  
## <a name="overview"></a>概述  
 本演练的第一部分主要有以下四个任务：  
  
-   创建解决方案。  
  
-   添加 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> 控件。  
  
-   添加数据源。  
  
-   添加数据绑定控件。  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
## <a name="creating-a-datarepeater-solution"></a>创建 DataRepeater 解决方案  
 在第一步中，创建项目和解决方案。  
  
#### <a name="to-create-a-datarepeater-solution"></a>创建 DataRepeater 解决方案的步骤  
  
1.  在 Visual Studio**文件**菜单上，单击**新项目**。  
  
2.  在 **“新建项目”** 对话框中的 **“项目类型”** 窗格中，展开 **“Visual Basic”**，然后单击 **“Windows”**。  
  
3.  在 **“模板”** 窗格中，单击 **“Windows 窗体应用程序”**。  
  
4.  在“名称”框中键入 `DataRepeaterApp`。  
  
5.  单击 **“确定”**。  
  
     Windows 窗体设计器即会打开。  
  
6.  在“Windows 窗体设计器”中选择窗体。 在中**属性**窗口中，将**大小**属性设置为`800, 700`。  
  
## <a name="adding-a-datarepeater-control"></a>添加 DataRepeater 控件  
 在此步骤中，向窗体添加一个 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> 控件。  
  
#### <a name="to-add-a-datarepeater-control"></a>添加 DataRepeater 控件的步骤  
  
1.  在 **“视图”** 菜单上单击 **“工具箱”**。  
  
     将打开 **“工具箱”** 。  
  
2.  选择**Visual Basic PowerPacks**选项卡。  
  
3.  拖动<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>控件拖动到**Form1**。  
  
4.  在属性窗口中设置**位置**属性设置为`0, 25`。  
  
5.  设置**大小**属性设置为`460, 600`。  
  
## <a name="adding-a-data-source"></a>添加数据源  
 在此步骤中，为 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> 控件添加一个数据源。  
  
#### <a name="to-add-a-data-source"></a>添加数据源  
  
1.  在 **“数据”** 菜单上，单击 **“显示数据源”**。  
  
2.  在 **“数据源”** 窗口中，单击 **“添加新数据源”**。  
  
3.  在 **“选择数据源类型”** 页上选择 **“数据库”** ，然后单击 **“下一步”**。  
  
4.  在 **“选择你的数据连接”** 页上执行下列步骤之一：  
  
    -   如果下拉列表中包含到 Northwind 示例数据库的数据连接，请单击该连接。  
  
         或  
  
    -   单击**新的连接**来配置新的数据连接。 有关详细信息，请参阅[添加新连接](/visualstudio/data-tools/add-new-connections)。  
  
5.  如果数据库需要密码，请选择该选项以包括敏感数据，然后单击 **“下一步”**。  
  
    > [!NOTE]
    >  如果出现一个对话框，单击**是**将文件保存到你的项目。  
  
6.  单击**下一步**上**将连接字符串保存到应用程序配置文件**页。  
  
7.  在 **“选择数据库对象”** 页面上展开 **“表”** 节点。  
  
8.  选中的复选框旁边**客户**并**订单**表，并单击**完成**。  
  
     **NorthwindDataSet**添加到你的项目和**客户**并**订单**表中出现**数据源**窗口。  
  
## <a name="adding-data-bound-controls"></a>添加数据绑定控件  
 在此步骤中，向 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>添加数据绑定控件。  
  
#### <a name="to-add-data-bound-controls"></a>添加数据绑定控件  
  
1.  在中**数据源**窗口中，选择的顶级节点**客户**表。  
  
2.  将表拖放类型更改**详细信息**通过单击**详细信息**表节点上的下拉列表中。  
  
3.  选择**客户**表节点，然后将其拖动到项模板区域 （上半部分区域） 的<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>控件。  
  
     一个<xref:System.Windows.Forms.BindingNavigator>控件添加到窗体，并**NorthwindDataSet**， **CustomersBindingSource**， **CustomersTableAdapter**， **TableAdapterManager**，并**CustomersBindingNavigator**组件添加到组件栏。  
  
4.  选择所有字段及其关联标签，并将它们置于项模板区域左边缘附近。  
  
5.  选择的最后五个字段 (**区域**，**邮政编码**，**国家/地区**， **Phone**，并**传真**) 和及其关联的标签并将它们上移到前六个字段的右侧。  
  
6.  选择项模板（控件的上半部分区域）。  
  
7.  在属性窗口中设置**大小**属性设置为`427, 170`。  
  
 此时，你就得到了一个有效的应用程序，该应用程序将显示客户的重复列表。 可以按 F5 运行该应用程序、更改数据以及添加或删除客户记录。  
  
 在后续的可选步骤中，你将学习如何自定义 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> 控件。  
  
## <a name="next-steps-optional"></a>后续步骤（可选）  
 演练的本部分有以下四个可选任务：  
  
-   更改 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> 控件的外观。  
  
-   防止用户添加或删除记录。  
  
-   向 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> 控件添加搜索功能。  
  
-   向 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> 控件添加主表和详细信息表。  
  
## <a name="changing-the-appearance-of-the-datarepeater-control"></a>更改 DataRepeater 控件的外观  
 在此可选步骤中，你将在设计时更改 `BackColor` 控件的 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> 。 你还将添加代码来以交替颜色显示行以及有条件地更改标签的 `ForeColor` 。  
  
#### <a name="to-change-the-appearance-of-the-control"></a>更改控件外观的步骤  
  
1.  在 Windows 窗体设计器中，选择 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> 控件的主（下半部分）区域。  
  
2.  在“属性”窗口中，将 `BackColor` 属性设置为白色。  
  
3.  双击 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> 打开代码编辑器。  
  
4.  在代码编辑器中，在事件下拉列表中，单击**DrawItem**。  
  
5.  在 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DrawItem> 事件处理程序中添加下面的代码为 `BackColor`提供一个交替值：  
  
     [!code-csharp[VbPowerPacksDataRepeaterWalkthrough#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/walkthrough-displaying-data-in-a-datarepeater-control-visual-studio_1.cs)]
     [!code-vb[VbPowerPacksDataRepeaterWalkthrough#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/walkthrough-displaying-data-in-a-datarepeater-control-visual-studio_1.vb)]  
  
6.  在 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DrawItem> 事件处理程序中添加下面的代码，以根据条件更改某个标签的 `ForeColor` ：  
  
     [!code-csharp[VbPowerPacksDataRepeaterWalkthrough#2](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/walkthrough-displaying-data-in-a-datarepeater-control-visual-studio_2.cs)]
     [!code-vb[VbPowerPacksDataRepeaterWalkthrough#2](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/walkthrough-displaying-data-in-a-datarepeater-control-visual-studio_2.vb)]  
  
7.  按 F5 运行该应用程序并查看自定义项。  
  
## <a name="preventing-users-from-adding-or-deleting-records"></a>防止用户添加或删除记录  
 在此可选步骤中，你将添加代码来防止用户在 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> 控件中添加或删除记录。  
  
#### <a name="to-prevent-users-from-adding-and-deleting-records"></a>防止用户添加和删除记录的步骤  
  
1.  在 Windows 窗体设计器中，双击窗体打开代码编辑器。  
  
2.  将以下代码添加到 `Form_Load` 事件中：  
  
     [!code-csharp[VbPowerPacksDataRepeaterWalkthrough#3](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/walkthrough-displaying-data-in-a-datarepeater-control-visual-studio_3.cs)]
     [!code-vb[VbPowerPacksDataRepeaterWalkthrough#3](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/walkthrough-displaying-data-in-a-datarepeater-control-visual-studio_3.vb)]  
  
3.  在类名下拉列表中，单击**BindingNavigatorDeleteItem**。 在方法名称下拉列表中，单击**EnabledChanged**。  
  
4.  将以下代码添加到 `BindingNavigatorDeleteItem_EnabledChanged` 事件处理程序中：  
  
     [!code-csharp[VbPowerPacksDataRepeaterWalkthrough#4](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/walkthrough-displaying-data-in-a-datarepeater-control-visual-studio_4.cs)]
     [!code-vb[VbPowerPacksDataRepeaterWalkthrough#4](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/walkthrough-displaying-data-in-a-datarepeater-control-visual-studio_4.vb)]  
  
    > [!NOTE]
    >  此步骤是必需的因为<xref:System.Windows.Forms.BindingSource>将启用**DeleteItem**按钮每次当前记录更改时。  
  
5.  按 F5 运行该应用程序。 请注意， **DeleteItem**按钮处于禁用状态以及你不能删除项目，通过按 DELETE 键。  
  
## <a name="adding-search-capability-to-the-datarepeater-control"></a>向 DataRepeater 控件添加搜索功能  
 在此可选步骤中，你将实现在 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> 控件中搜索值的功能。 如果找到了搜索字符串，该控件将选中包含该值的项并将该项滚动到视图中。  
  
#### <a name="to-add-search-capability"></a>添加搜索功能的步骤  
  
1.  拖动<xref:System.Windows.Forms.TextBox>控件从**工具箱**拖到窗体包含<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>控件。  
  
     将它置于 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> 控件的下方。  
  
2.  在属性窗口中更改**名称**属性设置为**SearchTextBox**。  
  
3.  拖动<xref:System.Windows.Forms.Button>控件从**工具箱**拖到窗体包含<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>控件。 将它置于 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> 控件的下方。  
  
4.  在属性窗口中更改**名称**属性设置为**SearchButton**。 更改**文本**属性设置为**搜索**。  
  
5.  双击 <xref:System.Windows.Forms.Button> 控件打开代码编辑器，并将以下代码添加到 `SearchButton_Click` 事件处理程序中。  
  
     [!code-csharp[VbPowerPacksDataRepeaterWalkthrough#5](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/walkthrough-displaying-data-in-a-datarepeater-control-visual-studio_5.cs)]
     [!code-vb[VbPowerPacksDataRepeaterWalkthrough#5](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/walkthrough-displaying-data-in-a-datarepeater-control-visual-studio_5.vb)]  
  
6.  按 F5 运行该应用程序。 键入客户 ID，采用**SearchTextBox**然后单击**搜索**按钮。  
  
## <a name="adding-a-master-and-detail-table-to-the-datarepeater"></a>向 DataRepeater 添加主表和详细信息表  
 在此可选步骤中，你将再添加一个 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> 控件来显示每个客户的相关订单。  
  
#### <a name="to-add-a-master-and-detail-table"></a>添加主表和详细信息表的步骤  
  
1.  将另一个<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>控件从**Visual Basic PowerPacks**选项卡中**工具箱**拖到窗体。  
  
2.  在属性窗口中设置**位置**属性设置为`465, 25`。  
  
3.  设置**大小**属性设置为`315, 600`。  
  
4.  在中**数据源**窗口中，展开**客户**表节点，然后选择详细信息节点**订单**表。  
  
5.  此拖放类型更改**订单**通过单击详细信息表**详细信息**表节点上的下拉列表中。  
  
6.  将该**订单**表节点拖到第二个项模板区域 （上半部分区域）<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>控件。  
  
     **OrdersBindingSource**组件和一个**OrdersTableAdapter**组件添加到组件栏。  
  
7.  按 F5 运行该应用程序。 当你在第一个 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> 控件中选择每个客户时，该客户的订单会显示在第二个 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> 控件中。  
  
## <a name="see-also"></a>请参阅  
 [DataRepeater 控件简介](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-datarepeater-control-visual-studio.md)  
 [如何：在 DataRepeater 控件中显示绑定数据](../../../visual-basic/developing-apps/windows-forms/how-to-display-bound-data-in-a-datarepeater-control-visual-studio.md)  
 [如何：在 DataRepeater 控件中显示未绑定的控件](../../../visual-basic/developing-apps/windows-forms/how-to-display-unbound-controls-in-a-datarepeater-control-visual-studio.md)  
 [如何：更改 DataRepeater 控件的布局](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-layout-of-a-datarepeater-control-visual-studio.md)  
 [如何：在 DataRepeater 控件中显示项标题](../../../visual-basic/developing-apps/windows-forms/how-to-display-item-headers-in-a-datarepeater-control-visual-studio.md)  
 [如何：在 DataRepeater 控件中搜索数据](../../../visual-basic/developing-apps/windows-forms/how-to-search-data-in-a-datarepeater-control-visual-studio.md)  
 [如何： 使用两个 DataRepeater 控件 (Visual Studio) 创建母版/详细信息窗体](../../../visual-basic/developing-apps/windows-forms/how-to-create-a-master-detail-form-by-using-two-datarepeater-controls.md)  
 [如何：更改 DataRepeater 控件的外观](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio.md)  
 [如何：禁止添加和删除 DataRepeater 项](../../../visual-basic/developing-apps/windows-forms/how-to-disable-adding-and-deleting-datarepeater-items-visual-studio.md)  
 [DataRepeater 控件疑难解答](../../../visual-basic/developing-apps/windows-forms/troubleshooting-the-datarepeater-control-visual-studio.md)
