---
title: 如何：使用事件创建翻转效果
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- colors of elements [WPF], changing
- rollover effect [WPF]
- element colors [WPF], changing
ms.assetid: 3b20d028-6f1c-4b25-95d2-fa68cefbdb4c
ms.openlocfilehash: 87740a215136863199d962a2704cf691f27fc3bc
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/05/2019
ms.locfileid: "57369092"
---
# <a name="how-to-create-a-rollover-effect-using-events"></a><span data-ttu-id="fe0c5-102">如何：使用事件创建翻转效果</span><span class="sxs-lookup"><span data-stu-id="fe0c5-102">How to: Create a Rollover Effect Using Events</span></span>
<span data-ttu-id="fe0c5-103">此示例演示如何根据鼠标指针进入和离开的元素所占据的区域更改元素的颜色。</span><span class="sxs-lookup"><span data-stu-id="fe0c5-103">This example shows how to change the color of an element as the mouse pointer enters and leaves the area occupied by the element.</span></span>  
  
 <span data-ttu-id="fe0c5-104">此示例中包含的[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]文件和代码隐藏文件。</span><span class="sxs-lookup"><span data-stu-id="fe0c5-104">This example consists of a [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] file and a code-behind file.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="fe0c5-105">此示例演示如何使用事件，但要实现此相同的效果，建议的方式是使用<xref:System.Windows.Trigger>样式中。</span><span class="sxs-lookup"><span data-stu-id="fe0c5-105">This example demonstrates how to use events, but the recommended way to achieve this same effect is to use a <xref:System.Windows.Trigger> in a style.</span></span> <span data-ttu-id="fe0c5-106">有关详细信息，请参阅[样式设置和模板化](../controls/styling-and-templating.md)。</span><span class="sxs-lookup"><span data-stu-id="fe0c5-106">For more information, see [Styling and Templating](../controls/styling-and-templating.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="fe0c5-107">示例</span><span class="sxs-lookup"><span data-stu-id="fe0c5-107">Example</span></span>  
 <span data-ttu-id="fe0c5-108">以下[!INCLUDE[TLA2#tla_titlexaml](../../../../includes/tla2sharptla-titlexaml-md.md)]创建用户界面，其中包括<xref:System.Windows.Controls.Border>围绕<xref:System.Windows.Controls.TextBlock>，并将其附加<xref:System.Windows.Input.Mouse.MouseEnter>并<xref:System.Windows.UIElement.MouseLeave>事件处理程序到<xref:System.Windows.Controls.Border>。</span><span class="sxs-lookup"><span data-stu-id="fe0c5-108">The following [!INCLUDE[TLA2#tla_titlexaml](../../../../includes/tla2sharptla-titlexaml-md.md)] creates the user interface, which consists of <xref:System.Windows.Controls.Border> around a <xref:System.Windows.Controls.TextBlock>, and attaches the <xref:System.Windows.Input.Mouse.MouseEnter> and <xref:System.Windows.UIElement.MouseLeave> event handlers to the <xref:System.Windows.Controls.Border>.</span></span>  
  
 [!code-xaml[mouseenterMouseleave#MouseEnterLeaveSampleXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/mouseenterMouseleave/CSharp/Window1.xaml#mouseenterleavesamplexaml)]  
  
 <span data-ttu-id="fe0c5-109">下面的代码隐藏创建<xref:System.Windows.UIElement.MouseEnter>和<xref:System.Windows.UIElement.MouseLeave>事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="fe0c5-109">The following code behind creates the <xref:System.Windows.UIElement.MouseEnter> and <xref:System.Windows.UIElement.MouseLeave> event handlers.</span></span>  <span data-ttu-id="fe0c5-110">当鼠标指针进入<xref:System.Windows.Controls.Border>的背景<xref:System.Windows.Controls.Border>更改为红色。</span><span class="sxs-lookup"><span data-stu-id="fe0c5-110">When the mouse pointer enters the <xref:System.Windows.Controls.Border>, the background of the <xref:System.Windows.Controls.Border> is changed to red.</span></span>  <span data-ttu-id="fe0c5-111">当鼠标指针离开<xref:System.Windows.Controls.Border>的背景<xref:System.Windows.Controls.Border>更改回 white。</span><span class="sxs-lookup"><span data-stu-id="fe0c5-111">When the mouse pointer leaves the <xref:System.Windows.Controls.Border>, the background of the <xref:System.Windows.Controls.Border> is changed back to white.</span></span>  
  
 [!code-csharp[mouseenterMouseleave#MouseEnterLeaveSampleEventHandlers](~/samples/snippets/csharp/VS_Snippets_Wpf/mouseenterMouseleave/CSharp/Window1.xaml.cs#mouseenterleavesampleeventhandlers)]
 [!code-vb[mouseenterMouseleave#MouseEnterLeaveSampleEventHandlers](~/samples/snippets/visualbasic/VS_Snippets_Wpf/mouseenterMouseleave/VisualBasic/Window1.xaml.vb#mouseenterleavesampleeventhandlers)]
