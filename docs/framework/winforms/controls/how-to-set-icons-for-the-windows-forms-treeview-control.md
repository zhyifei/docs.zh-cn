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
ms.openlocfilehash: 451f9ab2b35ad1fbbe9401dacbc8aab44e302701
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69909810"
---
# <a name="how-to-set-icons-for-the-windows-forms-treeview-control"></a>如何：设置 Windows 窗体 TreeView 控件的图标
Windows 窗体<xref:System.Windows.Forms.TreeView>控件可以显示每个节点旁的图标。 图标位于节点文本的紧左侧。 若要显示这些图标, 您必须将树视图与<xref:System.Windows.Forms.ImageList>控件相关联。 有关图像列表的详细信息, 请参阅[ImageList 组件](imagelist-component-windows-forms.md)和[如何:添加或删除包含 Windows 窗体 ImageList 组件](how-to-add-or-remove-images-with-the-windows-forms-imagelist-component.md)的映像。  
  
> [!NOTE]
> Microsoft .NET Framework 版本1.1 中的 bug 可防止在应用程序<xref:System.Windows.Forms.TreeView>调用<xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=nameWithType>时图像显示在节点上。 若要解决此错误, 请<xref:System.Windows.Forms.Application.DoEvents%2A?displayProperty=nameWithType> `Main`在调用<xref:System.Windows.Forms.Application.EnableVisualStyles%2A>后立即在方法中调用。 此 bug 已在 .NET Framework 2.0 中解决。  
  
### <a name="to-display-images-in-a-tree-view"></a>在树视图中显示图像  
  
1. 将控件的<xref:System.Windows.Forms.TreeView.ImageList%2A>属性设置为要使用<xref:System.Windows.Forms.ImageList>的现有控件。 <xref:System.Windows.Forms.TreeView>  
  
     这些属性可以在设计器中设置属性窗口或代码中。  
  
    ```vb  
    TreeView1.ImageList = ImageList1  
    ```  
  
    ```csharp  
    treeView1.ImageList = imageList1;  
    ```  
  
    ```cpp  
    treeView1->ImageList = imageList1;  
    ```  
  
2. 设置节点的<xref:System.Windows.Forms.TreeNode.ImageIndex%2A>和<xref:System.Windows.Forms.TreeNode.SelectedImageIndex%2A>属性。 属性确定为节点的正常和已展开状态显示的图像, <xref:System.Windows.Forms.TreeNode.SelectedImageIndex%2A>属性确定为节点的选定状态显示的图像。 <xref:System.Windows.Forms.TreeNode.ImageIndex%2A>  
  
     这些属性可以在代码中设置, 也可以在 TreeNode 编辑器中设置。 若要打开 "TreeNode" 编辑器, 请单击属性窗口![上<xref:System.Windows.Forms.TreeView.Nodes%2A>属性旁的省略号按钮 (省略号按钮 (... 属性窗口](./media/visual-studio-ellipsis-button.png))。  
  
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
  
## <a name="see-also"></a>请参阅

- [TreeView 控件概述](treeview-control-overview-windows-forms.md)
- [如何：在 Windows 窗体 TreeView 控件中添加和删除节点](how-to-add-and-remove-nodes-with-the-windows-forms-treeview-control.md)
- [如何：遍历 Windows 窗体 TreeView 控件的所有节点](how-to-iterate-through-all-nodes-of-a-windows-forms-treeview-control.md)
- [如何：确定单击的 TreeView 节点](how-to-determine-which-treeview-node-was-clicked-windows-forms.md)
- [如何：向 TreeView 或 ListView 控件添加自定义信息 (Windows 窗体)](add-custom-information-to-a-treeview-or-listview-control-wf.md)
