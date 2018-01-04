---
title: "如何：在 Windows 窗体中更改 ToolStrip 项的间距和对齐方式"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ToolStrip control [Windows Forms], aligning items
- examples [Windows Forms], toolbars
- toolbars [Windows Forms], aligning items
ms.assetid: cd483466-0f49-43df-addf-e2b5fcd64027
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 58cad83b7253b71363f9ccf7fbda74e03803f381
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-change-the-spacing-and-alignment-of-toolstrip-items-in-windows-forms"></a>如何：在 Windows 窗体中更改 ToolStrip 项的间距和对齐方式
<xref:System.Windows.Forms.ToolStrip>控件完全支持布局功能，如调整大小的间距<xref:System.Windows.Forms.ToolStripItem>上的控件相对于彼此，控件的排列<xref:System.Windows.Forms.ToolStrip>，以及相对于控件的间距<xref:System.Windows.Forms.ToolStrip>。  
  
 因为的默认值<xref:System.Windows.Forms.ToolStripItem.AutoSize%2A>属性是`true`，除非你设置，将自动调整控件<xref:System.Windows.Forms.ToolStripItem.AutoSize%2A>属性`false`。  
  
### <a name="to-manually-size-a-toolstripitem"></a>若要手动调整大小 ToolStripItem  
  
1.  设置<xref:System.Windows.Forms.ToolStripItem.AutoSize%2A>属性`false`关联的控件。  
  
    ```vb  
    ToolStripButton1.AutoSize = False  
    ```  
  
    ```csharp  
    toolStripButton1.AutoSize = false;  
    ```  
  
2.  设置<xref:System.Windows.Forms.ToolStripItem.Size%2A>属性关联的所需的方式<xref:System.Windows.Forms.ToolStripItem>。  
  
### <a name="to-set-the-spacing-of-a-toolstripitem"></a>若要设置 ToolStripItem 的间距  
  
1.  将所需的值，以像素为单位，插入<xref:System.Windows.Forms.ToolStripItem.Margin%2A>关联控件的属性。  
  
     值<xref:System.Windows.Forms.ToolStripItem.Margin%2A>属性按此顺序指定项与相邻项之间的间距： 左侧、 顶部、 右侧和底部。  
  
    ```vb  
    ToolStripTextBox1.Margin = New System.Windows.Forms.Padding _  
        (3, 0, 3, 0)  
    ```  
  
    ```csharp  
    toolStripTextBox1.Margin = new System.Windows.Forms.Padding   
        (3, 0, 3, 0);  
    ```  
  
### <a name="to-align-a-toolstripitem-to-the-right-side-of-the-toolstrip"></a>若要对齐 ToolStrip 右侧 ToolStripItem  
  
1.  设置<xref:System.Windows.Forms.ToolStripItem.Alignment%2A>属性<xref:System.Windows.Forms.ToolStripItemAlignment.Right>关联的控件。 默认情况下，<xref:System.Windows.Forms.ToolStripItem.Alignment%2A>设置为<xref:System.Windows.Forms.ToolStripItemAlignment.Left>，这将控件的左侧对齐<xref:System.Windows.Forms.ToolStrip>。  
  
    ```vb  
    ToolStripSplitButton1.Alignment = _  
        System.Windows.Forms.ToolStripItemAlignment.Right  
    ```  
  
    ```csharp  
    toolStripSplitButton1.Alignment =   
        System.Windows.Forms.ToolStripItemAlignment.Right;  
    ```  
  
### <a name="to-arrange-toolstrip-items-on-the-toolstrip"></a>可以排列工具条上的 ToolStrip 项  
  
-   设置<xref:System.Windows.Forms.ToolStrip.LayoutStyle%2A>属性的值<xref:System.Windows.Forms.ToolStripLayoutStyle>所需。  
  
    ```vb  
    ToolStripDropDown1.LayoutStyle = _  
        System.Windows.Forms.ToolStripLayoutStyle.Flow  
    ```  
  
    ```csharp  
    toolStripDropDown1.LayoutStyle =   
        System.Windows.Forms.ToolStripLayoutStyle.Flow;  
    ```  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Windows.Forms.ToolStrip>  
 <xref:System.Windows.Forms.Control.Layout>  
 <xref:System.Windows.Forms.ToolStrip.LayoutCompleted>  
 <xref:System.Windows.Forms.ToolStrip.LayoutSettings%2A>  
 <xref:System.Windows.Forms.ToolStripItem.TextImageRelation%2A>  
 <xref:System.Windows.Forms.ToolStripItem.Placement%2A>  
 <xref:System.Windows.Forms.ToolStrip.CanOverflow%2A>  
 [ToolStrip 控件概述](../../../../docs/framework/winforms/controls/toolstrip-control-overview-windows-forms.md)  
 [ToolStrip 控件体系结构](../../../../docs/framework/winforms/controls/toolstrip-control-architecture.md)  
 [ToolStrip 技术摘要](../../../../docs/framework/winforms/controls/toolstrip-technology-summary.md)
