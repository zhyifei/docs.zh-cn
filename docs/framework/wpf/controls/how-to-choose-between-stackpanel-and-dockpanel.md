---
title: 如何：在 StackPanel 和 DockPanel 之间进行选择
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- controls [WPF], DockPanel
- DockPanel control [WPF], StackPanel control compared to
- StackPanel control [WPF], DockPanel control compared to
- controls [WPF], StackPanel
ms.assetid: f9239086-451f-42e6-81f7-ef89ef349742
ms.openlocfilehash: 8338421dfb1bea856c15edf9d324cec955584f9f
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59206962"
---
# <a name="how-to-choose-between-stackpanel-and-dockpanel"></a><span data-ttu-id="e6bfd-102">如何：在 StackPanel 和 DockPanel 之间进行选择</span><span class="sxs-lookup"><span data-stu-id="e6bfd-102">How to: Choose Between StackPanel and DockPanel</span></span>
<span data-ttu-id="e6bfd-103">此示例演示如何使用之间进行选择<xref:System.Windows.Controls.StackPanel>或<xref:System.Windows.Controls.DockPanel>堆叠中的内容时<xref:System.Windows.Controls.Panel>。</span><span class="sxs-lookup"><span data-stu-id="e6bfd-103">This example shows how to choose between using a <xref:System.Windows.Controls.StackPanel> or a <xref:System.Windows.Controls.DockPanel> when you stack content in a <xref:System.Windows.Controls.Panel>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e6bfd-104">示例</span><span class="sxs-lookup"><span data-stu-id="e6bfd-104">Example</span></span>  
 <span data-ttu-id="e6bfd-105">尽管可以使用任一<xref:System.Windows.Controls.DockPanel>或<xref:System.Windows.Controls.StackPanel>堆叠子元素，两个控件不始终生成相同的结果。</span><span class="sxs-lookup"><span data-stu-id="e6bfd-105">Although you can use either <xref:System.Windows.Controls.DockPanel> or <xref:System.Windows.Controls.StackPanel> to stack child elements, the two controls do not always produce the same results.</span></span> <span data-ttu-id="e6bfd-106">例如，放置子元素的顺序可能会影响中的子元素的大小<xref:System.Windows.Controls.DockPanel>但不能在<xref:System.Windows.Controls.StackPanel>。</span><span class="sxs-lookup"><span data-stu-id="e6bfd-106">For example, the order that you place child elements can affect the size of child elements in a <xref:System.Windows.Controls.DockPanel> but not in a <xref:System.Windows.Controls.StackPanel>.</span></span> <span data-ttu-id="e6bfd-107">出现此不同的行为的原因<xref:System.Windows.Controls.StackPanel>度量值中的堆叠在方向<xref:System.Double>。<xref:System.Double.PositiveInfinity>; 但是，<xref:System.Windows.Controls.DockPanel>测量仅的可用大小。</span><span class="sxs-lookup"><span data-stu-id="e6bfd-107">This different behavior occurs because <xref:System.Windows.Controls.StackPanel> measures in the direction of stacking at <xref:System.Double>.<xref:System.Double.PositiveInfinity>; however, <xref:System.Windows.Controls.DockPanel> measures only the available size.</span></span>  
  
 <span data-ttu-id="e6bfd-108">下面的示例演示此主要区别<xref:System.Windows.Controls.DockPanel>和<xref:System.Windows.Controls.StackPanel>。</span><span class="sxs-lookup"><span data-stu-id="e6bfd-108">The following example demonstrates this key difference between <xref:System.Windows.Controls.DockPanel> and <xref:System.Windows.Controls.StackPanel>.</span></span>  
  
 [!code-cpp[StackPanelOvw4#1](~/samples/snippets/cpp/VS_Snippets_Wpf/StackPanelOvw4/CPP/StackPanel_Ovw_Sample4.cpp#1)]
 [!code-csharp[StackPanelOvw4#1](~/samples/snippets/csharp/VS_Snippets_Wpf/StackPanelOvw4/CSharp/StackPanel_Ovw_Sample4.cs#1)]
 [!code-vb[StackPanelOvw4#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/StackPanelOvw4/VisualBasic/StackPanelSamp.vb#1)]
 [!code-xaml[StackPanelOvw4#1](~/samples/snippets/xaml/VS_Snippets_Wpf/StackPanelOvw4/XAML/default.xaml#1)]  
  
## <a name="see-also"></a><span data-ttu-id="e6bfd-109">请参阅</span><span class="sxs-lookup"><span data-stu-id="e6bfd-109">See also</span></span>

- <xref:System.Windows.Controls.StackPanel>
- <xref:System.Windows.Controls.DockPanel>
- [<span data-ttu-id="e6bfd-110">面板概述</span><span class="sxs-lookup"><span data-stu-id="e6bfd-110">Panels Overview</span></span>](panels-overview.md)
