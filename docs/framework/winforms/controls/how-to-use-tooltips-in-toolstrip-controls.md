---
title: 如何：在 ToolStrip 控件中使用工具提示
ms.date: 03/30/2017
helpviewer_keywords:
- ToolStrip control [Windows Forms], adding tooltips
- toolbars [Windows Forms], adding tooltips
- tooltips [Windows Forms], adding
ms.assetid: c5d86024-a7c5-44ee-8b3f-2daf53d80d3e
ms.openlocfilehash: 2b10b3fcf3930d5848f1d7a9602cfcc945bc8975
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-use-tooltips-in-toolstrip-controls"></a>如何：在 ToolStrip 控件中使用工具提示
可以显示<xref:System.Windows.Forms.ToolTip>为<xref:System.Windows.Forms.ToolStrip>想通过设置控件的控件<xref:System.Windows.Forms.ToolStrip.ShowItemToolTips%2A>属性`true`。  
  
### <a name="to-display-a-tooltip"></a>若要显示的工具提示  
  
-   设置<xref:System.Windows.Forms.ToolStrip.ShowItemToolTips%2A>该控件的属性`true`。  
  
     默认值<xref:System.Windows.Forms.ToolStrip.ShowItemToolTips%2A?displayProperty=nameWithType>是`true`，和的默认值<xref:System.Windows.Forms.MenuStrip.ShowItemToolTips%2A?displayProperty=nameWithType>和<xref:System.Windows.Forms.StatusStrip.ShowItemToolTips%2A?displayProperty=nameWithType>是`false`。  
  
### <a name="to-use-the-tooltiptext-property-for-the-tooltip-text-of-a-toolstripbutton"></a>ToolTipText 属性用于 ToolStripButton 的工具提示文本  
  
1.  设置<xref:System.Windows.Forms.ToolStrip.ShowItemToolTips%2A>到按钮属性`true`。  
  
2.  设置<xref:System.Windows.Forms.ToolStripButton.AutoToolTip%2A?displayProperty=nameWithType>到按钮属性`false`。  
  
     `AutoToolTip`属性是`true`默认情况下，为<xref:System.Windows.Forms.ToolStripButton>， <xref:System.Windows.Forms.ToolStripDropDownButton>，和<xref:System.Windows.Forms.ToolStripSplitButton>。  
  
     A<xref:System.Windows.Forms.ToolStripButton>使用其`Text`属性<xref:System.Windows.Forms.ToolTip>默认情况下的文本。 使用此过程用于显示自定义文本<xref:System.Windows.Forms.ToolStripButton> <xref:System.Windows.Forms.ToolTip>。  
  
> [!NOTE]
>  如果你设置<xref:System.Windows.Forms.ToolStripItemDisplayStyle>到<xref:System.Windows.Forms.ToolStripItemDisplayStyle.None>或<xref:System.Windows.Forms.ToolStripItemDisplayStyle.Image>，任何文本将出现在按钮，但仍将出现工具提示。  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Windows.Forms.ToolStrip.ShowItemToolTips%2A>  
 <xref:System.Windows.Forms.ToolStripButton>  
 <xref:System.Windows.Forms.ToolStripDropDownButton>  
 <xref:System.Windows.Forms.ToolStripSplitButton>  
 [ToolStrip 控件概述](../../../../docs/framework/winforms/controls/toolstrip-control-overview-windows-forms.md)
