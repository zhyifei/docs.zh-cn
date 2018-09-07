---
title: 如何：为 ListView 创建自定义视图模式
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ListView controls [WPF], creating custom View mode
ms.assetid: 71077349-eeb9-4344-ab29-b5df96df3314
ms.openlocfilehash: 239fb2e9a364bd0265ff7cf644ee296878280cf3
ms.sourcegitcommit: 64f4baed249341e5bf64d1385bf48e3f2e1a0211
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2018
ms.locfileid: "44081803"
---
# <a name="how-to-create-a-custom-view-mode-for-a-listview"></a>如何：为 ListView 创建自定义视图模式
此示例演示如何创建自定义<xref:System.Windows.Controls.ListView.View%2A>模式<xref:System.Windows.Controls.ListView>控件。  
  
## <a name="example"></a>示例  
 必须使用<xref:System.Windows.Controls.ViewBase>类创建的自定义视图时<xref:System.Windows.Controls.ListView>控件。 下面的示例演示调用的视图模式`PlainView`，它派生自<xref:System.Windows.Controls.ViewBase>类。  
  
 [!code-csharp[ListViewCustomView#PlainView](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewCustomView/CSharp/PlainView.cs#plainview)]
 [!code-vb[ListViewCustomView#PlainView](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ListViewCustomView/visualbasic/plainview.vb#plainview)]  
  
 若要将样式应用到自定义视图，请使用<xref:System.Windows.Style>类。 下面的示例定义<xref:System.Windows.Style>为`PlainView`视图模式。 在上一示例中，此样式设置的值作为<xref:System.Windows.Controls.ViewBase.DefaultStyleKey%2A>属性，可为定义`PlainView`。  
  
 [!code-xaml[ListViewCustomView#PlainViewStyle](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewCustomView/CSharp/Themes/Generic.xaml#plainviewstyle)]  
  
 若要在自定义视图模式中定义的数据布局，定义<xref:System.Windows.DataTemplate>对象。 下面的示例定义<xref:System.Windows.DataTemplate>可用来显示数据中的`PlainView`视图模式。  
  
 [!code-xaml[ListViewCustomView#PlainViewDataTemplate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewCustomView/CSharp/Window1.xaml#plainviewdatatemplate)]  
  
 下面的示例演示如何定义<xref:System.Windows.ResourceKey>有关`PlainView`使用的视图模式<xref:System.Windows.DataTemplate>上一示例中定义。  
  
 [!code-xaml[ListViewCustomView#PlainViewtileView](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewCustomView/CSharp/Window1.xaml#plainviewtileview)]  
  
 一个<xref:System.Windows.Controls.ListView>控件可以使用自定义视图，如果您设置<xref:System.Windows.Controls.ListView.View%2A>属性设置为资源键。 下面的示例演示如何指定`PlainView`的视图模式<xref:System.Windows.Controls.ListView>。  
  
 [!code-csharp[ListViewCustomView#ListViewtileViewmode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewCustomView/CSharp/Window1.xaml.cs#listviewtileviewmode)]
 [!code-vb[ListViewCustomView#ListViewtileViewmode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ListViewCustomView/visualbasic/window1.xaml.vb#listviewtileviewmode)]  
  
 有关完整示例，请参阅[ListView 与多个视图示例](https://go.microsoft.com/fwlink/?LinkID=160013)。  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Windows.Controls.ListView>  
 <xref:System.Windows.Controls.GridView>  
 [帮助主题](../../../../docs/framework/wpf/controls/listview-how-to-topics.md)  
 [ListView 概述](../../../../docs/framework/wpf/controls/listview-overview.md)  
 [GridView 概述](../../../../docs/framework/wpf/controls/gridview-overview.md)
