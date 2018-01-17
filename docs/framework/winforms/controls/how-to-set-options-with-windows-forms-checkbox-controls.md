---
title: "如何：使用 Windows 窗体 CheckBox 控件设置选项"
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
f1_keywords: checked
helpviewer_keywords:
- CheckBox control [Windows Forms], checked state
- check boxes [Windows Forms], using to set options
- CheckBox control [Windows Forms], using to set options
ms.assetid: 2ac70498-7e3e-4e07-8901-ccabaeb5fd3e
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 4059e3b4ad4c687234f2bc0c66c680b2c857cfe7
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-set-options-with-windows-forms-checkbox-controls"></a>如何：使用 Windows 窗体 CheckBox 控件设置选项
Windows 窗体<xref:System.Windows.Forms.CheckBox>控制用于授予用户 True/False 或是/否选项。 选择此项时，该控件将显示一个复选标记。  
  
### <a name="to-set-options-with-checkbox-controls"></a>若要设置选项的复选框控件  
  
1.  检查的值<xref:System.Windows.Forms.CheckBox.Checked%2A>属性以确定其状态，并使用该值来设置选项。  
  
     将以下代码示例，当在<xref:System.Windows.Forms.CheckBox>控件的<xref:System.Windows.Forms.CheckBox.CheckedChanged>引发事件时，窗体的<xref:System.Windows.Forms.Control.AllowDrop%2A>属性设置为`false`如果选中复选框。 这是适用于想要限制用户交互的情况。  
  
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
  
## <a name="see-also"></a>请参阅  
 <xref:System.Windows.Forms.CheckBox>  
 [CheckBox 控件概述](../../../../docs/framework/winforms/controls/checkbox-control-overview-windows-forms.md)  
 [如何：响应 Windows 窗体 CheckBox 控件单击](../../../../docs/framework/winforms/controls/how-to-respond-to-windows-forms-checkbox-clicks.md)  
 [CheckBox 控件](../../../../docs/framework/winforms/controls/checkbox-control-windows-forms.md)
