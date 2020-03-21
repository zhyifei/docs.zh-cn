---
title: 响应 CheckBox 单击
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- Click event [Windows Forms], CheckBox control
- CheckBox control [Windows Forms], Click events
- events [Windows Forms], Click events
- double-clicks
- check boxes [Windows Forms], responding to events
ms.assetid: c39f901e-8899-43b6-aa31-939cbf7089fb
ms.openlocfilehash: 6ff20c443519446d3804b325924cb3c5cbedea97
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79141921"
---
# <a name="how-to-respond-to-windows-forms-checkbox-clicks"></a>如何：响应 Windows 窗体 CheckBox 的单击
每当用户单击 Windows 窗体<xref:System.Windows.Forms.CheckBox>控件时，都会<xref:System.Windows.Forms.Control.Click>发生该事件。 您可以根据复选框的状态对应用程序进行编程以执行某些操作。  
  
### <a name="to-respond-to-checkbox-clicks"></a>响应复选框点击  
  
1. 在事件<xref:System.Windows.Forms.Control.Click>处理程序中，使用<xref:System.Windows.Forms.CheckBox.Checked%2A>属性确定控件的状态，并执行任何必要的操作。  
  
    ```vb  
    Private Sub CheckBox1_Click(ByVal sender As Object, ByVal e As System.EventArgs) Handles CheckBox1.Click  
       ' The CheckBox control's Text property is changed each time the
       ' control is clicked, indicating a checked or unchecked state.  
       If CheckBox1.Checked = True Then  
          CheckBox1.Text = "Checked"  
       Else  
          CheckBox1.Text = "Unchecked"  
       End If  
    End Sub  
    ```  
  
    ```csharp  
    private void checkBox1_Click(object sender, System.EventArgs e)  
    {  
       // The CheckBox control's Text property is changed each time the
       // control is clicked, indicating a checked or unchecked state.  
       if (checkBox1.Checked)  
       {  
          checkBox1.Text = "Checked";  
       }  
       else  
       {  
          checkBox1.Text = "Unchecked";  
       }  
    }  
    ```  
  
    ```cpp  
    private:  
       void checkBox1_CheckedChanged(System::Object ^ sender,  
          System::EventArgs ^ e)  
       {  
          if (checkBox1->Checked)  
          {  
             checkBox1->Text = "Checked";  
          }  
          else  
          {  
             checkBox1->Text = "Unchecked";  
          }  
       }  
    ```  
  
    > [!NOTE]
    > 如果用户尝试双击<xref:System.Windows.Forms.CheckBox>控件，则每次单击将单独处理;如果用户尝试双击控件，则每次单击都将单独处理。也就是说，<xref:System.Windows.Forms.CheckBox>控件不支持双击事件。  
  
    > [!NOTE]
    > 当<xref:System.Windows.Forms.CheckBox.AutoCheck%2A>属性为`true`（默认值）时，<xref:System.Windows.Forms.CheckBox>单击时会自动选择或清除 该属性。 否则，在<xref:System.Windows.Forms.Control.Click>事件发生时必须手动设置<xref:System.Windows.Forms.CheckBox.Checked%2A>属性。  
  
     您还可以使用控件<xref:System.Windows.Forms.CheckBox>来确定操作过程。  
  
### <a name="to-determine-a-course-of-action-when-a-check-box-is-clicked"></a>在单击复选框时确定操作过程  
  
1. 使用 case 语句查询<xref:System.Windows.Forms.CheckBox.CheckState%2A>属性的值以确定操作过程。 当<xref:System.Windows.Forms.CheckBox.ThreeState%2A>属性设置为`true`时，<xref:System.Windows.Forms.CheckBox.CheckState%2A>属性可能会返回三个可能的值，表示要选中的框、未选中的框或显示具有灰色外观的框以指示该选项不可用的第三个不确定状态。  
  
    ```vb  
    Private Sub CheckBox1_Click(ByVal sender As Object, ByVal e As System.EventArgs) Handles CheckBox1.Click  
       Select Case CheckBox1.CheckState  
          Case CheckState.Checked  
             ' Code for checked state.  
          Case CheckState.Unchecked  
             ' Code for unchecked state.  
          Case CheckState.Indeterminate  
             ' Code for indeterminate state.  
       End Select
    End Sub  
    ```  
  
    ```csharp  
    private void checkBox1_Click(object sender, System.EventArgs e)  
    {  
       switch(checkBox1.CheckState)  
       {  
          case CheckState.Checked:  
             // Code for checked state.  
             break;  
          case CheckState.Unchecked:  
             // Code for unchecked state.  
             break;  
          case CheckState.Indeterminate:  
             // Code for indeterminate state.  
             break;  
       }  
    }  
    ```  
  
    ```cpp  
    private:  
       void checkBox1_CheckedChanged(System::Object ^ sender,  
          System::EventArgs ^ e)  
       {  
          switch(checkBox1->CheckState) {  
             case CheckState::Checked:  
                // Code for checked state.  
                break;  
             case CheckState::Unchecked:  
                // Code for unchecked state.  
                break;  
             case CheckState::Indeterminate:  
                // Code for indeterminate state.  
                break;  
          }  
       }  
    ```  
  
    > [!NOTE]
    > 当属性<xref:System.Windows.Forms.CheckBox.ThreeState%2A>`true`设置为<xref:System.Windows.Forms.CheckBox.Checked%2A>时，属性将返回`true`和<xref:System.Windows.Forms.CheckState.Checked><xref:System.Windows.Forms.CheckState.Indeterminate>。  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Forms.CheckBox>
- [CheckBox 控件概述](checkbox-control-overview-windows-forms.md)
- [如何：使用 Windows 窗体 CheckBox 控件设置选项](how-to-set-options-with-windows-forms-checkbox-controls.md)
- [复选框控制](checkbox-control-windows-forms.md)
