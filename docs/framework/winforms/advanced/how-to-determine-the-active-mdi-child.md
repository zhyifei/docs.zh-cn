---
title: 如何：确定活动的 MDI 子窗体
ms.date: 03/30/2017
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
ms.openlocfilehash: 57491faa10c182630d41565ba236d65e393929b3
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182550"
---
# <a name="how-to-determine-the-active-mdi-child"></a><span data-ttu-id="cccd9-102">如何：确定活动的 MDI 子窗体</span><span class="sxs-lookup"><span data-stu-id="cccd9-102">How to: Determine the Active MDI Child</span></span>
<span data-ttu-id="cccd9-103">有时，您需要提供一个命令，该命令对侧重于当前活动子窗体的控件进行操作。</span><span class="sxs-lookup"><span data-stu-id="cccd9-103">On occasion, you will want to provide a command that operates on the control that has focus on the currently active child form.</span></span> <span data-ttu-id="cccd9-104">例如，假设您要将所选文本从子窗体的文本框复制到剪贴板。</span><span class="sxs-lookup"><span data-stu-id="cccd9-104">For example, suppose you want to copy selected text from the child form's text box to the Clipboard.</span></span> <span data-ttu-id="cccd9-105">您将创建一个过程，使用标准"编辑"菜单上的"复制<xref:System.Windows.Forms.Control.Click>"菜单项事件将所选文本复制到剪贴板。</span><span class="sxs-lookup"><span data-stu-id="cccd9-105">You would create a procedure that copies selected text to the Clipboard using the <xref:System.Windows.Forms.Control.Click> event of the Copy menu item on the standard Edit menu.</span></span>  
  
 <span data-ttu-id="cccd9-106">由于 MDI 应用程序可以具有同一子窗体的许多实例，因此该过程需要知道要使用的窗体。</span><span class="sxs-lookup"><span data-stu-id="cccd9-106">Because an MDI application can have many instances of the same child form, the procedure needs to know which form to use.</span></span> <span data-ttu-id="cccd9-107">要指定正确的窗体，请使用 属性<xref:System.Windows.Forms.Form.ActiveMdiChild%2A>，该属性返回具有焦点或最近处于活动状态的子窗体。</span><span class="sxs-lookup"><span data-stu-id="cccd9-107">To specify the correct form, use the <xref:System.Windows.Forms.Form.ActiveMdiChild%2A> property, which returns the child form that has the focus or that was most recently active.</span></span>  
  
 <span data-ttu-id="cccd9-108">当窗体上有多个控件时，还需要指定哪个控件处于活动状态。</span><span class="sxs-lookup"><span data-stu-id="cccd9-108">When you have several controls on a form, you also need to specify which control is active.</span></span> <span data-ttu-id="cccd9-109">与<xref:System.Windows.Forms.Form.ActiveMdiChild%2A>属性一样<xref:System.Windows.Forms.ContainerControl.ActiveControl%2A>，属性返回控件，重点放在活动子窗体上。</span><span class="sxs-lookup"><span data-stu-id="cccd9-109">Like the <xref:System.Windows.Forms.Form.ActiveMdiChild%2A> property, the <xref:System.Windows.Forms.ContainerControl.ActiveControl%2A> property returns the control with the focus on the active child form.</span></span> <span data-ttu-id="cccd9-110">下面的过程演示了可以从子窗体菜单、MDI 窗体上的菜单或工具栏按钮调用的复制过程。</span><span class="sxs-lookup"><span data-stu-id="cccd9-110">The procedure below illustrates a copy procedure that can be called from a child form menu, a menu on the MDI form, or a toolbar button.</span></span>  
  
### <a name="to-determine-the-active-mdi-child-to-copy-its-text-to-the-clipboard"></a><span data-ttu-id="cccd9-111">确定活动 MDI 子级（将其文本复制到剪贴板）</span><span class="sxs-lookup"><span data-stu-id="cccd9-111">To determine the active MDI child (to copy its text to the Clipboard)</span></span>  
  
1. <span data-ttu-id="cccd9-112">在方法中，将活动子窗体的活动控件的文本复制到剪贴板。</span><span class="sxs-lookup"><span data-stu-id="cccd9-112">Within a method, copy the text of the active control of the active child form to the Clipboard.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="cccd9-113">此示例假定有一个 MDI 父窗体`Form1`（ ） 具有一个或多个包含控件的<xref:System.Windows.Forms.RichTextBox>MDI 子窗口。</span><span class="sxs-lookup"><span data-stu-id="cccd9-113">This example assumes there is an MDI parent form (`Form1`) that has one or more MDI child windows containing a <xref:System.Windows.Forms.RichTextBox> control.</span></span> <span data-ttu-id="cccd9-114">有关详细信息，请参阅创建[MDI 父窗体](how-to-create-mdi-parent-forms.md)。</span><span class="sxs-lookup"><span data-stu-id="cccd9-114">For more information, see [Creating MDI Parent Forms](how-to-create-mdi-parent-forms.md).</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="cccd9-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="cccd9-115">See also</span></span>

- [<span data-ttu-id="cccd9-116">多文档界面 (MDI) 应用程序</span><span class="sxs-lookup"><span data-stu-id="cccd9-116">Multiple-Document Interface (MDI) Applications</span></span>](multiple-document-interface-mdi-applications.md)
- [<span data-ttu-id="cccd9-117">如何：创建 MDI 父窗体</span><span class="sxs-lookup"><span data-stu-id="cccd9-117">How to: Create MDI Parent Forms</span></span>](how-to-create-mdi-parent-forms.md)
- [<span data-ttu-id="cccd9-118">如何：创建 MDI 子窗体</span><span class="sxs-lookup"><span data-stu-id="cccd9-118">How to: Create MDI Child Forms</span></span>](how-to-create-mdi-child-forms.md)
- [<span data-ttu-id="cccd9-119">如何：将数据发送到活动的 MDI 子窗体</span><span class="sxs-lookup"><span data-stu-id="cccd9-119">How to: Send Data to the Active MDI Child</span></span>](how-to-send-data-to-the-active-mdi-child.md)
- [<span data-ttu-id="cccd9-120">如何：排列 MDI 子窗体</span><span class="sxs-lookup"><span data-stu-id="cccd9-120">How to: Arrange MDI Child Forms</span></span>](how-to-arrange-mdi-child-forms.md)
