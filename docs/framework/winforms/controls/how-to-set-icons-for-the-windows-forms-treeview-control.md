---
title: "如何：设置 Windows 窗体 TreeView 控件的图标"
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
- examples [Windows Forms], TreeView control
- TreeView control [Windows Forms], node icons
- ImageList component [Windows Forms], adding images
- icons [Windows Forms], setting for TreeView control
- tree nodes in TreeView control [Windows Forms], icons
ms.assetid: c14ddcc0-e5a6-4c21-a2d5-6799fd491781
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 5abe07a80e457c4a0254b4c1a734cba2f6ed1766
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-set-icons-for-the-windows-forms-treeview-control"></a>如何：设置 Windows 窗体 TreeView 控件的图标
Windows 窗体<xref:System.Windows.Forms.TreeView>控件可以显示每个节点旁边的图标。 图标位于节点文本的即时的左侧。 若要显示这些图标，你必须将关联的树视图<xref:System.Windows.Forms.ImageList>控件。 有关图像列表的详细信息，请参阅[ImageList 组件](../../../../docs/framework/winforms/controls/imagelist-component-windows-forms.md)和[如何： 添加或移除图像使用 Windows 窗体 ImageList 组件](../../../../docs/framework/winforms/controls/how-to-add-or-remove-images-with-the-windows-forms-imagelist-component.md)。  
  
> [!NOTE]
>  Microsoft.NET Framework 1.1 版中的 bug 可防止映像上出现<xref:System.Windows.Forms.TreeView>节点时应用程序调用<xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=nameWithType>。 若要解决此 bug，请调用<xref:System.Windows.Forms.Application.DoEvents%2A?displayProperty=nameWithType>中你`Main`方法后立即调用<xref:System.Windows.Forms.Application.EnableVisualStyles%2A>。 在中修复此 bug [!INCLUDE[dnprdnlong](../../../../includes/dnprdnlong-md.md)]。  
  
### <a name="to-display-images-in-a-tree-view"></a>在树视图中显示图像  
  
1.  设置<xref:System.Windows.Forms.TreeView>控件的<xref:System.Windows.Forms.TreeView.ImageList%2A>到现有的属性<xref:System.Windows.Forms.ImageList>你想要使用的控件。  
  
     在属性窗口中，设计器或代码中，可以设置这些属性。  
  
    ```vb  
    TreeView1.ImageList = ImageList1  
    ```  
  
    ```csharp  
    treeView1.ImageList = imageList1;  
    ```  
  
    ```cpp  
    treeView1->ImageList = imageList1;  
    ```  
  
2.  设置节点的<xref:System.Windows.Forms.TreeNode.ImageIndex%2A>和<xref:System.Windows.Forms.TreeNode.SelectedImageIndex%2A>属性。 <xref:System.Windows.Forms.TreeNode.ImageIndex%2A>属性确定节点的正常并且可扩展的状态，显示的图像和<xref:System.Windows.Forms.TreeNode.SelectedImageIndex%2A>属性确定显示为节点的所选状态的图像。  
  
     在代码中，或在 TreeNode 编辑器中，可以设置这些属性。 若要打开 TreeNode 编辑器，单击省略号按钮 ( ![VisualStudioEllipsesButton 屏幕快照](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")) 旁边<xref:System.Windows.Forms.TreeView.Nodes%2A>属性窗口上的属性。  
  
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
  
## <a name="see-also"></a>另请参阅  
 [TreeView 控件概述](../../../../docs/framework/winforms/controls/treeview-control-overview-windows-forms.md)  
 [如何：使用 Windows 窗体 TreeView 控件添加和删除节点](../../../../docs/framework/winforms/controls/how-to-add-and-remove-nodes-with-the-windows-forms-treeview-control.md)  
 [如何：循环访问 Windows 窗体 TreeView 控件的所有节点](../../../../docs/framework/winforms/controls/how-to-iterate-through-all-nodes-of-a-windows-forms-treeview-control.md)  
 [如何：确定哪个 TreeView 节点获得了单击](../../../../docs/framework/winforms/controls/how-to-determine-which-treeview-node-was-clicked-windows-forms.md)  
 [如何：向 TreeView 或 ListView 控件（Windows 窗体）添加自定义信息](../../../../docs/framework/winforms/controls/add-custom-information-to-a-treeview-or-listview-control-wf.md)
