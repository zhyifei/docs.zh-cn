---
title: "如何：使用设计器用 Windows 窗体 TreeView 控件添加和移除节点"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- examples [Windows Forms], TreeView control
- TreeView control [Windows Forms], removing nodes
- tree nodes in TreeView control
- TreeView control [Windows Forms], adding nodes
ms.assetid: 35bf1750-045e-4ec5-97cb-b47b0dbdaa2c
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 3f6295f915e9204e9996d8902b07a3dfc4c5c2ae
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-add-and-remove-nodes-with-the-windows-forms-treeview-control-using-the-designer"></a><span data-ttu-id="2b2a2-102">如何：使用设计器用 Windows 窗体 TreeView 控件添加和移除节点</span><span class="sxs-lookup"><span data-stu-id="2b2a2-102">How to: Add and Remove Nodes with the Windows Forms TreeView Control Using the Designer</span></span>
<span data-ttu-id="2b2a2-103">因为 Windows 窗体<xref:System.Windows.Forms.TreeView>控件以分层方式，添加你必须注意到其父节点是节点时将显示节点。</span><span class="sxs-lookup"><span data-stu-id="2b2a2-103">Because the Windows Forms <xref:System.Windows.Forms.TreeView> control displays nodes in a hierarchical manner, when adding a node you must pay attention to what its parent node is.</span></span>  
  
 <span data-ttu-id="2b2a2-104">下面的过程需要**Windows 应用程序**具有一个窗体包含项目<xref:System.Windows.Forms.TreeView>控件。</span><span class="sxs-lookup"><span data-stu-id="2b2a2-104">The following procedure requires a **Windows Application** project with a form containing a <xref:System.Windows.Forms.TreeView> control.</span></span> <span data-ttu-id="2b2a2-105">有关设置此类项目的信息，请参阅[如何： 创建 Windows 应用程序项目](http://msdn.microsoft.com/en-us/b2f93fed-c635-4705-8d0e-cf079a264efa)和[如何： 向 Windows 窗体添加控件](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md)。</span><span class="sxs-lookup"><span data-stu-id="2b2a2-105">For information about setting up such a project, see [How to: Create a Windows Application Project](http://msdn.microsoft.com/en-us/b2f93fed-c635-4705-8d0e-cf079a264efa) and [How to: Add Controls to Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2b2a2-106">显示的对话框和菜单命令可能会与“帮助”中的描述不同，具体取决于你现用的设置或版本。</span><span class="sxs-lookup"><span data-stu-id="2b2a2-106">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="2b2a2-107">若要更改设置，请在 **“工具”** 菜单上选择 **“导入和导出设置”** 。</span><span class="sxs-lookup"><span data-stu-id="2b2a2-107">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="2b2a2-108">有关详细信息，请参阅[在 Visual Studio 中自定义开发设置](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3)。</span><span class="sxs-lookup"><span data-stu-id="2b2a2-108">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
### <a name="to-add-or-remove-nodes-in-the-designer"></a><span data-ttu-id="2b2a2-109">若要添加或在设计器中删除节点</span><span class="sxs-lookup"><span data-stu-id="2b2a2-109">To add or remove nodes in the designer</span></span>  
  
1.  <span data-ttu-id="2b2a2-110">选择 <xref:System.Windows.Forms.TreeView> 控件。</span><span class="sxs-lookup"><span data-stu-id="2b2a2-110">Select the <xref:System.Windows.Forms.TreeView> control.</span></span>  
  
2.  <span data-ttu-id="2b2a2-111">在**属性**窗口中，单击**省略号**(![VisualStudioEllipsesButton 屏幕快照](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")) 旁边按钮<xref:System.Windows.Forms.TreeView.Nodes%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="2b2a2-111">In the **Properties** window, click the **Ellipsis** (![VisualStudioEllipsesButton screenshot](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")) button next to the <xref:System.Windows.Forms.TreeView.Nodes%2A> property.</span></span>  
  
     <span data-ttu-id="2b2a2-112">**TreeNode 编辑器**显示。</span><span class="sxs-lookup"><span data-stu-id="2b2a2-112">The **TreeNode Editor** appears.</span></span>  
  
3.  <span data-ttu-id="2b2a2-113">若要添加的节点，必须存在根节点;如果不存在，则首先必须通过单击来添加根**添加根**按钮。</span><span class="sxs-lookup"><span data-stu-id="2b2a2-113">To add nodes, a root node must exist; if one does not exist, you must first add a root by clicking the **Add Root** button.</span></span> <span data-ttu-id="2b2a2-114">然后可以通过选择根节点或任何其他节点，然后单击添加子节点**添加子项**按钮。</span><span class="sxs-lookup"><span data-stu-id="2b2a2-114">You can then add child nodes by selecting the root or any other node and clicking the **Add Child** button.</span></span>  
  
4.  <span data-ttu-id="2b2a2-115">若要删除节点，选择要删除，然后单击的节点**删除**按钮。</span><span class="sxs-lookup"><span data-stu-id="2b2a2-115">To delete nodes, select the node to delete and then click the **Delete** button.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2b2a2-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2b2a2-116">See Also</span></span>  
 [<span data-ttu-id="2b2a2-117">TreeView 控件</span><span class="sxs-lookup"><span data-stu-id="2b2a2-117">TreeView Control</span></span>](../../../../docs/framework/winforms/controls/treeview-control-windows-forms.md)  
 [<span data-ttu-id="2b2a2-118">TreeView 控件概述</span><span class="sxs-lookup"><span data-stu-id="2b2a2-118">TreeView Control Overview</span></span>](../../../../docs/framework/winforms/controls/treeview-control-overview-windows-forms.md)  
 [<span data-ttu-id="2b2a2-119">如何：设置 Windows 窗体 TreeView 控件的图标</span><span class="sxs-lookup"><span data-stu-id="2b2a2-119">How to: Set Icons for the Windows Forms TreeView Control</span></span>](../../../../docs/framework/winforms/controls/how-to-set-icons-for-the-windows-forms-treeview-control.md)  
 [<span data-ttu-id="2b2a2-120">如何：循环访问 Windows 窗体 TreeView 控件的所有节点</span><span class="sxs-lookup"><span data-stu-id="2b2a2-120">How to: Iterate Through All Nodes of a Windows Forms TreeView Control</span></span>](../../../../docs/framework/winforms/controls/how-to-iterate-through-all-nodes-of-a-windows-forms-treeview-control.md)  
 [<span data-ttu-id="2b2a2-121">如何：确定哪个 TreeView 节点获得了单击</span><span class="sxs-lookup"><span data-stu-id="2b2a2-121">How to: Determine Which TreeView Node Was Clicked</span></span>](../../../../docs/framework/winforms/controls/how-to-determine-which-treeview-node-was-clicked-windows-forms.md)  
 [<span data-ttu-id="2b2a2-122">如何：向 TreeView 或 ListView 控件（Windows 窗体）添加自定义信息</span><span class="sxs-lookup"><span data-stu-id="2b2a2-122">How to: Add Custom Information to a TreeView or ListView Control (Windows Forms)</span></span>](../../../../docs/framework/winforms/controls/add-custom-information-to-a-treeview-or-listview-control-wf.md)
