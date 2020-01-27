---
title: 如何：启用 ToolStrip 项的运行时重新排序
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ToolStrip control [Windows Forms], examples
- examples [Windows Forms], toolbars
- toolbars [Windows Forms], rearranging controls
- ToolStrip control [Windows Forms], reordering items
ms.assetid: 8480b69a-379f-4dc2-8dcf-365ed93692b2
ms.openlocfilehash: 44b52bf997819f090569d08eb395d8af18f61370
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745487"
---
# <a name="how-to-enable-reordering-of-toolstrip-items-at-run-time-in-windows-forms"></a>如何：在 Windows 窗体中启用 ToolStrip 项的运行时重新排序
可以让用户重新排列 <xref:System.Windows.Forms.ToolStrip>上 <xref:System.Windows.Forms.ToolStripItem> 控件。  
  
### <a name="to-enable-toolstripitem-rearrangement-at-run-time"></a>在运行时启用 ToolStripItem 重排  
  
- 将 <xref:System.Windows.Forms.ToolStrip.AllowItemReorder%2A> 属性设置为 `true`。 默认情况下，<xref:System.Windows.Forms.ToolStrip.AllowItemReorder%2A> `false`。  
  
     在运行时，用户按下 ALT 键和鼠标左键，将 <xref:System.Windows.Forms.ToolStripItem> 拖动到 <xref:System.Windows.Forms.ToolStrip>上的其他位置。  
  
    ```vb  
    toolStrip1.AllowItemReorder = True  
    ```  
  
    ```csharp  
    toolStrip1.AllowItemReorder = true;  
    ```  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.ToolStrip.AllowItemReorder%2A>
- [ToolStrip 控件概述](toolstrip-control-overview-windows-forms.md)
- [ToolStrip 控件体系结构](toolstrip-control-architecture.md)
- [ToolStrip 技术摘要](toolstrip-technology-summary.md)
