---
title: 如何：更改 ListView 中列的水平对齐方式
ms.date: 03/30/2017
helpviewer_keywords:
- ListView controls [WPF], horizontal alignment [WPF]
ms.assetid: b9573e44-9dad-4d14-939c-7859ca372758
ms.openlocfilehash: 5447f1a73b008b2ed4f345eba00f4d631e11e257
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2019
ms.locfileid: "73458604"
---
# <a name="how-to-change-the-horizontal-alignment-of-a-column-in-a-listview"></a>如何：更改 ListView 中列的水平对齐方式
默认情况下，<xref:System.Windows.Controls.ListViewItem> 中每一列的内容都为左对齐。 您可以通过提供 <xref:System.Windows.DataTemplate> 并在 <xref:System.Windows.DataTemplate>内的元素上设置 <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> 属性，来更改每个列的对齐方式。 本主题演示 <xref:System.Windows.Controls.ListView> 如何默认对齐其内容，以及如何更改 <xref:System.Windows.Controls.ListView>中一列的对齐方式。  
  
## <a name="example"></a>示例  
 在下面的示例中，"`Title`" 和 "`ISBN`" 列中的数据保持左对齐。  
  
 [!code-xaml[ListViewHowTos#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#1)]  
[!code-xaml[ListViewHowTos#2](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#2)]  
  
 若要更改 `ISBN` 列的对齐方式，需指定 <xref:System.Windows.Controls.ListViewItem> 每个 <xref:System.Windows.HorizontalAlignment.Stretch>的 <xref:System.Windows.Controls.Control.HorizontalContentAlignment%2A> 属性，以便每个 <xref:System.Windows.Controls.ListViewItem> 中的元素可以跨每个列的整个宽度。 由于 <xref:System.Windows.Controls.ListView> 绑定到数据源，因此需要创建设置 <xref:System.Windows.Controls.Control.HorizontalContentAlignment%2A>的样式。 接下来，需要使用 <xref:System.Windows.DataTemplate> 显示内容，而不使用 <xref:System.Windows.Controls.GridViewColumn.DisplayMemberBinding%2A> 属性。 若要显示每个模板的 `ISBN`，<xref:System.Windows.DataTemplate> 可以只包含其 <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> 属性设置为 <xref:System.Windows.HorizontalAlignment.Right>的 <xref:System.Windows.Controls.TextBlock>。  
  
 下面的示例定义使 `ISBN` 列右对齐所需的样式和 <xref:System.Windows.DataTemplate>，并更改 <xref:System.Windows.Controls.GridViewColumn> 以引用该 <xref:System.Windows.DataTemplate>。  
  
 [!code-xaml[ListViewHowTos#3](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#3)]  
[!code-xaml[ListViewHowTos#4](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#4)]  
  
## <a name="see-also"></a>请参阅

- [数据绑定概述](../../../desktop-wpf/data/data-binding-overview.md)
- [数据模板化概述](../data/data-templating-overview.md)
- [使用 XMLDataProvider 和 XPath 查询绑定到 XML 数据](../data/how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md)
- [ListView 概述](listview-overview.md)
