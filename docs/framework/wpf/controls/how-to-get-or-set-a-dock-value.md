---
title: 如何：获取或设置 Dock 值
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Dock values [WPF], setting
- Dock values [WPF], getting
ms.assetid: fcf4ab8a-c7cd-4835-8d04-de1c999ab4a8
ms.openlocfilehash: fb6c8a7d62aa09a6e1d82cb4079d1425a7f39f8c
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59160728"
---
# <a name="how-to-get-or-set-a-dock-value"></a><span data-ttu-id="37080-102">如何：获取或设置 Dock 值</span><span class="sxs-lookup"><span data-stu-id="37080-102">How to: Get or Set a Dock Value</span></span>
<span data-ttu-id="37080-103">下面的示例演示如何分配<xref:System.Windows.Controls.Dock>对象值。</span><span class="sxs-lookup"><span data-stu-id="37080-103">The following example shows how to assign a <xref:System.Windows.Controls.Dock> value for an object.</span></span> <span data-ttu-id="37080-104">该示例使用<xref:System.Windows.Controls.DockPanel.GetDock%2A>并<xref:System.Windows.Controls.DockPanel.SetDock%2A>方法的<xref:System.Windows.Controls.DockPanel>。</span><span class="sxs-lookup"><span data-stu-id="37080-104">The example uses the <xref:System.Windows.Controls.DockPanel.GetDock%2A> and <xref:System.Windows.Controls.DockPanel.SetDock%2A> methods of <xref:System.Windows.Controls.DockPanel>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="37080-105">示例</span><span class="sxs-lookup"><span data-stu-id="37080-105">Example</span></span>  
 <span data-ttu-id="37080-106">该示例创建的实例<xref:System.Windows.Controls.TextBlock>元素中， `txt1`，并将分配<xref:System.Windows.Controls.Dock>的值`Top`通过<xref:System.Windows.Controls.DockPanel.SetDock%2A>方法<xref:System.Windows.Controls.DockPanel>。</span><span class="sxs-lookup"><span data-stu-id="37080-106">The example creates an instance of the <xref:System.Windows.Controls.TextBlock> element, `txt1`, and assigns a <xref:System.Windows.Controls.Dock> value of `Top` by using the <xref:System.Windows.Controls.DockPanel.SetDock%2A> method of <xref:System.Windows.Controls.DockPanel>.</span></span> <span data-ttu-id="37080-107">然后，将的值<xref:System.Windows.Controls.Dock>属性设置为<xref:System.Windows.Controls.TextBlock.Text%2A>的<xref:System.Windows.Controls.TextBlock>元素中的使用<xref:System.Windows.Controls.DockPanel.GetDock%2A>方法。</span><span class="sxs-lookup"><span data-stu-id="37080-107">It then appends the value of the <xref:System.Windows.Controls.Dock> property to the <xref:System.Windows.Controls.TextBlock.Text%2A> of the <xref:System.Windows.Controls.TextBlock> element by using the <xref:System.Windows.Controls.DockPanel.GetDock%2A> method.</span></span> <span data-ttu-id="37080-108">最后，该示例将添加<xref:System.Windows.Controls.TextBlock>父元素<xref:System.Windows.Controls.DockPanel>， `dp1`。</span><span class="sxs-lookup"><span data-stu-id="37080-108">Finally, the example adds the <xref:System.Windows.Controls.TextBlock> element to the parent <xref:System.Windows.Controls.DockPanel>, `dp1`.</span></span>  
  
 [!code-csharp[DockPanelSetDock#1](~/samples/snippets/csharp/VS_Snippets_Wpf/DockPanelSetDock/CSharp/DockPanel_SetDock.cs#1)]
 [!code-vb[DockPanelSetDock#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DockPanelSetDock/VisualBasic/DockPanel_SetDock.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="37080-109">请参阅</span><span class="sxs-lookup"><span data-stu-id="37080-109">See also</span></span>

- <xref:System.Windows.Controls.DockPanel>
- <xref:System.Windows.Controls.DockPanel.GetDock%2A>
- <xref:System.Windows.Controls.DockPanel.SetDock%2A>
- [<span data-ttu-id="37080-110">面板概述</span><span class="sxs-lookup"><span data-stu-id="37080-110">Panels Overview</span></span>](panels-overview.md)
