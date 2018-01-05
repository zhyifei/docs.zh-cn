---
title: "如何：为实现 GridView 的 ListView 中的行设置样式"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- GridView controls [WPF], styling rows
- styling rows in ListViews implementing GridViews [WPF]
- ListView controls [WPF], styling rows with GridViews
ms.assetid: 2e406ba2-70a0-4e62-841f-0934859de76e
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 1e37d70fe1cb6aefb1404424c1a8f5339e0badf7
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-style-a-row-in-a-listview-that-implements-a-gridview"></a>如何：为实现 GridView 的 ListView 中的行设置样式
此示例演示如何设置样式中的行<xref:System.Windows.Controls.ListView>实现控件<xref:System.Windows.Controls.GridView><xref:System.Windows.Controls.ListView.View%2A>模式。  
  
## <a name="example"></a>示例  
 你可以设置样式中的行<xref:System.Windows.Controls.ListView>通过设置<xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A>上<xref:System.Windows.Controls.ListView>控件。 将表示为其项的样式设置<xref:System.Windows.Controls.ListViewItem>对象。 <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A>引用<xref:System.Windows.Controls.ControlTemplate>用于显示行内容的对象。  
  
 提取了以下示例的完整示例中显示了存储在 [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] 数据库中的歌曲信息集合。 数据库中的每首歌都有一个评级字段，此字段的值指定了歌曲信息行的显示方式。  
  
 下面的示例演示如何定义<xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A>为<xref:System.Windows.Controls.ListViewItem>表示歌曲首歌曲集合中的对象。 <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A>引用<xref:System.Windows.Controls.ControlTemplate>指定如何显示一行歌曲信息的对象。  
  
 [!code-xaml[ListViewItemStyleSnippet#ItemContainerStyle](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewItemStyleSnippet/CS/Window1.xaml#itemcontainerstyle)]  
  
 下面的示例演示<xref:System.Windows.Controls.ControlTemplate>，它将添加的文本字符串`"Strongly Recommended"`的行。 此模板中引用<xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A>并显示歌曲的分级具有 5 （五个） 的值时。 <xref:System.Windows.Controls.ControlTemplate>包括<xref:System.Windows.Controls.GridViewRowPresenter>是布局中列的行的内容由定义的对象<xref:System.Windows.Controls.GridView>视图模式。  
  
 [!code-xaml[ListViewItemStyleSnippet#ControlTemplate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewItemStyleSnippet/CS/Window1.xaml#controltemplate)]  
  
 下面的示例定义<xref:System.Windows.Controls.GridView>。  
  
 [!code-xaml[ListViewItemStyleSnippet#GridView](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewItemStyleSnippet/CS/Window1.xaml#gridview)]  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Windows.Controls.ListView>  
 <xref:System.Windows.Controls.GridView>  
 [帮助主题](../../../../docs/framework/wpf/controls/listview-how-to-topics.md)  
 [ListView 概述](../../../../docs/framework/wpf/controls/listview-overview.md)  
 [样式设置和模板化](../../../../docs/framework/wpf/controls/styling-and-templating.md)
