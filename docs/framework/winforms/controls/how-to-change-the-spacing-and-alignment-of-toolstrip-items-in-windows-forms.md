---
title: 如何：更改 ToolStrip 项的间距和对齐方式
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ToolStrip control [Windows Forms], aligning items
- examples [Windows Forms], toolbars
- toolbars [Windows Forms], aligning items
ms.assetid: cd483466-0f49-43df-addf-e2b5fcd64027
ms.openlocfilehash: 805fbac5fe33071006f29692d503e5c57eacd765
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746559"
---
# <a name="how-to-change-the-spacing-and-alignment-of-toolstrip-items-in-windows-forms"></a><span data-ttu-id="c530b-102">如何：在 Windows 窗体中更改 ToolStrip 项的间距和对齐方式</span><span class="sxs-lookup"><span data-stu-id="c530b-102">How to: Change the Spacing and Alignment of ToolStrip Items in Windows Forms</span></span>
<span data-ttu-id="c530b-103"><xref:System.Windows.Forms.ToolStrip> 控件完全支持布局功能，如调整大小、<xref:System.Windows.Forms.ToolStripItem> 控件之间的间距、<xref:System.Windows.Forms.ToolStrip>上的控件排列以及控件与 <xref:System.Windows.Forms.ToolStrip>的间距。</span><span class="sxs-lookup"><span data-stu-id="c530b-103">The <xref:System.Windows.Forms.ToolStrip> control fully supports layout features such as sizing, the spacing of <xref:System.Windows.Forms.ToolStripItem> controls relative to each other, the arrangement of controls on the <xref:System.Windows.Forms.ToolStrip>, and the spacing of controls relative to the <xref:System.Windows.Forms.ToolStrip>.</span></span>  
  
 <span data-ttu-id="c530b-104">由于 <xref:System.Windows.Forms.ToolStripItem.AutoSize%2A> 属性的默认值为 `true`，因此控件将自动调整大小，除非您将 <xref:System.Windows.Forms.ToolStripItem.AutoSize%2A> 属性设置为 `false`。</span><span class="sxs-lookup"><span data-stu-id="c530b-104">Because the default value of the <xref:System.Windows.Forms.ToolStripItem.AutoSize%2A> property is `true`, controls are sized automatically unless you set the <xref:System.Windows.Forms.ToolStripItem.AutoSize%2A> property to `false`.</span></span>  
  
### <a name="to-manually-size-a-toolstripitem"></a><span data-ttu-id="c530b-105">手动调整 ToolStripItem 的大小</span><span class="sxs-lookup"><span data-stu-id="c530b-105">To manually size a ToolStripItem</span></span>  
  
1. <span data-ttu-id="c530b-106">将关联控件的 <xref:System.Windows.Forms.ToolStripItem.AutoSize%2A> 属性设置为 `false`。</span><span class="sxs-lookup"><span data-stu-id="c530b-106">Set the <xref:System.Windows.Forms.ToolStripItem.AutoSize%2A> property to `false` for the associated control.</span></span>  
  
    ```vb  
    ToolStripButton1.AutoSize = False  
    ```  
  
    ```csharp  
    toolStripButton1.AutoSize = false;  
    ```  
  
2. <span data-ttu-id="c530b-107">按所需的方式为关联 <xref:System.Windows.Forms.ToolStripItem>设置 <xref:System.Windows.Forms.ToolStripItem.Size%2A> 属性。</span><span class="sxs-lookup"><span data-stu-id="c530b-107">Set the <xref:System.Windows.Forms.ToolStripItem.Size%2A> property the way you want for the associated <xref:System.Windows.Forms.ToolStripItem>.</span></span>  
  
### <a name="to-set-the-spacing-of-a-toolstripitem"></a><span data-ttu-id="c530b-108">设置 ToolStripItem 的间距</span><span class="sxs-lookup"><span data-stu-id="c530b-108">To set the spacing of a ToolStripItem</span></span>  
  
1. <span data-ttu-id="c530b-109">在关联控件的 <xref:System.Windows.Forms.ToolStripItem.Margin%2A> 属性中插入所需的值（以像素为单位）。</span><span class="sxs-lookup"><span data-stu-id="c530b-109">Insert the desired values, in pixels, into the <xref:System.Windows.Forms.ToolStripItem.Margin%2A> property of the associated control.</span></span>  
  
     <span data-ttu-id="c530b-110"><xref:System.Windows.Forms.ToolStripItem.Margin%2A> 属性的值按此顺序指定项和相邻项之间的间距： Left、Top、Right 和底端。</span><span class="sxs-lookup"><span data-stu-id="c530b-110">The values of the <xref:System.Windows.Forms.ToolStripItem.Margin%2A> property specify the spacing between the item and adjacent items in this order: Left, Top, Right, and Bottom.</span></span>  
  
    ```vb  
    ToolStripTextBox1.Margin = New System.Windows.Forms.Padding _  
        (3, 0, 3, 0)  
    ```  
  
    ```csharp  
    toolStripTextBox1.Margin = new System.Windows.Forms.Padding   
        (3, 0, 3, 0);  
    ```  
  
### <a name="to-align-a-toolstripitem-to-the-right-side-of-the-toolstrip"></a><span data-ttu-id="c530b-111">将 ToolStripItem 与 ToolStrip 右端对齐</span><span class="sxs-lookup"><span data-stu-id="c530b-111">To align a ToolStripItem to the right side of the ToolStrip</span></span>  
  
1. <span data-ttu-id="c530b-112">将关联控件的 <xref:System.Windows.Forms.ToolStripItem.Alignment%2A> 属性设置为 <xref:System.Windows.Forms.ToolStripItemAlignment.Right>。</span><span class="sxs-lookup"><span data-stu-id="c530b-112">Set the <xref:System.Windows.Forms.ToolStripItem.Alignment%2A> property to <xref:System.Windows.Forms.ToolStripItemAlignment.Right> for the associated control.</span></span> <span data-ttu-id="c530b-113">默认情况下，<xref:System.Windows.Forms.ToolStripItem.Alignment%2A> 设置为 <xref:System.Windows.Forms.ToolStripItemAlignment.Left>，这会使控件与 <xref:System.Windows.Forms.ToolStrip>的左侧对齐。</span><span class="sxs-lookup"><span data-stu-id="c530b-113">By default, <xref:System.Windows.Forms.ToolStripItem.Alignment%2A> is set to <xref:System.Windows.Forms.ToolStripItemAlignment.Left>, which aligns controls to the left side of the <xref:System.Windows.Forms.ToolStrip>.</span></span>  
  
    ```vb  
    ToolStripSplitButton1.Alignment = _  
        System.Windows.Forms.ToolStripItemAlignment.Right  
    ```  
  
    ```csharp  
    toolStripSplitButton1.Alignment =   
        System.Windows.Forms.ToolStripItemAlignment.Right;  
    ```  
  
### <a name="to-arrange-toolstrip-items-on-the-toolstrip"></a><span data-ttu-id="c530b-114">在 ToolStrip 上排列 ToolStrip 项</span><span class="sxs-lookup"><span data-stu-id="c530b-114">To arrange ToolStrip items on the ToolStrip</span></span>  
  
- <span data-ttu-id="c530b-115">将 <xref:System.Windows.Forms.ToolStrip.LayoutStyle%2A> 属性设置为所需 <xref:System.Windows.Forms.ToolStripLayoutStyle> 的值。</span><span class="sxs-lookup"><span data-stu-id="c530b-115">Set the <xref:System.Windows.Forms.ToolStrip.LayoutStyle%2A> property to the value of <xref:System.Windows.Forms.ToolStripLayoutStyle> that you want.</span></span>  
  
    ```vb  
    ToolStripDropDown1.LayoutStyle = _  
        System.Windows.Forms.ToolStripLayoutStyle.Flow  
    ```  
  
    ```csharp  
    toolStripDropDown1.LayoutStyle =   
        System.Windows.Forms.ToolStripLayoutStyle.Flow;  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="c530b-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c530b-116">See also</span></span>

- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.Control.Layout>
- <xref:System.Windows.Forms.ToolStrip.LayoutCompleted>
- <xref:System.Windows.Forms.ToolStrip.LayoutSettings%2A>
- <xref:System.Windows.Forms.ToolStripItem.TextImageRelation%2A>
- <xref:System.Windows.Forms.ToolStripItem.Placement%2A>
- <xref:System.Windows.Forms.ToolStrip.CanOverflow%2A>
- [<span data-ttu-id="c530b-117">ToolStrip 控件概述</span><span class="sxs-lookup"><span data-stu-id="c530b-117">ToolStrip Control Overview</span></span>](toolstrip-control-overview-windows-forms.md)
- [<span data-ttu-id="c530b-118">ToolStrip 控件体系结构</span><span class="sxs-lookup"><span data-stu-id="c530b-118">ToolStrip Control Architecture</span></span>](toolstrip-control-architecture.md)
- [<span data-ttu-id="c530b-119">ToolStrip 技术摘要</span><span class="sxs-lookup"><span data-stu-id="c530b-119">ToolStrip Technology Summary</span></span>](toolstrip-technology-summary.md)
