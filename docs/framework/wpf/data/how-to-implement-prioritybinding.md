---
title: 如何：实现 PriorityBinding
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data binding [WPF], PriorityBinding class
ms.assetid: d63b65ab-b3e9-4322-9aa8-1450f8d89532
ms.openlocfilehash: 343b0aca4736905f3a0cbff5a0f76b170da0c920
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2019
ms.locfileid: "73459780"
---
# <a name="how-to-implement-prioritybinding"></a>如何：实现 PriorityBinding
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 中的 <xref:System.Windows.Data.PriorityBinding> 通过指定绑定列表来实现。 绑定列表按从最高优先级到最低优先级的顺序排列。 如果最高优先级绑定在处理时成功返回值，则永远不需要处理列表中的其他绑定。 这种情况可能是最高优先级的绑定需要很长的时间来计算，因此，在更高优先级的绑定成功返回值之前，将使用下一个最高优先级来成功返回值。  
  
## <a name="example"></a>示例  
 为了演示 <xref:System.Windows.Data.PriorityBinding> 的工作方式，已使用以下三个属性创建了 `AsyncDataSource` 对象： "`FastDP`"、"`SlowerDP`" 和 "`SlowestDP`"。  
  
 `FastDP` 的 get 访问器返回 `_fastDP` 数据成员的值。  
  
 `SlowerDP` 的 get 访问器在返回 `_slowerDP` 数据成员的值之前等待3秒。  
  
 `SlowestDP` 的 get 访问器在返回 `_slowestDP` 数据成员的值之前等待5秒。  
  
> [!NOTE]
> 此示例只为了方便本文演示。 .NET 指导原则建议不要定义比字段集慢的数量级顺序的属性。 有关详细信息，请参阅[在属性和方法之间进行选择](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms229054(v=vs.100))。  
  
 [!code-csharp[PriorityBinding#1](~/samples/snippets/csharp/VS_Snippets_Wpf/PriorityBinding/CSharp/Window1.xaml.cs#1)]
 [!code-vb[PriorityBinding#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PriorityBinding/VisualBasic/AsyncDataSource.vb#1)]  
  
 <xref:System.Windows.Controls.TextBlock.Text%2A> 属性使用 <xref:System.Windows.Data.PriorityBinding>绑定到上述 `AsyncDS`：  
  
 [!code-xaml[PriorityBinding#2](~/samples/snippets/csharp/VS_Snippets_Wpf/PriorityBinding/CSharp/Window1.xaml#2)]  
  
 当绑定引擎处理 <xref:System.Windows.Data.Binding> 对象时，它将从绑定到 `SlowestDP` 属性的第一个 <xref:System.Windows.Data.Binding>开始。 处理此 <xref:System.Windows.Data.Binding> 时，它不会成功返回值，因为它处于休眠状态5秒，因此处理下一个 <xref:System.Windows.Data.Binding> 元素。 接下来的 <xref:System.Windows.Data.Binding> 不会成功返回值，因为它处于休眠状态3秒。 然后，绑定引擎会移动到绑定到 `FastDP` 属性的下一个 <xref:System.Windows.Data.Binding> 元素。 此 <xref:System.Windows.Data.Binding> 返回值 "Fast Value"。 现在 <xref:System.Windows.Controls.TextBlock> 显示值 "Fast Value"。  
  
 3秒钟后，`SlowerDP` 属性返回值 "慢速值"。 然后 <xref:System.Windows.Controls.TextBlock> 显示值 "慢速值"。  
  
 超过5秒钟后，`SlowestDP` 属性返回值 "最慢的值"。 由于此绑定首先列出，因此具有最高优先级。 现在 <xref:System.Windows.Controls.TextBlock> 显示值 "最慢的值"。  
  
 请参阅 <xref:System.Windows.Data.PriorityBinding>，了解从绑定中被视为成功返回值的内容。  
  
## <a name="see-also"></a>请参阅

- <xref:System.Windows.Data.Binding.IsAsync%2A?displayProperty=nameWithType>
- [数据绑定概述](../../../desktop-wpf/data/data-binding-overview.md)
- [帮助主题](data-binding-how-to-topics.md)
