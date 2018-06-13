---
title: 如何：使用 Windows 窗体 CheckBox 控件设置选项
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
f1_keywords:
- checked
helpviewer_keywords:
- CheckBox control [Windows Forms], checked state
- check boxes [Windows Forms], using to set options
- CheckBox control [Windows Forms], using to set options
ms.assetid: 2ac70498-7e3e-4e07-8901-ccabaeb5fd3e
ms.openlocfilehash: dc9e7b1aea74874c66bf9eb96a5b919ed9b4b73b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33534081"
---
# <a name="how-to-set-options-with-windows-forms-checkbox-controls"></a><span data-ttu-id="e05cb-102">如何：使用 Windows 窗体 CheckBox 控件设置选项</span><span class="sxs-lookup"><span data-stu-id="e05cb-102">How to: Set Options with Windows Forms CheckBox Controls</span></span>
<span data-ttu-id="e05cb-103">Windows 窗体<xref:System.Windows.Forms.CheckBox>控制用于授予用户 True/False 或是/否选项。</span><span class="sxs-lookup"><span data-stu-id="e05cb-103">A Windows Forms <xref:System.Windows.Forms.CheckBox> control is used to give users True/False or Yes/No options.</span></span> <span data-ttu-id="e05cb-104">选择此项时，该控件将显示一个复选标记。</span><span class="sxs-lookup"><span data-stu-id="e05cb-104">The control displays a check mark when it is selected.</span></span>  
  
### <a name="to-set-options-with-checkbox-controls"></a><span data-ttu-id="e05cb-105">若要设置选项的复选框控件</span><span class="sxs-lookup"><span data-stu-id="e05cb-105">To set options with CheckBox controls</span></span>  
  
1.  <span data-ttu-id="e05cb-106">检查的值<xref:System.Windows.Forms.CheckBox.Checked%2A>属性以确定其状态，并使用该值来设置选项。</span><span class="sxs-lookup"><span data-stu-id="e05cb-106">Examine the value of the <xref:System.Windows.Forms.CheckBox.Checked%2A> property to determine its state, and use that value to set an option.</span></span>  
  
     <span data-ttu-id="e05cb-107">将以下代码示例，当在<xref:System.Windows.Forms.CheckBox>控件的<xref:System.Windows.Forms.CheckBox.CheckedChanged>引发事件时，窗体的<xref:System.Windows.Forms.Control.AllowDrop%2A>属性设置为`false`如果选中复选框。</span><span class="sxs-lookup"><span data-stu-id="e05cb-107">In the code sample below, when the <xref:System.Windows.Forms.CheckBox> control's <xref:System.Windows.Forms.CheckBox.CheckedChanged> event is raised, the form's <xref:System.Windows.Forms.Control.AllowDrop%2A> property is set to `false` if the check box is checked.</span></span> <span data-ttu-id="e05cb-108">这是适用于想要限制用户交互的情况。</span><span class="sxs-lookup"><span data-stu-id="e05cb-108">This is useful for situations where you want to restrict user interaction.</span></span>  
  
    ```vb  
    Private Sub CheckBox1_CheckedChanged(ByVal sender As System.Object, _  
       ByVal e As System.EventArgs) Handles CheckBox1.CheckedChanged  
       ' Determine the CheckState of the check box.  
       If CheckBox1.CheckState = CheckState.Checked Then  
          ' If checked, do not allow items to be dragged onto the form.  
          Me.AllowDrop = False  
       End If  
    End Sub  
    ```  
  
    ```csharp  
    private void checkBox1_CheckedChanged(object sender, System.EventArgs e)  
    {  
       // Determine the CheckState of the check box.  
       if (checkBox1.CheckState == CheckState.Checked)   
       {  
          // If checked, do not allow items to be dragged onto the form.  
          this.AllowDrop = false;  
       }  
    }  
    ```  
  
    ```cpp  
    private:  
       void checkBox1_CheckedChanged(System::Object ^ sender,  
          System::EventArgs ^ e)  
       {  
          // Determine the CheckState of the check box.  
          if (checkBox1->CheckState == CheckState::Checked)   
          {  
             // If checked, do not allow items to be dragged onto the form.  
             this->AllowDrop = false;  
          }  
       }  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="e05cb-109">请参阅</span><span class="sxs-lookup"><span data-stu-id="e05cb-109">See Also</span></span>  
 <xref:System.Windows.Forms.CheckBox>  
 [<span data-ttu-id="e05cb-110">CheckBox 控件概述</span><span class="sxs-lookup"><span data-stu-id="e05cb-110">CheckBox Control Overview</span></span>](../../../../docs/framework/winforms/controls/checkbox-control-overview-windows-forms.md)  
 [<span data-ttu-id="e05cb-111">如何：响应 Windows 窗体 CheckBox 控件单击</span><span class="sxs-lookup"><span data-stu-id="e05cb-111">How to: Respond to Windows Forms CheckBox Clicks</span></span>](../../../../docs/framework/winforms/controls/how-to-respond-to-windows-forms-checkbox-clicks.md)  
 [<span data-ttu-id="e05cb-112">CheckBox 控件</span><span class="sxs-lookup"><span data-stu-id="e05cb-112">CheckBox Control</span></span>](../../../../docs/framework/winforms/controls/checkbox-control-windows-forms.md)
