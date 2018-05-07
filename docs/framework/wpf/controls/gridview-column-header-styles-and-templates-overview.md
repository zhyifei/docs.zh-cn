---
title: GridView 列标题的样式和模板概述
ms.date: 03/30/2017
helpviewer_keywords:
- column headers [WPF], customizing
- ListView controls [WPF], GridView column header styles
- controls [WPF], ListView
- headers [WPF], customizing
- GridView view mode [WPF], customizing column headers
ms.assetid: 74835674-a39e-4ab5-9418-ad7f6ab7b956
ms.openlocfilehash: 28b4a64a6c79b226b1ff4b3bfcbf9a55b6d8df78
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="gridview-column-header-styles-and-templates-overview"></a>GridView 列标题的样式和模板概述
此概述介绍了优先顺序中的属性，用于自定义中的列标题的顺序<xref:System.Windows.Controls.GridView>的查看模式<xref:System.Windows.Controls.ListView>控件。  
  
## <a name="customizing-a-column-header-in-a-gridview"></a>自定义一个 GridView 中的列标题  
 定义内容、 布局和样式中的列标题的属性<xref:System.Windows.Controls.GridView>许多相关的类上找到。 其中一些属性具有类似的功能或相同的。  
  
 下表中的行显示执行相同的功能的属性的组。 你可以使用这些属性以自定义中的列标题<xref:System.Windows.Controls.GridView>。 优先顺序中的相关属性的顺序是从右到左其中最右边的列中的属性具有最高优先级。 例如，如果<xref:System.Windows.Controls.ContentControl.ContentTemplate%2A>上设置<xref:System.Windows.Controls.GridViewColumnHeader>对象和<xref:System.Windows.Controls.GridViewColumn.HeaderTemplateSelector%2A>是设置关联<xref:System.Windows.Controls.GridViewColumn>、<xref:System.Windows.Controls.ContentControl.ContentTemplate%2A>优先。 在此方案中，<xref:System.Windows.Controls.GridViewColumn.HeaderTemplateSelector%2A>不起作用。  
  
 **列中的标头 GridView 的相关的属性**  
  
|||||  
|-|-|-|-|  
|**类**|<xref:System.Windows.Controls.GridView>|<xref:System.Windows.Controls.GridViewColumn>|<xref:System.Windows.Controls.GridViewColumnHeader>|  
|**上下文菜单属性**|<xref:System.Windows.Controls.GridView.ColumnHeaderContextMenu%2A>|不适用|<xref:System.Windows.FrameworkElement.ContextMenu%2A>|  
|**工具提示**<br /><br /> **属性**|<xref:System.Windows.Controls.GridView.ColumnHeaderToolTip%2A>|不适用|<xref:System.Windows.FrameworkElement.ToolTip%2A>|  
|**标头模板**<br /><br /> **属性**|<xref:System.Windows.Controls.GridView.ColumnHeaderTemplate%2A> <sup>1</sup>/<br /><br /> <xref:System.Windows.Controls.GridView.ColumnHeaderTemplateSelector%2A>|<xref:System.Windows.Controls.GridViewColumn.HeaderTemplate%2A> <sup>1</sup>/<br /><br /> <xref:System.Windows.Controls.GridViewColumn.HeaderTemplateSelector%2A>|<xref:System.Windows.Controls.ContentControl.ContentTemplate%2A> <sup>1</sup>/<br /><br /> <xref:System.Windows.Controls.ContentControl.ContentTemplateSelector%2A>|  
|**样式属性**|<xref:System.Windows.Controls.GridView.ColumnHeaderContainerStyle%2A>|<xref:System.Windows.Controls.GridViewColumn.HeaderContainerStyle%2A>|<xref:System.Windows.FrameworkElement.Style%2A>|  
  
 <sup>1</sup>为**标头模板属性**，如果设置这两种模板和模板选择器属性，模板属性优先。 例如，如果同时设置<xref:System.Windows.Controls.ContentControl.ContentTemplate%2A>和<xref:System.Windows.Controls.ContentControl.ContentTemplateSelector%2A>属性，<xref:System.Windows.Controls.ContentControl.ContentTemplate%2A>属性优先。  
  
## <a name="see-also"></a>请参阅  
 [帮助主题](../../../../docs/framework/wpf/controls/listview-how-to-topics.md)  
 [ListView 概述](../../../../docs/framework/wpf/controls/listview-overview.md)  
 [GridView 概述](../../../../docs/framework/wpf/controls/gridview-overview.md)
