---
title: "如何：在 Windows 窗体中启用 ToolStrip 项的运行时重新排序"
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
- ToolStrip control [Windows Forms], examples
- examples [Windows Forms], toolbars
- toolbars [Windows Forms], rearranging controls
- ToolStrip control [Windows Forms], reordering items
ms.assetid: 8480b69a-379f-4dc2-8dcf-365ed93692b2
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 73ea6d3615780c8def31b7dbdcf870020a106e80
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-enable-reordering-of-toolstrip-items-at-run-time-in-windows-forms"></a>如何：在 Windows 窗体中启用 ToolStrip 项的运行时重新排序
你可以让用户在重新排列<xref:System.Windows.Forms.ToolStripItem>上的控件<xref:System.Windows.Forms.ToolStrip>。  
  
### <a name="to-enable-toolstripitem-rearrangement-at-run-time"></a>若要启用 ToolStripItem 重新排列在运行时  
  
-   将 <xref:System.Windows.Forms.ToolStrip.AllowItemReorder%2A> 属性设置为 `true`。 默认情况下，<xref:System.Windows.Forms.ToolStrip.AllowItemReorder%2A>是`false`。  
  
     在运行时，同时用户按住 ALT 键和鼠标左键拖动<xref:System.Windows.Forms.ToolStripItem>到上的不同位置<xref:System.Windows.Forms.ToolStrip>。  
  
    ```vb  
    toolStrip1.AllowItemReorder = True  
    ```  
  
    ```csharp  
    toolStrip1.AllowItemReorder = true;  
    ```  
  
## <a name="see-also"></a>另请参阅  
 <xref:System.Windows.Forms.ToolStrip>  
 <xref:System.Windows.Forms.ToolStrip.AllowItemReorder%2A>  
 [ToolStrip 控件概述](../../../../docs/framework/winforms/controls/toolstrip-control-overview-windows-forms.md)  
 [ToolStrip 控件体系结构](../../../../docs/framework/winforms/controls/toolstrip-control-architecture.md)  
 [ToolStrip 技术摘要](../../../../docs/framework/winforms/controls/toolstrip-technology-summary.md)
