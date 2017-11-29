---
title: "如何：将数据发送到活动的 MDI 子窗体"
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
- child forms
- MDI [Windows Forms], sending data to forms
- Clipboard [Windows Forms], pasting
- Clipboard [Windows Forms], getting data from
ms.assetid: 1047d2fe-1235-46db-aad9-563aea1d743b
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: b7f505d68bfd6d8c65104244f9583fd3cf975dd6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-send-data-to-the-active-mdi-child"></a><span data-ttu-id="d52c7-102">如何：将数据发送到活动的 MDI 子窗体</span><span class="sxs-lookup"><span data-stu-id="d52c7-102">How to: Send Data to the Active MDI Child</span></span>
<span data-ttu-id="d52c7-103">通常情况下中的上下文[多文档界面 (MDI) 应用程序](../../../../docs/framework/winforms/advanced/multiple-document-interface-mdi-applications.md)，你将需要将数据发送到活动子窗口，如当用户将数据从剪贴板粘贴到 MDI 应用程序。</span><span class="sxs-lookup"><span data-stu-id="d52c7-103">Often, within the context of [Multiple-Document Interface (MDI) Applications](../../../../docs/framework/winforms/advanced/multiple-document-interface-mdi-applications.md), you will need to send data to the active child window, such as when the user pastes data from the Clipboard into an MDI application.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d52c7-104">有关验证的子窗口具有焦点并将其内容发送到剪贴板的信息，请参阅[确定活动 MDI 子窗体](../../../../docs/framework/winforms/advanced/how-to-determine-the-active-mdi-child.md)。</span><span class="sxs-lookup"><span data-stu-id="d52c7-104">For information about verifying which child window has focus and sending its contents to the Clipboard, see [Determining the Active MDI Child](../../../../docs/framework/winforms/advanced/how-to-determine-the-active-mdi-child.md).</span></span>  
  
### <a name="to-send-data-to-the-active-mdi-child-window-from-the-clipboard"></a><span data-ttu-id="d52c7-105">若要从剪贴板将数据发送到活动的 MDI 子窗口</span><span class="sxs-lookup"><span data-stu-id="d52c7-105">To send data to the active MDI child window from the Clipboard</span></span>  
  
1.  <span data-ttu-id="d52c7-106">在方法中，将在剪贴板上的文本复制到活动子窗体的活动控件。</span><span class="sxs-lookup"><span data-stu-id="d52c7-106">Within a method, copy the text on the Clipboard to the active control of the active child form.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="d52c7-107">此示例假定有一个 MDI 父窗体 (`Form1`)，其包含一个或多个 MDI 子窗口<xref:System.Windows.Forms.RichTextBox>控件。</span><span class="sxs-lookup"><span data-stu-id="d52c7-107">This example assumes there is an MDI parent form (`Form1`) that has one or more MDI child windows containing a <xref:System.Windows.Forms.RichTextBox> control.</span></span> <span data-ttu-id="d52c7-108">有关详细信息，请参阅[创建 MDI 父窗体](../../../../docs/framework/winforms/advanced/how-to-create-mdi-parent-forms.md)。</span><span class="sxs-lookup"><span data-stu-id="d52c7-108">For more information, see [Creating MDI Parent Forms](../../../../docs/framework/winforms/advanced/how-to-create-mdi-parent-forms.md).</span></span>  
  
    ```vb  
    Public Sub mniPaste_Click(ByVal sender As Object, _  
       ByVal e As System.EventArgs) Handles mniPaste.Click  
  
       ' Determine the active child form.  
       Dim activeChild As Form = Me.ParentForm.ActiveMDIChild  
  
       ' If there is an active child form, find the active control, which  
       ' in this example should be a RichTextBox.  
       If (Not activeChild Is Nothing) Then  
          Try  
             Dim theBox As RichTextBox = Ctype(activeChild.ActiveControl, RichTextBox)  
             If (Not theBox Is Nothing) Then  
                ' Create a new instance of the DataObject interface.  
                Dim data As IDataObject = Clipboard.GetDataObject()  
                ' If the data is text, then set the text of the   
                ' RichTextBox to the text in the clipboard.  
                If (data.GetDataPresent(DataFormats.Text)) Then  
                   theBox.SelectedText = data.GetData(DataFormats.Text).ToString()  
                End If  
             End If  
          Catch  
             MessageBox.Show("You need to select a RichTextBox.")  
          End Try  
       End If  
    End Sub  
    ```  
  
    ```csharp  
    protected void mniPaste_Click (object sender, System.EventArgs e)  
    {  
      // Determine the active child form.  
       Form activeChild = this.ParentForm.ActiveMdiChild;  
  
       // If there is an active child form, find the active control, which  
       // in this example should be a RichTextBox.  
       if (activeChild != null)  
       {  
          try   
          {  
             RichTextBox theBox = (RichTextBox)activeChild.ActiveControl;  
             if (theBox != null)  
             {  
                // Create a new instance of the DataObject interface.  
                IDataObject data = Clipboard.GetDataObject();  
                // If the data is text, then set the text of the   
                // RichTextBox to the text in the clipboard.  
                if (data.GetDataPresent(DataFormats.Text))  
                {  
                   theBox.SelectedText = data.GetData(DataFormats.Text).ToString();                 
                }  
             }  
          }  
          catch   
          {  
             MessageBox.Show("You need to select a RichTextBox.");  
          }  
       }  
    }  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="d52c7-109">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d52c7-109">See Also</span></span>  
 [<span data-ttu-id="d52c7-110">多文档界面 (MDI) 应用程序</span><span class="sxs-lookup"><span data-stu-id="d52c7-110">Multiple-Document Interface (MDI) Applications</span></span>](../../../../docs/framework/winforms/advanced/multiple-document-interface-mdi-applications.md)  
 [<span data-ttu-id="d52c7-111">如何：创建 MDI 父窗体</span><span class="sxs-lookup"><span data-stu-id="d52c7-111">How to: Create MDI Parent Forms</span></span>](../../../../docs/framework/winforms/advanced/how-to-create-mdi-parent-forms.md)  
 [<span data-ttu-id="d52c7-112">如何：创建 MDI 子窗体</span><span class="sxs-lookup"><span data-stu-id="d52c7-112">How to: Create MDI Child Forms</span></span>](../../../../docs/framework/winforms/advanced/how-to-create-mdi-child-forms.md)  
 [<span data-ttu-id="d52c7-113">如何：确定活动的 MDI 子窗体</span><span class="sxs-lookup"><span data-stu-id="d52c7-113">How to: Determine the Active MDI Child</span></span>](../../../../docs/framework/winforms/advanced/how-to-determine-the-active-mdi-child.md)  
 [<span data-ttu-id="d52c7-114">如何：排列 MDI 子窗体</span><span class="sxs-lookup"><span data-stu-id="d52c7-114">How to: Arrange MDI Child Forms</span></span>](../../../../docs/framework/winforms/advanced/how-to-arrange-mdi-child-forms.md)
