---
title: "如何：使用设计器用 Windows 窗体 DataGrid 控件创建主/详细信息列表"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- master-details lists
- DataGrid control [Windows Forms], master-details lists
- related tables [Windows Forms], displaying in DataGrid control
ms.assetid: 19438ba2-f687-4417-a2fb-ab1cd69d4ded
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 66de6fb17e3ee5b916c4bb20dfa0799758375406
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-master-details-lists-with-the-windows-forms-datagrid-control-using-the-designer"></a>如何：使用设计器用 Windows 窗体 DataGrid 控件创建主/详细信息列表
> [!NOTE]
>  <xref:System.Windows.Forms.DataGridView> 控件取代了 <xref:System.Windows.Forms.DataGrid> 控件并添加了功能；但是，可以选择保留 <xref:System.Windows.Forms.DataGrid> 控件以实现向后兼容并供将来使用。 有关详细信息，请参阅 [Windows 窗体 DataGridView 控件与 DataGrid 控件之间的区别](../../../../docs/framework/winforms/controls/differences-between-the-windows-forms-datagridview-and-datagrid-controls.md)。  
  
 如果你<xref:System.Data.DataSet>包含一系列相关表，则可以使用两个<xref:System.Windows.Forms.DataGrid>控件以显示主-详细信息格式中的数据。 一个<xref:System.Windows.Forms.DataGrid>指定为将主网格，和第二个指定为详细信息网格。 后在主列表中选择一个条目，所有相关的子项将显示在详细信息列表。 例如，如果你<xref:System.Data.DataSet>包含 Customers 表和相关的 Orders 表，则会指定要将主网格的 Customers 表和 Orders 表的详细信息网格。 时从主网格中选择某个客户时，将在详细信息网格中显示所有与 Orders 表中的客户的订单。  
  
 下面的过程需要**Windows 应用程序**项目。 有关设置此类项目的信息，请参阅[如何： 创建 Windows 应用程序项目](http://msdn.microsoft.com/en-us/b2f93fed-c635-4705-8d0e-cf079a264efa)。  
  
> [!NOTE]
>  显示的对话框和菜单命令可能会与“帮助”中的描述不同，具体取决于你现用的设置或版本。 若要更改设置，请在 **“工具”** 菜单上选择 **“导入和导出设置”** 。 有关详细信息，请参阅[在 Visual Studio 中自定义开发设置](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3)。  
  
### <a name="to-create-a-master-details-list-in-the-designer"></a>在设计器中创建主-详细信息列表  
  
1.  添加两个<xref:System.Windows.Forms.DataGrid>到窗体控件。 有关详细信息，请参阅[如何： 向 Windows 窗体添加控件](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md)。 在[!INCLUDE[vsprvslong](../../../../includes/vsprvslong-md.md)]、<xref:System.Windows.Forms.DataGrid>控件将不处于**工具箱**默认情况下。 有关详细信息，请参阅[如何： 将项添加到工具箱](http://msdn.microsoft.com/en-us/458e119e-17fe-450b-b889-e31c128bd7e0)。  
  
    > [!NOTE]
    >  以下步骤不适用于[!INCLUDE[vsprvslong](../../../../includes/vsprvslong-md.md)]，它使用**数据源**设计时数据绑定的窗口。 有关详细信息，请参阅[将控件绑定到 Visual Studio 中的数据](/visualstudio/data-tools/bind-controls-to-data-in-visual-studio)和[如何： 在 Windows 窗体应用程序中显示相关数据](http://msdn.microsoft.com/library/60b1f1ec-6257-42ab-83f0-06d54ed364fd)。  
  
2.  将两个或多个表从**服务器资源管理器**到窗体。  
  
3.  从**数据**菜单上，选择**生成数据集**。  
  
4.  设置使用 XML 设计器的表之间的关系。 有关详细信息，请参阅"如何： 创建一个对多关系中 XML 架构和数据集"MSDN 上。  
  
5.  通过选择保存关系**保存所有**从**文件**菜单。  
  
6.  配置<xref:System.Windows.Forms.DataGrid>你想要将主网格中，指定，如下所示的控件：  
  
    1.  选择<xref:System.Data.DataSet>从下拉列表中<xref:System.Windows.Forms.DataGrid.DataSource%2A>属性。  
  
    2.  从下拉列表中选择的主表 （例如，"客户"）<xref:System.Windows.Forms.DataGrid.DataMember%2A>属性。  
  
7.  配置<xref:System.Windows.Forms.DataGrid>你想要如下所示指定详细信息网格中的控件：  
  
    1.  选择<xref:System.Data.DataSet>从下拉列表中<xref:System.Windows.Forms.DataGrid.DataSource%2A>属性。  
  
    2.  选择从下拉列表中的 master 和详细信息表之间的关系 (例如，"Customers.CustOrd")<xref:System.Windows.Forms.DataGrid.DataMember%2A>属性。 若要查看的关系，通过单击加号展开的节点 (**+**) 旁边的下拉列表中的主表。  
  
## <a name="see-also"></a>另请参阅  
 [DataGrid 控件](../../../../docs/framework/winforms/controls/datagrid-control-windows-forms.md)  
 [DataGrid 控件概述](../../../../docs/framework/winforms/controls/datagrid-control-overview-windows-forms.md)  
 [如何：将 Windows 窗体 DataGrid 控件绑定到数据源](../../../../docs/framework/winforms/controls/how-to-bind-the-windows-forms-datagrid-control-to-a-data-source.md)  
 [在 Visual Studio 中将控件绑定到数据](/visualstudio/data-tools/bind-controls-to-data-in-visual-studio)
