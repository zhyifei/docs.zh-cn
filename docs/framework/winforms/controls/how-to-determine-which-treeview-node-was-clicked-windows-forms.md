---
title: 如何：确定被单击的 TreeView 节点
ms.date: 03/30/2017
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
ms.openlocfilehash: d960eaae2aa479e0be74e9a5e4fdbfec8ff411c1
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182177"
---
# <a name="how-to-determine-which-treeview-node-was-clicked-windows-forms"></a><span data-ttu-id="defe2-102">如何：确定被单击的 TreeView 节点（Windows 窗体）</span><span class="sxs-lookup"><span data-stu-id="defe2-102">How to: Determine Which TreeView Node Was Clicked (Windows Forms)</span></span>
<span data-ttu-id="defe2-103">使用 Windows 窗体<xref:System.Windows.Forms.TreeView>控件时，常见任务是确定单击了哪个节点，并适当地响应。</span><span class="sxs-lookup"><span data-stu-id="defe2-103">When working with the Windows Forms <xref:System.Windows.Forms.TreeView> control, a common task is to determine which node was clicked, and respond appropriately.</span></span>  
  
### <a name="to-determine-which-treeview-node-was-clicked"></a><span data-ttu-id="defe2-104">确定单击了哪个树视图节点</span><span class="sxs-lookup"><span data-stu-id="defe2-104">To determine which TreeView node was clicked</span></span>  
  
1. <span data-ttu-id="defe2-105">使用<xref:System.EventArgs>对象返回对单击的节点对象的引用。</span><span class="sxs-lookup"><span data-stu-id="defe2-105">Use the <xref:System.EventArgs> object to return a reference to the clicked node object.</span></span>  
  
2. <span data-ttu-id="defe2-106">通过检查包含与事件相关的数据的类<xref:System.Windows.Forms.TreeViewEventArgs>确定单击了哪个节点。</span><span class="sxs-lookup"><span data-stu-id="defe2-106">Determine which node was clicked by checking the <xref:System.Windows.Forms.TreeViewEventArgs> class, which contains data related to the event.</span></span>  
  
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
    > <span data-ttu-id="defe2-107"><xref:System.Windows.Forms.MouseEventArgs>作为替代方法，可以使用<xref:System.Windows.Forms.Control.MouseDown>或<xref:System.Windows.Forms.Control.MouseUp>事件获取发生单击<xref:System.Drawing.Point.X%2A><xref:System.Drawing.Point.Y%2A><xref:System.Drawing.Point>的位置的 和 坐标值。</span><span class="sxs-lookup"><span data-stu-id="defe2-107">As an alternative, you can use the <xref:System.Windows.Forms.MouseEventArgs> of the <xref:System.Windows.Forms.Control.MouseDown> or <xref:System.Windows.Forms.Control.MouseUp> event to get the <xref:System.Drawing.Point.X%2A> and <xref:System.Drawing.Point.Y%2A> coordinate values of the <xref:System.Drawing.Point> where the click occurred.</span></span> <span data-ttu-id="defe2-108">然后，<xref:System.Windows.Forms.TreeView>使用控件<xref:System.Windows.Forms.TreeView.GetNodeAt%2A>的方法确定单击了哪个节点。</span><span class="sxs-lookup"><span data-stu-id="defe2-108">Then, use the <xref:System.Windows.Forms.TreeView> control's <xref:System.Windows.Forms.TreeView.GetNodeAt%2A> method to determine which node was clicked.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="defe2-109">另请参阅</span><span class="sxs-lookup"><span data-stu-id="defe2-109">See also</span></span>

- [<span data-ttu-id="defe2-110">TreeView 控件</span><span class="sxs-lookup"><span data-stu-id="defe2-110">TreeView Control</span></span>](treeview-control-windows-forms.md)
