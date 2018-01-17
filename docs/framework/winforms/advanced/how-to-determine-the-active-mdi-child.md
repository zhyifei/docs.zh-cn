---
title: "如何：确定活动的 MDI 子窗体"
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
helpviewer_keywords:
- Clipboard [Windows Forms], copying data to
- MDI [Windows Forms], child windows
- child forms
- MDI [Windows Forms], activating forms
- MDI [Windows Forms], locating focus
ms.assetid: 33880ec3-0207-4c2b-a616-ff140443cc0f
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: c026df631c2ac033594ea86887bb8440a6aa240a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-determine-the-active-mdi-child"></a>如何：确定活动的 MDI 子窗体
有时，你将想要在当前处于活动状态的子窗体具有焦点的控件上提供的命令。 例如，假设你想要将子窗体的文本框中的选定的文本复制到剪贴板。 将创建一个过程，它将选定的文本复制到剪贴板使用<xref:System.Windows.Forms.Control.Click>标准的编辑菜单上的复制菜单项的事件。  
  
 因为 MDI 应用程序可以有相同的子窗体的多个实例，该过程将需要知道要使用哪个窗体。 若要指定正确的窗体，使用<xref:System.Windows.Forms.Form.ActiveMdiChild%2A>属性，它返回的子窗体中具有焦点的或最近的活动。  
  
 如果必须在窗体上的多个控件，你还需要指定哪些控件处于活动状态。 如<xref:System.Windows.Forms.Form.ActiveMdiChild%2A>属性，<xref:System.Windows.Forms.ContainerControl.ActiveControl%2A>属性在活动子窗体上返回具有焦点的控件。 下面的过程阐释了可从子窗体菜单上，MDI 窗体或工具栏按钮的菜单中调用的复制过程。  
  
### <a name="to-determine-the-active-mdi-child-to-copy-its-text-to-the-clipboard"></a>若要确定活动 MDI 子窗体 （若要将其文本复制到剪贴板）  
  
1.  在方法中，将活动子窗体的活动控件的文本复制到剪贴板。  
  
    > [!NOTE]
    >  此示例假定有一个 MDI 父窗体 (`Form1`)，其包含一个或多个 MDI 子窗口<xref:System.Windows.Forms.RichTextBox>控件。 有关详细信息，请参阅[创建 MDI 父窗体](../../../../docs/framework/winforms/advanced/how-to-create-mdi-parent-forms.md)。  
  
    ```vb  
    Public Sub mniCopy_Click(ByVal sender As Object, _  
       ByVal e As System.EventArgs) Handles mniCopy.Click  
  
       ' Determine the active child form.  
       Dim activeChild As Form = Me.ActiveMDIChild  
  
       ' If there is an active child form, find the active control, which  
       ' in this example should be a RichTextBox.  
       If (Not activeChild Is Nothing) Then  
          Dim theBox As RichTextBox = _  
            TryCast(activeChild.ActiveControl, RichTextBox)  
  
          If (Not theBox Is Nothing) Then  
             'Put selected text on Clipboard.  
             Clipboard.SetDataObject(theBox.SelectedText)  
          Else  
             MessageBox.Show("You need to select a RichTextBox.")  
          End If  
       End If  
    End Sub  
    ```  
  
    ```csharp  
    protected void mniCopy_Click (object sender, System.EventArgs e)  
    {  
       // Determine the active child form.  
       Form activeChild = this.ActiveMdiChild;  
  
       // If there is an active child form, find the active control, which  
       // in this example should be a RichTextBox.  
       if (activeChild != null)  
       {    
          try  
          {  
             RichTextBox theBox = (RichTextBox)activeChild.ActiveControl;  
             if (theBox != null)  
             {  
                // Put the selected text on the Clipboard.  
                Clipboard.SetDataObject(theBox.SelectedText);  
  
             }  
          }  
          catch  
          {  
             MessageBox.Show("You need to select a RichTextBox.");  
          }  
       }  
    }  
    ```  
  
## <a name="see-also"></a>请参阅  
 [多文档界面 (MDI) 应用程序](../../../../docs/framework/winforms/advanced/multiple-document-interface-mdi-applications.md)  
 [如何：创建 MDI 父窗体](../../../../docs/framework/winforms/advanced/how-to-create-mdi-parent-forms.md)  
 [如何：创建 MDI 子窗体](../../../../docs/framework/winforms/advanced/how-to-create-mdi-child-forms.md)  
 [如何：将数据发送到活动的 MDI 子窗体](../../../../docs/framework/winforms/advanced/how-to-send-data-to-the-active-mdi-child.md)  
 [如何：排列 MDI 子窗体](../../../../docs/framework/winforms/advanced/how-to-arrange-mdi-child-forms.md)
