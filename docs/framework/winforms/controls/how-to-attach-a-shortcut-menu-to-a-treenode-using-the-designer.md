---
title: 如何：使用设计器将快捷菜单附加到 TreeNode
ms.date: 03/30/2017
helpviewer_keywords:
- shortcut menus [Windows Forms], attaching to TreeNodes
- TreeNode [Windows Forms], attaching a shortcut menu using Designer
ms.assetid: 8e45e184-1313-4f8f-90ff-2cd5789b2268
ms.openlocfilehash: 2700be06ceb4c20926d6af9c962799db4afc31da
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-attach-a-shortcut-menu-to-a-treenode-using-the-designer"></a><span data-ttu-id="88ba7-102">如何：使用设计器将快捷菜单附加到 TreeNode</span><span class="sxs-lookup"><span data-stu-id="88ba7-102">How to: Attach a Shortcut Menu to a TreeNode Using the Designer</span></span>
<span data-ttu-id="88ba7-103">Windows 窗体<xref:System.Windows.Forms.TreeView>控件显示节点，类似于文件和文件夹在 Windows 操作系统中的 Windows 资源管理器功能的左窗格中显示的层次结构。</span><span class="sxs-lookup"><span data-stu-id="88ba7-103">The Windows Forms <xref:System.Windows.Forms.TreeView> control displays a hierarchy of nodes, similar to the files and folders displayed in the left pane of the Windows Explorer feature in Windows operating systems.</span></span> <span data-ttu-id="88ba7-104">通过设置<xref:System.Windows.Forms.Control.ContextMenuStrip%2A>属性，你可以提供区分上下文的操作向用户时用户右击<xref:System.Windows.Forms.TreeView>控件。</span><span class="sxs-lookup"><span data-stu-id="88ba7-104">By setting the <xref:System.Windows.Forms.Control.ContextMenuStrip%2A> property, you can provide context-sensitive operations to the user when they right-click the <xref:System.Windows.Forms.TreeView> control.</span></span> <span data-ttu-id="88ba7-105">通过将相关联<xref:System.Windows.Forms.ContextMenuStrip>组件与单个<xref:System.Windows.Forms.TreeNode>项，可以添加到快捷菜单功能的自定义的级别你<xref:System.Windows.Forms.TreeView>控件。</span><span class="sxs-lookup"><span data-stu-id="88ba7-105">By associating a <xref:System.Windows.Forms.ContextMenuStrip> component with individual <xref:System.Windows.Forms.TreeNode> items, you can add a customized level of shortcut menu functionality to your <xref:System.Windows.Forms.TreeView> controls.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="88ba7-106">显示的对话框和菜单命令可能会与“帮助”中的描述不同，具体取决于你现用的设置或版本。</span><span class="sxs-lookup"><span data-stu-id="88ba7-106">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="88ba7-107">若要更改设置，请在 **“工具”** 菜单上选择 **“导入和导出设置”** 。</span><span class="sxs-lookup"><span data-stu-id="88ba7-107">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="88ba7-108">有关详细信息，请参阅[在 Visual Studio 中自定义开发设置](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3)。</span><span class="sxs-lookup"><span data-stu-id="88ba7-108">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
### <a name="to-associate-a-shortcut-menu-with-a-treenode-at-design-time"></a><span data-ttu-id="88ba7-109">要在设计时与树节点关联的快捷菜单</span><span class="sxs-lookup"><span data-stu-id="88ba7-109">To associate a shortcut menu with a TreeNode at design time</span></span>  
  
1.  <span data-ttu-id="88ba7-110">添加<xref:System.Windows.Forms.TreeView>控制转移到窗体中，并将节点<xref:System.Windows.Forms.TreeView>根据需要。</span><span class="sxs-lookup"><span data-stu-id="88ba7-110">Add a <xref:System.Windows.Forms.TreeView> control to your form, and then add nodes to the <xref:System.Windows.Forms.TreeView> as needed.</span></span> <span data-ttu-id="88ba7-111">有关详细信息，请参阅[如何： 添加和删除使用 Windows 窗体 TreeView 控件的节点](../../../../docs/framework/winforms/controls/how-to-add-and-remove-nodes-with-the-windows-forms-treeview-control.md)。</span><span class="sxs-lookup"><span data-stu-id="88ba7-111">For more information, see [How to: Add and Remove Nodes with the Windows Forms TreeView Control](../../../../docs/framework/winforms/controls/how-to-add-and-remove-nodes-with-the-windows-forms-treeview-control.md).</span></span>  
  
2.  <span data-ttu-id="88ba7-112">添加<xref:System.Windows.Forms.ContextMenuStrip>组件到窗体中，然后将菜单项添加到表示你想要在运行时提供节点级别操作的快捷菜单。</span><span class="sxs-lookup"><span data-stu-id="88ba7-112">Add a <xref:System.Windows.Forms.ContextMenuStrip> component to your form, and then add menu items to the shortcut menu that represent node-level operations you wish to make available at run time.</span></span> <span data-ttu-id="88ba7-113">有关详细信息，请参阅[如何： 向 ContextMenuStrip 添加菜单项](../../../../docs/framework/winforms/controls/how-to-add-menu-items-to-a-contextmenustrip.md)。</span><span class="sxs-lookup"><span data-stu-id="88ba7-113">For more information, see [How to: Add Menu Items to a ContextMenuStrip](../../../../docs/framework/winforms/controls/how-to-add-menu-items-to-a-contextmenustrip.md).</span></span>  
  
3.  <span data-ttu-id="88ba7-114">重新打开**TreeNodeEditor**对话框<xref:System.Windows.Forms.TreeView>控件中，选择要编辑，并将设置的节点其<xref:System.Windows.Forms.ContextMenuStrip>属性设置为你添加的快捷菜单。</span><span class="sxs-lookup"><span data-stu-id="88ba7-114">Reopen the **TreeNodeEditor** dialog box for the <xref:System.Windows.Forms.TreeView> control, select the node to edit, and set its <xref:System.Windows.Forms.ContextMenuStrip> property to the shortcut menu that you added.</span></span>  
  
4.  <span data-ttu-id="88ba7-115">当设置此属性时，右键单击节点时，将显示的快捷菜单。</span><span class="sxs-lookup"><span data-stu-id="88ba7-115">When this property is set, the shortcut menu will be displayed when you right-click the node.</span></span>  
  
     <span data-ttu-id="88ba7-116">此外，你将想要编写代码来处理<xref:System.Windows.Forms.ToolStripItem.Click>这些菜单项的事件。</span><span class="sxs-lookup"><span data-stu-id="88ba7-116">Additionally, you will want to write code to handle the <xref:System.Windows.Forms.ToolStripItem.Click> events for these menu items.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="88ba7-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="88ba7-117">See Also</span></span>  
 [<span data-ttu-id="88ba7-118">TreeView 控件</span><span class="sxs-lookup"><span data-stu-id="88ba7-118">TreeView Control</span></span>](../../../../docs/framework/winforms/controls/treeview-control-windows-forms.md)  
 [<span data-ttu-id="88ba7-119">TreeView 控件概述</span><span class="sxs-lookup"><span data-stu-id="88ba7-119">TreeView Control Overview</span></span>](../../../../docs/framework/winforms/controls/treeview-control-overview-windows-forms.md)  
 [<span data-ttu-id="88ba7-120">ContextMenuStrip 控件</span><span class="sxs-lookup"><span data-stu-id="88ba7-120">ContextMenuStrip Control</span></span>](../../../../docs/framework/winforms/controls/contextmenustrip-control.md)
