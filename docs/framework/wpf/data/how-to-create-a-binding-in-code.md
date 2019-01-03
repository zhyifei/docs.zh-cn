---
title: 如何：在代码中创建绑定
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- binding data [WPF], creating
- data binding [WPF], creating
ms.assetid: 1a606db9-cf5f-42ed-a1c5-9e4722ec77a0
ms.openlocfilehash: 2d13650cb3e9a4e97a6642992b7211f323b9ea96
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/04/2018
ms.locfileid: "43502253"
---
# <a name="how-to-create-a-binding-in-code"></a>如何：在代码中创建绑定
此示例演示如何在代码中创建和设置 <xref:System.Windows.Data.Binding>。  
  
## <a name="example"></a>示例  
 <xref:System.Windows.FrameworkElement> 类和 <xref:System.Windows.FrameworkContentElement> 类都公开了 `SetBinding` 方法。如果要绑定的元素继承其中的一个类，则可直接调用 <xref:System.Windows.FrameworkElement.SetBinding%2A> 方法。
  
 下面的示例创建了一个名为 `MyData` 的类，其中包含一个名为 `MyDataProperty` 的属性。
  
 [!code-csharp[CodeOnlyBinding#DataObject](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CodeOnlyBinding/CSharp/MyData.cs#dataobject)]
 [!code-vb[CodeOnlyBinding#DataObject](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CodeOnlyBinding/VisualBasic/MyData.vb#dataobject)]  
  
 下面的示例演示如何创建绑定对象来设置绑定源。该示例使用 <xref:System.Windows.FrameworkElement.SetBinding%2A> 将 `myText` （一个 <xref:System.Windows.Controls.TextBlock> 控件）的 <xref:System.Windows.Controls.TextBlock.Text%2A> 属性绑定到 `MyDataProperty`。
  
 [!code-csharp[CodeOnlyBinding#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CodeOnlyBinding/CSharp/binding.cs#1)]
 [!code-vb[CodeOnlyBinding#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CodeOnlyBinding/VisualBasic/App.vb#1)]  
  
 有关完整的代码示例，请参阅[仅限代码的绑定示例](https://msdn.microsoft.com/library/764aaf0b-2216-4941-9548-9c98da18d1a6)。  
  
 可以使用 <xref:System.Windows.Data.BindingOperations> 类的静态方法 <xref:System.Windows.Data.BindingOperations.SetBinding%2A>，而不是调用 <xref:System.Windows.FrameworkElement.SetBinding%2A>。下面的示例通过调用 <xref:System.Windows.Data.BindingOperations.SetBinding%2A?displayProperty=nameWithType> 而不是 <xref:System.Windows.FrameworkElement.SetBinding%2A?displayProperty=nameWithType> 将 `myText` 绑定到 `myDataProperty`。
  
 [!code-csharp[CodeOnlyBinding#BOSetBinding](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CodeOnlyBinding/CSharp/binding.cs#bosetbinding)]
 [!code-vb[CodeOnlyBinding#BOSetBinding](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CodeOnlyBinding/VisualBasic/App.vb#bosetbinding)]  
  
## <a name="see-also"></a>请参阅  
 [数据绑定概述](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [帮助主题](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
