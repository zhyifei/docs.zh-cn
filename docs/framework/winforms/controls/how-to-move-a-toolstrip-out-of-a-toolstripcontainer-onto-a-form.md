---
title: "如何：将 ToolStrip 从 ToolStripContainer 移到窗体上"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- ToolStrip control [Windows Forms], parenting to forms
- Windows Forms, parenting ToolStrip controls
ms.assetid: a1c94a7f-6fc5-4e4c-84cf-ff11dc573d33
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: daa372397a3c85ef8359261c4816fbba664928bf
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-move-a-toolstrip-out-of-a-toolstripcontainer-onto-a-form"></a><span data-ttu-id="937a3-102">如何：将 ToolStrip 从 ToolStripContainer 移到窗体上</span><span class="sxs-lookup"><span data-stu-id="937a3-102">How to: Move a ToolStrip Out of a ToolStripContainer onto a Form</span></span>
<span data-ttu-id="937a3-103">使用以下过程移动<xref:System.Windows.Forms.ToolStrip>外<xref:System.Windows.Forms.ToolStripContainer>拖到窗体。</span><span class="sxs-lookup"><span data-stu-id="937a3-103">Use the following procedure to move a <xref:System.Windows.Forms.ToolStrip> out of a <xref:System.Windows.Forms.ToolStripContainer> onto a form.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="937a3-104">显示的对话框和菜单命令可能会与“帮助”中的描述不同，具体取决于你现用的设置或版本。</span><span class="sxs-lookup"><span data-stu-id="937a3-104">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="937a3-105">若要更改设置，请在 **“工具”** 菜单上选择 **“导入和导出设置”** 。</span><span class="sxs-lookup"><span data-stu-id="937a3-105">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="937a3-106">有关详细信息，请参阅 [在 Visual Studio 中自定义开发设置](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3)。</span><span class="sxs-lookup"><span data-stu-id="937a3-106">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
### <a name="to-move-a-toolstrip-out-of-a-toolstripcontainer-onto-a-form"></a><span data-ttu-id="937a3-107">若要移动的 ToolStrip 从 toolstripcontainer 移到窗体外</span><span class="sxs-lookup"><span data-stu-id="937a3-107">To move a ToolStrip out of a ToolStripContainer onto a form</span></span>  
  
1.  <span data-ttu-id="937a3-108">选择 <xref:System.Windows.Forms.ToolStrip>。</span><span class="sxs-lookup"><span data-stu-id="937a3-108">Select the <xref:System.Windows.Forms.ToolStrip>.</span></span>  
  
2.  <span data-ttu-id="937a3-109">剪切<xref:System.Windows.Forms.ToolStrip>通过按 CTRL + X，或右键单击<xref:System.Windows.Forms.ToolStrip>选择**剪切**从上下文菜单。</span><span class="sxs-lookup"><span data-stu-id="937a3-109">Cut the <xref:System.Windows.Forms.ToolStrip> by pressing CTRL+X, or right-click the <xref:System.Windows.Forms.ToolStrip> and choose **Cut** from the context menu.</span></span>  
  
3.  <span data-ttu-id="937a3-110">选择窗体。</span><span class="sxs-lookup"><span data-stu-id="937a3-110">Select the form.</span></span>  
  
4.  <span data-ttu-id="937a3-111">粘贴<xref:System.Windows.Forms.ToolStrip>通过按 CTRL + V，或选择**粘贴**从**编辑**菜单。</span><span class="sxs-lookup"><span data-stu-id="937a3-111">Paste the <xref:System.Windows.Forms.ToolStrip> by pressing CTRL+V, or choose **Paste** from the **Edit** menu.</span></span>  
  
5.  <span data-ttu-id="937a3-112">设置<xref:System.Windows.Forms.ToolStrip.Dock%2A>属性<xref:System.Windows.Forms.ToolStrip>到**顶部**。</span><span class="sxs-lookup"><span data-stu-id="937a3-112">Set the <xref:System.Windows.Forms.ToolStrip.Dock%2A> property of the <xref:System.Windows.Forms.ToolStrip> to **Top**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="937a3-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="937a3-113">See Also</span></span>  
 <xref:System.Windows.Forms.ToolStrip>  
 <xref:System.Windows.Forms.ToolStripContainer>  
 [<span data-ttu-id="937a3-114">ToolStrip 控件概述</span><span class="sxs-lookup"><span data-stu-id="937a3-114">ToolStrip Control Overview</span></span>](../../../../docs/framework/winforms/controls/toolstrip-control-overview-windows-forms.md)
