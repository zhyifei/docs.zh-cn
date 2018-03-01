---
title: "如何：确定被单击的 TreeView 节点（Windows 窗体）"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
f1_keywords:
- TreeNode
helpviewer_keywords:
- examples [Windows Forms], TreeView control
- tree nodes in TreeView control [Windows Forms], determining node clicked
- TreeView control [Windows Forms], determining node clicked
ms.assetid: 06a4a191-d918-42af-9f49-956c93eff261
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 2671d2790b3c5e476513cd5932d4684838aeceb6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-determine-which-treeview-node-was-clicked-windows-forms"></a><span data-ttu-id="5fbc8-102">如何：确定被单击的 TreeView 节点（Windows 窗体）</span><span class="sxs-lookup"><span data-stu-id="5fbc8-102">How to: Determine Which TreeView Node Was Clicked (Windows Forms)</span></span>
<span data-ttu-id="5fbc8-103">使用 Windows 窗体时<xref:System.Windows.Forms.TreeView>控件，一项常见任务是确定哪个节点被单击，并做出相应响应。</span><span class="sxs-lookup"><span data-stu-id="5fbc8-103">When working with the Windows Forms <xref:System.Windows.Forms.TreeView> control, a common task is to determine which node was clicked, and respond appropriately.</span></span>  
  
### <a name="to-determine-which-treeview-node-was-clicked"></a><span data-ttu-id="5fbc8-104">若要确定被单击的 TreeView 节点</span><span class="sxs-lookup"><span data-stu-id="5fbc8-104">To determine which TreeView node was clicked</span></span>  
  
1.  <span data-ttu-id="5fbc8-105">使用<xref:System.EventArgs>对象返回到的被单击的节点对象的引用。</span><span class="sxs-lookup"><span data-stu-id="5fbc8-105">Use the <xref:System.EventArgs> object to return a reference to the clicked node object.</span></span>  
  
2.  <span data-ttu-id="5fbc8-106">确定通过检查被单击的节点<xref:System.Windows.Forms.TreeViewEventArgs>类，其中包含与事件相关的数据。</span><span class="sxs-lookup"><span data-stu-id="5fbc8-106">Determine which node was clicked by checking the <xref:System.Windows.Forms.TreeViewEventArgs> class, which contains data related to the event.</span></span>  
  
    ```vb  
    Private Sub TreeView1_AfterSelect(ByVal sender As System.Object, _  
    ByVal e As System.Windows.Forms.TreeViewEventArgs) Handles TreeView1.AfterSelect  
       ' Determine by checking the Node property of the TreeViewEventArgs.  
       MessageBox.Show(e.Node.Text)  
    End Sub  
    ```  
  
    ```csharp  
    protected void treeView1_AfterSelect (object sender,   
    System.Windows.Forms.TreeViewEventArgs e)  
    {  
       // Determine by checking the Text property.  
       MessageBox.Show(e.Node.Text);  
    }  
    ```  
  
    ```cpp  
    private:  
       void treeView1_AfterSelect(System::Object ^  sender,  
          System::Windows::Forms::TreeViewEventArgs ^  e)  
       {  
          // Determine by checking the Text property.  
          MessageBox::Show(e->Node->Text);  
       }  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="5fbc8-107">作为替代方法，你可以使用<xref:System.Windows.Forms.MouseEventArgs>的<xref:System.Windows.Forms.Control.MouseDown>或<xref:System.Windows.Forms.Control.MouseUp>要获取事件<xref:System.Drawing.Point.X%2A>和<xref:System.Drawing.Point.Y%2A>坐标值的<xref:System.Drawing.Point>单击发生处。</span><span class="sxs-lookup"><span data-stu-id="5fbc8-107">As an alternative, you can use the <xref:System.Windows.Forms.MouseEventArgs> of the <xref:System.Windows.Forms.Control.MouseDown> or <xref:System.Windows.Forms.Control.MouseUp> event to get the <xref:System.Drawing.Point.X%2A> and <xref:System.Drawing.Point.Y%2A> coordinate values of the <xref:System.Drawing.Point> where the click occurred.</span></span> <span data-ttu-id="5fbc8-108">然后，使用<xref:System.Windows.Forms.TreeView>控件的<xref:System.Windows.Forms.TreeView.GetNodeAt%2A>方法来确定被单击的节点。</span><span class="sxs-lookup"><span data-stu-id="5fbc8-108">Then, use the <xref:System.Windows.Forms.TreeView> control's <xref:System.Windows.Forms.TreeView.GetNodeAt%2A> method to determine which node was clicked.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5fbc8-109">请参阅</span><span class="sxs-lookup"><span data-stu-id="5fbc8-109">See Also</span></span>  
 [<span data-ttu-id="5fbc8-110">TreeView 控件</span><span class="sxs-lookup"><span data-stu-id="5fbc8-110">TreeView Control</span></span>](../../../../docs/framework/winforms/controls/treeview-control-windows-forms.md)
