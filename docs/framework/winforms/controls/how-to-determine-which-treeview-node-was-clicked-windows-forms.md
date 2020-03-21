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
# <a name="how-to-determine-which-treeview-node-was-clicked-windows-forms"></a>如何：确定被单击的 TreeView 节点（Windows 窗体）
使用 Windows 窗体<xref:System.Windows.Forms.TreeView>控件时，常见任务是确定单击了哪个节点，并适当地响应。  
  
### <a name="to-determine-which-treeview-node-was-clicked"></a>确定单击了哪个树视图节点  
  
1. 使用<xref:System.EventArgs>对象返回对单击的节点对象的引用。  
  
2. 通过检查包含与事件相关的数据的类<xref:System.Windows.Forms.TreeViewEventArgs>确定单击了哪个节点。  
  
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
    > <xref:System.Windows.Forms.MouseEventArgs>作为替代方法，可以使用<xref:System.Windows.Forms.Control.MouseDown>或<xref:System.Windows.Forms.Control.MouseUp>事件获取发生单击<xref:System.Drawing.Point.X%2A><xref:System.Drawing.Point.Y%2A><xref:System.Drawing.Point>的位置的 和 坐标值。 然后，<xref:System.Windows.Forms.TreeView>使用控件<xref:System.Windows.Forms.TreeView.GetNodeAt%2A>的方法确定单击了哪个节点。  
  
## <a name="see-also"></a>另请参阅

- [TreeView 控件](treeview-control-windows-forms.md)
