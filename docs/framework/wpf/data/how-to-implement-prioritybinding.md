---
title: "如何：实现 PriorityBinding"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data binding [WPF], PriorityBinding class
ms.assetid: d63b65ab-b3e9-4322-9aa8-1450f8d89532
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 0e6ab8826f2298a8660a85d739fbe3456374b476
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/19/2018
---
# <a name="how-to-implement-prioritybinding"></a>如何：实现 PriorityBinding
<xref:System.Windows.Data.PriorityBinding>在[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]的工作原理是指定的绑定的列表。 绑定列表按优先级从高到最低优先级排序。 如果高优先级的绑定返回一个值成功处理时则永远不会需要处理其他列表中的绑定。 它可能是最高的优先级绑定需要很长的时间要进行求值的用例时，将使用成功返回一个值的下一步最高优先级，直到较高优先级的绑定成功返回一个值。  
  
## <a name="example"></a>示例  
 为了演示如何<xref:System.Windows.Data.PriorityBinding>可以正常工作，`AsyncDataSource`对象已创建具有以下三个属性： `FastDP`， `SlowerDP`，和`SlowestDP`。  
  
 Get 访问器`FastDP`返回的值`_fastDP`数据成员。  
  
 Get 访问器`SlowerDP`等待 3 秒，然后返回的值`_slowerDP`数据成员。  
  
 Get 访问器`SlowestDP`等待 5 秒，然后返回的值`_slowestDP`数据成员。  
  
> [!NOTE]
>  此示例是仅用于演示目的。 [!INCLUDE[TLA#tla_net](../../../../includes/tlasharptla-net-md.md)]准则建议您定义个数量级慢于字段集的属性。 有关详细信息，请参阅[NIB： 选择之间属性和方法](http://msdn.microsoft.com/library/55825e8f-7e2e-448a-9505-7217cc91b1af)。  
  
 [!code-csharp[PriorityBinding#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PriorityBinding/CSharp/Window1.xaml.cs#1)]
 [!code-vb[PriorityBinding#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PriorityBinding/VisualBasic/AsyncDataSource.vb#1)]  
  
 <xref:System.Windows.Controls.TextBlock.Text%2A>属性将绑定到上述`AsyncDS`使用<xref:System.Windows.Data.PriorityBinding>:  
  
 [!code-xaml[PriorityBinding#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PriorityBinding/CSharp/Window1.xaml#2)]  
  
 当处理绑定引擎<xref:System.Windows.Data.Binding>对象，它与第一个启动<xref:System.Windows.Data.Binding>，该元素绑定到`SlowestDP`属性。 当这<xref:System.Windows.Data.Binding>是处理，它不返回值成功因为它等待 5 秒，因此下一步<xref:System.Windows.Data.Binding>处理元素。 下一步<xref:System.Windows.Data.Binding>不返回值成功因为它等待 3 秒。 绑定引擎然后移到下一步<xref:System.Windows.Data.Binding>元素，它绑定到`FastDP`属性。 这<xref:System.Windows.Data.Binding>返回"快速 Value"的值。 <xref:System.Windows.Controls.TextBlock>现在显示"快速 Value"的值。  
  
 后 3 秒过后，`SlowerDP`属性返回的值"速度较慢值"。 <xref:System.Windows.Controls.TextBlock>然后显示值"速度较慢值"。  
  
 后 5 秒过后，`SlowestDP`属性返回的值"最慢的值"。 该绑定具有最高优先级，因为它会最先列出。 <xref:System.Windows.Controls.TextBlock>现在显示"最慢 Value"的值。  
  
 请参阅<xref:System.Windows.Data.PriorityBinding>有关什么被视为一个成功的返回值从绑定信息。  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Windows.Data.Binding.IsAsync%2A?displayProperty=nameWithType>  
 [数据绑定概述](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [帮助主题](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
