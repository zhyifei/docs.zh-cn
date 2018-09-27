---
title: 如何：实现 PriorityBinding
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data binding [WPF], PriorityBinding class
ms.assetid: d63b65ab-b3e9-4322-9aa8-1450f8d89532
ms.openlocfilehash: a7729ec3d06ec701cf2194bed5d90b5bed76573a
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/27/2018
ms.locfileid: "47398805"
---
# <a name="how-to-implement-prioritybinding"></a>如何：实现 PriorityBinding
<xref:System.Windows.Data.PriorityBinding> 在[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]的工作原理是指定的绑定的列表。 绑定的列表按从最高优先级到最低优先级排序。 如果最高优先级绑定返回一个值成功时对其进行处理然后则永远不需要处理列表中的其他绑定。 这是最高优先级的绑定需要很长的时间要计算的情况下，将使用成功返回值的下一步最高优先级，直到较高优先级的绑定会成功返回一个值。  
  
## <a name="example"></a>示例  
 若要演示如何<xref:System.Windows.Data.PriorityBinding>的工作原理，`AsyncDataSource`对象已创建具有以下三个属性： `FastDP`， `SlowerDP`，和`SlowestDP`。  
  
 Get 访问器的`FastDP`返回的值`_fastDP`数据成员。  
  
 Get 访问器的`SlowerDP`等待返回的值之前的 3 秒`_slowerDP`数据成员。  
  
 Get 访问器的`SlowestDP`等待 5 秒钟之后返回的值`_slowestDP`数据成员。  
  
> [!NOTE]
>  此示例只为了方便本文演示。 [!INCLUDE[TLA#tla_net](../../../../includes/tlasharptla-net-md.md)]准则不建议将定义所数量级字段集相比，速度较慢的属性。 有关详细信息，请参阅[NIB： 选择属性和方法](https://msdn.microsoft.com/library/55825e8f-7e2e-448a-9505-7217cc91b1af)。  
  
 [!code-csharp[PriorityBinding#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PriorityBinding/CSharp/Window1.xaml.cs#1)]
 [!code-vb[PriorityBinding#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PriorityBinding/VisualBasic/AsyncDataSource.vb#1)]  
  
 <xref:System.Windows.Controls.TextBlock.Text%2A>属性绑定到上述`AsyncDS`使用<xref:System.Windows.Data.PriorityBinding>:  
  
 [!code-xaml[PriorityBinding#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PriorityBinding/CSharp/Window1.xaml#2)]  
  
 当处理绑定引擎<xref:System.Windows.Data.Binding>对象，它与第一个启动<xref:System.Windows.Data.Binding>，后者已绑定到`SlowestDP`属性。 当这<xref:System.Windows.Data.Binding>是处理，它不返回一个值成功因为它处于睡眠状态 5 秒钟，因此下一步<xref:System.Windows.Data.Binding>处理元素。 下一步<xref:System.Windows.Data.Binding>不返回值成功因为等待 3 秒。 绑定引擎随后会转至下一步<xref:System.Windows.Data.Binding>元素，它绑定到`FastDP`属性。 这<xref:System.Windows.Data.Binding>返回"快速值"的值。 <xref:System.Windows.Controls.TextBlock>现在将显示"快速值"的值。  
  
 3 秒结束后`SlowerDP`属性返回的值"慢值"。 <xref:System.Windows.Controls.TextBlock>然后显示"慢 Value"的值。  
  
 在 5 秒结束后`SlowestDP`属性返回的值"最慢值"。 该绑定具有最高优先级，因为首先列出。 <xref:System.Windows.Controls.TextBlock>现在将显示"最慢 Value"的值。  
  
 请参阅<xref:System.Windows.Data.PriorityBinding>有关被视为成功的返回值从绑定信息。  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Windows.Data.Binding.IsAsync%2A?displayProperty=nameWithType>  
 [数据绑定概述](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [帮助主题](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
