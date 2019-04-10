---
title: TrackBar 控件概述（Windows 窗体）
ms.date: 03/30/2017
f1_keywords:
- TrackBar
helpviewer_keywords:
- sliders [Windows Forms], about sliders
- TrackBar control [Windows Forms], about TrackBar control
- slider controls [Windows Forms], about slider controls
ms.assetid: 95910ecb-8a4c-4776-89fa-206c89ed6973
ms.openlocfilehash: 1606db73485944f3dfa8b9c084bffda817520c7c
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59200631"
---
# <a name="trackbar-control-overview-windows-forms"></a><span data-ttu-id="b269a-102">TrackBar 控件概述（Windows 窗体）</span><span class="sxs-lookup"><span data-stu-id="b269a-102">TrackBar Control Overview (Windows Forms)</span></span>
<span data-ttu-id="b269a-103">Windows 窗体<xref:System.Windows.Forms.TrackBar>控件 （有时也称为"滑块"控件） 用于浏览大量的信息或用于直观地调整数字设置。</span><span class="sxs-lookup"><span data-stu-id="b269a-103">The Windows Forms <xref:System.Windows.Forms.TrackBar> control (also sometimes called a "slider" control) is used for navigating through a large amount of information or for visually adjusting a numeric setting.</span></span> <span data-ttu-id="b269a-104"><xref:System.Windows.Forms.TrackBar>控件具有两个部分： thumb，也称为滑块，将和刻度线。</span><span class="sxs-lookup"><span data-stu-id="b269a-104">The <xref:System.Windows.Forms.TrackBar> control has two parts: the thumb, also known as a slider, and the tick marks.</span></span> <span data-ttu-id="b269a-105">滚动块是可调整的一部分。</span><span class="sxs-lookup"><span data-stu-id="b269a-105">The thumb is the part that can be adjusted.</span></span> <span data-ttu-id="b269a-106">其位置对应于<xref:System.Windows.Forms.TrackBar.Value%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="b269a-106">Its position corresponds to the <xref:System.Windows.Forms.TrackBar.Value%2A> property.</span></span> <span data-ttu-id="b269a-107">刻度线是按固定间隔分布的可视指示符。</span><span class="sxs-lookup"><span data-stu-id="b269a-107">The tick marks are visual indicators that are spaced at regular intervals.</span></span> <span data-ttu-id="b269a-108">指定并可以水平或垂直对齐的增量移动跟踪条。</span><span class="sxs-lookup"><span data-stu-id="b269a-108">The trackbar moves in increments that you specify and can be aligned horizontally or vertically.</span></span> <span data-ttu-id="b269a-109">例如，可能会使用跟踪条以控制光标闪烁速率或鼠标的速度的系统。</span><span class="sxs-lookup"><span data-stu-id="b269a-109">For example, you might use the track bar to control the cursor blink rate or mouse speed for a system.</span></span>  
  
## <a name="key-properties"></a><span data-ttu-id="b269a-110">键属性</span><span class="sxs-lookup"><span data-stu-id="b269a-110">Key Properties</span></span>  
 <span data-ttu-id="b269a-111">键属性<xref:System.Windows.Forms.TrackBar>控制是在<xref:System.Windows.Forms.TrackBar.Value%2A>， <xref:System.Windows.Forms.TrackBar.TickFrequency%2A>， <xref:System.Windows.Forms.TrackBar.Minimum%2A>，和<xref:System.Windows.Forms.TrackBar.Maximum%2A>。</span><span class="sxs-lookup"><span data-stu-id="b269a-111">The key properties of the <xref:System.Windows.Forms.TrackBar> control are <xref:System.Windows.Forms.TrackBar.Value%2A>, <xref:System.Windows.Forms.TrackBar.TickFrequency%2A>, <xref:System.Windows.Forms.TrackBar.Minimum%2A>, and <xref:System.Windows.Forms.TrackBar.Maximum%2A>.</span></span> <xref:System.Windows.Forms.TrackBar.TickFrequency%2A> <span data-ttu-id="b269a-112">为刻度间隔。</span><span class="sxs-lookup"><span data-stu-id="b269a-112">is the spacing of the ticks.</span></span> <xref:System.Windows.Forms.TrackBar.Minimum%2A> <span data-ttu-id="b269a-113">和<xref:System.Windows.Forms.TrackBar.Maximum%2A>是可以表示跟踪条的最小和最大值。</span><span class="sxs-lookup"><span data-stu-id="b269a-113">and <xref:System.Windows.Forms.TrackBar.Maximum%2A> are the smallest and largest values that can be represented on the track bar.</span></span>  
  
 <span data-ttu-id="b269a-114">其他两个重要属性是<xref:System.Windows.Forms.TrackBar.SmallChange%2A>和<xref:System.Windows.Forms.TrackBar.LargeChange%2A>。</span><span class="sxs-lookup"><span data-stu-id="b269a-114">Two other important properties are <xref:System.Windows.Forms.TrackBar.SmallChange%2A> and <xref:System.Windows.Forms.TrackBar.LargeChange%2A>.</span></span> <span data-ttu-id="b269a-115">值<xref:System.Windows.Forms.TrackBar.SmallChange%2A>属性是滚动块移动到具有左或向右箭头键按下的响应中的位置数。</span><span class="sxs-lookup"><span data-stu-id="b269a-115">The value of the <xref:System.Windows.Forms.TrackBar.SmallChange%2A> property is the number of positions the thumb moves in response to having the LEFT or RIGHT ARROW key pressed.</span></span> <span data-ttu-id="b269a-116">值<xref:System.Windows.Forms.TrackBar.LargeChange%2A>属性是 thumb 响应具有 PAGE UP 或 PAGE DOWN 键按下，移动或以响应鼠标单击跟踪条上滚动块的任何一侧上的位置数。</span><span class="sxs-lookup"><span data-stu-id="b269a-116">The value of the <xref:System.Windows.Forms.TrackBar.LargeChange%2A> property is the number of positions the thumb moves in response to having the PAGE UP or PAGE DOWN key pressed, or in response to mouse clicks on the track bar on either side of the thumb.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b269a-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="b269a-117">See also</span></span>

- <xref:System.Windows.Forms.TrackBar>
- [<span data-ttu-id="b269a-118">TrackBar 控件</span><span class="sxs-lookup"><span data-stu-id="b269a-118">TrackBar Control</span></span>](trackbar-control-windows-forms.md)
