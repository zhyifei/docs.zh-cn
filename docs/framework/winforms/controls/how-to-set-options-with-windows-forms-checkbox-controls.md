---
title: 使用 CheckBox 控件设置选项
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
ms.openlocfilehash: 84198eab42aa02b1bb37fa16a3c4247a37f58a10
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746766"
---
# <a name="how-to-set-options-with-windows-forms-checkbox-controls"></a>如何： 使用 Windows 窗体复选框控件设置选项
Windows 窗体 <xref:System.Windows.Forms.CheckBox> 控件用于向用户授予 True/False 或 Yes/No 选项。 选中时，控件将显示复选标记。  
  
### <a name="to-set-options-with-checkbox-controls"></a>用 CheckBox 控件设置选项  
  
1. 检查 <xref:System.Windows.Forms.CheckBox.Checked%2A> 属性的值以确定其状态，并使用该值来设置选项。  
  
     在下面的代码示例中，当引发 <xref:System.Windows.Forms.CheckBox> 控件的 <xref:System.Windows.Forms.CheckBox.CheckedChanged> 事件时，如果选中此复选框，则窗体的 <xref:System.Windows.Forms.Control.AllowDrop%2A> 属性设置为 `false`。 这对于想要限制用户交互的情况非常有用。  
  
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
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Forms.CheckBox>
- [CheckBox 控件概述](checkbox-control-overview-windows-forms.md)
- [如何：响应 Windows 窗体 CheckBox 控件单击](how-to-respond-to-windows-forms-checkbox-clicks.md)
- [CheckBox 控件](checkbox-control-windows-forms.md)
