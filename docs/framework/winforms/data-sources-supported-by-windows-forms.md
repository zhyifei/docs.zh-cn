---
title: "Windows 窗体支持的数据源"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- collections [Windows Forms], binding to
- OLE DB providers [Windows Forms], Windows Forms
- DataTable class [Windows Forms], binding and Windows Forms
- Windows Forms, data binding
- DataView class [Windows Forms], binding and Windows Forms
- DataViewManager class [Windows Forms], binding and Windows Forms
- Windows Forms, source data
- arrays [Windows Forms]
- data sources [Windows Forms]
- data providers [Windows Forms]
- DataSet class [Windows Forms], binding and Windows Forms
- data [Windows Forms], data providers
ms.assetid: 3d2c43f6-462b-4d35-9c86-13e9afe012e1
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 2d2c1c021759c7032257e95eb2cad202a461dc05
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="data-sources-supported-by-windows-forms"></a>Windows 窗体支持的数据源
传统上，数据绑定具有内使用应用程序以利用在数据库中存储的数据。 使用 Windows 窗体数据绑定，你可以在访问数据时从数据库以及其他结构，如数组和集合中的数据处理程序，但前提是已满足某些最低要求。  
  
## <a name="structures-to-bind-to"></a>绑定到结构  
 在 Windows 窗体，你可以将绑定到各种结构，从简单到如 ADO.NET 数据表 （复杂绑定） 的复杂列表的对象 （简单绑定）。 对于简单绑定，Windows 窗体上的简单对象支持绑定到的公共属性。 Windows 窗体的基于列表的绑定通常需要对象支持<xref:System.Collections.IList>接口或<xref:System.ComponentModel.IListSource>接口。 此外，如果你正在通过绑定与<xref:System.Windows.Forms.BindingSource>组件，你可以将绑定到支持的对象<xref:System.Collections.IEnumerable>接口。 有关与数据绑定相关的接口的详细信息，请参阅[与数据绑定相关的接口](../../../docs/framework/winforms/interfaces-related-to-data-binding.md)。  
  
 以下列表显示了你可以将绑定到 Windows 窗体中的结构。  
  
 <xref:System.Windows.Forms.BindingSource>  
 A<xref:System.Windows.Forms.BindingSource>是最常见的 Windows 窗体数据源和数据源和 Windows 窗体控件之间的代理的作用。 常规<xref:System.Windows.Forms.BindingSource>用法模式是你将控件绑定到<xref:System.Windows.Forms.BindingSource>并将绑定<xref:System.Windows.Forms.BindingSource>到数据源 （例如，ADO.NET 数据表或业务对象）。 <xref:System.Windows.Forms.BindingSource>提供服务，启用和改进的数据绑定支持的级别。 例如，Windows 窗体列表基于控件如<xref:System.Windows.Forms.DataGridView>和<xref:System.Windows.Forms.ComboBox>不直接支持绑定到<xref:System.Collections.IEnumerable>数据源但是，你可以启用这种情况下通过绑定<xref:System.Windows.Forms.BindingSource>。 在这种情况下，<xref:System.Windows.Forms.BindingSource>会将转换到的数据源<xref:System.Collections.IList>。  
  
 简单对象  
 Windows 窗体支持数据绑定控件属性绑定到公共属性的对象使用的实例上<xref:System.Windows.Forms.Binding>类型。 Windows 窗体还支持绑定基于列表的控件，如<xref:System.Windows.Forms.ListControl>到对象实例时<xref:System.Windows.Forms.BindingSource>使用。  
  
 数组或集合  
 若要充当数据源，列表必须实现<xref:System.Collections.IList>接口; 一个示例将数组的实例<xref:System.Array>类。 在阵列上的详细信息，请参阅[如何： 创建数组的对象 (Visual Basic)](http://msdn.microsoft.com/en-us/6b64e069-0387-400c-9081-3bdc581020c3)。  
  
 一般情况下，应使用<xref:System.ComponentModel.BindingList%601>当你创建的数据绑定的对象的列表。 <xref:System.ComponentModel.BindingList%601>是一个泛型版本<xref:System.ComponentModel.IBindingList>接口。 <xref:System.ComponentModel.IBindingList>接口扩展<xref:System.Collections.IList>通过添加属性、 方法和事件所需双向数据绑定接口。  
  
 <xref:System.Collections.IEnumerable>  
 Windows 窗体控件可以绑定到数据源仅支持<xref:System.Collections.IEnumerable>接口如果它们绑定通过<xref:System.Windows.Forms.BindingSource>组件。  
  
 [!INCLUDE[vstecado](../../../includes/vstecado-md.md)]数据对象  
 [!INCLUDE[vstecado](../../../includes/vstecado-md.md)]提供多种适用于绑定到的数据结构。 在复杂程度和复杂性，每个而异。  
  
-   <xref:System.Data.DataColumn>。 A<xref:System.Data.DataColumn>是基本的构建基块的<xref:System.Data.DataTable>，因为大量的列构成表。 每个<xref:System.Data.DataColumn>具有<xref:System.Data.DataColumn.DataType%2A>确定的数据列保留 （例如，描述汽车的表中的汽车的品牌） 类型的属性。 你可以简单绑定控件 (如<xref:System.Windows.Forms.TextBox>控件的<xref:System.Windows.Forms.Control.Text%2A>属性) 到数据表中的列。  
  
-   <xref:System.Data.DataTable>。 A<xref:System.Data.DataTable>处于的表示形式的表，具有行和列， [!INCLUDE[vstecado](../../../includes/vstecado-md.md)]。 数据表包含两个集合： <xref:System.Data.DataColumn>，表示给定的表 （其最终确定的可以进入该表的数据类型） 中的数据的列和<xref:System.Data.DataRow>，表示给定表中的数据行。 你可以复杂绑定控件到数据表中包含的信息 (如绑定<xref:System.Windows.Forms.DataGridView>到数据表的控件)。 但是，当绑定到<xref:System.Data.DataTable>，则实际上绑定到表的默认视图。  
  
-   <xref:System.Data.DataView>。 A<xref:System.Data.DataView>是单个的数据表可能筛选或排序的自定义的视图。 数据视图是"快照"使用的复杂绑定控件的数据。 你可以简单绑定或复杂绑定到的数据在数据视图中，但请注意你正在绑定到的固定"图片"的数据，而不是干净的、 不断更新数据源。  
  
-   <xref:System.Data.DataSet>。 A<xref:System.Data.DataSet>是表、 关系和约束的数据库中的数据的集合。 你可以简单绑定或复杂绑定到数据集中，但请注意你正在绑定到默认值<xref:System.Data.DataViewManager>为<xref:System.Data.DataSet>（请参阅下一步项目符号的内容）。  
  
-   <xref:System.Data.DataViewManager>。 A<xref:System.Data.DataViewManager>是整个的自定义的视图<xref:System.Data.DataSet>，类似于<xref:System.Data.DataView>，但其中包括各种关系。 与<xref:System.Data.DataViewManager.DataViewSettings%2A>集合，你可以设置默认筛选器和任何视图的排序选项，<xref:System.Data.DataViewManager>具有给定表的。  
  
## <a name="see-also"></a>请参阅  
 [Windows 窗体数据绑定中的更改通知](../../../docs/framework/winforms/change-notification-in-windows-forms-data-binding.md)  
 [数据绑定和 Windows 窗体](../../../docs/framework/winforms/data-binding-and-windows-forms.md)  
 [Windows 窗体数据绑定](../../../docs/framework/winforms/windows-forms-data-binding.md)
