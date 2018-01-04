---
title: "DataGridView 控件方案（Windows 窗体）"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- data [Windows Forms], displaying in tabular format
- data grids [Windows Forms], about data grids
- DataGridView control [Windows Forms], scenarios
ms.assetid: 09a5fd05-3447-47ec-a4ec-6082a2b7f0dd
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 38e5337f775d98f8729c62b3481c3e839bff2252
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="datagridview-control-scenarios-windows-forms"></a>DataGridView 控件方案（Windows 窗体）
与<xref:System.Windows.Forms.DataGridView>控件，您可以显示来自各种数据源的表格数据。 有关简单用法，则可以手动填充<xref:System.Windows.Forms.DataGridView>和操作直接通过控件的数据。 通常情况下，但是，你将在外部数据源中存储你的数据并将控件绑定到它通过<xref:System.Windows.Forms.BindingSource>组件。  
  
 本主题介绍了一些常见方案涉及<xref:System.Windows.Forms.DataGridView>控件。  
  
## <a name="scenario-1-displaying-small-amounts-of-data"></a>方案 1： 显示少量数据  
 无需将你的数据存储在外部数据源，使其显示在<xref:System.Windows.Forms.DataGridView>控件。 如果你正在使用的少量数据，你可以自行填充控件和操作通过控件的数据。 这称为*取消绑定的模式*。 有关详细信息，请参阅[如何： 创建未绑定的 Windows 窗体 DataGridView 控件](../../../../docs/framework/winforms/controls/how-to-create-an-unbound-windows-forms-datagridview-control.md)。  
  
### <a name="scenario-key-points"></a>方案关键点  
  
-   在未绑定模式下，你手动填充控件。  
  
-   未绑定的模式是特别适用于只读数据的信息量很小。  
  
-   取消绑定的模式也适用于类似电子表格或稀疏填充表。  
  
## <a name="scenario-2-viewing-and-updating-data-stored-in-an-external-data-source"></a>方案 2： 查看和更新的外部数据源中存储的数据  
 你可以使用<xref:System.Windows.Forms.DataGridView>控制用户界面 (UI) 通过哪些用户可以访问数据保留在数据源，如数据库表或业务对象的集合。 有关详细信息，请参阅[如何： 将数据绑定到 Windows 窗体 DataGridView 控件](../../../../docs/framework/winforms/controls/how-to-bind-data-to-the-windows-forms-datagridview-control.md)。  
  
### <a name="scenario-key-points"></a>方案关键点  
  
-   绑定的模式允许你连接到数据源、 自动生成基于数据源属性或数据库列的列和自动填充该控件。  
  
-   绑定的模式适合用于与数据的大量用户交互。 数据可用于显示，格式设置和用户指定的数据可以解析为数据源的预期格式。 可以检测到格式设置错误和数据库约束错误的数据输入，以便用户可以会收到警告，并可以更正错误的单元格。  
  
-   附加功能，例如列排序，冻结，和重新排序操作使用户能够查看其工作流最方便的方法中的数据。  
  
-   剪贴板支持使用户能够将数据复制到其他应用程序的应用程序。  
  
## <a name="scenario-3-advanced-data"></a>方案 3： 高级的数据  
 如果你有标准的数据绑定模型不能解决的特殊需求，你可以通过实现管理控件和你的数据之间的交互*虚拟模式*。 需要实现虚拟模式是指实现一个或多个事件处理程序，使控件请求的信息有关单元格的信息。  
  
 例如，如果你使用大量的数据，你可能想要实现虚拟模式以确保最佳的效率。 虚拟模式也是有用的维护，以及从其他数据源检索数据的列显示未绑定列的值。  
  
 有关虚拟模式的详细信息，请参阅[演练： 在 Windows 窗体 DataGridView 控件中实现虚拟模式](../../../../docs/framework/winforms/controls/implementing-virtual-mode-wf-datagridview-control.md)。  
  
### <a name="scenario-key-points"></a>方案关键点  
  
-   虚拟模式适合需要进行微调性能时显示的数据量非常大。  
  
## <a name="scenario-4-automatically-resizing-rows-and-columns"></a>方案 4： 自动调整行和列  
 当显示定期更新的数据时，您可以自动调整行和列以确保所有内容都是可见。 <xref:System.Windows.Forms.DataGridView>控件提供了几个选项，可以启用或禁用手动调整大小，在特定时间，以编程方式调整大小或大小调整内容时自动更改。 有关详细信息，请参阅[在 Windows 窗体 DataGridView 控件中调整选项](../../../../docs/framework/winforms/controls/sizing-options-in-the-windows-forms-datagridview-control.md)。  
  
### <a name="scenario-key-points"></a>方案关键点  
  
-   手动调整大小使用户能够调整单元格的高度和宽度。  
  
-   自动调整大小，可以以维护单元格的大小，以便永远不会剪切单元格内容。  
  
-   以编程方式调整大小，你能够调整单元格大小在特定时间，以避免对性能的影响的连续自动调整大小。  
  
## <a name="scenario-5-simple-customization"></a>方案 5： 简单的自定义项  
 <xref:System.Windows.Forms.DataGridView>控件提供了许多方法为您要更改其基本外观和行为。 有关详细信息，请参阅[在 Windows 窗体 DataGridView 控件中的单元格样式](../../../../docs/framework/winforms/controls/cell-styles-in-the-windows-forms-datagridview-control.md)。  
  
### <a name="scenario-key-points"></a>方案关键点  
  
-   <xref:System.Windows.Forms.DataGridViewCellStyle>对象使您可以提供颜色、 字体格式设置，和多个级别和控件的各个元素的定位信息。  
  
-   可以层和共享的多个元素，从而允许重用代码的单元格样式。  
  
## <a name="scenario-6-advanced-customization"></a>方案 6： 高级自定义  
 <xref:System.Windows.Forms.DataGridView>控件提供了许多方法供你自定义其外观和行为。  
  
### <a name="scenario-key-points"></a>方案关键点  
  
-   你可以提供你自己的单元格绘制代码。 有关详细信息，请参阅[如何： 自定义 Windows 窗体 DataGridView 控件中的单元外观](../../../../docs/framework/winforms/controls/customize-the-appearance-of-cells-in-the-datagrid.md)。  
  
-   你可以提供你自己的行绘制。 这很有用，例如，若要创建具有跨多个列的内容的行。 有关详细信息，请参阅[如何： 自定义 Windows 窗体 DataGridView 控件中的行外观](../../../../docs/framework/winforms/controls/customize-the-appearance-of-rows-in-the-datagrid.md)。  
  
-   你可以实现您自己的单元格和列类以自定义单元格的外观。 有关详细信息，请参阅[如何： 自定义单元格和扩展他们行为和外观由 Windows 窗体 DataGridView 控件中的列](../../../../docs/framework/winforms/controls/customize-cells-and-columns-in-the-datagrid-by-extending-behavior.md)。  
  
-   你可以实现您自己到提供的内置列类型之外的主机控件的单元格和列的类。 有关详细信息，请参阅[如何： 在 Windows 窗体 DataGridView 单元格的主机控件](../../../../docs/framework/winforms/controls/how-to-host-controls-in-windows-forms-datagridview-cells.md)。  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Windows.Forms.DataGridView>  
 [DataGridView 控件概述](../../../../docs/framework/winforms/controls/datagridview-control-overview-windows-forms.md)
