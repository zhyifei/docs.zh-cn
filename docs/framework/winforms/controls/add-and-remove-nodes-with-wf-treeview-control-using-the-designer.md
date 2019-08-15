---
title: 如何：通过使用设计器添加和删除 Windows 窗体 TreeView 控件中的节点
ms.date: 03/30/2017
helpviewer_keywords:
- examples [Windows Forms], TreeView control
- TreeView control [Windows Forms], removing nodes
- tree nodes in TreeView control
- TreeView control [Windows Forms], adding nodes
ms.assetid: 35bf1750-045e-4ec5-97cb-b47b0dbdaa2c
ms.openlocfilehash: ef3a963b5621f0b972b02a007681f600fbdb1050
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/15/2019
ms.locfileid: "69040079"
---
# <a name="how-to-add-and-remove-nodes-with-the-windows-forms-treeview-control-using-the-designer"></a><span data-ttu-id="40d10-102">如何：通过使用设计器添加和删除 Windows 窗体 TreeView 控件中的节点</span><span class="sxs-lookup"><span data-stu-id="40d10-102">How to: Add and Remove Nodes with the Windows Forms TreeView Control Using the Designer</span></span>

<span data-ttu-id="40d10-103">由于 Windows 窗体<xref:System.Windows.Forms.TreeView>控件以分层方式显示节点, 因此在添加节点时, 必须注意其父节点。</span><span class="sxs-lookup"><span data-stu-id="40d10-103">Because the Windows Forms <xref:System.Windows.Forms.TreeView> control displays nodes in a hierarchical manner, when adding a node you must pay attention to what its parent node is.</span></span>

<span data-ttu-id="40d10-104">下面的过程需要一个**Windows 应用程序**项目, 该项目具有<xref:System.Windows.Forms.TreeView>包含控件的窗体。</span><span class="sxs-lookup"><span data-stu-id="40d10-104">The following procedure requires a **Windows Application** project with a form containing a <xref:System.Windows.Forms.TreeView> control.</span></span> <span data-ttu-id="40d10-105">有关设置此类项目的信息, 请参阅[如何:创建 Windows 窗体应用程序项目](/visualstudio/ide/step-1-create-a-windows-forms-application-project)以及[如何:将控件添加到](how-to-add-controls-to-windows-forms.md)Windows 窗体。</span><span class="sxs-lookup"><span data-stu-id="40d10-105">For information about setting up such a project, see [How to: Create a Windows Forms application project](/visualstudio/ide/step-1-create-a-windows-forms-application-project) and [How to: Add Controls to Windows Forms](how-to-add-controls-to-windows-forms.md).</span></span>

### <a name="to-add-or-remove-nodes-in-the-designer"></a><span data-ttu-id="40d10-106">在设计器中添加或删除节点</span><span class="sxs-lookup"><span data-stu-id="40d10-106">To add or remove nodes in the designer</span></span>

1. <span data-ttu-id="40d10-107">选择 <xref:System.Windows.Forms.TreeView> 控件。</span><span class="sxs-lookup"><span data-stu-id="40d10-107">Select the <xref:System.Windows.Forms.TreeView> control.</span></span>

2. <span data-ttu-id="40d10-108">在 "**属性**" 窗口中<xref:System.Windows.Forms.TreeView.Nodes%2A> , 单击属性![旁边的**省略号**("Visual Studio](./media/visual-studio-ellipsis-button.png)" 的属性窗口中的省略号按钮 (...)。</span><span class="sxs-lookup"><span data-stu-id="40d10-108">In the **Properties** window, click the **Ellipsis** (![The Ellipsis button (...) in the Properties window of Visual Studio.](./media/visual-studio-ellipsis-button.png)) button next to the <xref:System.Windows.Forms.TreeView.Nodes%2A> property.</span></span>

     <span data-ttu-id="40d10-109">此时将显示 " **TreeNode 节点编辑器**"。</span><span class="sxs-lookup"><span data-stu-id="40d10-109">The **TreeNode Editor** appears.</span></span>

3. <span data-ttu-id="40d10-110">若要添加节点, 根节点必须存在;如果不存在, 则必须先通过单击 "**添加根**" 按钮添加一个根。</span><span class="sxs-lookup"><span data-stu-id="40d10-110">To add nodes, a root node must exist; if one does not exist, you must first add a root by clicking the **Add Root** button.</span></span> <span data-ttu-id="40d10-111">然后, 可以通过选择根节点或任何其他节点, 然后单击 "**添加子级**" 按钮来添加子节点。</span><span class="sxs-lookup"><span data-stu-id="40d10-111">You can then add child nodes by selecting the root or any other node and clicking the **Add Child** button.</span></span>

4. <span data-ttu-id="40d10-112">若要删除节点, 请选择要删除的节点, 然后单击 "**删除**" 按钮。</span><span class="sxs-lookup"><span data-stu-id="40d10-112">To delete nodes, select the node to delete and then click the **Delete** button.</span></span>

## <a name="see-also"></a><span data-ttu-id="40d10-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="40d10-113">See also</span></span>

- [<span data-ttu-id="40d10-114">TreeView 控件</span><span class="sxs-lookup"><span data-stu-id="40d10-114">TreeView Control</span></span>](treeview-control-windows-forms.md)
- [<span data-ttu-id="40d10-115">TreeView 控件概述</span><span class="sxs-lookup"><span data-stu-id="40d10-115">TreeView Control Overview</span></span>](treeview-control-overview-windows-forms.md)
- [<span data-ttu-id="40d10-116">如何：设置 Windows 窗体 TreeView 控件的图标</span><span class="sxs-lookup"><span data-stu-id="40d10-116">How to: Set Icons for the Windows Forms TreeView Control</span></span>](how-to-set-icons-for-the-windows-forms-treeview-control.md)
- [<span data-ttu-id="40d10-117">如何：遍历 Windows 窗体 TreeView 控件的所有节点</span><span class="sxs-lookup"><span data-stu-id="40d10-117">How to: Iterate Through All Nodes of a Windows Forms TreeView Control</span></span>](how-to-iterate-through-all-nodes-of-a-windows-forms-treeview-control.md)
- [<span data-ttu-id="40d10-118">如何：确定单击的 TreeView 节点</span><span class="sxs-lookup"><span data-stu-id="40d10-118">How to: Determine Which TreeView Node Was Clicked</span></span>](how-to-determine-which-treeview-node-was-clicked-windows-forms.md)
- [<span data-ttu-id="40d10-119">如何：向 TreeView 或 ListView 控件添加自定义信息 (Windows 窗体)</span><span class="sxs-lookup"><span data-stu-id="40d10-119">How to: Add Custom Information to a TreeView or ListView Control (Windows Forms)</span></span>](add-custom-information-to-a-treeview-or-listview-control-wf.md)
