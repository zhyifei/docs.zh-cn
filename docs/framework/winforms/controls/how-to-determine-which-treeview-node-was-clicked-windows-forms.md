---
title: 如何：确定被单击的 TreeView 节点（Windows 窗体）
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
ms.openlocfilehash: d1e9df6a928f1ea60e4663c78d204ec2b16baf23
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-determine-which-treeview-node-was-clicked-windows-forms"></a>如何：确定被单击的 TreeView 节点（Windows 窗体）
使用 Windows 窗体时<xref:System.Windows.Forms.TreeView>控件，一项常见任务是确定哪个节点被单击，并做出相应响应。  
  
### <a name="to-determine-which-treeview-node-was-clicked"></a>若要确定被单击的 TreeView 节点  
  
1.  使用<xref:System.EventArgs>对象返回到的被单击的节点对象的引用。  
  
2.  确定通过检查被单击的节点<xref:System.Windows.Forms.TreeViewEventArgs>类，其中包含与事件相关的数据。  
  
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
    >  作为替代方法，你可以使用<xref:System.Windows.Forms.MouseEventArgs>的<xref:System.Windows.Forms.Control.MouseDown>或<xref:System.Windows.Forms.Control.MouseUp>要获取事件<xref:System.Drawing.Point.X%2A>和<xref:System.Drawing.Point.Y%2A>坐标值的<xref:System.Drawing.Point>单击发生处。 然后，使用<xref:System.Windows.Forms.TreeView>控件的<xref:System.Windows.Forms.TreeView.GetNodeAt%2A>方法来确定被单击的节点。  
  
## <a name="see-also"></a>请参阅  
 [TreeView 控件](../../../../docs/framework/winforms/controls/treeview-control-windows-forms.md)
