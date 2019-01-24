---
title: 如何：将快捷菜单附加到 TreeView 节点
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- shortcut menus [Windows Forms], adding to TreeView controls
- TreeView control [Windows Forms], adding shortcut menus
- tree nodes in TreeView control [Windows Forms], shortcut menus
ms.assetid: a23c6752-fd8f-44ad-b781-bab37962fc7c
ms.openlocfilehash: 7c9e2a2fc51628116a7762e343f36f9f7e93fe67
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54685199"
---
# <a name="how-to-attach-a-shortcut-menu-to-a-treeview-node"></a><span data-ttu-id="a9de0-102">如何：将快捷菜单附加到 TreeView 节点</span><span class="sxs-lookup"><span data-stu-id="a9de0-102">How to: Attach a ShortCut Menu to a TreeView Node</span></span>
<span data-ttu-id="a9de0-103">Windows 窗体<xref:System.Windows.Forms.TreeView>控件显示节点，类似于文件和文件夹显示在 Windows 资源管理器的左窗格中的层次结构。</span><span class="sxs-lookup"><span data-stu-id="a9de0-103">The Windows Forms <xref:System.Windows.Forms.TreeView> control displays a hierarchy of nodes, similar to the files and folders displayed in the left pane of Windows Explorer.</span></span> <span data-ttu-id="a9de0-104">通过设置<xref:System.Windows.Forms.Control.ContextMenuStrip%2A>属性，您可以区分上下文的操作向用户提供他们右键单击时<xref:System.Windows.Forms.TreeView>控件。</span><span class="sxs-lookup"><span data-stu-id="a9de0-104">By setting the <xref:System.Windows.Forms.Control.ContextMenuStrip%2A> property, you can provide context-sensitive operations to the user when they right-click the <xref:System.Windows.Forms.TreeView> control.</span></span> <span data-ttu-id="a9de0-105">通过将相关联<xref:System.Windows.Forms.ContextMenuStrip>组件与单个<xref:System.Windows.Forms.TreeNode>项，可以添加到快捷菜单上功能的自定义的级别应用<xref:System.Windows.Forms.TreeView>控件。</span><span class="sxs-lookup"><span data-stu-id="a9de0-105">By associating a <xref:System.Windows.Forms.ContextMenuStrip> component with individual <xref:System.Windows.Forms.TreeNode> items, you can add a customized level of shortcut menu functionality to your <xref:System.Windows.Forms.TreeView> controls.</span></span>  
  
### <a name="to-associate-a-shortcut-menu-with-a-treenode-programmatically"></a><span data-ttu-id="a9de0-106">要以编程方式与树节点关联的快捷菜单</span><span class="sxs-lookup"><span data-stu-id="a9de0-106">To associate a shortcut menu with a TreeNode programmatically</span></span>  
  
1.  <span data-ttu-id="a9de0-107">实例化<xref:System.Windows.Forms.TreeView>控件的相应属性设置，创建一个根<xref:System.Windows.Forms.TreeNode>，以及如何将子节点。</span><span class="sxs-lookup"><span data-stu-id="a9de0-107">Instantiate a <xref:System.Windows.Forms.TreeView> control with the appropriate property settings, create a root <xref:System.Windows.Forms.TreeNode>, and then add subnodes.</span></span>  
  
2.  <span data-ttu-id="a9de0-108">实例化<xref:System.Windows.Forms.ContextMenuStrip>组件，以及如何将<xref:System.Windows.Forms.ToolStripMenuItem>为想要在运行时提供每个操作。</span><span class="sxs-lookup"><span data-stu-id="a9de0-108">Instantiate a <xref:System.Windows.Forms.ContextMenuStrip> component, and then add a <xref:System.Windows.Forms.ToolStripMenuItem> for each operation you want to make available at run time.</span></span>  
  
3.  <span data-ttu-id="a9de0-109">设置<xref:System.Windows.Forms.TreeNode.ContextMenuStrip%2A>属性的相应<xref:System.Windows.Forms.TreeNode>到你创建的快捷菜单。</span><span class="sxs-lookup"><span data-stu-id="a9de0-109">Set the <xref:System.Windows.Forms.TreeNode.ContextMenuStrip%2A> property of the appropriate <xref:System.Windows.Forms.TreeNode> to the shortcut menu you create.</span></span>  
  
4.  <span data-ttu-id="a9de0-110">当设置此属性时，右键单击节点时，将显示的快捷菜单。</span><span class="sxs-lookup"><span data-stu-id="a9de0-110">When this property is set, the shortcut menu will be displayed when you right-click the node.</span></span>  
  
 <span data-ttu-id="a9de0-111">下面的代码示例将创建一个基本<xref:System.Windows.Forms.TreeView>并<xref:System.Windows.Forms.ContextMenuStrip>与根关联<xref:System.Windows.Forms.TreeNode>的<xref:System.Windows.Forms.TreeView>。</span><span class="sxs-lookup"><span data-stu-id="a9de0-111">The following code example creates a basic <xref:System.Windows.Forms.TreeView> and <xref:System.Windows.Forms.ContextMenuStrip> associated with the root <xref:System.Windows.Forms.TreeNode> of the <xref:System.Windows.Forms.TreeView>.</span></span> <span data-ttu-id="a9de0-112">将需要自定义菜单选项为适合<xref:System.Windows.Forms.TreeView>进行开发。</span><span class="sxs-lookup"><span data-stu-id="a9de0-112">You will need to customize the menu choices to those that fit the <xref:System.Windows.Forms.TreeView> you are developing.</span></span> <span data-ttu-id="a9de0-113">此外，你将想要编写代码来处理<xref:System.Windows.Forms.ToolStripItem.Click>这些菜单项的事件。</span><span class="sxs-lookup"><span data-stu-id="a9de0-113">Additionally, you will want to write code to handle the <xref:System.Windows.Forms.ToolStripItem.Click> events for these menu items.</span></span>  
  
 [!code-cpp[System.Windows.Forms.TreeNodeContextMenuStrip#1](../../../../samples/snippets/cpp/VS_Snippets_Winforms/system.windows.forms.TreeNodeContextMenuStrip/cpp/Form1.cpp#1)]
 [!code-csharp[System.Windows.Forms.TreeNodeContextMenuStrip#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/system.windows.forms.TreeNodeContextMenuStrip/CS/Form1.cs#1)]
 [!code-vb[System.Windows.Forms.TreeNodeContextMenuStrip#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/system.windows.forms.TreeNodeContextMenuStrip/VB/Form1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="a9de0-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="a9de0-114">See also</span></span>
- <xref:System.Windows.Forms.ContextMenuStrip>
- [<span data-ttu-id="a9de0-115">TreeView 控件</span><span class="sxs-lookup"><span data-stu-id="a9de0-115">TreeView Control</span></span>](../../../../docs/framework/winforms/controls/treeview-control-windows-forms.md)
