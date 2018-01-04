---
title: "TrackBar 控件概述（Windows 窗体）"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: TrackBar
helpviewer_keywords:
- sliders [Windows Forms], about sliders
- TrackBar control [Windows Forms], about TrackBar control
- slider controls [Windows Forms], about slider controls
ms.assetid: 95910ecb-8a4c-4776-89fa-206c89ed6973
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e62fc49a8a08c79138df080246b99b6fe891162e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="trackbar-control-overview-windows-forms"></a><span data-ttu-id="32ef2-102">TrackBar 控件概述（Windows 窗体）</span><span class="sxs-lookup"><span data-stu-id="32ef2-102">TrackBar Control Overview (Windows Forms)</span></span>
<span data-ttu-id="32ef2-103">Windows 窗体<xref:System.Windows.Forms.TrackBar>（有时也称为"滑块"控件） 的控件用于浏览大量的信息或用于直观地调整数值设置。</span><span class="sxs-lookup"><span data-stu-id="32ef2-103">The Windows Forms <xref:System.Windows.Forms.TrackBar> control (also sometimes called a "slider" control) is used for navigating through a large amount of information or for visually adjusting a numeric setting.</span></span> <span data-ttu-id="32ef2-104"><xref:System.Windows.Forms.TrackBar>控件具有两个部分： 滚动块，也称为滑块和刻度线。</span><span class="sxs-lookup"><span data-stu-id="32ef2-104">The <xref:System.Windows.Forms.TrackBar> control has two parts: the thumb, also known as a slider, and the tick marks.</span></span> <span data-ttu-id="32ef2-105">滚动块是可以进行调整的一部分。</span><span class="sxs-lookup"><span data-stu-id="32ef2-105">The thumb is the part that can be adjusted.</span></span> <span data-ttu-id="32ef2-106">其位置对应于<xref:System.Windows.Forms.TrackBar.Value%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="32ef2-106">Its position corresponds to the <xref:System.Windows.Forms.TrackBar.Value%2A> property.</span></span> <span data-ttu-id="32ef2-107">刻度线是定期间距的可视指示器。</span><span class="sxs-lookup"><span data-stu-id="32ef2-107">The tick marks are visual indicators that are spaced at regular intervals.</span></span> <span data-ttu-id="32ef2-108">Trackbar 指定和可以水平或垂直对齐的增量移动。</span><span class="sxs-lookup"><span data-stu-id="32ef2-108">The trackbar moves in increments that you specify and can be aligned horizontally or vertically.</span></span> <span data-ttu-id="32ef2-109">例如，可能会使用跟踪条以控制系统的光标闪烁速率或鼠标速度。</span><span class="sxs-lookup"><span data-stu-id="32ef2-109">For example, you might use the track bar to control the cursor blink rate or mouse speed for a system.</span></span>  
  
## <a name="key-properties"></a><span data-ttu-id="32ef2-110">键属性</span><span class="sxs-lookup"><span data-stu-id="32ef2-110">Key Properties</span></span>  
 <span data-ttu-id="32ef2-111">键属性<xref:System.Windows.Forms.TrackBar>控件<xref:System.Windows.Forms.TrackBar.Value%2A>， <xref:System.Windows.Forms.TrackBar.TickFrequency%2A>， <xref:System.Windows.Forms.TrackBar.Minimum%2A>，和<xref:System.Windows.Forms.TrackBar.Maximum%2A>。</span><span class="sxs-lookup"><span data-stu-id="32ef2-111">The key properties of the <xref:System.Windows.Forms.TrackBar> control are <xref:System.Windows.Forms.TrackBar.Value%2A>, <xref:System.Windows.Forms.TrackBar.TickFrequency%2A>, <xref:System.Windows.Forms.TrackBar.Minimum%2A>, and <xref:System.Windows.Forms.TrackBar.Maximum%2A>.</span></span> <span data-ttu-id="32ef2-112"><xref:System.Windows.Forms.TrackBar.TickFrequency%2A>是的刻度的间距。</span><span class="sxs-lookup"><span data-stu-id="32ef2-112"><xref:System.Windows.Forms.TrackBar.TickFrequency%2A> is the spacing of the ticks.</span></span> <span data-ttu-id="32ef2-113"><xref:System.Windows.Forms.TrackBar.Minimum%2A>和<xref:System.Windows.Forms.TrackBar.Maximum%2A>是可以表示跟踪条的最小和最大值。</span><span class="sxs-lookup"><span data-stu-id="32ef2-113"><xref:System.Windows.Forms.TrackBar.Minimum%2A> and <xref:System.Windows.Forms.TrackBar.Maximum%2A> are the smallest and largest values that can be represented on the track bar.</span></span>  
  
 <span data-ttu-id="32ef2-114">其他两个重要属性都是<xref:System.Windows.Forms.TrackBar.SmallChange%2A>和<xref:System.Windows.Forms.TrackBar.LargeChange%2A>。</span><span class="sxs-lookup"><span data-stu-id="32ef2-114">Two other important properties are <xref:System.Windows.Forms.TrackBar.SmallChange%2A> and <xref:System.Windows.Forms.TrackBar.LargeChange%2A>.</span></span> <span data-ttu-id="32ef2-115">值<xref:System.Windows.Forms.TrackBar.SmallChange%2A>属性是滚动块移动到具有左或向右箭头键按下的响应中的位置数。</span><span class="sxs-lookup"><span data-stu-id="32ef2-115">The value of the <xref:System.Windows.Forms.TrackBar.SmallChange%2A> property is the number of positions the thumb moves in response to having the LEFT or RIGHT ARROW key pressed.</span></span> <span data-ttu-id="32ef2-116">值<xref:System.Windows.Forms.TrackBar.LargeChange%2A>属性是的滚动块移动到具有 PAGE UP 或 PAGE DOWN 键按下的响应中或以响应鼠标单击跟踪条上滚动块的任何一侧上的位置数。</span><span class="sxs-lookup"><span data-stu-id="32ef2-116">The value of the <xref:System.Windows.Forms.TrackBar.LargeChange%2A> property is the number of positions the thumb moves in response to having the PAGE UP or PAGE DOWN key pressed, or in response to mouse clicks on the track bar on either side of the thumb.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="32ef2-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="32ef2-117">See Also</span></span>  
 <xref:System.Windows.Forms.TrackBar>  
 [<span data-ttu-id="32ef2-118">TrackBar 控件</span><span class="sxs-lookup"><span data-stu-id="32ef2-118">TrackBar Control</span></span>](../../../../docs/framework/winforms/controls/trackbar-control-windows-forms.md)
