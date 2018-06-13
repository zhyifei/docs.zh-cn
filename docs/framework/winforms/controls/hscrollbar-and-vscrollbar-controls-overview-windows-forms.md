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
ms.openlocfilehash: 572ba9f16d1c78e1825d0c9db7530c6c78175d27
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33538460"
---
# <a name="hscrollbar-and-vscrollbar-controls-overview-windows-forms"></a><span data-ttu-id="435f6-102">HScrollBar 控件和 VScrollBar 控件概述（Windows 窗体）</span><span class="sxs-lookup"><span data-stu-id="435f6-102">HScrollBar and VScrollBar Controls Overview (Windows Forms)</span></span>
<span data-ttu-id="435f6-103">Windows 窗体<xref:System.Windows.Forms.ScrollBar>控件用于提供较长列表项或大量信息中的轻松导航，请水平或垂直滚动内的应用程序或控件。</span><span class="sxs-lookup"><span data-stu-id="435f6-103">Windows Forms <xref:System.Windows.Forms.ScrollBar> controls are used to provide easy navigation through a long list of items or a large amount of information by scrolling either horizontally or vertically within an application or control.</span></span> <span data-ttu-id="435f6-104">滚动条是一种常见元素的 Windows 界面中，因此<xref:System.Windows.Forms.ScrollBar>控件通常用于是非派生自的控件<xref:System.Windows.Forms.ScrollableControl>类。</span><span class="sxs-lookup"><span data-stu-id="435f6-104">Scroll bars are a common element of the Windows interface, so the <xref:System.Windows.Forms.ScrollBar> control is often used with controls that do not derive from the <xref:System.Windows.Forms.ScrollableControl> class.</span></span> <span data-ttu-id="435f6-105">同样，许多开发人员选择合并<xref:System.Windows.Forms.ScrollBar>控制创建其自己的用户控件时。</span><span class="sxs-lookup"><span data-stu-id="435f6-105">Similarly, many developers choose to incorporate the <xref:System.Windows.Forms.ScrollBar> control when authoring their own user controls.</span></span>  
  
 <span data-ttu-id="435f6-106"><xref:System.Windows.Forms.HScrollBar> （水平） 和<xref:System.Windows.Forms.VScrollBar>（垂直） 控件运行独立于其他控件，并且具有其自己的事件、 属性和方法集。</span><span class="sxs-lookup"><span data-stu-id="435f6-106">The <xref:System.Windows.Forms.HScrollBar> (horizontal) and <xref:System.Windows.Forms.VScrollBar> (vertical) controls operate independently from other controls and have their own set of events, properties, and methods.</span></span> <span data-ttu-id="435f6-107"><xref:System.Windows.Forms.ScrollBar> 控件不是附加到文本框、 列表框、 组合框或 MDI 窗体的内置滚动条相同 (<xref:System.Windows.Forms.TextBox>控件具有<xref:System.Windows.Forms.TextBox.ScrollBars%2A>属性来显示或隐藏附加到控件的滚动条)。</span><span class="sxs-lookup"><span data-stu-id="435f6-107"><xref:System.Windows.Forms.ScrollBar> controls are not the same as the built-in scroll bars that are attached to text boxes, list boxes, combo boxes, or MDI forms (the <xref:System.Windows.Forms.TextBox> control has a <xref:System.Windows.Forms.TextBox.ScrollBars%2A> property to show or hide scroll bars that are attached to the control).</span></span>  
  
 <span data-ttu-id="435f6-108"><xref:System.Windows.Forms.ScrollBar>控制是否使用<xref:System.Windows.Forms.ScrollBar.Scroll>事件来监视沿滚动条的滚动框 （有时称为滚动块） 的移动。</span><span class="sxs-lookup"><span data-stu-id="435f6-108">The <xref:System.Windows.Forms.ScrollBar> controls use the <xref:System.Windows.Forms.ScrollBar.Scroll> event to monitor the movement of the scroll box (sometimes referred to as the thumb) along the scroll bar.</span></span> <span data-ttu-id="435f6-109">使用<xref:System.Windows.Forms.ScrollBar.Scroll>事件提供滚动栏值的访问，如进行拖动。</span><span class="sxs-lookup"><span data-stu-id="435f6-109">Using the <xref:System.Windows.Forms.ScrollBar.Scroll> event provides access to the scroll bar value as it is being dragged.</span></span>  
  
## <a name="value-property"></a><span data-ttu-id="435f6-110">Value 属性</span><span class="sxs-lookup"><span data-stu-id="435f6-110">Value Property</span></span>  
 <span data-ttu-id="435f6-111"><xref:System.Windows.Forms.ScrollBar.Value%2A>属性 （它，默认情况下，为 0） 是`integer`到滚动条中滚动框的位置相对应的值。</span><span class="sxs-lookup"><span data-stu-id="435f6-111">The <xref:System.Windows.Forms.ScrollBar.Value%2A> property (which, by default, is 0) is an `integer` value corresponding to the position of the scroll box in the scroll bar.</span></span> <span data-ttu-id="435f6-112">最小值的滚动框位置时，它将移动到的最左边的位置 （水平滚动条） 或 （对于垂直滚动条） 的最顶部位置。</span><span class="sxs-lookup"><span data-stu-id="435f6-112">When the scroll box position is at the minimum value, it moves to the left-most position (for horizontal scroll bars) or the top position (for vertical scroll bars).</span></span> <span data-ttu-id="435f6-113">在最大值、 滚动框移到最右侧或底部位置时滚动框。</span><span class="sxs-lookup"><span data-stu-id="435f6-113">When the scroll box is at the maximum value, the scroll box moves to the right-most or bottom position.</span></span> <span data-ttu-id="435f6-114">同样，值的范围顶部和底部的中间值将置于中间的滚动条的滚动框的前边缘。</span><span class="sxs-lookup"><span data-stu-id="435f6-114">Similarly, a value halfway between the bottom and top of the range places the leading edge of the scroll box in the middle of the scroll bar.</span></span>  
  
 <span data-ttu-id="435f6-115">除了使用鼠标单击的滚动条值更改，用户可以还将滚动框拖动到沿条任何点。</span><span class="sxs-lookup"><span data-stu-id="435f6-115">In addition to using mouse clicks to change the scroll bar value, a user can also drag the scroll box to any point along the bar.</span></span> <span data-ttu-id="435f6-116">生成的值取决于滚动框的位置，但它并总是的范围内<xref:System.Windows.Forms.ScrollBar.Minimum%2A>到<xref:System.Windows.Forms.ScrollBar.Maximum%2A>由用户设置的属性。</span><span class="sxs-lookup"><span data-stu-id="435f6-116">The resulting value depends on the position of the scroll box, but it is always within the range of the <xref:System.Windows.Forms.ScrollBar.Minimum%2A> to <xref:System.Windows.Forms.ScrollBar.Maximum%2A> properties set by the user.</span></span>  
  
## <a name="largechange-and-smallchange-properties"></a><span data-ttu-id="435f6-117">是它和 SmallChange 属性</span><span class="sxs-lookup"><span data-stu-id="435f6-117">LargeChange and SmallChange Properties</span></span>  
 <span data-ttu-id="435f6-118">当用户按 PAGE UP 或 PAGE DOWN 键或单击中的滚动框中，任何一侧的滚动条轨道<xref:System.Windows.Forms.ScrollBar.Value%2A>根据中设置的值的属性更改<xref:System.Windows.Forms.ScrollBar.LargeChange%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="435f6-118">When the user presses the PAGE UP or PAGE DOWN key or clicks in the scroll bar track on either side of the scroll box, the <xref:System.Windows.Forms.ScrollBar.Value%2A> property changes according to the value set in the <xref:System.Windows.Forms.ScrollBar.LargeChange%2A> property.</span></span>  
  
 <span data-ttu-id="435f6-119">当用户按某个箭头键或单击滚动条按钮时，之一<xref:System.Windows.Forms.ScrollBar.Value%2A>根据中设置的值的属性更改<xref:System.Windows.Forms.ScrollBar.SmallChange%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="435f6-119">When the user presses one of the arrow keys or clicks one of the scroll bar buttons, the <xref:System.Windows.Forms.ScrollBar.Value%2A> property changes according to the value set in the <xref:System.Windows.Forms.ScrollBar.SmallChange%2A> property.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="435f6-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="435f6-120">See Also</span></span>  
 <xref:System.Windows.Forms.HScrollBar>  
 <xref:System.Windows.Forms.VScrollBar>  
 [<span data-ttu-id="435f6-121">用于.NET Framework 2.0 向 Windows 窗体的添加件</span><span class="sxs-lookup"><span data-stu-id="435f6-121">Additions to Windows Forms for the .NET Framework 2.0</span></span>](http://msdn.microsoft.com/library/c61a923d-3d6a-4c8c-820c-e94c83f3f9a8)  
 [<span data-ttu-id="435f6-122">在 Windows 窗体上使用的控件</span><span class="sxs-lookup"><span data-stu-id="435f6-122">Controls to Use on Windows Forms</span></span>](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)
