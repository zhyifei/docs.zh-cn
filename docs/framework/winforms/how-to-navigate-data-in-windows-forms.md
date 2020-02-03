---
title: 如何：导航数据
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- cursors [Windows Forms], data sources
- data sources [Windows Forms], Windows Forms
- Windows Forms, navigating
- CurrencyManager class [Windows Forms], navigating Windows Forms data
- data [Windows Forms], navigating
ms.assetid: 97360f7b-b181-4084-966a-4c62518f735b
ms.openlocfilehash: 2dd900b652b0ff21ea0eb0dbc5463b22c869ec7c
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76739396"
---
# <a name="how-to-navigate-data-in-windows-forms"></a>如何：在 Windows 窗体中导航数据
在 Windows 应用程序中，在数据源中导航记录的最简单方法是将 <xref:System.Windows.Forms.BindingSource> 组件绑定到数据源，然后将控件绑定到 <xref:System.Windows.Forms.BindingSource>。 然后，你可以在 <xref:System.Windows.Forms.BindingSource> 上使用内置的导航方法，如 <xref:System.Windows.Forms.BindingSource.MoveNext%2A>、<xref:System.Windows.Forms.BindingSource.MoveLast%2A>、<xref:System.Windows.Forms.BindingSource.MovePrevious%2A> 和 <xref:System.Windows.Forms.BindingSource.MoveFirst%2A>。 使用这些方法会适当地调整 <xref:System.Windows.Forms.BindingSource> 的 <xref:System.Windows.Forms.BindingSource.Position%2A> 和 <xref:System.Windows.Forms.BindingSource.Current%2A> 属性。 还可以通过设置 "<xref:System.Windows.Forms.BindingSource.Position%2A>" 属性来查找项并将其设置为当前项。  
  
### <a name="to-increment-the-position-in-a-data-source"></a>递增数据源中的位置  
  
1. 将绑定数据的 <xref:System.Windows.Forms.BindingSource> 的 <xref:System.Windows.Forms.BindingSource.Position%2A> 属性设置为要定位到的记录位置。 下面的示例演示如何使用 <xref:System.Windows.Forms.BindingSource> 的 <xref:System.Windows.Forms.BindingSource.MoveNext%2A> 方法在单击 `nextButton` 时递增 <xref:System.Windows.Forms.BindingSource.Position%2A> 属性。 <xref:System.Windows.Forms.BindingSource> 与数据集 `Northwind`的 `Customers` 表相关联。  
  
    > [!NOTE]
    > 将 <xref:System.Windows.Forms.BindingSource.Position%2A> 属性设置为超出第一条或最后一条记录的值不会导致错误，因为 .NET Framework 不允许将位置设置为列表边界之外的值。 如果你的应用程序中有必要了解你是否已超出第一条或最后一条记录，请包括用于测试是否会超出数据元素计数的逻辑。  
  
     [!code-csharp[System.Windows.Forms.NavigatingData#4](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.NavigatingData/CS/Form1.cs#4)]
     [!code-vb[System.Windows.Forms.NavigatingData#4](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.NavigatingData/VB/Form1.vb#4)]  
  
### <a name="to-check-whether-you-have-passed-the-end-or-beginning"></a>检查是否已通过结尾或开头  
  
1. 为 <xref:System.Windows.Forms.BindingSource.PositionChanged> 事件创建一个事件处理程序。 在处理程序中，你可以测试建议的位置值是否超过了实际的数据元素计数。  
  
     下面的示例演示如何测试是否已到达最后一个数据元素。 在此示例中，如果您位于最后一个元素，则窗体上的 "**下一步**" 按钮处于禁用状态。  
  
    > [!NOTE]
    > 请注意，如果您在代码中导航列表，应重新启用 "**下一步**" 按钮，以便用户可以浏览新列表的整个长度。 此外，请注意，所使用的特定 <xref:System.Windows.Forms.BindingSource> 的上述 <xref:System.Windows.Forms.BindingSource.PositionChanged> 事件需要与其事件处理方法关联。 下面是用于处理 <xref:System.Windows.Forms.BindingSource.PositionChanged> 事件的方法示例：  
  
     [!code-csharp[System.Windows.Forms.NavigatingData#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.NavigatingData/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.NavigatingData#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.NavigatingData/VB/Form1.vb#3)]  
  
### <a name="to-find-an-item-and-set-it-as-the-current-item"></a>查找项并将其设置为当前项  
  
1. 查找要设置为当前项的记录。 如果数据源实现了 <xref:System.ComponentModel.IBindingList>，则可以使用 <xref:System.Windows.Forms.BindingSource>的 <xref:System.Windows.Forms.BindingSource.Find%2A> 方法执行此操作。 <xref:System.ComponentModel.BindingList%601> 和 <xref:System.Data.DataView>实现 <xref:System.ComponentModel.IBindingList> 的数据源的一些示例。  
  
     [!code-csharp[System.Windows.Forms.NavigatingData#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.NavigatingData/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.NavigatingData#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.NavigatingData/VB/Form1.vb#2)]  
  
## <a name="see-also"></a>另请参阅

- [Windows 窗体支持的数据源](data-sources-supported-by-windows-forms.md)
- [Windows 窗体数据绑定中的更改通知](change-notification-in-windows-forms-data-binding.md)
- [数据绑定和 Windows 窗体](data-binding-and-windows-forms.md)
- [Windows 窗体数据绑定](windows-forms-data-binding.md)
