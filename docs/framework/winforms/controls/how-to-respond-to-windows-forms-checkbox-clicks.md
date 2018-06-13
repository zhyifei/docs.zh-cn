---
title: 如何：响应 Windows 窗体 CheckBox 的单击
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
ms.openlocfilehash: aa8a15d4f55fb1dd47fdf004fa05091ec88fe03e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33539732"
---
# <a name="how-to-respond-to-windows-forms-checkbox-clicks"></a>如何：响应 Windows 窗体 CheckBox 的单击
每当用户单击 Windows 窗体<xref:System.Windows.Forms.CheckBox>控件，<xref:System.Windows.Forms.Control.Click>事件发生。 你可以在应用程序中执行一些操作根据复选框的状态。  
  
### <a name="to-respond-to-checkbox-clicks"></a>若要响应复选框单击  
  
1.  在<xref:System.Windows.Forms.Control.Click>事件处理程序中，使用<xref:System.Windows.Forms.CheckBox.Checked%2A>属性来确定控件的状态，然后执行任何必要的操作。  
  
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
    >  如果用户尝试双击<xref:System.Windows.Forms.CheckBox>控件，每次单击将单独处理; 也就是，则<xref:System.Windows.Forms.CheckBox>控件不支持双击事件。  
  
    > [!NOTE]
    >  当<xref:System.Windows.Forms.CheckBox.AutoCheck%2A>属性是`true`（默认值）、<xref:System.Windows.Forms.CheckBox>自动选中或清除单击时其。 否则，你必须手动设置<xref:System.Windows.Forms.CheckBox.Checked%2A>属性时<xref:System.Windows.Forms.Control.Click>事件发生。  
  
     你还可以使用<xref:System.Windows.Forms.CheckBox>控件来确定的操作过程。  
  
### <a name="to-determine-a-course-of-action-when-a-check-box-is-clicked"></a>若要确定操作过程的复选框时单击  
  
1.  使用 case 语句来查询的值<xref:System.Windows.Forms.CheckBox.CheckState%2A>属性来确定的操作过程。 当<xref:System.Windows.Forms.CheckBox.ThreeState%2A>属性设置为`true`、<xref:System.Windows.Forms.CheckBox.CheckState%2A>属性可能会返回三个可能的值，表示要检查该复选框，框未选中或第三个不确定状态将显示的框与为灰色外观，表示该选项不可用。  
  
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
    >  当<xref:System.Windows.Forms.CheckBox.ThreeState%2A>属性设置为`true`、<xref:System.Windows.Forms.CheckBox.Checked%2A>属性返回`true`两个<xref:System.Windows.Forms.CheckState.Checked>和<xref:System.Windows.Forms.CheckState.Indeterminate>。  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Windows.Forms.CheckBox>  
 [CheckBox 控件概述](../../../../docs/framework/winforms/controls/checkbox-control-overview-windows-forms.md)  
 [如何：使用 Windows 窗体 CheckBox 控件设置选项](../../../../docs/framework/winforms/controls/how-to-set-options-with-windows-forms-checkbox-controls.md)  
 [CheckBox 控件](../../../../docs/framework/winforms/controls/checkbox-control-windows-forms.md)
