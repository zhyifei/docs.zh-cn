---
title: 如何：更改工具条项目的间距和对齐方式
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ToolStrip control [Windows Forms], aligning items
- examples [Windows Forms], toolbars
- toolbars [Windows Forms], aligning items
ms.assetid: cd483466-0f49-43df-addf-e2b5fcd64027
ms.openlocfilehash: 550ac1660a077e8d766a01bfa8d102c07f0fbfeb
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182227"
---
# <a name="how-to-change-the-spacing-and-alignment-of-toolstrip-items-in-windows-forms"></a><span data-ttu-id="1d2c6-102">如何：在 Windows 窗体中更改 ToolStrip 项的间距和对齐方式</span><span class="sxs-lookup"><span data-stu-id="1d2c6-102">How to: Change the Spacing and Alignment of ToolStrip Items in Windows Forms</span></span>
<span data-ttu-id="1d2c6-103">控件<xref:System.Windows.Forms.ToolStrip>完全支持布局功能，如大小调整、控件相对于彼此的<xref:System.Windows.Forms.ToolStripItem>间距、控件的<xref:System.Windows.Forms.ToolStrip>排列以及控件相对于 的<xref:System.Windows.Forms.ToolStrip>间距。</span><span class="sxs-lookup"><span data-stu-id="1d2c6-103">The <xref:System.Windows.Forms.ToolStrip> control fully supports layout features such as sizing, the spacing of <xref:System.Windows.Forms.ToolStripItem> controls relative to each other, the arrangement of controls on the <xref:System.Windows.Forms.ToolStrip>, and the spacing of controls relative to the <xref:System.Windows.Forms.ToolStrip>.</span></span>  
  
 <span data-ttu-id="1d2c6-104">由于<xref:System.Windows.Forms.ToolStripItem.AutoSize%2A>属性的默认值为`true`，控件会自动调整大小，除非您将<xref:System.Windows.Forms.ToolStripItem.AutoSize%2A>属性设置为`false`。</span><span class="sxs-lookup"><span data-stu-id="1d2c6-104">Because the default value of the <xref:System.Windows.Forms.ToolStripItem.AutoSize%2A> property is `true`, controls are sized automatically unless you set the <xref:System.Windows.Forms.ToolStripItem.AutoSize%2A> property to `false`.</span></span>  
  
### <a name="to-manually-size-a-toolstripitem"></a><span data-ttu-id="1d2c6-105">手动调整工具条项目的大小</span><span class="sxs-lookup"><span data-stu-id="1d2c6-105">To manually size a ToolStripItem</span></span>  
  
1. <span data-ttu-id="1d2c6-106">将<xref:System.Windows.Forms.ToolStripItem.AutoSize%2A>属性设置为`false`关联的控件。</span><span class="sxs-lookup"><span data-stu-id="1d2c6-106">Set the <xref:System.Windows.Forms.ToolStripItem.AutoSize%2A> property to `false` for the associated control.</span></span>  
  
    ```vb  
    ToolStripButton1.AutoSize = False  
    ```  
  
    ```csharp  
    toolStripButton1.AutoSize = false;  
    ```  
  
2. <span data-ttu-id="1d2c6-107">以<xref:System.Windows.Forms.ToolStripItem.Size%2A>所需方式设置关联的<xref:System.Windows.Forms.ToolStripItem>属性。</span><span class="sxs-lookup"><span data-stu-id="1d2c6-107">Set the <xref:System.Windows.Forms.ToolStripItem.Size%2A> property the way you want for the associated <xref:System.Windows.Forms.ToolStripItem>.</span></span>  
  
### <a name="to-set-the-spacing-of-a-toolstripitem"></a><span data-ttu-id="1d2c6-108">设置工具条项目的间距</span><span class="sxs-lookup"><span data-stu-id="1d2c6-108">To set the spacing of a ToolStripItem</span></span>  
  
1. <span data-ttu-id="1d2c6-109">将所需值（以像素为单位）插入到关联<xref:System.Windows.Forms.ToolStripItem.Margin%2A>控件的属性中。</span><span class="sxs-lookup"><span data-stu-id="1d2c6-109">Insert the desired values, in pixels, into the <xref:System.Windows.Forms.ToolStripItem.Margin%2A> property of the associated control.</span></span>  
  
     <span data-ttu-id="1d2c6-110"><xref:System.Windows.Forms.ToolStripItem.Margin%2A>属性的值按此顺序指定项和相邻项之间的间距：左、上、右和下。</span><span class="sxs-lookup"><span data-stu-id="1d2c6-110">The values of the <xref:System.Windows.Forms.ToolStripItem.Margin%2A> property specify the spacing between the item and adjacent items in this order: Left, Top, Right, and Bottom.</span></span>  
  
    ```vb  
    ToolStripTextBox1.Margin = New System.Windows.Forms.Padding _  
        (3, 0, 3, 0)  
    ```  
  
    ```csharp  
    toolStripTextBox1.Margin = new System.Windows.Forms.Padding
        (3, 0, 3, 0);  
    ```  
  
### <a name="to-align-a-toolstripitem-to-the-right-side-of-the-toolstrip"></a><span data-ttu-id="1d2c6-111">将工具条项目与工具条的右侧对齐</span><span class="sxs-lookup"><span data-stu-id="1d2c6-111">To align a ToolStripItem to the right side of the ToolStrip</span></span>  
  
1. <span data-ttu-id="1d2c6-112">将<xref:System.Windows.Forms.ToolStripItem.Alignment%2A>属性设置为<xref:System.Windows.Forms.ToolStripItemAlignment.Right>关联的控件。</span><span class="sxs-lookup"><span data-stu-id="1d2c6-112">Set the <xref:System.Windows.Forms.ToolStripItem.Alignment%2A> property to <xref:System.Windows.Forms.ToolStripItemAlignment.Right> for the associated control.</span></span> <span data-ttu-id="1d2c6-113">默认情况下，<xref:System.Windows.Forms.ToolStripItem.Alignment%2A>设置为<xref:System.Windows.Forms.ToolStripItemAlignment.Left>，将控件与 的<xref:System.Windows.Forms.ToolStrip>左侧对齐。</span><span class="sxs-lookup"><span data-stu-id="1d2c6-113">By default, <xref:System.Windows.Forms.ToolStripItem.Alignment%2A> is set to <xref:System.Windows.Forms.ToolStripItemAlignment.Left>, which aligns controls to the left side of the <xref:System.Windows.Forms.ToolStrip>.</span></span>  
  
    ```vb  
    ToolStripSplitButton1.Alignment = _  
        System.Windows.Forms.ToolStripItemAlignment.Right  
    ```  
  
    ```csharp  
    toolStripSplitButton1.Alignment =
        System.Windows.Forms.ToolStripItemAlignment.Right;  
    ```  
  
### <a name="to-arrange-toolstrip-items-on-the-toolstrip"></a><span data-ttu-id="1d2c6-114">在工具条上排列工具条项目</span><span class="sxs-lookup"><span data-stu-id="1d2c6-114">To arrange ToolStrip items on the ToolStrip</span></span>  
  
- <span data-ttu-id="1d2c6-115">将<xref:System.Windows.Forms.ToolStrip.LayoutStyle%2A>属性设置为所需的值<xref:System.Windows.Forms.ToolStripLayoutStyle>。</span><span class="sxs-lookup"><span data-stu-id="1d2c6-115">Set the <xref:System.Windows.Forms.ToolStrip.LayoutStyle%2A> property to the value of <xref:System.Windows.Forms.ToolStripLayoutStyle> that you want.</span></span>  
  
    ```vb  
    ToolStripDropDown1.LayoutStyle = _  
        System.Windows.Forms.ToolStripLayoutStyle.Flow  
    ```  
  
    ```csharp  
    toolStripDropDown1.LayoutStyle =
        System.Windows.Forms.ToolStripLayoutStyle.Flow;  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="1d2c6-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1d2c6-116">See also</span></span>

- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.Control.Layout>
- <xref:System.Windows.Forms.ToolStrip.LayoutCompleted>
- <xref:System.Windows.Forms.ToolStrip.LayoutSettings%2A>
- <xref:System.Windows.Forms.ToolStripItem.TextImageRelation%2A>
- <xref:System.Windows.Forms.ToolStripItem.Placement%2A>
- <xref:System.Windows.Forms.ToolStrip.CanOverflow%2A>
- [<span data-ttu-id="1d2c6-117">ToolStrip 控件概述</span><span class="sxs-lookup"><span data-stu-id="1d2c6-117">ToolStrip Control Overview</span></span>](toolstrip-control-overview-windows-forms.md)
- [<span data-ttu-id="1d2c6-118">ToolStrip 控件体系结构</span><span class="sxs-lookup"><span data-stu-id="1d2c6-118">ToolStrip Control Architecture</span></span>](toolstrip-control-architecture.md)
- [<span data-ttu-id="1d2c6-119">ToolStrip 技术摘要</span><span class="sxs-lookup"><span data-stu-id="1d2c6-119">ToolStrip Technology Summary</span></span>](toolstrip-technology-summary.md)
