---
title: 如何：绑定到 LINQ 查询的结果
ms.date: 03/30/2017
helpviewer_keywords:
- running a LINQ query [WPF], bind to results
- binding to LINQ query results [WPF]
ms.assetid: ff2844d9-17ed-4ea6-aab1-5111af0bc684
ms.openlocfilehash: 70f4b439d231d69e5671216bc4e62d0789ce66c7
ms.sourcegitcommit: 82f94a44ad5c64a399df2a03fa842db308185a76
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/25/2019
ms.locfileid: "72920134"
---
# <a name="how-to-bind-to-the-results-of-a-linq-query"></a>如何：绑定到 LINQ 查询的结果

此示例演示如何运行 LINQ 查询并将其绑定到结果。

## <a name="example"></a>示例

下面的示例创建两个列表框。 第一个列表框包含三个列表项。

[!code-xaml[LinqExample#UI](~/samples/snippets/csharp/VS_Snippets_Wpf/LinqExample/CSharp/Window1.xaml#ui)]

从第一个列表框中选择一项将调用以下事件处理程序。 在此示例中，`Tasks` 是 `Task` 对象的集合。 `Task` 类具有一个名为 `Priority`的属性。 此事件处理程序运行 LINQ 查询，该查询返回具有选定优先级值的 `Task` 对象的集合，然后将其设置为 <xref:System.Windows.FrameworkElement.DataContext%2A>：

[!code-csharp[LinqExample#Using](~/samples/snippets/csharp/VS_Snippets_Wpf/LinqExample/CSharp/Window1.xaml.cs#using)]
[!code-csharp[LinqExample#Tasks](~/samples/snippets/csharp/VS_Snippets_Wpf/LinqExample/CSharp/Window1.xaml.cs#tasks)]
[!code-csharp[LinqExample#Handler](~/samples/snippets/csharp/VS_Snippets_Wpf/LinqExample/CSharp/Window1.xaml.cs#handler)]

第二个列表框绑定到该集合，因为其 <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> 值设置为 `{Binding}`。 因此，它会显示返回的集合（基于 `myTaskTemplate` <xref:System.Windows.DataTemplate>）。

## <a name="see-also"></a>请参阅

- [让数据可供 XAML 中的绑定使用](how-to-make-data-available-for-binding-in-xaml.md)
- [绑定到集合并根据选择的内容显示信息](how-to-bind-to-a-collection-and-display-information-based-on-selection.md)
- [WPF 版本 4.5 中的新增功能](../getting-started/whats-new.md)
- [数据绑定概述](data-binding-overview.md)
