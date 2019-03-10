---
title: 如何：处理 ContextMenuStrip 打开事件
ms.date: 03/30/2017
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
ms.openlocfilehash: 179411da96362fd9ba42e2b97682f335beb894c1
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/09/2019
ms.locfileid: "57715446"
---
# <a name="how-to-handle-the-contextmenustrip-opening-event"></a><span data-ttu-id="e1e1e-102">如何：处理 ContextMenuStrip 打开事件</span><span class="sxs-lookup"><span data-stu-id="e1e1e-102">How to: Handle the ContextMenuStrip Opening Event</span></span>
<span data-ttu-id="e1e1e-103">您可以自定义的行为在<xref:System.Windows.Forms.ContextMenuStrip>控件通过处理<xref:System.Windows.Forms.ToolStripDropDown.Opening>事件。</span><span class="sxs-lookup"><span data-stu-id="e1e1e-103">You can customize the behavior of your <xref:System.Windows.Forms.ContextMenuStrip> control by handling the <xref:System.Windows.Forms.ToolStripDropDown.Opening> event.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e1e1e-104">示例</span><span class="sxs-lookup"><span data-stu-id="e1e1e-104">Example</span></span>  
 <span data-ttu-id="e1e1e-105">下面的代码示例演示如何处理<xref:System.Windows.Forms.ToolStripDropDown.Opening>事件。</span><span class="sxs-lookup"><span data-stu-id="e1e1e-105">The following code example demonstrates how to handle the <xref:System.Windows.Forms.ToolStripDropDown.Opening> event.</span></span> <span data-ttu-id="e1e1e-106">事件处理程序将添加项目到动态<xref:System.Windows.Forms.ContextMenuStrip>控件。</span><span class="sxs-lookup"><span data-stu-id="e1e1e-106">The event handler adds items dynamically to a <xref:System.Windows.Forms.ContextMenuStrip> control.</span></span> <span data-ttu-id="e1e1e-107">有关完整的代码示例，请参阅[如何：动态添加 ToolStrip 项](how-to-add-toolstrip-items-dynamically.md)。</span><span class="sxs-lookup"><span data-stu-id="e1e1e-107">For the complete code example, see [How to: Add ToolStrip Items Dynamically](how-to-add-toolstrip-items-dynamically.md).</span></span>  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.Misc#42](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#42)]
 [!code-vb[System.Windows.Forms.ToolStrip.Misc#42](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#42)]  
  
 <span data-ttu-id="e1e1e-108">设置<xref:System.ComponentModel.CancelEventArgs.Cancel%2A?displayProperty=nameWithType>属性设置为`true`以防止打开的菜单。</span><span class="sxs-lookup"><span data-stu-id="e1e1e-108">Set the <xref:System.ComponentModel.CancelEventArgs.Cancel%2A?displayProperty=nameWithType> property to `true` to prevent the menu from opening.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e1e1e-109">请参阅</span><span class="sxs-lookup"><span data-stu-id="e1e1e-109">See also</span></span>
- <xref:System.Windows.Forms.ContextMenuStrip>
- <xref:System.ComponentModel.CancelEventArgs.Cancel%2A>
- <xref:System.Windows.Forms.ToolStripDropDown>
- [<span data-ttu-id="e1e1e-110">ToolStrip 控件</span><span class="sxs-lookup"><span data-stu-id="e1e1e-110">ToolStrip Control</span></span>](toolstrip-control-windows-forms.md)
