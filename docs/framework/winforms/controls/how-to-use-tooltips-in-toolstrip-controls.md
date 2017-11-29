---
title: "如何：在 ToolStrip 控件中使用工具提示"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- ToolStrip control [Windows Forms], adding tooltips
- toolbars [Windows Forms], adding tooltips
- tooltips [Windows Forms], adding
ms.assetid: c5d86024-a7c5-44ee-8b3f-2daf53d80d3e
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: bc52dd1b629829564532fd93650737f51e5d7f24
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-use-tooltips-in-toolstrip-controls"></a><span data-ttu-id="8ddab-102">如何：在 ToolStrip 控件中使用工具提示</span><span class="sxs-lookup"><span data-stu-id="8ddab-102">How to: Use ToolTips in ToolStrip Controls</span></span>
<span data-ttu-id="8ddab-103">可以显示<xref:System.Windows.Forms.ToolTip>为<xref:System.Windows.Forms.ToolStrip>想通过设置控件的控件<xref:System.Windows.Forms.ToolStrip.ShowItemToolTips%2A>属性`true`。</span><span class="sxs-lookup"><span data-stu-id="8ddab-103">You can display a <xref:System.Windows.Forms.ToolTip> for the <xref:System.Windows.Forms.ToolStrip> control you want by setting the control's <xref:System.Windows.Forms.ToolStrip.ShowItemToolTips%2A> property to `true`.</span></span>  
  
### <a name="to-display-a-tooltip"></a><span data-ttu-id="8ddab-104">若要显示的工具提示</span><span class="sxs-lookup"><span data-stu-id="8ddab-104">To display a ToolTip</span></span>  
  
-   <span data-ttu-id="8ddab-105">设置<xref:System.Windows.Forms.ToolStrip.ShowItemToolTips%2A>该控件的属性`true`。</span><span class="sxs-lookup"><span data-stu-id="8ddab-105">Set the <xref:System.Windows.Forms.ToolStrip.ShowItemToolTips%2A> property of the control to `true`.</span></span>  
  
     <span data-ttu-id="8ddab-106">默认值<xref:System.Windows.Forms.ToolStrip.ShowItemToolTips%2A?displayProperty=nameWithType>是`true`，和的默认值<xref:System.Windows.Forms.MenuStrip.ShowItemToolTips%2A?displayProperty=nameWithType>和<xref:System.Windows.Forms.StatusStrip.ShowItemToolTips%2A?displayProperty=nameWithType>是`false`。</span><span class="sxs-lookup"><span data-stu-id="8ddab-106">The default value of <xref:System.Windows.Forms.ToolStrip.ShowItemToolTips%2A?displayProperty=nameWithType> is `true`, and the default value of <xref:System.Windows.Forms.MenuStrip.ShowItemToolTips%2A?displayProperty=nameWithType> and <xref:System.Windows.Forms.StatusStrip.ShowItemToolTips%2A?displayProperty=nameWithType> is `false`.</span></span>  
  
### <a name="to-use-the-tooltiptext-property-for-the-tooltip-text-of-a-toolstripbutton"></a><span data-ttu-id="8ddab-107">ToolTipText 属性用于 ToolStripButton 的工具提示文本</span><span class="sxs-lookup"><span data-stu-id="8ddab-107">To use the ToolTipText property for the ToolTip text of a ToolStripButton</span></span>  
  
1.  <span data-ttu-id="8ddab-108">设置<xref:System.Windows.Forms.ToolStrip.ShowItemToolTips%2A>到按钮属性`true`。</span><span class="sxs-lookup"><span data-stu-id="8ddab-108">Set the <xref:System.Windows.Forms.ToolStrip.ShowItemToolTips%2A> property of the button to `true`.</span></span>  
  
2.  <span data-ttu-id="8ddab-109">设置<xref:System.Windows.Forms.ToolStripButton.AutoToolTip%2A?displayProperty=nameWithType>到按钮属性`false`。</span><span class="sxs-lookup"><span data-stu-id="8ddab-109">Set the <xref:System.Windows.Forms.ToolStripButton.AutoToolTip%2A?displayProperty=nameWithType> property of the button to `false`.</span></span>  
  
     <span data-ttu-id="8ddab-110">`AutoToolTip`属性是`true`默认情况下，为<xref:System.Windows.Forms.ToolStripButton>， <xref:System.Windows.Forms.ToolStripDropDownButton>，和<xref:System.Windows.Forms.ToolStripSplitButton>。</span><span class="sxs-lookup"><span data-stu-id="8ddab-110">The `AutoToolTip` property is `true` by default for <xref:System.Windows.Forms.ToolStripButton>, <xref:System.Windows.Forms.ToolStripDropDownButton>, and <xref:System.Windows.Forms.ToolStripSplitButton>.</span></span>  
  
     <span data-ttu-id="8ddab-111">A<xref:System.Windows.Forms.ToolStripButton>使用其`Text`属性<xref:System.Windows.Forms.ToolTip>默认情况下的文本。</span><span class="sxs-lookup"><span data-stu-id="8ddab-111">A <xref:System.Windows.Forms.ToolStripButton> uses its `Text` property for the <xref:System.Windows.Forms.ToolTip> text by default.</span></span> <span data-ttu-id="8ddab-112">使用此过程用于显示自定义文本<xref:System.Windows.Forms.ToolStripButton> <xref:System.Windows.Forms.ToolTip>。</span><span class="sxs-lookup"><span data-stu-id="8ddab-112">Use this procedure to display custom text in a <xref:System.Windows.Forms.ToolStripButton><xref:System.Windows.Forms.ToolTip>.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8ddab-113">如果你设置<xref:System.Windows.Forms.ToolStripItemDisplayStyle>到<xref:System.Windows.Forms.ToolStripItemDisplayStyle.None>或<xref:System.Windows.Forms.ToolStripItemDisplayStyle.Image>，任何文本将出现在按钮，但仍将出现工具提示。</span><span class="sxs-lookup"><span data-stu-id="8ddab-113">If you set <xref:System.Windows.Forms.ToolStripItemDisplayStyle> to <xref:System.Windows.Forms.ToolStripItemDisplayStyle.None> or <xref:System.Windows.Forms.ToolStripItemDisplayStyle.Image>, no text will appear on the button, but the tool tip still appears.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8ddab-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8ddab-114">See Also</span></span>  
 <xref:System.Windows.Forms.ToolStrip.ShowItemToolTips%2A>  
 <xref:System.Windows.Forms.ToolStripButton>  
 <xref:System.Windows.Forms.ToolStripDropDownButton>  
 <xref:System.Windows.Forms.ToolStripSplitButton>  
 [<span data-ttu-id="8ddab-115">ToolStrip 控件概述</span><span class="sxs-lookup"><span data-stu-id="8ddab-115">ToolStrip Control Overview</span></span>](../../../../docs/framework/winforms/controls/toolstrip-control-overview-windows-forms.md)
