---
title: FlowLayoutPanel 控件概述
ms.date: 03/30/2017
f1_keywords:
- FlowLayoutPanel
helpviewer_keywords:
- forms [Windows Forms], dynamic layout
- layout [Windows Forms], dynamic
- Windows Forms, dynamic layout
- FlowLayoutPanel control [Windows Forms], about FlowLayoutPanel control
ms.assetid: 3883e024-f5a0-456d-9c27-b4dfa1cc9045
ms.openlocfilehash: 260146cd901fe2b80a73c01060ccd55958cd169e
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59203036"
---
# <a name="flowlayoutpanel-control-overview"></a><span data-ttu-id="5d367-102">FlowLayoutPanel 控件概述</span><span class="sxs-lookup"><span data-stu-id="5d367-102">FlowLayoutPanel Control Overview</span></span>
<span data-ttu-id="5d367-103"><xref:System.Windows.Forms.FlowLayoutPanel> 控件沿水平或纵排方向排列其内容。</span><span class="sxs-lookup"><span data-stu-id="5d367-103">The <xref:System.Windows.Forms.FlowLayoutPanel> control arranges its contents in a horizontal or vertical flow direction.</span></span> <span data-ttu-id="5d367-104">可从一行到下一行，或从一列到下一列来进行控件内容换行。</span><span class="sxs-lookup"><span data-stu-id="5d367-104">You can wrap the control's contents from one row to the next, or from one column to the next.</span></span> <span data-ttu-id="5d367-105">或者，可以剪切其内容，而非进行换行。</span><span class="sxs-lookup"><span data-stu-id="5d367-105">Alternately, you can clip instead of wrap its contents.</span></span>  
  
 <span data-ttu-id="5d367-106">可以通过设置 <xref:System.Windows.Forms.FlowLayoutPanel.FlowDirection%2A> 属性的值来指定排列方向。</span><span class="sxs-lookup"><span data-stu-id="5d367-106">You can specify the flow direction by setting the value of the <xref:System.Windows.Forms.FlowLayoutPanel.FlowDirection%2A> property.</span></span> <span data-ttu-id="5d367-107"><xref:System.Windows.Forms.FlowLayoutPanel> 控件在从右到左 (RTL) 布局中正确地反转其排列方向。</span><span class="sxs-lookup"><span data-stu-id="5d367-107">The <xref:System.Windows.Forms.FlowLayoutPanel> control correctly reverses its flow direction in Right-to-Left (RTL) layouts.</span></span> <span data-ttu-id="5d367-108">也可通过设置 <xref:System.Windows.Forms.FlowLayoutPanel.WrapContents%2A> 属性的值来指定是对 <xref:System.Windows.Forms.FlowLayoutPanel> 控件的内容进行换行还是剪切。</span><span class="sxs-lookup"><span data-stu-id="5d367-108">You can also specify whether the <xref:System.Windows.Forms.FlowLayoutPanel> control's contents are wrapped or clipped by setting the value of the <xref:System.Windows.Forms.FlowLayoutPanel.WrapContents%2A> property.</span></span>  
  
 <span data-ttu-id="5d367-109">将 <xref:System.Windows.Forms.Control.AutoSize%2A> 属性设置为 `true` 时，<xref:System.Windows.Forms.FlowLayoutPanel> 控件自动调整根据其内容调整大小。</span><span class="sxs-lookup"><span data-stu-id="5d367-109">The <xref:System.Windows.Forms.FlowLayoutPanel> control automatically sizes to its contents when you set the <xref:System.Windows.Forms.Control.AutoSize%2A> property to `true`.</span></span> <span data-ttu-id="5d367-110">它还提供了**FlowBreak**给其子控件的属性。</span><span class="sxs-lookup"><span data-stu-id="5d367-110">It also provides a **FlowBreak** property to its child controls.</span></span> <span data-ttu-id="5d367-111">将 FlowBreak 属性的值设置为 `true` 导致 <xref:System.Windows.Forms.FlowLayoutPanel> 控件停止按当前排列方向对控件进行布局，并换行到下一行或下一列。</span><span class="sxs-lookup"><span data-stu-id="5d367-111">Setting the value of the FlowBreak property to `true` causes the <xref:System.Windows.Forms.FlowLayoutPanel> control to stop laying out controls in the current flow direction and wrap to the next row or column.</span></span>  
  
 <span data-ttu-id="5d367-112">任何 Windows 窗体控件均可以是 <xref:System.Windows.Forms.FlowLayoutPanel> 控制的子控件，包括 <xref:System.Windows.Forms.FlowLayoutPanel> 的其他实例。</span><span class="sxs-lookup"><span data-stu-id="5d367-112">Any Windows Forms control can be a child of the <xref:System.Windows.Forms.FlowLayoutPanel> control, including other instances of <xref:System.Windows.Forms.FlowLayoutPanel>.</span></span> <span data-ttu-id="5d367-113">使用此功能，可以构造在运行时适应窗体尺寸的复杂布局。</span><span class="sxs-lookup"><span data-stu-id="5d367-113">With this capability, you can construct sophisticated layouts that adapt to your form's dimensions at run time.</span></span>  
  
 <span data-ttu-id="5d367-114">另请参阅[演练：使用 FlowLayoutPanel 的 Windows 窗体上排列控件](walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md)。</span><span class="sxs-lookup"><span data-stu-id="5d367-114">Also see [Walkthrough: Arranging Controls on Windows Forms Using a FlowLayoutPanel](walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5d367-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="5d367-115">See also</span></span>

- <xref:System.Windows.Forms.FlowLayoutPanel.FlowDirection%2A>
- <xref:System.Windows.Forms.TableLayoutPanel>
- [<span data-ttu-id="5d367-116">FlowLayoutPanel 控件</span><span class="sxs-lookup"><span data-stu-id="5d367-116">FlowLayoutPanel Control</span></span>](flowlayoutpanel-control-windows-forms.md)
