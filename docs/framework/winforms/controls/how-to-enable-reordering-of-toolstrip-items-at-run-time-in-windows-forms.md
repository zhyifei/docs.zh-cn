---
title: 如何：在 Windows 窗体中启用 ToolStrip 项的运行时重新排序
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
ms.openlocfilehash: e3f4510071c83b9d1baab358d4962b54fb7361ee
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33531617"
---
# <a name="how-to-enable-reordering-of-toolstrip-items-at-run-time-in-windows-forms"></a><span data-ttu-id="64294-102">如何：在 Windows 窗体中启用 ToolStrip 项的运行时重新排序</span><span class="sxs-lookup"><span data-stu-id="64294-102">How to: Enable Reordering of ToolStrip Items at Run Time in Windows Forms</span></span>
<span data-ttu-id="64294-103">你可以让用户在重新排列<xref:System.Windows.Forms.ToolStripItem>上的控件<xref:System.Windows.Forms.ToolStrip>。</span><span class="sxs-lookup"><span data-stu-id="64294-103">You can enable the user to rearrange <xref:System.Windows.Forms.ToolStripItem> controls on the <xref:System.Windows.Forms.ToolStrip>.</span></span>  
  
### <a name="to-enable-toolstripitem-rearrangement-at-run-time"></a><span data-ttu-id="64294-104">若要启用 ToolStripItem 重新排列在运行时</span><span class="sxs-lookup"><span data-stu-id="64294-104">To enable ToolStripItem rearrangement at run time</span></span>  
  
-   <span data-ttu-id="64294-105">将 <xref:System.Windows.Forms.ToolStrip.AllowItemReorder%2A> 属性设置为 `true`。</span><span class="sxs-lookup"><span data-stu-id="64294-105">Set the <xref:System.Windows.Forms.ToolStrip.AllowItemReorder%2A> property to `true`.</span></span> <span data-ttu-id="64294-106">默认情况下，<xref:System.Windows.Forms.ToolStrip.AllowItemReorder%2A>是`false`。</span><span class="sxs-lookup"><span data-stu-id="64294-106">By default, <xref:System.Windows.Forms.ToolStrip.AllowItemReorder%2A> is `false`.</span></span>  
  
     <span data-ttu-id="64294-107">在运行时，同时用户按住 ALT 键和鼠标左键拖动<xref:System.Windows.Forms.ToolStripItem>到上的不同位置<xref:System.Windows.Forms.ToolStrip>。</span><span class="sxs-lookup"><span data-stu-id="64294-107">At run time, the user holds down the ALT key and the left mouse button to drag a <xref:System.Windows.Forms.ToolStripItem> to a different location on the <xref:System.Windows.Forms.ToolStrip>.</span></span>  
  
    ```vb  
    toolStrip1.AllowItemReorder = True  
    ```  
  
    ```csharp  
    toolStrip1.AllowItemReorder = true;  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="64294-108">请参阅</span><span class="sxs-lookup"><span data-stu-id="64294-108">See Also</span></span>  
 <xref:System.Windows.Forms.ToolStrip>  
 <xref:System.Windows.Forms.ToolStrip.AllowItemReorder%2A>  
 [<span data-ttu-id="64294-109">ToolStrip 控件概述</span><span class="sxs-lookup"><span data-stu-id="64294-109">ToolStrip Control Overview</span></span>](../../../../docs/framework/winforms/controls/toolstrip-control-overview-windows-forms.md)  
 [<span data-ttu-id="64294-110">ToolStrip 控件体系结构</span><span class="sxs-lookup"><span data-stu-id="64294-110">ToolStrip Control Architecture</span></span>](../../../../docs/framework/winforms/controls/toolstrip-control-architecture.md)  
 [<span data-ttu-id="64294-111">ToolStrip 技术摘要</span><span class="sxs-lookup"><span data-stu-id="64294-111">ToolStrip Technology Summary</span></span>](../../../../docs/framework/winforms/controls/toolstrip-technology-summary.md)
