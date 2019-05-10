---
title: 如何：在设计时将控件与窗体边缘对齐
ms.date: 03/30/2017
helpviewer_keywords:
- custom controls [Windows Forms], docking using designer
- Dock property [Windows Forms], aligning controls (using designer)
ms.assetid: 51f08998-5e3b-4330-be58-a4edd0eb60f4
ms.openlocfilehash: b08e01eb9adb984a32a8fc435cf1f3b93b159a14
ms.sourcegitcommit: 0d0a6e96737dfe24d3257b7c94f25d9500f383ea
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65210370"
---
# <a name="how-to-align-a-control-to-the-edges-of-forms-at-design-time"></a><span data-ttu-id="ae75b-102">如何：在设计时将控件与窗体边缘对齐</span><span class="sxs-lookup"><span data-stu-id="ae75b-102">How to: Align a Control to the Edges of Forms at Design Time</span></span>

<span data-ttu-id="ae75b-103">可以使控件与窗体的边缘对齐的值设置<xref:System.Windows.Forms.Control.Dock%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="ae75b-103">You can make your control align to the edge of your forms by setting the value of the <xref:System.Windows.Forms.Control.Dock%2A> property.</span></span> <span data-ttu-id="ae75b-104">此属性指定控件在窗体中的驻留位置。</span><span class="sxs-lookup"><span data-stu-id="ae75b-104">This property designates where your control resides in the form.</span></span> <span data-ttu-id="ae75b-105">可以将 <xref:System.Windows.Forms.Control.Dock%2A> 属性设置为下列值：</span><span class="sxs-lookup"><span data-stu-id="ae75b-105">The <xref:System.Windows.Forms.Control.Dock%2A> property can be set to the following values:</span></span>

|<span data-ttu-id="ae75b-106">设置</span><span class="sxs-lookup"><span data-stu-id="ae75b-106">Setting</span></span>|<span data-ttu-id="ae75b-107">控件上的效果</span><span class="sxs-lookup"><span data-stu-id="ae75b-107">Effect on your control</span></span>|
|-------------|----------------------------|
|<xref:System.Windows.Forms.DockStyle.Bottom>|<span data-ttu-id="ae75b-108">停靠到窗体底部。</span><span class="sxs-lookup"><span data-stu-id="ae75b-108">Docks to the bottom of the form.</span></span>|
|<xref:System.Windows.Forms.DockStyle.Fill>|<span data-ttu-id="ae75b-109">占据窗体中的所有剩余空间。</span><span class="sxs-lookup"><span data-stu-id="ae75b-109">Fills all remaining space in the form.</span></span>|
|<xref:System.Windows.Forms.DockStyle.Left>|<span data-ttu-id="ae75b-110">停靠到窗体的左侧。</span><span class="sxs-lookup"><span data-stu-id="ae75b-110">Docks to the left side of the form.</span></span>|
|<xref:System.Windows.Forms.DockStyle.None>|<span data-ttu-id="ae75b-111">执行停靠任何位置，而是显示在指定的位置及其<xref:System.Windows.Forms.Control.Location%2A>。</span><span class="sxs-lookup"><span data-stu-id="ae75b-111">Does not dock anywhere, and it appears at the location specified by its <xref:System.Windows.Forms.Control.Location%2A>.</span></span>|
|<xref:System.Windows.Forms.DockStyle.Right>|<span data-ttu-id="ae75b-112">停靠到窗体的右侧。</span><span class="sxs-lookup"><span data-stu-id="ae75b-112">Docks to the right side of the form.</span></span>|
|<xref:System.Windows.Forms.DockStyle.Top>|<span data-ttu-id="ae75b-113">停靠到窗体的顶部。</span><span class="sxs-lookup"><span data-stu-id="ae75b-113">Docks to the top of the form.</span></span>|

<span data-ttu-id="ae75b-114">此外可以在代码中设置这些值。</span><span class="sxs-lookup"><span data-stu-id="ae75b-114">These values can also be set in code.</span></span> <span data-ttu-id="ae75b-115">有关详细信息，请参阅[如何：将控件与窗体边缘对齐](how-to-align-a-control-to-the-edges-of-forms.md)。</span><span class="sxs-lookup"><span data-stu-id="ae75b-115">For more information, see [How to: Align a Control to the Edges of Forms](how-to-align-a-control-to-the-edges-of-forms.md).</span></span>

## <a name="set-the-dock-property-for-your-control-at-design-time"></a><span data-ttu-id="ae75b-116">在设计时设置控件的 Dock 属性</span><span class="sxs-lookup"><span data-stu-id="ae75b-116">Set the Dock property for your control at design time</span></span>

1. <span data-ttu-id="ae75b-117">在 Visual Studio 中的 Windows 窗体设计器，选择控件。</span><span class="sxs-lookup"><span data-stu-id="ae75b-117">In the Windows Forms Designer in Visual Studio, select your control.</span></span>

2. <span data-ttu-id="ae75b-118">在中**属性**窗口中，单击下拉列表框旁边的<xref:System.Windows.Forms.Control.Dock%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="ae75b-118">In the **Properties** window, click the drop-down box next to the <xref:System.Windows.Forms.Control.Dock%2A> property.</span></span>

     <span data-ttu-id="ae75b-119">表示六种可能的图形界面<xref:System.Windows.Forms.Control.Dock%2A>显示设置。</span><span class="sxs-lookup"><span data-stu-id="ae75b-119">A graphical interface representing the six possible <xref:System.Windows.Forms.Control.Dock%2A> settings is displayed.</span></span>

3. <span data-ttu-id="ae75b-120">选择合适的设置。</span><span class="sxs-lookup"><span data-stu-id="ae75b-120">Choose the appropriate setting.</span></span>

4. <span data-ttu-id="ae75b-121">您的控件现在将停靠的设置指定的方式。</span><span class="sxs-lookup"><span data-stu-id="ae75b-121">Your control will now dock in the manner specified by the setting.</span></span>

## <a name="see-also"></a><span data-ttu-id="ae75b-122">请参阅</span><span class="sxs-lookup"><span data-stu-id="ae75b-122">See also</span></span>

- <xref:System.Windows.Forms.Control.Dock%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.Control.Anchor%2A?displayProperty=nameWithType>
- [<span data-ttu-id="ae75b-123">如何：将控件与窗体边缘对齐</span><span class="sxs-lookup"><span data-stu-id="ae75b-123">How to: Align a Control to the Edges of Forms</span></span>](how-to-align-a-control-to-the-edges-of-forms.md)
- [<span data-ttu-id="ae75b-124">演练：使用对齐线的 Windows 窗体上排列控件</span><span class="sxs-lookup"><span data-stu-id="ae75b-124">Walkthrough: Arranging Controls on Windows Forms Using Snaplines</span></span>](walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)
- [<span data-ttu-id="ae75b-125">如何：在 Windows 窗体上定位控件</span><span class="sxs-lookup"><span data-stu-id="ae75b-125">How to: Anchor Controls on Windows Forms</span></span>](how-to-anchor-controls-on-windows-forms.md)
- [<span data-ttu-id="ae75b-126">如何：锚定和停靠在 TableLayoutPanel 控件中的子控件</span><span class="sxs-lookup"><span data-stu-id="ae75b-126">How to: Anchor and Dock Child Controls in a TableLayoutPanel Control</span></span>](how-to-anchor-and-dock-child-controls-in-a-tablelayoutpanel-control.md)
- [<span data-ttu-id="ae75b-127">如何：锚定和停靠子控件在 FlowLayoutPanel 控件中</span><span class="sxs-lookup"><span data-stu-id="ae75b-127">How to: Anchor and Dock Child Controls in a FlowLayoutPanel Control</span></span>](how-to-anchor-and-dock-child-controls-in-a-flowlayoutpanel-control.md)
- [<span data-ttu-id="ae75b-128">演练：使用 TableLayoutPanel 的 Windows 窗体上排列控件</span><span class="sxs-lookup"><span data-stu-id="ae75b-128">Walkthrough: Arranging Controls on Windows Forms Using a TableLayoutPanel</span></span>](walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)
- [<span data-ttu-id="ae75b-129">演练：使用 FlowLayoutPanel 的 Windows 窗体上排列控件</span><span class="sxs-lookup"><span data-stu-id="ae75b-129">Walkthrough: Arranging Controls on Windows Forms Using a FlowLayoutPanel</span></span>](walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md)
- [<span data-ttu-id="ae75b-130">设计时开发 Windows 窗体控件</span><span class="sxs-lookup"><span data-stu-id="ae75b-130">Developing Windows Forms Controls at Design Time</span></span>](developing-windows-forms-controls-at-design-time.md)
