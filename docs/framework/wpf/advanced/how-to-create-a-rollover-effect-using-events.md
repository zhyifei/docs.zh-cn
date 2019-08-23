---
title: 如何：使用事件创建变换效果
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- colors of elements [WPF], changing
- rollover effect [WPF]
- element colors [WPF], changing
ms.assetid: 3b20d028-6f1c-4b25-95d2-fa68cefbdb4c
ms.openlocfilehash: 3996a3b9bb976dd5f2e5b675de3894bbaba7d9d3
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69960390"
---
# <a name="how-to-create-a-rollover-effect-using-events"></a><span data-ttu-id="5e244-102">如何：使用事件创建变换效果</span><span class="sxs-lookup"><span data-stu-id="5e244-102">How to: Create a Rollover Effect Using Events</span></span>
<span data-ttu-id="5e244-103">此示例演示如何在鼠标指针进入和离开元素占用的区域时更改元素的颜色。</span><span class="sxs-lookup"><span data-stu-id="5e244-103">This example shows how to change the color of an element as the mouse pointer enters and leaves the area occupied by the element.</span></span>  
  
 <span data-ttu-id="5e244-104">此示例由一个[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]文件和一个代码隐藏文件组成。</span><span class="sxs-lookup"><span data-stu-id="5e244-104">This example consists of a [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] file and a code-behind file.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="5e244-105">此示例演示如何使用事件, 但建议的方法是<xref:System.Windows.Trigger>在样式中使用。</span><span class="sxs-lookup"><span data-stu-id="5e244-105">This example demonstrates how to use events, but the recommended way to achieve this same effect is to use a <xref:System.Windows.Trigger> in a style.</span></span> <span data-ttu-id="5e244-106">有关详细信息，请参阅[样式设置和模板化](../controls/styling-and-templating.md)。</span><span class="sxs-lookup"><span data-stu-id="5e244-106">For more information, see [Styling and Templating](../controls/styling-and-templating.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="5e244-107">示例</span><span class="sxs-lookup"><span data-stu-id="5e244-107">Example</span></span>  
 <span data-ttu-id="5e244-108">[!INCLUDE[TLA2#tla_titlexaml](../../../../includes/tla2sharptla-titlexaml-md.md)]下面的将创建<xref:System.Windows.Controls.TextBlock> <xref:System.Windows.UIElement.MouseLeave> <xref:System.Windows.Controls.Border> 一个用户界面,<xref:System.Windows.Controls.Border>该用户界面由围绕, 并将和事件处理程序附加到。<xref:System.Windows.Input.Mouse.MouseEnter></span><span class="sxs-lookup"><span data-stu-id="5e244-108">The following [!INCLUDE[TLA2#tla_titlexaml](../../../../includes/tla2sharptla-titlexaml-md.md)] creates the user interface, which consists of <xref:System.Windows.Controls.Border> around a <xref:System.Windows.Controls.TextBlock>, and attaches the <xref:System.Windows.Input.Mouse.MouseEnter> and <xref:System.Windows.UIElement.MouseLeave> event handlers to the <xref:System.Windows.Controls.Border>.</span></span>  
  
 [!code-xaml[mouseenterMouseleave#MouseEnterLeaveSampleXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/mouseenterMouseleave/CSharp/Window1.xaml#mouseenterleavesamplexaml)]  
  
 <span data-ttu-id="5e244-109">下面的代码用于创建<xref:System.Windows.UIElement.MouseEnter>和<xref:System.Windows.UIElement.MouseLeave>事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="5e244-109">The following code behind creates the <xref:System.Windows.UIElement.MouseEnter> and <xref:System.Windows.UIElement.MouseLeave> event handlers.</span></span>  <span data-ttu-id="5e244-110">当鼠标指针进入<xref:System.Windows.Controls.Border>时, 的<xref:System.Windows.Controls.Border>背景将更改为红色。</span><span class="sxs-lookup"><span data-stu-id="5e244-110">When the mouse pointer enters the <xref:System.Windows.Controls.Border>, the background of the <xref:System.Windows.Controls.Border> is changed to red.</span></span>  <span data-ttu-id="5e244-111">当鼠标指针离开<xref:System.Windows.Controls.Border>时, 的<xref:System.Windows.Controls.Border>背景将改回为白色。</span><span class="sxs-lookup"><span data-stu-id="5e244-111">When the mouse pointer leaves the <xref:System.Windows.Controls.Border>, the background of the <xref:System.Windows.Controls.Border> is changed back to white.</span></span>  
  
 [!code-csharp[mouseenterMouseleave#MouseEnterLeaveSampleEventHandlers](~/samples/snippets/csharp/VS_Snippets_Wpf/mouseenterMouseleave/CSharp/Window1.xaml.cs#mouseenterleavesampleeventhandlers)]
 [!code-vb[mouseenterMouseleave#MouseEnterLeaveSampleEventHandlers](~/samples/snippets/visualbasic/VS_Snippets_Wpf/mouseenterMouseleave/VisualBasic/Window1.xaml.vb#mouseenterleavesampleeventhandlers)]
