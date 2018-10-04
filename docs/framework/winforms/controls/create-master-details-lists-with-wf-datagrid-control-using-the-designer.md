---
title: 如何：使用设计器用 Windows 窗体 DataGrid 控件创建主/详细信息列表
ms.date: 03/30/2017
helpviewer_keywords:
- master-details lists
- DataGrid control [Windows Forms], master-details lists
- related tables [Windows Forms], displaying in DataGrid control
ms.assetid: 19438ba2-f687-4417-a2fb-ab1cd69d4ded
ms.openlocfilehash: aec02e38fbe80302108397543144b1cc9c3ea346
ms.sourcegitcommit: 69229651598b427c550223d3c58aba82e47b3f82
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "48266768"
---
# <a name="how-to-create-master-details-lists-with-the-windows-forms-datagrid-control-using-the-designer"></a>如何：使用设计器用 Windows 窗体 DataGrid 控件创建主/详细信息列表

> [!NOTE]
>  <xref:System.Windows.Forms.DataGridView> 控件取代了 <xref:System.Windows.Forms.DataGrid> 控件并添加了功能；但是，可以选择保留 <xref:System.Windows.Forms.DataGrid> 控件以实现向后兼容并供将来使用。 有关详细信息，请参阅 [Windows 窗体 DataGridView 控件与 DataGrid 控件之间的区别](../../../../docs/framework/winforms/controls/differences-between-the-windows-forms-datagridview-and-datagrid-controls.md)。  
  
 如果你<xref:System.Data.DataSet>包含一系列相关表，则可以使用两个<xref:System.Windows.Forms.DataGrid>控件以显示母版-详细信息格式的数据。 一个<xref:System.Windows.Forms.DataGrid>指定主网格中，且第二个指定要在详细信息网格。 当在主列表中选择一个条目时，所有相关的子条目所示详细信息列表。 例如，如果你<xref:System.Data.DataSet>包含 Customers 表和相关的 Orders 表，需要指定要将主网格客户表和 Orders 表中，会在详细信息网格。 在主网格中选择客户后，将详细信息网格中显示所有关联订单表中与该客户的订单。  
  
 下面的过程需要**Windows 应用程序**项目 (**文件** > **新建** > **项目** >  **Visual C#** 或**Visual Basic** > **经典桌面** > **Windows 窗体应用程序**)。  
  
> [!NOTE]
>  显示的对话框和菜单命令可能会与“帮助”中的描述不同，具体取决于你现用的设置或版本。 若要更改设置，请在 **“工具”** 菜单上选择 **“导入和导出设置”** 。 有关详细信息，请参阅[个性化设置 Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide)。  
  
### <a name="to-create-a-master-details-list-in-the-designer"></a>若要在设计器中创建母版-详细信息列表  
  
1.  添加两个<xref:System.Windows.Forms.DataGrid>到窗体控件。 有关详细信息，请参阅[如何： 向 Windows 窗体添加控件](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md)。 在 Visual Studio 2005 中，<xref:System.Windows.Forms.DataGrid>控件不在**工具箱**默认情况下。 有关详细信息，请参阅[如何： 将项添加到工具箱](https://msdn.microsoft.com/library/458e119e-17fe-450b-b889-e31c128bd7e0)。  
  
    > [!NOTE]
    >  以下步骤不是适用于 Visual Studio 2005 中，使用**数据源**设计时数据绑定的窗口。 有关详细信息，请参阅[将控件绑定到 Visual Studio 中的数据](/visualstudio/data-tools/bind-controls-to-data-in-visual-studio)并[如何： 在 Windows 窗体应用程序中显示相关数据](https://msdn.microsoft.com/library/60b1f1ec-6257-42ab-83f0-06d54ed364fd)。  
  
2.  将从两个或多个表拖**服务器资源管理器**到窗体。  
  
3.  从**数据**菜单中，选择**生成数据集**。  
  
4.  设置使用在 XML 设计器在表之间的关系。 有关详细信息，请参阅"如何： 创建一个对多关系中的 XML 架构和数据集"MSDN 上。  
  
5.  通过选择保存关系**全部保存**从**文件**菜单。  
  
6.  配置<xref:System.Windows.Forms.DataGrid>控制你想要指定主网格中，按如下所示：  
  
    1.  选择<xref:System.Data.DataSet>从下拉列表中<xref:System.Windows.Forms.DataGrid.DataSource%2A>属性。  
  
    2.  从下拉列表中选择主表 （例如，"客户"）<xref:System.Windows.Forms.DataGrid.DataMember%2A>属性。  
  
7.  配置<xref:System.Windows.Forms.DataGrid>控件指定详细信息网格中，按如下所示：  
  
    1.  选择<xref:System.Data.DataSet>从下拉列表中<xref:System.Windows.Forms.DataGrid.DataSource%2A>属性。  
  
    2.  选择从下拉列表中的母版和详细信息表之间的关系 (例如，"Customers.CustOrd")<xref:System.Windows.Forms.DataGrid.DataMember%2A>属性。 若要查看的关系，通过单击加号展开节点 (**+**) 旁边的下拉列表中的主表。  
  
## <a name="see-also"></a>请参阅  
 [DataGrid 控件](../../../../docs/framework/winforms/controls/datagrid-control-windows-forms.md)  
 [DataGrid 控件概述](../../../../docs/framework/winforms/controls/datagrid-control-overview-windows-forms.md)  
 [如何：将 Windows 窗体 DataGrid 控件绑定到数据源](../../../../docs/framework/winforms/controls/how-to-bind-the-windows-forms-datagrid-control-to-a-data-source.md)  
 [在 Visual Studio 中将控件绑定到数据](/visualstudio/data-tools/bind-controls-to-data-in-visual-studio)
