---
title: 如何：在 Windows 窗体中管理 ToolStrip 溢出
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ToolStrip control [Windows Forms], managing overflow
- toolbars [Windows Forms], managing overflow
- examples [Windows Forms], toolbars
- CanOverflow property
ms.assetid: fa10e0ad-4cbf-4c0d-9082-359c2f855d4e
ms.openlocfilehash: 32bbc06320f0dc7f096a4b9021bebfbefedaf8f7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-manage-toolstrip-overflow-in-windows-forms"></a><span data-ttu-id="7587e-102">如何：在 Windows 窗体中管理 ToolStrip 溢出</span><span class="sxs-lookup"><span data-stu-id="7587e-102">How to: Manage ToolStrip Overflow in Windows Forms</span></span>
<span data-ttu-id="7587e-103">当上的所有项<xref:System.Windows.Forms.ToolStrip>控件不适合在分配的空间，则可以在启用溢出功能<xref:System.Windows.Forms.ToolStrip>并确定特定的溢出行为<xref:System.Windows.Forms.ToolStripItem>s。</span><span class="sxs-lookup"><span data-stu-id="7587e-103">When all the items on a <xref:System.Windows.Forms.ToolStrip> control do not fit in the allotted space, you can enable overflow functionality on the <xref:System.Windows.Forms.ToolStrip> and determine the overflow behavior of specific <xref:System.Windows.Forms.ToolStripItem>s.</span></span>  
  
 <span data-ttu-id="7587e-104">当你将添加<xref:System.Windows.Forms.ToolStripItem>需要更多的空间比已分配到的 s<xref:System.Windows.Forms.ToolStrip>给定窗体的当前大小，<xref:System.Windows.Forms.ToolStripOverflowButton>会自动出现在<xref:System.Windows.Forms.ToolStrip>。</span><span class="sxs-lookup"><span data-stu-id="7587e-104">When you add <xref:System.Windows.Forms.ToolStripItem>s that require more space than is allotted to the <xref:System.Windows.Forms.ToolStrip> given the form's current size, a <xref:System.Windows.Forms.ToolStripOverflowButton> automatically appears on the <xref:System.Windows.Forms.ToolStrip>.</span></span> <span data-ttu-id="7587e-105"><xref:System.Windows.Forms.ToolStripOverflowButton>出现，并启用了溢出的项移到下拉列表溢出菜单。</span><span class="sxs-lookup"><span data-stu-id="7587e-105">The <xref:System.Windows.Forms.ToolStripOverflowButton> appears, and overflow-enabled items are moved into the drop-down overflow menu.</span></span> <span data-ttu-id="7587e-106">这使您可以自定义并划分其优先级如何你<xref:System.Windows.Forms.ToolStrip>项未能正确地调整到不同的窗体大小。</span><span class="sxs-lookup"><span data-stu-id="7587e-106">This allows you to customize and prioritize how your <xref:System.Windows.Forms.ToolStrip> items properly adjust to different form sizes.</span></span> <span data-ttu-id="7587e-107">你还可以更改你的项的外观，当它们发生溢出时，通过使用<xref:System.Windows.Forms.ToolStripItem.Placement%2A>和<xref:System.Windows.Forms.ToolStripOverflow.DisplayedItems%2A?displayProperty=nameWithType>属性和<xref:System.Windows.Forms.ToolStrip.LayoutCompleted>事件。</span><span class="sxs-lookup"><span data-stu-id="7587e-107">You can also change the appearance of your items when they fall into the overflow by using the <xref:System.Windows.Forms.ToolStripItem.Placement%2A> and <xref:System.Windows.Forms.ToolStripOverflow.DisplayedItems%2A?displayProperty=nameWithType> properties and the <xref:System.Windows.Forms.ToolStrip.LayoutCompleted> event.</span></span> <span data-ttu-id="7587e-108">如果你扩大窗体在设计时或运行的时，更<xref:System.Windows.Forms.ToolStripItem>s 可以显示在主<xref:System.Windows.Forms.ToolStrip>和<xref:System.Windows.Forms.ToolStripOverflowButton>甚至可能会消失，直到减小窗体的大小。</span><span class="sxs-lookup"><span data-stu-id="7587e-108">If you enlarge the form at either design time or run time, more <xref:System.Windows.Forms.ToolStripItem>s can be displayed on the main <xref:System.Windows.Forms.ToolStrip> and the <xref:System.Windows.Forms.ToolStripOverflowButton> might even disappear until you decrease the size of the form.</span></span>  
  
### <a name="to-enable-overflow-on-a-toolstrip-control"></a><span data-ttu-id="7587e-109">若要启用溢出的 ToolStrip 控件</span><span class="sxs-lookup"><span data-stu-id="7587e-109">To enable overflow on a ToolStrip control</span></span>  
  
-   <span data-ttu-id="7587e-110">确保<xref:System.Windows.Forms.ToolStrip.CanOverflow%2A>属性未设置为`false`为<xref:System.Windows.Forms.ToolStrip>。</span><span class="sxs-lookup"><span data-stu-id="7587e-110">Ensure that the <xref:System.Windows.Forms.ToolStrip.CanOverflow%2A> property is not set to `false` for the <xref:System.Windows.Forms.ToolStrip>.</span></span> <span data-ttu-id="7587e-111">默认值为 `True`。</span><span class="sxs-lookup"><span data-stu-id="7587e-111">The default is `True`.</span></span>  
  
     <span data-ttu-id="7587e-112">当<xref:System.Windows.Forms.ToolStrip.CanOverflow%2A>是`True`（默认值）、<xref:System.Windows.Forms.ToolStripItem>发送到下拉列表溢出菜单时的内容<xref:System.Windows.Forms.ToolStripItem>超过的水平宽度<xref:System.Windows.Forms.ToolStrip>或高度的垂直<xref:System.Windows.Forms.ToolStrip>。</span><span class="sxs-lookup"><span data-stu-id="7587e-112">When <xref:System.Windows.Forms.ToolStrip.CanOverflow%2A> is `True` (the default), a <xref:System.Windows.Forms.ToolStripItem> is sent to the drop-down overflow menu when the content of the <xref:System.Windows.Forms.ToolStripItem> exceeds the width of a horizontal <xref:System.Windows.Forms.ToolStrip> or the height of a vertical <xref:System.Windows.Forms.ToolStrip>.</span></span>  
  
### <a name="to-specify-overflow-behavior-of-a-specific-toolstripitem"></a><span data-ttu-id="7587e-113">若要指定特定 ToolStripItem 溢出行为</span><span class="sxs-lookup"><span data-stu-id="7587e-113">To specify overflow behavior of a specific ToolStripItem</span></span>  
  
-   <span data-ttu-id="7587e-114">设置<xref:System.Windows.Forms.ToolStripItem.Overflow%2A>属性<xref:System.Windows.Forms.ToolStripItem>到所需的值。</span><span class="sxs-lookup"><span data-stu-id="7587e-114">Set the <xref:System.Windows.Forms.ToolStripItem.Overflow%2A> property of the <xref:System.Windows.Forms.ToolStripItem> to the desired value.</span></span> <span data-ttu-id="7587e-115">可能的匹配项是`Always`， `Never`，和`AsNeeded`。</span><span class="sxs-lookup"><span data-stu-id="7587e-115">The possibilities are `Always`, `Never`, and `AsNeeded`.</span></span> <span data-ttu-id="7587e-116">Defaultis `AsNeeded`。</span><span class="sxs-lookup"><span data-stu-id="7587e-116">The defaultis `AsNeeded`.</span></span>  
  
    ```vb  
    toolStripTextBox1.Overflow = _  
    System.Windows.Forms.ToolStripItemOverflow.Never  
    ```  
  
    ```csharp  
    toolStripTextBox1.Overflow = _  
    System.Windows.Forms.ToolStripItemOverflow.Never;  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="7587e-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="7587e-117">See Also</span></span>  
 <xref:System.Windows.Forms.ToolStrip>  
 <xref:System.Windows.Forms.ToolStripOverflowButton>  
 <xref:System.Windows.Forms.ToolStripItem.Overflow%2A>  
 <xref:System.Windows.Forms.ToolStrip.CanOverflow%2A>  
 [<span data-ttu-id="7587e-118">ToolStrip 控件概述</span><span class="sxs-lookup"><span data-stu-id="7587e-118">ToolStrip Control Overview</span></span>](../../../../docs/framework/winforms/controls/toolstrip-control-overview-windows-forms.md)  
 [<span data-ttu-id="7587e-119">ToolStrip 控件体系结构</span><span class="sxs-lookup"><span data-stu-id="7587e-119">ToolStrip Control Architecture</span></span>](../../../../docs/framework/winforms/controls/toolstrip-control-architecture.md)  
 [<span data-ttu-id="7587e-120">ToolStrip 技术摘要</span><span class="sxs-lookup"><span data-stu-id="7587e-120">ToolStrip Technology Summary</span></span>](../../../../docs/framework/winforms/controls/toolstrip-technology-summary.md)
