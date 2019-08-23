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
# <a name="how-to-use-tooltips-in-toolstrip-controls"></a>如何：在 ToolStrip 控件中使用工具提示
可以通过将控件<xref:System.Windows.Forms.ToolTip>的<xref:System.Windows.Forms.ToolStrip.ShowItemToolTips%2A>属性<xref:System.Windows.Forms.ToolStrip>设置为`true`, 为所需的控件显示。  
  
### <a name="to-display-a-tooltip"></a>显示工具提示  
  
- 将控件<xref:System.Windows.Forms.ToolStrip.ShowItemToolTips%2A>的属性设置为。 `true`  
  
     的<xref:System.Windows.Forms.ToolStrip.ShowItemToolTips%2A?displayProperty=nameWithType>默认值`false`为`true` <xref:System.Windows.Forms.MenuStrip.ShowItemToolTips%2A?displayProperty=nameWithType> ,<xref:System.Windows.Forms.StatusStrip.ShowItemToolTips%2A?displayProperty=nameWithType>而的默认值为。  
  
### <a name="to-use-the-tooltiptext-property-for-the-tooltip-text-of-a-toolstripbutton"></a>使用 ToolStripButton 的工具提示文本的 ToolTipText 属性  
  
1. 将按钮的`true` <xref:System.Windows.Forms.ToolStrip.ShowItemToolTips%2A>属性设置为。  
  
2. 将按钮的`false` <xref:System.Windows.Forms.ToolStripButton.AutoToolTip%2A?displayProperty=nameWithType>属性设置为。  
  
     `true` <xref:System.Windows.Forms.ToolStripDropDownButton>默认情况下`AutoToolTip` <xref:System.Windows.Forms.ToolStripSplitButton>, 属性为、和。 <xref:System.Windows.Forms.ToolStripButton>  
  
     默认<xref:System.Windows.Forms.ToolStripButton>情况下`Text` , 为<xref:System.Windows.Forms.ToolTip>文本使用其属性。 使用此过程在中<xref:System.Windows.Forms.ToolStripButton> <xref:System.Windows.Forms.ToolTip>显示自定义文本。  
  
> [!NOTE]
> 如果将设置<xref:System.Windows.Forms.ToolStripItemDisplayStyle>为<xref:System.Windows.Forms.ToolStripItemDisplayStyle.None>或<xref:System.Windows.Forms.ToolStripItemDisplayStyle.Image>, 则按钮上不会显示任何文本, 但会出现工具提示。  
  
## <a name="see-also"></a>请参阅

- <xref:System.Windows.Forms.ToolStrip.ShowItemToolTips%2A>
- <xref:System.Windows.Forms.ToolStripButton>
- <xref:System.Windows.Forms.ToolStripDropDownButton>
- <xref:System.Windows.Forms.ToolStripSplitButton>
- [ToolStrip 控件概述](toolstrip-control-overview-windows-forms.md)
