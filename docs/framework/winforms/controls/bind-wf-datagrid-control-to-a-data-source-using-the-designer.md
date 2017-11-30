---
title: "如何：使用设计器将 Windows 窗体 DataGrid 控件绑定到数据源"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- datasets [Windows Forms], binding to DataGrid control
- data binding [Windows Forms], DataGrid control
- DataGrid control [Windows Forms], data binding
- Windows Forms controls, data binding
- bound controls [Windows Forms]
ms.assetid: 4e96e3d0-b1cc-4de1-8774-bc9970ec4554
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 378f1d80392ae7b2058d5c3b2d987e4810cbd07b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-bind-the-windows-forms-datagrid-control-to-a-data-source-using-the-designer"></a>如何：使用设计器将 Windows 窗体 DataGrid 控件绑定到数据源
> [!NOTE]
>  <xref:System.Windows.Forms.DataGridView> 控件取代了 <xref:System.Windows.Forms.DataGrid> 控件并添加了功能；但是，可以选择保留 <xref:System.Windows.Forms.DataGrid> 控件以实现向后兼容并供将来使用。 有关详细信息，请参阅 [Windows 窗体 DataGridView 控件与 DataGrid 控件之间的区别](../../../../docs/framework/winforms/controls/differences-between-the-windows-forms-datagridview-and-datagrid-controls.md)。  
  
 Windows 窗体<xref:System.Windows.Forms.DataGrid>控件专门用于显示数据源中的信息。 将控件在设计时绑定通过设置<xref:System.Windows.Forms.DataGrid.DataSource%2A>和<xref:System.Windows.Forms.DataGrid.DataMember%2A>属性，或在运行时通过调用<xref:System.Windows.Forms.DataGrid.SetDataBinding%2A>方法。 尽管可以显示来自各种数据源数据，最典型的源是数据集和数据的视图。  
  
 如果在设计时数据源是否可用 — 例如，如果该窗体包含数据集或数据视图的实例 — 你可以在设计时将网格绑定到数据源。 然后可以预览数据在网格中的外观。  
  
 此外可以在运行时以编程方式，绑定网格。 当你想要设置基于在运行时获取的信息的数据源时，这非常有用。 例如，应用程序可能允许用户指定要查看的表的名称。 它也是在数据源在不存在在设计时的情况下需要的。 这包括如数组、 集合、 非类型化数据集和数据读取器的数据源。  
  
 下面的过程需要**Windows 应用程序**具有一个窗体包含项目<xref:System.Windows.Forms.DataGrid>控件。 有关设置此类项目的信息，请参阅[如何： 创建 Windows 应用程序项目](http://msdn.microsoft.com/en-us/b2f93fed-c635-4705-8d0e-cf079a264efa)和[如何： 向 Windows 窗体添加控件](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md)。 在[!INCLUDE[vsprvslong](../../../../includes/vsprvslong-md.md)]、<xref:System.Windows.Forms.DataGrid>控件将不处于**工具箱**默认情况下。 有关将其添加的信息，请参阅[如何： 将项添加到工具箱](http://msdn.microsoft.com/en-us/458e119e-17fe-450b-b889-e31c128bd7e0)。 另外，在[!INCLUDE[vsprvslong](../../../../includes/vsprvslong-md.md)]，你可以使用**数据源**设计时数据绑定的窗口。 有关详细信息请参阅[将控件绑定到 Visual Studio 中的数据](/visualstudio/data-tools/bind-controls-to-data-in-visual-studio)。  
  
> [!NOTE]
>  显示的对话框和菜单命令可能会与“帮助”中的描述不同，具体取决于你现用的设置或版本。 若要更改设置，请在 **“工具”** 菜单上选择 **“导入和导出设置”** 。 有关详细信息，请参阅[在 Visual Studio 中自定义开发设置](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3)。  
  
### <a name="to-data-bind-the-datagrid-control-to-a-single-table-in-the-designer"></a>若要将数据绑定的 DataGrid 控件到设计器中的单个表  
  
1.  设置控件的<xref:System.Windows.Forms.DataGrid.DataSource%2A>到包含你想要将绑定到的数据项的对象的属性。  
  
2.  如果数据源，数据集设置<xref:System.Windows.Forms.DataGrid.DataMember%2A>属性设置为要绑定到的表的名称。  
  
3.  如果数据源的数据集或数据视图基于数据集表，请将代码添加到窗体来填充数据集。  
  
     你使用的确切代码取决于数据集从何处获取数据。 如果要直接从数据库填充数据集，则通常会调用`Fill`数据适配器，如下面的代码示例填充数据集调用中所示方法`DsCategories1`:  
  
    ```vb  
    sqlDataAdapter1.Fill(DsCategories1)  
    ```  
  
    ```csharp  
    sqlDataAdapter1.Fill(DsCategories1);  
    ```  
  
    ```cpp  
    sqlDataAdapter1->Fill(dsCategories1);  
    ```  
  
4.  （可选）将适当的表样式和列样式添加到网格中。  
  
     如果不有任何表样式，你将看到表，但其格式设置很少，且所有列均可见。  
  
### <a name="to-data-bind-the-datagrid-control-to-multiple-tables-in-a-dataset-in-the-designer"></a>若要将数据绑定的 DataGrid 控件到多个表设计器中的数据集  
  
1.  设置控件的<xref:System.Windows.Forms.DataGrid.DataSource%2A>到包含你想要将绑定到的数据项的对象的属性。  
  
2.  如果数据集 （即，如果它不包含关系对象） 包含相关的表，请设置<xref:System.Windows.Forms.DataGrid.DataMember%2A>为父表的名称的属性。  
  
3.  编写代码以填充数据集。  
  
## <a name="see-also"></a>另请参阅  
 [DataGrid 控件概述](../../../../docs/framework/winforms/controls/datagrid-control-overview-windows-forms.md)  
 [如何：向 Windows 窗体 DataGrid 控件添加表和列](../../../../docs/framework/winforms/controls/how-to-add-tables-and-columns-to-the-windows-forms-datagrid-control.md)  
 [DataGrid 控件](../../../../docs/framework/winforms/controls/datagrid-control-windows-forms.md)  
 [Windows 窗体数据绑定](../../../../docs/framework/winforms/windows-forms-data-binding.md)  
 [在 Visual Studio 中访问数据](/visualstudio/data-tools/accessing-data-in-visual-studio)
