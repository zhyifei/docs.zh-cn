---
title: HScrollBar 控件和 VScrollBar 控件概述（Windows 窗体）
ms.date: 03/30/2017
f1_keywords:
- HScrollBar
- VScrollBar
helpviewer_keywords:
- ScrollBar control [Windows Forms]
- HScrollBar control [Windows Forms], about HScrollBar
- VScrollBar control [Windows Forms], about VScrollBar control
- ScrollBar control [Windows Forms], about ScrollBar control
- scroll bars [Windows Forms], about scroll bars
ms.assetid: 8b307679-1cae-41d8-99aa-3d1efd207cd6
ms.openlocfilehash: 2c6436e77753322733580acba5a20d6bb220f29c
ms.sourcegitcommit: 2350a091ef6459f0fcfd894301242400374d8558
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/21/2018
ms.locfileid: "46561430"
---
# <a name="hscrollbar-and-vscrollbar-controls-overview-windows-forms"></a><span data-ttu-id="665bf-102">HScrollBar 控件和 VScrollBar 控件概述（Windows 窗体）</span><span class="sxs-lookup"><span data-stu-id="665bf-102">HScrollBar and VScrollBar Controls Overview (Windows Forms)</span></span>
<span data-ttu-id="665bf-103">Windows 窗体<xref:System.Windows.Forms.ScrollBar>控制用于方便地在长列表项或大量的信息的任一水平或垂直滚动应用程序或控件。</span><span class="sxs-lookup"><span data-stu-id="665bf-103">Windows Forms <xref:System.Windows.Forms.ScrollBar> controls are used to provide easy navigation through a long list of items or a large amount of information by scrolling either horizontally or vertically within an application or control.</span></span> <span data-ttu-id="665bf-104">滚动条是一种常见元素的 Windows 接口，因此<xref:System.Windows.Forms.ScrollBar>控件通常用于无法从元素派生的控件<xref:System.Windows.Forms.ScrollableControl>类。</span><span class="sxs-lookup"><span data-stu-id="665bf-104">Scroll bars are a common element of the Windows interface, so the <xref:System.Windows.Forms.ScrollBar> control is often used with controls that do not derive from the <xref:System.Windows.Forms.ScrollableControl> class.</span></span> <span data-ttu-id="665bf-105">同样，许多开发人员选择合并<xref:System.Windows.Forms.ScrollBar>控制创建其自己的用户控件时。</span><span class="sxs-lookup"><span data-stu-id="665bf-105">Similarly, many developers choose to incorporate the <xref:System.Windows.Forms.ScrollBar> control when authoring their own user controls.</span></span>  
  
 <span data-ttu-id="665bf-106"><xref:System.Windows.Forms.HScrollBar> （水平） 和<xref:System.Windows.Forms.VScrollBar>（垂直） 控件的其他控件的工作方式，并且具有其自己的事件、 属性和方法集。</span><span class="sxs-lookup"><span data-stu-id="665bf-106">The <xref:System.Windows.Forms.HScrollBar> (horizontal) and <xref:System.Windows.Forms.VScrollBar> (vertical) controls operate independently from other controls and have their own set of events, properties, and methods.</span></span> <span data-ttu-id="665bf-107"><xref:System.Windows.Forms.ScrollBar> 控件不是附加到的文本框、 列表框、 组合框或 MDI 窗体的内置滚动条相同 (<xref:System.Windows.Forms.TextBox>控件具有<xref:System.Windows.Forms.TextBox.ScrollBars%2A>属性来显示或隐藏附加到控件的滚动条)。</span><span class="sxs-lookup"><span data-stu-id="665bf-107"><xref:System.Windows.Forms.ScrollBar> controls are not the same as the built-in scroll bars that are attached to text boxes, list boxes, combo boxes, or MDI forms (the <xref:System.Windows.Forms.TextBox> control has a <xref:System.Windows.Forms.TextBox.ScrollBars%2A> property to show or hide scroll bars that are attached to the control).</span></span>  
  
 <span data-ttu-id="665bf-108"><xref:System.Windows.Forms.ScrollBar>控件使用<xref:System.Windows.Forms.ScrollBar.Scroll>事件来监视沿滚动条的滚动框 （有时称为滚动块） 的移动。</span><span class="sxs-lookup"><span data-stu-id="665bf-108">The <xref:System.Windows.Forms.ScrollBar> controls use the <xref:System.Windows.Forms.ScrollBar.Scroll> event to monitor the movement of the scroll box (sometimes referred to as the thumb) along the scroll bar.</span></span> <span data-ttu-id="665bf-109">使用<xref:System.Windows.Forms.ScrollBar.Scroll>事件提供了对滚动条值的访问，因为它正被拖动。</span><span class="sxs-lookup"><span data-stu-id="665bf-109">Using the <xref:System.Windows.Forms.ScrollBar.Scroll> event provides access to the scroll bar value as it is being dragged.</span></span>  
  
## <a name="value-property"></a><span data-ttu-id="665bf-110">Value 属性</span><span class="sxs-lookup"><span data-stu-id="665bf-110">Value Property</span></span>  
 <span data-ttu-id="665bf-111"><xref:System.Windows.Forms.ScrollBar.Value%2A>属性 （其中，默认情况下，为 0） 是`integer`滚动条中滚动框的位置相对应的值。</span><span class="sxs-lookup"><span data-stu-id="665bf-111">The <xref:System.Windows.Forms.ScrollBar.Value%2A> property (which, by default, is 0) is an `integer` value corresponding to the position of the scroll box in the scroll bar.</span></span> <span data-ttu-id="665bf-112">最小值的滚动框位置时，它将移到最左侧的位置 （对于水平滚动条） 或 （对于垂直滚动条） 的顶部位置。</span><span class="sxs-lookup"><span data-stu-id="665bf-112">When the scroll box position is at the minimum value, it moves to the left-most position (for horizontal scroll bars) or the top position (for vertical scroll bars).</span></span> <span data-ttu-id="665bf-113">当滚动框位于最大值、 滚动框移到最右侧或底部位置。</span><span class="sxs-lookup"><span data-stu-id="665bf-113">When the scroll box is at the maximum value, the scroll box moves to the right-most or bottom position.</span></span> <span data-ttu-id="665bf-114">同样，值范围的顶部和底部之间的中间位置将前导边缘中间的滚动条的滚动框。</span><span class="sxs-lookup"><span data-stu-id="665bf-114">Similarly, a value halfway between the bottom and top of the range places the leading edge of the scroll box in the middle of the scroll bar.</span></span>  
  
 <span data-ttu-id="665bf-115">除了使用鼠标单击的滚动栏值更改，用户还可以拖动滚动框到沿条的任意点。</span><span class="sxs-lookup"><span data-stu-id="665bf-115">In addition to using mouse clicks to change the scroll bar value, a user can also drag the scroll box to any point along the bar.</span></span> <span data-ttu-id="665bf-116">生成的值取决于滚动框的位置，但它始终位于范围内<xref:System.Windows.Forms.ScrollBar.Minimum%2A>到<xref:System.Windows.Forms.ScrollBar.Maximum%2A>由用户设置的属性。</span><span class="sxs-lookup"><span data-stu-id="665bf-116">The resulting value depends on the position of the scroll box, but it is always within the range of the <xref:System.Windows.Forms.ScrollBar.Minimum%2A> to <xref:System.Windows.Forms.ScrollBar.Maximum%2A> properties set by the user.</span></span>  
  
## <a name="largechange-and-smallchange-properties"></a><span data-ttu-id="665bf-117">LargeChange 和 SmallChange 属性</span><span class="sxs-lookup"><span data-stu-id="665bf-117">LargeChange and SmallChange Properties</span></span>  
 <span data-ttu-id="665bf-118">当用户按下 PAGE UP 或 PAGE DOWN 键或单击中滚动框中，任意一侧的滚动条轨道<xref:System.Windows.Forms.ScrollBar.Value%2A>根据中设置的值的属性更改<xref:System.Windows.Forms.ScrollBar.LargeChange%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="665bf-118">When the user presses the PAGE UP or PAGE DOWN key or clicks in the scroll bar track on either side of the scroll box, the <xref:System.Windows.Forms.ScrollBar.Value%2A> property changes according to the value set in the <xref:System.Windows.Forms.ScrollBar.LargeChange%2A> property.</span></span>  
  
 <span data-ttu-id="665bf-119">当用户按下一个箭头键或单击滚动条按钮时，之一<xref:System.Windows.Forms.ScrollBar.Value%2A>根据中设置的值的属性更改<xref:System.Windows.Forms.ScrollBar.SmallChange%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="665bf-119">When the user presses one of the arrow keys or clicks one of the scroll bar buttons, the <xref:System.Windows.Forms.ScrollBar.Value%2A> property changes according to the value set in the <xref:System.Windows.Forms.ScrollBar.SmallChange%2A> property.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="665bf-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="665bf-120">See Also</span></span>  
 <xref:System.Windows.Forms.HScrollBar>  
 <xref:System.Windows.Forms.VScrollBar>  
 [<span data-ttu-id="665bf-121">用于.NET Framework 2.0 向 Windows 窗体的新增功能</span><span class="sxs-lookup"><span data-stu-id="665bf-121">Additions to Windows Forms for the .NET Framework 2.0</span></span>](https://msdn.microsoft.com/library/c61a923d-3d6a-4c8c-820c-e94c83f3f9a8)  
 [<span data-ttu-id="665bf-122">在 Windows 窗体上使用的控件</span><span class="sxs-lookup"><span data-stu-id="665bf-122">Controls to Use on Windows Forms</span></span>](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)
