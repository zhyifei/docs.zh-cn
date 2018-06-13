---
title: 如何：为 ListView 创建自定义视图模式
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ListView controls [WPF], creating custom View mode
ms.assetid: 71077349-eeb9-4344-ab29-b5df96df3314
ms.openlocfilehash: b8600a2e201fdbcb566e6a322e3ecdabbe1641ef
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33551864"
---
# <a name="how-to-create-a-custom-view-mode-for-a-listview"></a>如何：为 ListView 创建自定义视图模式
此示例演示如何创建自定义<xref:System.Windows.Controls.ListView.View%2A>模式<xref:System.Windows.Controls.ListView>控件。  
  
## <a name="example"></a>示例  
 必须使用<xref:System.Windows.Controls.ViewBase>类时创建的自定义视图<xref:System.Windows.Controls.ListView>控件。 下面的示例演示一种视图模式，称为`PlainView`，该类派生自<xref:System.Windows.Controls.ViewBase>类。  
  
 [!code-csharp[ListViewCustomView#PlainView](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewCustomView/CSharp/PlainView.cs#plainview)]
 [!code-vb[ListViewCustomView#PlainView](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ListViewCustomView/visualbasic/plainview.vb#plainview)]  
  
 若要将样式应用到自定义视图，使用<xref:System.Windows.Style>类。 下面的示例定义<xref:System.Windows.Style>为`PlainView`视图模式。 在前面的示例中，此样式设置为的值<xref:System.Windows.Controls.ViewBase.DefaultStyleKey%2A>为定义的属性`PlainView`。  
  
 [!code-xaml[ListViewCustomView#PlainViewStyle](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewCustomView/CSharp/Themes/Generic.xaml#plainviewstyle)]  
  
 若要在自定义视图模式中定义的数据布局，定义<xref:System.Windows.DataTemplate>对象。 下面的示例定义<xref:System.Windows.DataTemplate>可以用于显示中的数据`PlainView`视图模式。  
  
 [!code-xaml[ListViewCustomView#PlainViewDataTemplate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewCustomView/CSharp/Window1.xaml#plainviewdatatemplate)]  
  
 下面的示例演示如何定义<xref:System.Windows.ResourceKey>为`PlainView`使用的视图模式<xref:System.Windows.DataTemplate>前面的示例中定义。  
  
 [!code-xaml[ListViewCustomView#PlainViewtileView](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewCustomView/CSharp/Window1.xaml#plainviewtileview)]  
  
 A<xref:System.Windows.Controls.ListView>控件可以使用自定义视图，如果你设置<xref:System.Windows.Controls.ListView.View%2A>到的资源键的属性。 下面的示例演示如何指定`PlainView`为的视图模式<xref:System.Windows.Controls.ListView>。  
  
 [!code-csharp[ListViewCustomView#ListViewtileViewmode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewCustomView/CSharp/Window1.xaml.cs#listviewtileviewmode)]
 [!code-vb[ListViewCustomView#ListViewtileViewmode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ListViewCustomView/visualbasic/window1.xaml.vb#listviewtileviewmode)]  
  
 有关完整的示例，请参阅[与多个视图示例 ListView](http://go.microsoft.com/fwlink/?LinkID=160013)。  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Windows.Controls.ListView>  
 <xref:System.Windows.Controls.GridView>  
 [帮助主题](../../../../docs/framework/wpf/controls/listview-how-to-topics.md)  
 [ListView 概述](../../../../docs/framework/wpf/controls/listview-overview.md)  
 [GridView 概述](../../../../docs/framework/wpf/controls/gridview-overview.md)
