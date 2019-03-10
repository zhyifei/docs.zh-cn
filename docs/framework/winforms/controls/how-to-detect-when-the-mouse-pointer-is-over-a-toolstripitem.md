---
title: 如何：检测鼠标指针何时悬停在 toolstripitem 之上
ms.date: 03/30/2017
helpviewer_keywords:
- toolbars [Windows Forms], detecting mouse movement
- ToolStrip control [Windows Forms], detecting mouse movement
- ToolStripItem class [Windows Forms], detecting mouse movement
- mouse [Windows Forms], detecting movement on toolbars
ms.assetid: d38b5082-aba7-4f6c-841b-bd9714e307fd
ms.openlocfilehash: 39173490c31711cca9f26f5f0cb2ab493546dda3
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/09/2019
ms.locfileid: "57720801"
---
# <a name="how-to-detect-when-the-mouse-pointer-is-over-a-toolstripitem"></a><span data-ttu-id="b01c9-102">如何：检测鼠标指针何时悬停在 toolstripitem 之上</span><span class="sxs-lookup"><span data-stu-id="b01c9-102">How to: Detect When the Mouse Pointer Is Over a ToolStripItem</span></span>
<span data-ttu-id="b01c9-103">使用以下过程来检测鼠标指针位于时<xref:System.Windows.Forms.ToolStripItem>。</span><span class="sxs-lookup"><span data-stu-id="b01c9-103">Use the following procedure to detect when the mouse pointer is over a <xref:System.Windows.Forms.ToolStripItem>.</span></span>  
  
### <a name="to-detect-when-the-pointer-is-over-a-toolstripitem"></a><span data-ttu-id="b01c9-104">若要检测鼠标指针何时悬停在 toolstripitem 之上</span><span class="sxs-lookup"><span data-stu-id="b01c9-104">To detect when the pointer is over a ToolStripItem</span></span>  
  
-   <span data-ttu-id="b01c9-105">使用<xref:System.Windows.Forms.ToolStripItem.Selected%2A>属性中的项<xref:System.Windows.Forms.ToolStripItem.CanSelect%2A>是`true`。</span><span class="sxs-lookup"><span data-stu-id="b01c9-105">Use the <xref:System.Windows.Forms.ToolStripItem.Selected%2A> property for items in which <xref:System.Windows.Forms.ToolStripItem.CanSelect%2A> is `true`.</span></span>  
  
     <span data-ttu-id="b01c9-106">这将阻止你无需同步<xref:System.Windows.Forms.ToolStripItem.MouseEnter>和<xref:System.Windows.Forms.ToolStripItem.MouseLeave>事件。</span><span class="sxs-lookup"><span data-stu-id="b01c9-106">This will prevent you from having to synchronize the <xref:System.Windows.Forms.ToolStripItem.MouseEnter> and <xref:System.Windows.Forms.ToolStripItem.MouseLeave> events.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b01c9-107">请参阅</span><span class="sxs-lookup"><span data-stu-id="b01c9-107">See also</span></span>
- <xref:System.Windows.Forms.ToolStripItem>
- <xref:System.Windows.Forms.ToolStripItem.Selected%2A>
- [<span data-ttu-id="b01c9-108">ToolStrip 控件概述</span><span class="sxs-lookup"><span data-stu-id="b01c9-108">ToolStrip Control Overview</span></span>](toolstrip-control-overview-windows-forms.md)
