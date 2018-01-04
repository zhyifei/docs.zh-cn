---
title: "如何：在 Windows 窗体中导航数据"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: d99d794164307cb22c5dfc89d6c9c227aa457a59
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-navigate-data-in-windows-forms"></a>如何：在 Windows 窗体中导航数据
在 Windows 应用程序，以浏览数据源中的记录的最简单方法是将绑定<xref:System.Windows.Forms.BindingSource>组件到数据源，然后将控件绑定到<xref:System.Windows.Forms.BindingSource>。 你可以然后使用内置的导航方法上,<xref:System.Windows.Forms.BindingSource>此类<xref:System.Windows.Forms.BindingSource.MoveNext%2A>， <xref:System.Windows.Forms.BindingSource.MoveLast%2A>，<xref:System.Windows.Forms.BindingSource.MovePrevious%2A>和<xref:System.Windows.Forms.BindingSource.MoveFirst%2A>。 使用这些方法将调整<xref:System.Windows.Forms.BindingSource.Position%2A>和<xref:System.Windows.Forms.BindingSource.Current%2A>属性<xref:System.Windows.Forms.BindingSource>正确。 此外可以查找某个项，并将其设置为当前项，通过设置<xref:System.Windows.Forms.BindingSource.Position%2A>属性。  
  
### <a name="to-increment-the-position-in-a-data-source"></a>若要递增的数据源中的位置  
  
1.  设置<xref:System.Windows.Forms.BindingSource.Position%2A>属性<xref:System.Windows.Forms.BindingSource>绑定到记录的位置以转到数据。 下面的示例演示如何使用<xref:System.Windows.Forms.BindingSource.MoveNext%2A>方法<xref:System.Windows.Forms.BindingSource>递增<xref:System.Windows.Forms.BindingSource.Position%2A>属性时`nextButton`单击。 <xref:System.Windows.Forms.BindingSource>与关联`Customers`数据集的表`Northwind`。  
  
    > [!NOTE]
    >  设置<xref:System.Windows.Forms.BindingSource.Position%2A>属性的第一个或最后一个记录之外的值不会导致错误，作为[!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)]不允许你将位置设置为的值超出了列表的界限。 如果这很重要应用程序，以了解是否已越过的第一个或最后一个记录中，包括逻辑来测试是否将超过数据元素计数。  
  
     [!code-csharp[System.Windows.Forms.NavigatingData#4](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.NavigatingData/CS/Form1.cs#4)]
     [!code-vb[System.Windows.Forms.NavigatingData#4](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.NavigatingData/VB/Form1.vb#4)]  
  
### <a name="to-check-whether-you-have-passed-the-end-or-beginning"></a>若要检查是否已通过末尾或开头  
  
1.  为 <xref:System.Windows.Forms.BindingSource.PositionChanged> 事件创建一个事件处理程序。 在处理程序中，你可以测试是否建议的位置值超出实际数据元素计数。  
  
     下面的示例演示如何测试是否已到达最后一个的数据元素。 在示例中，如果你在最后一个元素，**下一步**窗体上的按钮处于禁用状态。  
  
    > [!NOTE]
    >  请注意，你应更改在代码中导航的列表，则应该重新启用**下一步**按钮，以便用户可以浏览新列表的整个长度。 此外，请注意，上述<xref:System.Windows.Forms.BindingSource.PositionChanged>针对特定的事件<xref:System.Windows.Forms.BindingSource>你正在使用必须与其事件处理方法关联。 以下是用于处理的方法的示例<xref:System.Windows.Forms.BindingSource.PositionChanged>事件：  
  
     [!code-csharp[System.Windows.Forms.NavigatingData#3](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.NavigatingData/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.NavigatingData#3](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.NavigatingData/VB/Form1.vb#3)]  
  
### <a name="to-find-an-item-and-set-it-as-the-current-item"></a>若要查找某个项并将其设置为当前项  
  
1.  查找你想要将设置为当前项的记录。 你可以执行此使用<xref:System.Windows.Forms.BindingSource.Find%2A>方法<xref:System.Windows.Forms.BindingSource>，如果你的数据源实现<xref:System.ComponentModel.IBindingList>。 一些示例数据源实现<xref:System.ComponentModel.IBindingList>是<xref:System.ComponentModel.BindingList%601>和<xref:System.Data.DataView>。  
  
     [!code-csharp[System.Windows.Forms.NavigatingData#2](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.NavigatingData/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.NavigatingData#2](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.NavigatingData/VB/Form1.vb#2)]  
  
## <a name="see-also"></a>请参阅  
 [Windows 窗体支持的数据源](../../../docs/framework/winforms/data-sources-supported-by-windows-forms.md)  
 [Windows 窗体数据绑定中的更改通知](../../../docs/framework/winforms/change-notification-in-windows-forms-data-binding.md)  
 [数据绑定和 Windows 窗体](../../../docs/framework/winforms/data-binding-and-windows-forms.md)  
 [Windows 窗体数据绑定](../../../docs/framework/winforms/windows-forms-data-binding.md)
