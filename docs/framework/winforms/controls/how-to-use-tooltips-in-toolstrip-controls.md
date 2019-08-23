---
title: 如何：在 ToolStrip 控件中使用工具提示
ms.date: 03/30/2017
helpviewer_keywords:
- ToolStrip control [Windows Forms], adding tooltips
- toolbars [Windows Forms], adding tooltips
- tooltips [Windows Forms], adding
ms.assetid: c5d86024-a7c5-44ee-8b3f-2daf53d80d3e
ms.openlocfilehash: 3f383b6cccba7825637ea65a0e13280b91b406c9
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69939736"
---
# <a name="how-to-use-tooltips-in-toolstrip-controls"></a><span data-ttu-id="c9401-102">如何：在 ToolStrip 控件中使用工具提示</span><span class="sxs-lookup"><span data-stu-id="c9401-102">How to: Use ToolTips in ToolStrip Controls</span></span>
<span data-ttu-id="c9401-103">可以通过将控件<xref:System.Windows.Forms.ToolTip>的<xref:System.Windows.Forms.ToolStrip.ShowItemToolTips%2A>属性<xref:System.Windows.Forms.ToolStrip>设置为`true`, 为所需的控件显示。</span><span class="sxs-lookup"><span data-stu-id="c9401-103">You can display a <xref:System.Windows.Forms.ToolTip> for the <xref:System.Windows.Forms.ToolStrip> control you want by setting the control's <xref:System.Windows.Forms.ToolStrip.ShowItemToolTips%2A> property to `true`.</span></span>  
  
### <a name="to-display-a-tooltip"></a><span data-ttu-id="c9401-104">显示工具提示</span><span class="sxs-lookup"><span data-stu-id="c9401-104">To display a ToolTip</span></span>  
  
- <span data-ttu-id="c9401-105">将控件<xref:System.Windows.Forms.ToolStrip.ShowItemToolTips%2A>的属性设置为。 `true`</span><span class="sxs-lookup"><span data-stu-id="c9401-105">Set the <xref:System.Windows.Forms.ToolStrip.ShowItemToolTips%2A> property of the control to `true`.</span></span>  
  
     <span data-ttu-id="c9401-106">的<xref:System.Windows.Forms.ToolStrip.ShowItemToolTips%2A?displayProperty=nameWithType>默认值`false`为`true` <xref:System.Windows.Forms.MenuStrip.ShowItemToolTips%2A?displayProperty=nameWithType> ,<xref:System.Windows.Forms.StatusStrip.ShowItemToolTips%2A?displayProperty=nameWithType>而的默认值为。</span><span class="sxs-lookup"><span data-stu-id="c9401-106">The default value of <xref:System.Windows.Forms.ToolStrip.ShowItemToolTips%2A?displayProperty=nameWithType> is `true`, and the default value of <xref:System.Windows.Forms.MenuStrip.ShowItemToolTips%2A?displayProperty=nameWithType> and <xref:System.Windows.Forms.StatusStrip.ShowItemToolTips%2A?displayProperty=nameWithType> is `false`.</span></span>  
  
### <a name="to-use-the-tooltiptext-property-for-the-tooltip-text-of-a-toolstripbutton"></a><span data-ttu-id="c9401-107">使用 ToolStripButton 的工具提示文本的 ToolTipText 属性</span><span class="sxs-lookup"><span data-stu-id="c9401-107">To use the ToolTipText property for the ToolTip text of a ToolStripButton</span></span>  
  
1. <span data-ttu-id="c9401-108">将按钮的`true` <xref:System.Windows.Forms.ToolStrip.ShowItemToolTips%2A>属性设置为。</span><span class="sxs-lookup"><span data-stu-id="c9401-108">Set the <xref:System.Windows.Forms.ToolStrip.ShowItemToolTips%2A> property of the button to `true`.</span></span>  
  
2. <span data-ttu-id="c9401-109">将按钮的`false` <xref:System.Windows.Forms.ToolStripButton.AutoToolTip%2A?displayProperty=nameWithType>属性设置为。</span><span class="sxs-lookup"><span data-stu-id="c9401-109">Set the <xref:System.Windows.Forms.ToolStripButton.AutoToolTip%2A?displayProperty=nameWithType> property of the button to `false`.</span></span>  
  
     <span data-ttu-id="c9401-110">`true` <xref:System.Windows.Forms.ToolStripDropDownButton>默认情况下`AutoToolTip` <xref:System.Windows.Forms.ToolStripSplitButton>, 属性为、和。 <xref:System.Windows.Forms.ToolStripButton></span><span class="sxs-lookup"><span data-stu-id="c9401-110">The `AutoToolTip` property is `true` by default for <xref:System.Windows.Forms.ToolStripButton>, <xref:System.Windows.Forms.ToolStripDropDownButton>, and <xref:System.Windows.Forms.ToolStripSplitButton>.</span></span>  
  
     <span data-ttu-id="c9401-111">默认<xref:System.Windows.Forms.ToolStripButton>情况下`Text` , 为<xref:System.Windows.Forms.ToolTip>文本使用其属性。</span><span class="sxs-lookup"><span data-stu-id="c9401-111">A <xref:System.Windows.Forms.ToolStripButton> uses its `Text` property for the <xref:System.Windows.Forms.ToolTip> text by default.</span></span> <span data-ttu-id="c9401-112">使用此过程在中<xref:System.Windows.Forms.ToolStripButton> <xref:System.Windows.Forms.ToolTip>显示自定义文本。</span><span class="sxs-lookup"><span data-stu-id="c9401-112">Use this procedure to display custom text in a <xref:System.Windows.Forms.ToolStripButton><xref:System.Windows.Forms.ToolTip>.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="c9401-113">如果将设置<xref:System.Windows.Forms.ToolStripItemDisplayStyle>为<xref:System.Windows.Forms.ToolStripItemDisplayStyle.None>或<xref:System.Windows.Forms.ToolStripItemDisplayStyle.Image>, 则按钮上不会显示任何文本, 但会出现工具提示。</span><span class="sxs-lookup"><span data-stu-id="c9401-113">If you set <xref:System.Windows.Forms.ToolStripItemDisplayStyle> to <xref:System.Windows.Forms.ToolStripItemDisplayStyle.None> or <xref:System.Windows.Forms.ToolStripItemDisplayStyle.Image>, no text will appear on the button, but the tool tip still appears.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c9401-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="c9401-114">See also</span></span>

- <xref:System.Windows.Forms.ToolStrip.ShowItemToolTips%2A>
- <xref:System.Windows.Forms.ToolStripButton>
- <xref:System.Windows.Forms.ToolStripDropDownButton>
- <xref:System.Windows.Forms.ToolStripSplitButton>
- [<span data-ttu-id="c9401-115">ToolStrip 控件概述</span><span class="sxs-lookup"><span data-stu-id="c9401-115">ToolStrip Control Overview</span></span>](toolstrip-control-overview-windows-forms.md)
