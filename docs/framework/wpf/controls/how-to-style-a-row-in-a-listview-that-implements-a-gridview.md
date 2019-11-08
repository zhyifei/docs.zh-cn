---
title: 如何：为实现 GridView 的 ListView 中的行设置样式
ms.date: 03/30/2017
helpviewer_keywords:
- GridView controls [WPF], styling rows
- styling rows in ListViews implementing GridViews [WPF]
- ListView controls [WPF], styling rows with GridViews
ms.assetid: 2e406ba2-70a0-4e62-841f-0934859de76e
ms.openlocfilehash: ce79899d5c8e825ecb39e14ae8af4e0c33f13db3
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/07/2019
ms.locfileid: "73733539"
---
# <a name="how-to-style-a-row-in-a-listview-that-implements-a-gridview"></a>如何：为实现 GridView 的 ListView 中的行设置样式
此示例演示如何为实现 <xref:System.Windows.Controls.GridView><xref:System.Windows.Controls.ListView.View%2A> 模式的 <xref:System.Windows.Controls.ListView> 控件中的行进行样式。  
  
## <a name="example"></a>示例  
 您可以通过在 <xref:System.Windows.Controls.ListView> 控件上设置 <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> 来设置 <xref:System.Windows.Controls.ListView> 控件中的行的样式。 为表示为 <xref:System.Windows.Controls.ListViewItem> 对象的项设置样式。 <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> 引用用于显示行内容的 <xref:System.Windows.Controls.ControlTemplate> 对象。  
  
 下面的示例从中提取的完整示例显示了存储在 XML 数据库中的歌曲信息的集合。 数据库中的每首歌都有一个评级字段，此字段的值指定了歌曲信息行的显示方式。  
  
 下面的示例演示如何为表示歌曲集中歌曲的 <xref:System.Windows.Controls.ListViewItem> 对象定义 <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A>。 <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> 引用 <xref:System.Windows.Controls.ControlTemplate> 对象，这些对象指定如何显示一行歌曲信息。  
  
 [!code-xaml[ListViewItemStyleSnippet#ItemContainerStyle](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewItemStyleSnippet/CS/Window1.xaml#itemcontainerstyle)]  
  
 下面的示例演示了一个 <xref:System.Windows.Controls.ControlTemplate>，它将 `"Strongly Recommended"` 文本字符串添加到该行。 此模板在 <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> 中引用，并显示歌曲的评分值为5（5）。 <xref:System.Windows.Controls.ControlTemplate> 包含一个 <xref:System.Windows.Controls.GridViewRowPresenter> 对象，该对象按照 <xref:System.Windows.Controls.GridView> 查看模式的定义，在列中布局行的内容。  
  
 [!code-xaml[ListViewItemStyleSnippet#ControlTemplate](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewItemStyleSnippet/CS/Window1.xaml#controltemplate)]  
  
 下面的示例定义 <xref:System.Windows.Controls.GridView>。  
  
 [!code-xaml[ListViewItemStyleSnippet#GridView](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewItemStyleSnippet/CS/Window1.xaml#gridview)]  
  
## <a name="see-also"></a>请参阅

- <xref:System.Windows.Controls.ListView>
- <xref:System.Windows.Controls.GridView>
- [帮助主题](listview-how-to-topics.md)
- [ListView 概述](listview-overview.md)
- [样式设置和模板化](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
