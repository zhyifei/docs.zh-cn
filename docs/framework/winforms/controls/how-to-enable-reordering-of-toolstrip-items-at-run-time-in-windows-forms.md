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
# <a name="how-to-enable-reordering-of-toolstrip-items-at-run-time-in-windows-forms"></a><span data-ttu-id="e3260-102">如何：在 Windows 窗体中启用 ToolStrip 项的运行时重新排序</span><span class="sxs-lookup"><span data-stu-id="e3260-102">How to: Enable Reordering of ToolStrip Items at Run Time in Windows Forms</span></span>
<span data-ttu-id="e3260-103">可以让用户重新排列 <xref:System.Windows.Forms.ToolStrip>上 <xref:System.Windows.Forms.ToolStripItem> 控件。</span><span class="sxs-lookup"><span data-stu-id="e3260-103">You can enable the user to rearrange <xref:System.Windows.Forms.ToolStripItem> controls on the <xref:System.Windows.Forms.ToolStrip>.</span></span>  
  
### <a name="to-enable-toolstripitem-rearrangement-at-run-time"></a><span data-ttu-id="e3260-104">在运行时启用 ToolStripItem 重排</span><span class="sxs-lookup"><span data-stu-id="e3260-104">To enable ToolStripItem rearrangement at run time</span></span>  
  
- <span data-ttu-id="e3260-105">将 <xref:System.Windows.Forms.ToolStrip.AllowItemReorder%2A> 属性设置为 `true`。</span><span class="sxs-lookup"><span data-stu-id="e3260-105">Set the <xref:System.Windows.Forms.ToolStrip.AllowItemReorder%2A> property to `true`.</span></span> <span data-ttu-id="e3260-106">默认情况下，<xref:System.Windows.Forms.ToolStrip.AllowItemReorder%2A> `false`。</span><span class="sxs-lookup"><span data-stu-id="e3260-106">By default, <xref:System.Windows.Forms.ToolStrip.AllowItemReorder%2A> is `false`.</span></span>  
  
     <span data-ttu-id="e3260-107">在运行时，用户按下 ALT 键和鼠标左键，将 <xref:System.Windows.Forms.ToolStripItem> 拖动到 <xref:System.Windows.Forms.ToolStrip>上的其他位置。</span><span class="sxs-lookup"><span data-stu-id="e3260-107">At run time, the user holds down the ALT key and the left mouse button to drag a <xref:System.Windows.Forms.ToolStripItem> to a different location on the <xref:System.Windows.Forms.ToolStrip>.</span></span>  
  
    ```vb  
    toolStrip1.AllowItemReorder = True  
    ```  
  
    ```csharp  
    toolStrip1.AllowItemReorder = true;  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="e3260-108">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e3260-108">See also</span></span>

- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.ToolStrip.AllowItemReorder%2A>
- [<span data-ttu-id="e3260-109">ToolStrip 控件概述</span><span class="sxs-lookup"><span data-stu-id="e3260-109">ToolStrip Control Overview</span></span>](toolstrip-control-overview-windows-forms.md)
- [<span data-ttu-id="e3260-110">ToolStrip 控件体系结构</span><span class="sxs-lookup"><span data-stu-id="e3260-110">ToolStrip Control Architecture</span></span>](toolstrip-control-architecture.md)
- [<span data-ttu-id="e3260-111">ToolStrip 技术摘要</span><span class="sxs-lookup"><span data-stu-id="e3260-111">ToolStrip Technology Summary</span></span>](toolstrip-technology-summary.md)
