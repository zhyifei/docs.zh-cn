---
title: "如何：使用 Windows 窗体 ErrorProvider 组件显示窗体验证的错误图标"
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
helpviewer_keywords:
- errors [Windows Forms], displaying to users
- error icons
- ErrorProvider component [Windows Forms], displaying error icons
- error messages [Windows Forms], displaying icons
ms.assetid: 3b681a32-9db4-497b-a34b-34980eabee46
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 02638ab59c0ba1c0eb0f8090be118b3d5a9111f8
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-display-error-icons-for-form-validation-with-the-windows-forms-errorprovider-component"></a>如何：使用 Windows 窗体 ErrorProvider 组件显示窗体验证的错误图标
你可以使用 Windows 窗体<xref:System.Windows.Forms.ErrorProvider>组件以显示错误图标，当用户输入无效数据。 你必须具有它们之间切换，从而调用的验证代码以在窗体上的至少两个控件。  
  
### <a name="to-display-an-error-icon-when-a-controls-value-is-invalid"></a>若要将控件的值无效时显示错误图标  
  
1.  添加两个控件 — 例如，文本框中，向 Windows 窗体。  
  
2.  添加<xref:System.Windows.Forms.ErrorProvider>组件到窗体。  
  
3.  选择第一个控件，然后将代码添加到其<xref:System.Windows.Forms.Control.Validating>事件处理程序。 为了使此代码正确运行，该过程必须连接到该事件。 有关详细信息，请参阅[如何： 在运行时添加的 Windows 窗体创建事件处理程序](../../../../docs/framework/winforms/how-to-create-event-handlers-at-run-time-for-windows-forms.md)。  
  
     下面的代码测试的用户输入; 数据的有效性如果数据是无效的<xref:System.Windows.Forms.ErrorProvider.SetError%2A>调用方法。 第一个参数<xref:System.Windows.Forms.ErrorProvider.SetError%2A>方法指定在哪个控件旁边显示图标。 第二个参数是要显示的错误文本。  
  
    ```vb  
    Private Sub TextBox1_Validating(ByVal Sender As Object, _  
       ByVal e As System.ComponentModel.CancelEventArgs) Handles _  
       TextBox1.Validating  
          If Not IsNumeric(TextBox1.Text) Then  
             ErrorProvider1.SetError(TextBox1, "Not a numeric value.")  
          Else  
             ' Clear the error.  
             ErrorProvider1.SetError(TextBox1, "")  
          End If  
    End Sub  
    ```  
  
    ```csharp  
    protected void textBox1_Validating (object sender,  
       System.ComponentModel.CancelEventArgs e)  
    {  
       try  
       {  
          int x = Int32.Parse(textBox1.Text);  
          errorProvider1.SetError(textBox1, "");  
       }  
       catch (Exception ex)  
       {  
          errorProvider1.SetError(textBox1, "Not an integer value.");  
       }  
    }  
    ```  
  
    ```cpp  
    private:  
       System::Void textBox1_Validating(System::Object ^  sender,  
          System::ComponentModel::CancelEventArgs ^  e)  
       {  
          try  
          {  
             int x = Int32::Parse(textBox1->Text);  
             errorProvider1->SetError(textBox1, "");  
          }  
          catch (System::Exception ^ ex)  
          {  
             errorProvider1->SetError(textBox1, "Not an integer value.");  
          }  
       }  
    ```  
  
     ([!INCLUDE[csprcs](../../../../includes/csprcs-md.md)][!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) 将以下代码放在窗体构造函数中以注册事件处理程序。  
  
    ```csharp  
    this.textBox1.Validating += new  
    System.ComponentModel.CancelEventHandler(this.textBox1_Validating);  
    ```  
  
    ```cpp  
    this->textBox1->Validating += gcnew  
       System::ComponentModel::CancelEventHandler  
       (this, &Form1::textBox1_Validating);  
    ```  
  
4.  运行该项目。 键入第一个控件，然后切换到第二个 （在此示例中，非数字） 无效的数据。 显示错误图标时, 点它与鼠标指针以查看错误文本。  
  
## <a name="see-also"></a>另请参阅  
 <xref:System.Windows.Forms.ErrorProvider.SetError%2A>  
 [ErrorProvider 组件概述](../../../../docs/framework/winforms/controls/errorprovider-component-overview-windows-forms.md)  
 [如何：使用 Windows 窗体 ErrorProvider 组件查看数据集中的错误](../../../../docs/framework/winforms/controls/view-errors-within-a-dataset-with-wf-errorprovider-component.md)
