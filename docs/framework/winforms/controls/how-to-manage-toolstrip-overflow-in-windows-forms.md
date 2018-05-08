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
# <a name="how-to-manage-toolstrip-overflow-in-windows-forms"></a>如何：在 Windows 窗体中管理 ToolStrip 溢出
当上的所有项<xref:System.Windows.Forms.ToolStrip>控件不适合在分配的空间，则可以在启用溢出功能<xref:System.Windows.Forms.ToolStrip>并确定特定的溢出行为<xref:System.Windows.Forms.ToolStripItem>s。  
  
 当你将添加<xref:System.Windows.Forms.ToolStripItem>需要更多的空间比已分配到的 s<xref:System.Windows.Forms.ToolStrip>给定窗体的当前大小，<xref:System.Windows.Forms.ToolStripOverflowButton>会自动出现在<xref:System.Windows.Forms.ToolStrip>。 <xref:System.Windows.Forms.ToolStripOverflowButton>出现，并启用了溢出的项移到下拉列表溢出菜单。 这使您可以自定义并划分其优先级如何你<xref:System.Windows.Forms.ToolStrip>项未能正确地调整到不同的窗体大小。 你还可以更改你的项的外观，当它们发生溢出时，通过使用<xref:System.Windows.Forms.ToolStripItem.Placement%2A>和<xref:System.Windows.Forms.ToolStripOverflow.DisplayedItems%2A?displayProperty=nameWithType>属性和<xref:System.Windows.Forms.ToolStrip.LayoutCompleted>事件。 如果你扩大窗体在设计时或运行的时，更<xref:System.Windows.Forms.ToolStripItem>s 可以显示在主<xref:System.Windows.Forms.ToolStrip>和<xref:System.Windows.Forms.ToolStripOverflowButton>甚至可能会消失，直到减小窗体的大小。  
  
### <a name="to-enable-overflow-on-a-toolstrip-control"></a>若要启用溢出的 ToolStrip 控件  
  
-   确保<xref:System.Windows.Forms.ToolStrip.CanOverflow%2A>属性未设置为`false`为<xref:System.Windows.Forms.ToolStrip>。 默认值为 `True`。  
  
     当<xref:System.Windows.Forms.ToolStrip.CanOverflow%2A>是`True`（默认值）、<xref:System.Windows.Forms.ToolStripItem>发送到下拉列表溢出菜单时的内容<xref:System.Windows.Forms.ToolStripItem>超过的水平宽度<xref:System.Windows.Forms.ToolStrip>或高度的垂直<xref:System.Windows.Forms.ToolStrip>。  
  
### <a name="to-specify-overflow-behavior-of-a-specific-toolstripitem"></a>若要指定特定 ToolStripItem 溢出行为  
  
-   设置<xref:System.Windows.Forms.ToolStripItem.Overflow%2A>属性<xref:System.Windows.Forms.ToolStripItem>到所需的值。 可能的匹配项是`Always`， `Never`，和`AsNeeded`。 Defaultis `AsNeeded`。  
  
    ```vb  
    toolStripTextBox1.Overflow = _  
    System.Windows.Forms.ToolStripItemOverflow.Never  
    ```  
  
    ```csharp  
    toolStripTextBox1.Overflow = _  
    System.Windows.Forms.ToolStripItemOverflow.Never;  
    ```  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Windows.Forms.ToolStrip>  
 <xref:System.Windows.Forms.ToolStripOverflowButton>  
 <xref:System.Windows.Forms.ToolStripItem.Overflow%2A>  
 <xref:System.Windows.Forms.ToolStrip.CanOverflow%2A>  
 [ToolStrip 控件概述](../../../../docs/framework/winforms/controls/toolstrip-control-overview-windows-forms.md)  
 [ToolStrip 控件体系结构](../../../../docs/framework/winforms/controls/toolstrip-control-architecture.md)  
 [ToolStrip 技术摘要](../../../../docs/framework/winforms/controls/toolstrip-technology-summary.md)
