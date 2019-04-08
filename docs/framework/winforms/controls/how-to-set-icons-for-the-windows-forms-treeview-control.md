---
title: 如何：设置 Windows 窗体 TreeView 控件的图标
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- examples [Windows Forms], TreeView control
- TreeView control [Windows Forms], node icons
- ImageList component [Windows Forms], adding images
- icons [Windows Forms], setting for TreeView control
- tree nodes in TreeView control [Windows Forms], icons
ms.assetid: c14ddcc0-e5a6-4c21-a2d5-6799fd491781
ms.openlocfilehash: 12b8354890f0ba613b35615dc5cf3a5b3555e7ca
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59097613"
---
# <a name="how-to-set-icons-for-the-windows-forms-treeview-control"></a><span data-ttu-id="ae73d-102">如何：设置 Windows 窗体 TreeView 控件的图标</span><span class="sxs-lookup"><span data-stu-id="ae73d-102">How to: Set Icons for the Windows Forms TreeView Control</span></span>
<span data-ttu-id="ae73d-103">Windows 窗体<xref:System.Windows.Forms.TreeView>控件可以显示每个节点旁的图标。</span><span class="sxs-lookup"><span data-stu-id="ae73d-103">The Windows Forms <xref:System.Windows.Forms.TreeView> control can display icons next to each node.</span></span> <span data-ttu-id="ae73d-104">图标位于即时左侧的节点文本。</span><span class="sxs-lookup"><span data-stu-id="ae73d-104">The icons are positioned to the immediate left of the node text.</span></span> <span data-ttu-id="ae73d-105">若要显示这些图标，则必须将关联的树视图<xref:System.Windows.Forms.ImageList>控件。</span><span class="sxs-lookup"><span data-stu-id="ae73d-105">To display these icons, you must associate the tree view with an <xref:System.Windows.Forms.ImageList> control.</span></span> <span data-ttu-id="ae73d-106">有关图像列表的详细信息，请参阅[ImageList 组件](imagelist-component-windows-forms.md)和[如何：添加或删除图像与 Windows 窗体 ImageList 组件](how-to-add-or-remove-images-with-the-windows-forms-imagelist-component.md)。</span><span class="sxs-lookup"><span data-stu-id="ae73d-106">For more information about image lists, see [ImageList Component](imagelist-component-windows-forms.md) and [How to: Add or Remove Images with the Windows Forms ImageList Component](how-to-add-or-remove-images-with-the-windows-forms-imagelist-component.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ae73d-107">Microsoft.NET Framework 1.1 版中的 bug 可防止映像上出现<xref:System.Windows.Forms.TreeView>节点时应用程序调用<xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="ae73d-107">A bug in Microsoft .NET Framework version 1.1 prevents images from appearing on <xref:System.Windows.Forms.TreeView> nodes when your application calls <xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="ae73d-108">若要解决此 bug，请调用<xref:System.Windows.Forms.Application.DoEvents%2A?displayProperty=nameWithType>在您`Main`方法后立即调用<xref:System.Windows.Forms.Application.EnableVisualStyles%2A>。</span><span class="sxs-lookup"><span data-stu-id="ae73d-108">To work around this bug, call <xref:System.Windows.Forms.Application.DoEvents%2A?displayProperty=nameWithType> in your `Main` method immediately after calling <xref:System.Windows.Forms.Application.EnableVisualStyles%2A>.</span></span> <span data-ttu-id="ae73d-109">在中已修复此 bug [!INCLUDE[dnprdnlong](../../../../includes/dnprdnlong-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="ae73d-109">This bug is fixed in [!INCLUDE[dnprdnlong](../../../../includes/dnprdnlong-md.md)].</span></span>  
  
### <a name="to-display-images-in-a-tree-view"></a><span data-ttu-id="ae73d-110">在树视图中显示图像</span><span class="sxs-lookup"><span data-stu-id="ae73d-110">To display images in a tree view</span></span>  
  
1.  <span data-ttu-id="ae73d-111">设置<xref:System.Windows.Forms.TreeView>控件的<xref:System.Windows.Forms.TreeView.ImageList%2A>属性设置为现有<xref:System.Windows.Forms.ImageList>你想要使用的控件。</span><span class="sxs-lookup"><span data-stu-id="ae73d-111">Set the <xref:System.Windows.Forms.TreeView> control's <xref:System.Windows.Forms.TreeView.ImageList%2A> property to the existing <xref:System.Windows.Forms.ImageList> control you wish to use.</span></span>  
  
     <span data-ttu-id="ae73d-112">可以在属性窗口中，使用在设计器或在代码中设置这些属性。</span><span class="sxs-lookup"><span data-stu-id="ae73d-112">These properties can be set in the designer with the Properties window, or in code.</span></span>  
  
    ```vb  
    TreeView1.ImageList = ImageList1  
    ```  
  
    ```csharp  
    treeView1.ImageList = imageList1;  
    ```  
  
    ```cpp  
    treeView1->ImageList = imageList1;  
    ```  
  
2.  <span data-ttu-id="ae73d-113">将节点设置<xref:System.Windows.Forms.TreeNode.ImageIndex%2A>和<xref:System.Windows.Forms.TreeNode.SelectedImageIndex%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="ae73d-113">Set the node's <xref:System.Windows.Forms.TreeNode.ImageIndex%2A> and <xref:System.Windows.Forms.TreeNode.SelectedImageIndex%2A> properties.</span></span> <span data-ttu-id="ae73d-114"><xref:System.Windows.Forms.TreeNode.ImageIndex%2A>属性确定节点的正常和展开状态，显示的图像和<xref:System.Windows.Forms.TreeNode.SelectedImageIndex%2A>属性确定显示节点的所选状态的图像。</span><span class="sxs-lookup"><span data-stu-id="ae73d-114">The <xref:System.Windows.Forms.TreeNode.ImageIndex%2A> property determines the image displayed for the node's normal and expanded states, and the <xref:System.Windows.Forms.TreeNode.SelectedImageIndex%2A> property determines the image displayed for the node's selected state.</span></span>  
  
     <span data-ttu-id="ae73d-115">在代码中，或在树节点编辑器中，可以设置这些属性。</span><span class="sxs-lookup"><span data-stu-id="ae73d-115">These properties can be set in code, or within the TreeNode Editor.</span></span> <span data-ttu-id="ae73d-116">若要打开树节点编辑器中，单击省略号按钮 ( ![VisualStudioEllipsesButton 屏幕快照](../media/vbellipsesbutton.png "vbEllipsesButton")) 旁边<xref:System.Windows.Forms.TreeView.Nodes%2A>属性窗口上的属性。</span><span class="sxs-lookup"><span data-stu-id="ae73d-116">To open the TreeNode Editor, click the ellipsis button ( ![VisualStudioEllipsesButton screenshot](../media/vbellipsesbutton.png "vbEllipsesButton")) next to the <xref:System.Windows.Forms.TreeView.Nodes%2A> property on the Properties window.</span></span>  
  
    ```vb  
    ' (Assumes that ImageList1 contains at least two images and  
    ' the TreeView control contains a selected image.)  
    TreeView1.SelectedNode.ImageIndex = 0  
    TreeView1.SelectedNode.SelectedImageIndex = 1  
    ```  
  
    ```csharp  
    // (Assumes that imageList1 contains at least two images and  
    // the TreeView control contains a selected image.)  
    treeView1.SelectedNode.ImageIndex = 0;  
    treeView1.SelectedNode.SelectedImageIndex = 1;  
    ```  
  
    ```cpp  
    // (Assumes that imageList1 contains at least two images and  
    // the TreeView control contains a selected image.)  
    treeView1->SelectedNode->ImageIndex = 0;  
    treeView1->SelectedNode->SelectedImageIndex = 1;  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="ae73d-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="ae73d-117">See also</span></span>

- [<span data-ttu-id="ae73d-118">TreeView 控件概述</span><span class="sxs-lookup"><span data-stu-id="ae73d-118">TreeView Control Overview</span></span>](treeview-control-overview-windows-forms.md)
- [<span data-ttu-id="ae73d-119">如何：添加和删除 Windows 窗体 TreeView 控件中的节点</span><span class="sxs-lookup"><span data-stu-id="ae73d-119">How to: Add and Remove Nodes with the Windows Forms TreeView Control</span></span>](how-to-add-and-remove-nodes-with-the-windows-forms-treeview-control.md)
- [<span data-ttu-id="ae73d-120">如何：循环访问 Windows 窗体 TreeView 控件的所有节点</span><span class="sxs-lookup"><span data-stu-id="ae73d-120">How to: Iterate Through All Nodes of a Windows Forms TreeView Control</span></span>](how-to-iterate-through-all-nodes-of-a-windows-forms-treeview-control.md)
- [<span data-ttu-id="ae73d-121">如何：确定被单击的 TreeView 节点</span><span class="sxs-lookup"><span data-stu-id="ae73d-121">How to: Determine Which TreeView Node Was Clicked</span></span>](how-to-determine-which-treeview-node-was-clicked-windows-forms.md)
- [<span data-ttu-id="ae73d-122">如何：向 TreeView 或 ListView 控件添加自定义信息（Windows 窗体）</span><span class="sxs-lookup"><span data-stu-id="ae73d-122">How to: Add Custom Information to a TreeView or ListView Control (Windows Forms)</span></span>](add-custom-information-to-a-treeview-or-listview-control-wf.md)
