---
title: "如何：使用模板创建使用 GridView 的 ListView 的样式"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- ListView controls [WPF], styling
ms.assetid: 94bf964b-96c8-4bdf-a0c3-f5271b7cb565
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 9abc19ca14cf512deff898f5f20d23870b8b7847
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-use-templates-to-style-a-listview-that-uses-gridview"></a>如何：使用模板创建使用 GridView 的 ListView 的样式
此示例演示如何使用<xref:System.Windows.DataTemplate>和<xref:System.Windows.Style>对象来指定的外观<xref:System.Windows.Controls.ListView>使用控件<xref:System.Windows.Controls.GridView>视图模式。  
  
## <a name="example"></a>示例  
 下面的示例演示<xref:System.Windows.Style>和<xref:System.Windows.DataTemplate>自定义的列标题的外观的对象<xref:System.Windows.Controls.GridViewColumn>。  
  
 [!code-xaml[ListViewTemplate#GridViewHeaderStyle](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewTemplate/CS/window1.xaml#gridviewheaderstyle)]  
  
 [!code-xaml[ListViewTemplate#GridViewHeaderTemplate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewTemplate/CS/window1.xaml#gridviewheadertemplate)]  
  
 下面的示例演示如何使用这些<xref:System.Windows.Style>和<xref:System.Windows.DataTemplate>对象来设置<xref:System.Windows.Controls.GridViewColumn.HeaderContainerStyle%2A>和<xref:System.Windows.Controls.GridViewColumn.HeaderTemplate%2A>属性<xref:System.Windows.Controls.GridViewColumn>。 <xref:System.Windows.Controls.GridViewColumn.DisplayMemberBinding%2A>属性定义的列单元格的内容。  
  
 [!code-xaml[ListViewTemplate#GridViewColumnTemplate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewTemplate/CS/window1.xaml#gridviewcolumntemplate)]  
  
 <xref:System.Windows.Controls.GridViewColumn.HeaderContainerStyle%2A>和<xref:System.Windows.Controls.GridViewColumn.HeaderTemplate%2A>是仅有两种可用于自定义列标题外观的多个属性<xref:System.Windows.Controls.GridView>控件。 有关详细信息，请参阅 [GridView 列标题的样式和模板概述](../../../../docs/framework/wpf/controls/gridview-column-header-styles-and-templates-overview.md)。  
  
 下面的示例演示如何定义<xref:System.Windows.DataTemplate>用于自定义中的单元格的外观<xref:System.Windows.Controls.GridViewColumn>。  
  
 [!code-xaml[ListViewTemplate#GridViewCellTemplate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewTemplate/CS/window1.xaml#gridviewcelltemplate)]  
  
 下面的示例演示如何使用此<xref:System.Windows.DataTemplate>定义的内容<xref:System.Windows.Controls.GridViewColumn>单元格。 而不是使用此模板<xref:System.Windows.Controls.GridViewColumn.DisplayMemberBinding%2A>在以前显示的属性<xref:System.Windows.Controls.GridViewColumn>示例。  
  
 [!code-xaml[ListViewTemplate#CellTemplateProperty](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewTemplate/CS/window1.xaml#celltemplateproperty)]  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Windows.Controls.ListView>  
 <xref:System.Windows.Controls.GridView>  
 [GridView 概述](../../../../docs/framework/wpf/controls/gridview-overview.md)  
 [帮助主题](../../../../docs/framework/wpf/controls/listview-how-to-topics.md)  
 [ListView 概述](../../../../docs/framework/wpf/controls/listview-overview.md)
