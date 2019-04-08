---
title: 如何：在 ToolStrip 控件中使用工具提示
ms.date: 03/30/2017
helpviewer_keywords:
- ToolStrip control [Windows Forms], adding tooltips
- toolbars [Windows Forms], adding tooltips
- tooltips [Windows Forms], adding
ms.assetid: c5d86024-a7c5-44ee-8b3f-2daf53d80d3e
ms.openlocfilehash: 884fb75d53e425702cdef46615a16394b835518f
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59076464"
---
# <a name="how-to-use-tooltips-in-toolstrip-controls"></a><span data-ttu-id="7cd38-102">如何：在 ToolStrip 控件中使用工具提示</span><span class="sxs-lookup"><span data-stu-id="7cd38-102">How to: Use ToolTips in ToolStrip Controls</span></span>
<span data-ttu-id="7cd38-103">可以显示<xref:System.Windows.Forms.ToolTip>有关<xref:System.Windows.Forms.ToolStrip>想通过设置控件的控件<xref:System.Windows.Forms.ToolStrip.ShowItemToolTips%2A>属性设置为`true`。</span><span class="sxs-lookup"><span data-stu-id="7cd38-103">You can display a <xref:System.Windows.Forms.ToolTip> for the <xref:System.Windows.Forms.ToolStrip> control you want by setting the control's <xref:System.Windows.Forms.ToolStrip.ShowItemToolTips%2A> property to `true`.</span></span>  
  
### <a name="to-display-a-tooltip"></a><span data-ttu-id="7cd38-104">若要显示的工具提示</span><span class="sxs-lookup"><span data-stu-id="7cd38-104">To display a ToolTip</span></span>  
  
-   <span data-ttu-id="7cd38-105">设置<xref:System.Windows.Forms.ToolStrip.ShowItemToolTips%2A>到控件属性`true`。</span><span class="sxs-lookup"><span data-stu-id="7cd38-105">Set the <xref:System.Windows.Forms.ToolStrip.ShowItemToolTips%2A> property of the control to `true`.</span></span>  
  
     <span data-ttu-id="7cd38-106">默认值<xref:System.Windows.Forms.ToolStrip.ShowItemToolTips%2A?displayProperty=nameWithType>是`true`，默认值的<xref:System.Windows.Forms.MenuStrip.ShowItemToolTips%2A?displayProperty=nameWithType>并<xref:System.Windows.Forms.StatusStrip.ShowItemToolTips%2A?displayProperty=nameWithType>是`false`。</span><span class="sxs-lookup"><span data-stu-id="7cd38-106">The default value of <xref:System.Windows.Forms.ToolStrip.ShowItemToolTips%2A?displayProperty=nameWithType> is `true`, and the default value of <xref:System.Windows.Forms.MenuStrip.ShowItemToolTips%2A?displayProperty=nameWithType> and <xref:System.Windows.Forms.StatusStrip.ShowItemToolTips%2A?displayProperty=nameWithType> is `false`.</span></span>  
  
### <a name="to-use-the-tooltiptext-property-for-the-tooltip-text-of-a-toolstripbutton"></a><span data-ttu-id="7cd38-107">若要使用的工具提示文本的 ToolStripButton ToolTipText 属性</span><span class="sxs-lookup"><span data-stu-id="7cd38-107">To use the ToolTipText property for the ToolTip text of a ToolStripButton</span></span>  
  
1.  <span data-ttu-id="7cd38-108">设置<xref:System.Windows.Forms.ToolStrip.ShowItemToolTips%2A>属性的按钮为`true`。</span><span class="sxs-lookup"><span data-stu-id="7cd38-108">Set the <xref:System.Windows.Forms.ToolStrip.ShowItemToolTips%2A> property of the button to `true`.</span></span>  
  
2.  <span data-ttu-id="7cd38-109">设置<xref:System.Windows.Forms.ToolStripButton.AutoToolTip%2A?displayProperty=nameWithType>属性的按钮为`false`。</span><span class="sxs-lookup"><span data-stu-id="7cd38-109">Set the <xref:System.Windows.Forms.ToolStripButton.AutoToolTip%2A?displayProperty=nameWithType> property of the button to `false`.</span></span>  
  
     <span data-ttu-id="7cd38-110">`AutoToolTip`属性是`true`对于默认情况下<xref:System.Windows.Forms.ToolStripButton>， <xref:System.Windows.Forms.ToolStripDropDownButton>，和<xref:System.Windows.Forms.ToolStripSplitButton>。</span><span class="sxs-lookup"><span data-stu-id="7cd38-110">The `AutoToolTip` property is `true` by default for <xref:System.Windows.Forms.ToolStripButton>, <xref:System.Windows.Forms.ToolStripDropDownButton>, and <xref:System.Windows.Forms.ToolStripSplitButton>.</span></span>  
  
     <span data-ttu-id="7cd38-111">一个<xref:System.Windows.Forms.ToolStripButton>使用其`Text`属性<xref:System.Windows.Forms.ToolTip>默认情况下的文本。</span><span class="sxs-lookup"><span data-stu-id="7cd38-111">A <xref:System.Windows.Forms.ToolStripButton> uses its `Text` property for the <xref:System.Windows.Forms.ToolTip> text by default.</span></span> <span data-ttu-id="7cd38-112">使用此过程用于显示自定义文本<xref:System.Windows.Forms.ToolStripButton><xref:System.Windows.Forms.ToolTip>。</span><span class="sxs-lookup"><span data-stu-id="7cd38-112">Use this procedure to display custom text in a <xref:System.Windows.Forms.ToolStripButton><xref:System.Windows.Forms.ToolTip>.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7cd38-113">如果您设置<xref:System.Windows.Forms.ToolStripItemDisplayStyle>到<xref:System.Windows.Forms.ToolStripItemDisplayStyle.None>或<xref:System.Windows.Forms.ToolStripItemDisplayStyle.Image>，没有文本将出现在按钮，但仍将显示工具提示。</span><span class="sxs-lookup"><span data-stu-id="7cd38-113">If you set <xref:System.Windows.Forms.ToolStripItemDisplayStyle> to <xref:System.Windows.Forms.ToolStripItemDisplayStyle.None> or <xref:System.Windows.Forms.ToolStripItemDisplayStyle.Image>, no text will appear on the button, but the tool tip still appears.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7cd38-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="7cd38-114">See also</span></span>

- <xref:System.Windows.Forms.ToolStrip.ShowItemToolTips%2A>
- <xref:System.Windows.Forms.ToolStripButton>
- <xref:System.Windows.Forms.ToolStripDropDownButton>
- <xref:System.Windows.Forms.ToolStripSplitButton>
- [<span data-ttu-id="7cd38-115">ToolStrip 控件概述</span><span class="sxs-lookup"><span data-stu-id="7cd38-115">ToolStrip Control Overview</span></span>](toolstrip-control-overview-windows-forms.md)
