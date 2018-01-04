---
title: "如何：处理 ContextMenuStrip 打开事件"
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
- ContextMenuStrip control [Windows Forms]
- context menus [Windows Forms], event handling
- ToolStrip control [Windows Forms]
- event handling [Windows Forms], context menus
- shortcut menus [Windows Forms], event handling
ms.assetid: b661b3dd-7815-4cc2-a1aa-a9a391ab3427
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 5de244abd35c83bce329882d679df8303ef3a833
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-handle-the-contextmenustrip-opening-event"></a><span data-ttu-id="b451b-102">如何：处理 ContextMenuStrip 打开事件</span><span class="sxs-lookup"><span data-stu-id="b451b-102">How to: Handle the ContextMenuStrip Opening Event</span></span>
<span data-ttu-id="b451b-103">你可以自定义的行为你<xref:System.Windows.Forms.ContextMenuStrip>通过处理控件<xref:System.Windows.Forms.ToolStripDropDown.Opening>事件。</span><span class="sxs-lookup"><span data-stu-id="b451b-103">You can customize the behavior of your <xref:System.Windows.Forms.ContextMenuStrip> control by handling the <xref:System.Windows.Forms.ToolStripDropDown.Opening> event.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b451b-104">示例</span><span class="sxs-lookup"><span data-stu-id="b451b-104">Example</span></span>  
 <span data-ttu-id="b451b-105">下面的代码示例演示如何处理<xref:System.Windows.Forms.ToolStripDropDown.Opening>事件。</span><span class="sxs-lookup"><span data-stu-id="b451b-105">The following code example demonstrates how to handle the <xref:System.Windows.Forms.ToolStripDropDown.Opening> event.</span></span> <span data-ttu-id="b451b-106">事件处理程序将项添加到动态<xref:System.Windows.Forms.ContextMenuStrip>控件。</span><span class="sxs-lookup"><span data-stu-id="b451b-106">The event handler adds items dynamically to a <xref:System.Windows.Forms.ContextMenuStrip> control.</span></span> <span data-ttu-id="b451b-107">有关完整的代码示例，请参阅[如何： 动态添加 ToolStrip 项](../../../../docs/framework/winforms/controls/how-to-add-toolstrip-items-dynamically.md)。</span><span class="sxs-lookup"><span data-stu-id="b451b-107">For the complete code example, see [How to: Add ToolStrip Items Dynamically](../../../../docs/framework/winforms/controls/how-to-add-toolstrip-items-dynamically.md).</span></span>  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.Misc#42](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#42)]
 [!code-vb[System.Windows.Forms.ToolStrip.Misc#42](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#42)]  
  
 <span data-ttu-id="b451b-108">设置<xref:System.ComponentModel.CancelEventArgs.Cancel%2A?displayProperty=nameWithType>属性`true`以防止打开菜单。</span><span class="sxs-lookup"><span data-stu-id="b451b-108">Set the <xref:System.ComponentModel.CancelEventArgs.Cancel%2A?displayProperty=nameWithType> property to `true` to prevent the menu from opening.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b451b-109">请参阅</span><span class="sxs-lookup"><span data-stu-id="b451b-109">See Also</span></span>  
 <xref:System.Windows.Forms.ContextMenuStrip>  
 <xref:System.ComponentModel.CancelEventArgs.Cancel%2A>  
 <xref:System.Windows.Forms.ToolStripDropDown>  
 [<span data-ttu-id="b451b-110">ToolStrip 控件</span><span class="sxs-lookup"><span data-stu-id="b451b-110">ToolStrip Control</span></span>](../../../../docs/framework/winforms/controls/toolstrip-control-windows-forms.md)
