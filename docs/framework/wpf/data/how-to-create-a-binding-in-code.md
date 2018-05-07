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
ms.openlocfilehash: 62c5610bf5590594f34a3401b9397bb17d23f5ab
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-create-a-binding-in-code"></a>如何：在代码中创建绑定
此示例演示如何创建和设置<xref:System.Windows.Data.Binding>在代码中。  
  
## <a name="example"></a>示例  
 <xref:System.Windows.FrameworkElement>类和<xref:System.Windows.FrameworkContentElement>类都公开`SetBinding`方法。 如果你正在绑定继承这些类之一的元素，可以调用<xref:System.Windows.FrameworkElement.SetBinding%2A>直接的方法。  
  
 下面的示例创建一个名为，类`MyData`，其中包含一个名为属性`MyDataProperty`。  
  
 [!code-csharp[CodeOnlyBinding#DataObject](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CodeOnlyBinding/CSharp/MyData.cs#dataobject)]
 [!code-vb[CodeOnlyBinding#DataObject](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CodeOnlyBinding/VisualBasic/MyData.vb#dataobject)]  
  
 下面的示例演示如何创建用于设置绑定源的绑定的对象。  该示例使用<xref:System.Windows.FrameworkElement.SetBinding%2A>绑定<xref:System.Windows.Controls.TextBlock.Text%2A>属性`myText`，即<xref:System.Windows.Controls.TextBlock>控件， `MyDataProperty`。  
  
 [!code-csharp[CodeOnlyBinding#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CodeOnlyBinding/CSharp/binding.cs#1)]
 [!code-vb[CodeOnlyBinding#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CodeOnlyBinding/VisualBasic/App.vb#1)]  
  
 有关完整的代码示例，请参阅[仅限代码的绑定的示例](http://msdn.microsoft.com/library/764aaf0b-2216-4941-9548-9c98da18d1a6)。  
  
 而不是调用<xref:System.Windows.FrameworkElement.SetBinding%2A>，你可以使用<xref:System.Windows.Data.BindingOperations.SetBinding%2A>静态方法<xref:System.Windows.Data.BindingOperations>类。 下面的示例，调用<xref:System.Windows.Data.BindingOperations.SetBinding%2A?displayProperty=nameWithType>而不是<xref:System.Windows.FrameworkElement.SetBinding%2A?displayProperty=nameWithType>绑定`myText`到`myDataProperty`。  
  
 [!code-csharp[CodeOnlyBinding#BOSetBinding](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CodeOnlyBinding/CSharp/binding.cs#bosetbinding)]
 [!code-vb[CodeOnlyBinding#BOSetBinding](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CodeOnlyBinding/VisualBasic/App.vb#bosetbinding)]  
  
## <a name="see-also"></a>请参阅  
 [数据绑定概述](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [帮助主题](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
