---
title: "如何：将快捷菜单附加到 TreeView 节点"
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
- cpp
helpviewer_keywords:
- shortcut menus [Windows Forms], adding to TreeView controls
- TreeView control [Windows Forms], adding shortcut menus
- tree nodes in TreeView control [Windows Forms], shortcut menus
ms.assetid: a23c6752-fd8f-44ad-b781-bab37962fc7c
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ca251c9dec87db0ecb4b565b522839ace7f44479
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-attach-a-shortcut-menu-to-a-treeview-node"></a><span data-ttu-id="1391d-102">如何：将快捷菜单附加到 TreeView 节点</span><span class="sxs-lookup"><span data-stu-id="1391d-102">How to: Attach a ShortCut Menu to a TreeView Node</span></span>
<span data-ttu-id="1391d-103">Windows 窗体<xref:System.Windows.Forms.TreeView>控件显示节点，类似于文件和文件夹在 Windows 资源管理器的左窗格中显示的层次结构。</span><span class="sxs-lookup"><span data-stu-id="1391d-103">The Windows Forms <xref:System.Windows.Forms.TreeView> control displays a hierarchy of nodes, similar to the files and folders displayed in the left pane of Windows Explorer.</span></span> <span data-ttu-id="1391d-104">通过设置<xref:System.Windows.Forms.Control.ContextMenuStrip%2A>属性，你可以提供区分上下文的操作向用户时用户右击<xref:System.Windows.Forms.TreeView>控件。</span><span class="sxs-lookup"><span data-stu-id="1391d-104">By setting the <xref:System.Windows.Forms.Control.ContextMenuStrip%2A> property, you can provide context-sensitive operations to the user when they right-click the <xref:System.Windows.Forms.TreeView> control.</span></span> <span data-ttu-id="1391d-105">通过将相关联<xref:System.Windows.Forms.ContextMenuStrip>组件与单个<xref:System.Windows.Forms.TreeNode>项，可以添加到快捷菜单功能的自定义的级别你<xref:System.Windows.Forms.TreeView>控件。</span><span class="sxs-lookup"><span data-stu-id="1391d-105">By associating a <xref:System.Windows.Forms.ContextMenuStrip> component with individual <xref:System.Windows.Forms.TreeNode> items, you can add a customized level of shortcut menu functionality to your <xref:System.Windows.Forms.TreeView> controls.</span></span>  
  
### <a name="to-associate-a-shortcut-menu-with-a-treenode-programmatically"></a><span data-ttu-id="1391d-106">要以编程方式与树节点关联的快捷菜单</span><span class="sxs-lookup"><span data-stu-id="1391d-106">To associate a shortcut menu with a TreeNode programmatically</span></span>  
  
1.  <span data-ttu-id="1391d-107">实例化<xref:System.Windows.Forms.TreeView>控件替换为相应的属性设置，创建一个根<xref:System.Windows.Forms.TreeNode>，并将子节点。</span><span class="sxs-lookup"><span data-stu-id="1391d-107">Instantiate a <xref:System.Windows.Forms.TreeView> control with the appropriate property settings, create a root <xref:System.Windows.Forms.TreeNode>, and then add subnodes.</span></span>  
  
2.  <span data-ttu-id="1391d-108">实例化<xref:System.Windows.Forms.ContextMenuStrip>组件，然后添加<xref:System.Windows.Forms.ToolStripMenuItem>为你想要在运行时提供每个操作。</span><span class="sxs-lookup"><span data-stu-id="1391d-108">Instantiate a <xref:System.Windows.Forms.ContextMenuStrip> component, and then add a <xref:System.Windows.Forms.ToolStripMenuItem> for each operation you want to make available at run time.</span></span>  
  
3.  <span data-ttu-id="1391d-109">设置<xref:System.Windows.Forms.TreeNode.ContextMenuStrip%2A>与相应的属性<xref:System.Windows.Forms.TreeNode>到你创建的快捷菜单。</span><span class="sxs-lookup"><span data-stu-id="1391d-109">Set the <xref:System.Windows.Forms.TreeNode.ContextMenuStrip%2A> property of the appropriate <xref:System.Windows.Forms.TreeNode> to the shortcut menu you create.</span></span>  
  
4.  <span data-ttu-id="1391d-110">当设置此属性时，右键单击节点时，将显示的快捷菜单。</span><span class="sxs-lookup"><span data-stu-id="1391d-110">When this property is set, the shortcut menu will be displayed when you right-click the node.</span></span>  
  
 <span data-ttu-id="1391d-111">下面的代码示例创建一个基本<xref:System.Windows.Forms.TreeView>和<xref:System.Windows.Forms.ContextMenuStrip>与的根关联<xref:System.Windows.Forms.TreeNode>的<xref:System.Windows.Forms.TreeView>。</span><span class="sxs-lookup"><span data-stu-id="1391d-111">The following code example creates a basic <xref:System.Windows.Forms.TreeView> and <xref:System.Windows.Forms.ContextMenuStrip> associated with the root <xref:System.Windows.Forms.TreeNode> of the <xref:System.Windows.Forms.TreeView>.</span></span> <span data-ttu-id="1391d-112">你将需要自定义为适合的菜单选项<xref:System.Windows.Forms.TreeView>你正在开发。</span><span class="sxs-lookup"><span data-stu-id="1391d-112">You will need to customize the menu choices to those that fit the <xref:System.Windows.Forms.TreeView> you are developing.</span></span> <span data-ttu-id="1391d-113">此外，你将想要编写代码来处理<xref:System.Windows.Forms.ToolStripItem.Click>这些菜单项的事件。</span><span class="sxs-lookup"><span data-stu-id="1391d-113">Additionally, you will want to write code to handle the <xref:System.Windows.Forms.ToolStripItem.Click> events for these menu items.</span></span>  
  
 [!code-cpp[System.Windows.Forms.TreeNodeContextMenuStrip#1](../../../../samples/snippets/cpp/VS_Snippets_Winforms/system.windows.forms.TreeNodeContextMenuStrip/cpp/Form1.cpp#1)]
 [!code-csharp[System.Windows.Forms.TreeNodeContextMenuStrip#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/system.windows.forms.TreeNodeContextMenuStrip/CS/Form1.cs#1)]
 [!code-vb[System.Windows.Forms.TreeNodeContextMenuStrip#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/system.windows.forms.TreeNodeContextMenuStrip/VB/Form1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="1391d-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="1391d-114">See Also</span></span>  
 <xref:System.Windows.Forms.ContextMenuStrip>  
 [<span data-ttu-id="1391d-115">TreeView 控件</span><span class="sxs-lookup"><span data-stu-id="1391d-115">TreeView Control</span></span>](../../../../docs/framework/winforms/controls/treeview-control-windows-forms.md)
