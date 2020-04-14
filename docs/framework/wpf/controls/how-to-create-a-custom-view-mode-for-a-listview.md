---
title: 如何：为 ListView 创建自定义视图模式
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ListView controls [WPF], creating custom View mode
ms.assetid: 71077349-eeb9-4344-ab29-b5df96df3314
ms.openlocfilehash: 3b9ca17bddcecb1895205fca76f0a489ecf25c4f
ms.sourcegitcommit: 7980a91f90ae5eca859db7e6bfa03e23e76a1a50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/13/2020
ms.locfileid: "81243214"
---
# <a name="how-to-create-a-custom-view-mode-for-a-listview"></a>如何：为列表视图创建自定义视图模式

此示例演示如何为<xref:System.Windows.Controls.ListView.View%2A><xref:System.Windows.Controls.ListView>控件创建自定义模式。  
  
## <a name="example"></a>示例  
 在为<xref:System.Windows.Controls.ListView>控件创建自定义<xref:System.Windows.Controls.ViewBase>视图时，必须使用 该类。 下面的示例显示了从类派生的称为`PlainView`视图模式<xref:System.Windows.Controls.ViewBase>。  
  
 [!code-csharp[ListViewCustomView#PlainView](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewCustomView/CSharp/PlainView.cs#plainview)]
 [!code-vb[ListViewCustomView#PlainView](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ListViewCustomView/visualbasic/plainview.vb#plainview)]  
  
 要将样式应用于自定义视图，请使用 类<xref:System.Windows.Style>。 下面的示例为`PlainView`视图模式定义<xref:System.Windows.Style>。 在前面的示例中，此样式设置为 为<xref:System.Windows.Controls.ViewBase.DefaultStyleKey%2A>`PlainView`定义的属性的值。  
  
 [!code-xaml[ListViewCustomView#PlainViewStyle](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewCustomView/CSharp/Themes/Generic.xaml#plainviewstyle)]  
  
 要在自定义视图模式下定义数据的布局，请定义对象<xref:System.Windows.DataTemplate>。 下面的示例定义了可用于在<xref:System.Windows.DataTemplate>`PlainView`视图模式下显示数据的 。  
  
 [!code-xaml[ListViewCustomView#PlainViewDataTemplate](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewCustomView/CSharp/Window1.xaml#plainviewdatatemplate)]  
  
 下面的示例演示如何<xref:System.Windows.ResourceKey>为`PlainView`使用上一个示例中定义的<xref:System.Windows.DataTemplate>视图模式定义 。  
  
 [!code-xaml[ListViewCustomView#PlainViewtileView](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewCustomView/CSharp/Window1.xaml#plainviewtileview)]  
  
 如果将<xref:System.Windows.Controls.ListView>属性设置为资源键，<xref:System.Windows.Controls.ListView.View%2A>则控件可以使用自定义视图。 下面的示例演示如何`PlainView`指定为 的视图模式<xref:System.Windows.Controls.ListView>。  
  
 [!code-csharp[ListViewCustomView#ListViewtileViewmode](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewCustomView/CSharp/Window1.xaml.cs#listviewtileviewmode)]
 [!code-vb[ListViewCustomView#ListViewtileViewmode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ListViewCustomView/visualbasic/window1.xaml.vb#listviewtileviewmode)]  
  
 有关完整示例，请参阅[具有多个视图的列表视图 （C#）](https://github.com/dotnet/docs/tree/master/samples/snippets/csharp/VS_Snippets_Wpf/ListViewCustomView/CSharp)或[具有多个视图的列表视图（可视基本视图）。](https://github.com/dotnet/docs/tree/master/samples/snippets/visualbasic/VS_Snippets_Wpf/ListViewCustomView/visualbasic)  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Controls.ListView>
- <xref:System.Windows.Controls.GridView>
- [操作指南主题](listview-how-to-topics.md)
- [ListView 概述](listview-overview.md)
- [GridView 概述](gridview-overview.md)
