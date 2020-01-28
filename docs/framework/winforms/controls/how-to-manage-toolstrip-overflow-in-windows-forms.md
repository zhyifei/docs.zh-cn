---
title: 如何：管理 ToolStrip 溢出
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
ms.openlocfilehash: 52cc02e626bee2d2457355028ecddc17e462d8fa
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76736144"
---
# <a name="how-to-manage-toolstrip-overflow-in-windows-forms"></a><span data-ttu-id="39d8a-102">如何：在 Windows 窗体中管理 ToolStrip 溢出</span><span class="sxs-lookup"><span data-stu-id="39d8a-102">How to: Manage ToolStrip Overflow in Windows Forms</span></span>

<span data-ttu-id="39d8a-103">如果 <xref:System.Windows.Forms.ToolStrip> 控件中的所有项都不适合于分配的空间，则可以对 <xref:System.Windows.Forms.ToolStrip> 启用溢出功能，并确定特定 <xref:System.Windows.Forms.ToolStripItem>的溢出行为。</span><span class="sxs-lookup"><span data-stu-id="39d8a-103">When all the items on a <xref:System.Windows.Forms.ToolStrip> control do not fit in the allotted space, you can enable overflow functionality on the <xref:System.Windows.Forms.ToolStrip> and determine the overflow behavior of specific <xref:System.Windows.Forms.ToolStripItem>s.</span></span>

<span data-ttu-id="39d8a-104">如果添加的 <xref:System.Windows.Forms.ToolStripItem>需要的空间超过了给定窗体的当前大小所分配到的 <xref:System.Windows.Forms.ToolStrip>，则 <xref:System.Windows.Forms.ToolStripOverflowButton> 会自动显示在 <xref:System.Windows.Forms.ToolStrip>上。</span><span class="sxs-lookup"><span data-stu-id="39d8a-104">When you add <xref:System.Windows.Forms.ToolStripItem>s that require more space than is allotted to the <xref:System.Windows.Forms.ToolStrip> given the form's current size, a <xref:System.Windows.Forms.ToolStripOverflowButton> automatically appears on the <xref:System.Windows.Forms.ToolStrip>.</span></span> <span data-ttu-id="39d8a-105"><xref:System.Windows.Forms.ToolStripOverflowButton> 随即出现，启用溢出的项将移至下拉溢出菜单。</span><span class="sxs-lookup"><span data-stu-id="39d8a-105">The <xref:System.Windows.Forms.ToolStripOverflowButton> appears, and overflow-enabled items are moved into the drop-down overflow menu.</span></span> <span data-ttu-id="39d8a-106">这使你可以自定义 <xref:System.Windows.Forms.ToolStrip> 项如何正确调整到不同的窗体大小并设置其优先级。</span><span class="sxs-lookup"><span data-stu-id="39d8a-106">This allows you to customize and prioritize how your <xref:System.Windows.Forms.ToolStrip> items properly adjust to different form sizes.</span></span> <span data-ttu-id="39d8a-107">还可以通过使用 "<xref:System.Windows.Forms.ToolStripItem.Placement%2A>" 和 "<xref:System.Windows.Forms.ToolStripOverflow.DisplayedItems%2A?displayProperty=nameWithType> 属性" 和 "<xref:System.Windows.Forms.ToolStrip.LayoutCompleted>" 事件，更改项目在溢出时的外观。</span><span class="sxs-lookup"><span data-stu-id="39d8a-107">You can also change the appearance of your items when they fall into the overflow by using the <xref:System.Windows.Forms.ToolStripItem.Placement%2A> and <xref:System.Windows.Forms.ToolStripOverflow.DisplayedItems%2A?displayProperty=nameWithType> properties and the <xref:System.Windows.Forms.ToolStrip.LayoutCompleted> event.</span></span> <span data-ttu-id="39d8a-108">如果您在设计时或运行时放大窗体，则主 <xref:System.Windows.Forms.ToolStrip> 上可以显示更多 <xref:System.Windows.Forms.ToolStripItem>，<xref:System.Windows.Forms.ToolStripOverflowButton> 即使您减小了窗体的大小，也可能消失。</span><span class="sxs-lookup"><span data-stu-id="39d8a-108">If you enlarge the form at either design time or run time, more <xref:System.Windows.Forms.ToolStripItem>s can be displayed on the main <xref:System.Windows.Forms.ToolStrip> and the <xref:System.Windows.Forms.ToolStripOverflowButton> might even disappear until you decrease the size of the form.</span></span>

## <a name="to-enable-overflow-on-a-toolstrip-control"></a><span data-ttu-id="39d8a-109">对 ToolStrip 控件启用溢出</span><span class="sxs-lookup"><span data-stu-id="39d8a-109">To enable overflow on a ToolStrip control</span></span>

- <span data-ttu-id="39d8a-110">确保 <xref:System.Windows.Forms.ToolStrip><xref:System.Windows.Forms.ToolStrip.CanOverflow%2A> 属性未设置为 `false`。</span><span class="sxs-lookup"><span data-stu-id="39d8a-110">Ensure that the <xref:System.Windows.Forms.ToolStrip.CanOverflow%2A> property is not set to `false` for the <xref:System.Windows.Forms.ToolStrip>.</span></span> <span data-ttu-id="39d8a-111">默认值为 `True`。</span><span class="sxs-lookup"><span data-stu-id="39d8a-111">The default is `True`.</span></span>

     <span data-ttu-id="39d8a-112">当 <xref:System.Windows.Forms.ToolStrip.CanOverflow%2A> 为 `True` （默认值）时，当 <xref:System.Windows.Forms.ToolStripItem> 的内容超出水平 <xref:System.Windows.Forms.ToolStrip> 的宽度或垂直 <xref:System.Windows.Forms.ToolStrip>的高度时，会将 <xref:System.Windows.Forms.ToolStripItem> 发送到下拉溢出菜单。</span><span class="sxs-lookup"><span data-stu-id="39d8a-112">When <xref:System.Windows.Forms.ToolStrip.CanOverflow%2A> is `True` (the default), a <xref:System.Windows.Forms.ToolStripItem> is sent to the drop-down overflow menu when the content of the <xref:System.Windows.Forms.ToolStripItem> exceeds the width of a horizontal <xref:System.Windows.Forms.ToolStrip> or the height of a vertical <xref:System.Windows.Forms.ToolStrip>.</span></span>

## <a name="to-specify-overflow-behavior-of-a-specific-toolstripitem"></a><span data-ttu-id="39d8a-113">指定特定 ToolStripItem 的溢出行为</span><span class="sxs-lookup"><span data-stu-id="39d8a-113">To specify overflow behavior of a specific ToolStripItem</span></span>

- <span data-ttu-id="39d8a-114">将 <xref:System.Windows.Forms.ToolStripItem> 的 <xref:System.Windows.Forms.ToolStripItem.Overflow%2A> 属性设置为所需的值。</span><span class="sxs-lookup"><span data-stu-id="39d8a-114">Set the <xref:System.Windows.Forms.ToolStripItem.Overflow%2A> property of the <xref:System.Windows.Forms.ToolStripItem> to the desired value.</span></span> <span data-ttu-id="39d8a-115">可能 `Always`、`Never`和 `AsNeeded`。</span><span class="sxs-lookup"><span data-stu-id="39d8a-115">The possibilities are `Always`, `Never`, and `AsNeeded`.</span></span> <span data-ttu-id="39d8a-116">默认值为 `AsNeeded`。</span><span class="sxs-lookup"><span data-stu-id="39d8a-116">The default is `AsNeeded`.</span></span>

    ```vb
    toolStripTextBox1.Overflow = _
    System.Windows.Forms.ToolStripItemOverflow.Never
    ```

    ```csharp
    toolStripTextBox1.Overflow = _
    System.Windows.Forms.ToolStripItemOverflow.Never;
    ```

## <a name="see-also"></a><span data-ttu-id="39d8a-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="39d8a-117">See also</span></span>

- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.ToolStripOverflowButton>
- <xref:System.Windows.Forms.ToolStripItem.Overflow%2A>
- <xref:System.Windows.Forms.ToolStrip.CanOverflow%2A>
- [<span data-ttu-id="39d8a-118">ToolStrip 控件概述</span><span class="sxs-lookup"><span data-stu-id="39d8a-118">ToolStrip Control Overview</span></span>](toolstrip-control-overview-windows-forms.md)
- [<span data-ttu-id="39d8a-119">ToolStrip 控件体系结构</span><span class="sxs-lookup"><span data-stu-id="39d8a-119">ToolStrip Control Architecture</span></span>](toolstrip-control-architecture.md)
- [<span data-ttu-id="39d8a-120">ToolStrip 技术摘要</span><span class="sxs-lookup"><span data-stu-id="39d8a-120">ToolStrip Technology Summary</span></span>](toolstrip-technology-summary.md)
