---
title: "如何：使用 Windows 窗体 TextBox 控件创建密码文本框"
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
- TextBox control [Windows Forms], entering passwords
- password boxes [Windows Forms], creating
- PasswordChar property in text boxes
- passwords [Windows Forms], input mask
- passwords [Windows Forms], password text box
ms.assetid: d105d6b9-3d50-44cd-80d8-2c0e2f486727
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: caf5cef9e23134715101545902e32e72d63c0aac
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-a-password-text-box-with-the-windows-forms-textbox-control"></a>如何：使用 Windows 窗体 TextBox 控件创建密码文本框
密码框是一个 Windows 窗体的文本框显示占位符字符，在用户键入一个字符串时。  
  
### <a name="to-create-a-password-text-box"></a>若要创建密码文本框  
  
1.  设置<xref:System.Windows.Forms.TextBox.PasswordChar%2A>属性<xref:System.Windows.Forms.TextBox>控件添加到特定的字符。  
  
     <xref:System.Windows.Forms.TextBox.PasswordChar%2A>属性指定显示在文本框中的字符。 例如，如果你想在密码框中显示星号，指定 * 有关<xref:System.Windows.Forms.TextBox.PasswordChar%2A>属性窗口中的属性。 然后，无论用户在文本框中键入的字符，将显示一个星号。  
  
2.  （可选）设置<xref:System.Windows.Forms.TextBoxBase.MaxLength%2A>属性。 属性用于确定可以在文本框中键入多少个字符。 如果超过了最大长度，系统会发出播放提示音且文本框不接受任何更多的字符。 请注意，你可能不希望这样做，因为密码的最大长度可能会利用黑客尝试猜测密码。  
  
     下面的代码示例演示如何初始化将接受最多 14 个字符长的字符串，并显示星号来替代字符串的文本框。 `InitializeMyControl`不会自动执行过程，必须调用它。  
  
    > [!IMPORTANT]
    >  使用<xref:System.Windows.Forms.TextBox.PasswordChar%2A>上文本框中的属性可帮助确保其他人将无法确定用户的密码，如果它们观察用户输入。 此安全措施不涉及任何种类的存储或传输可能导致你的应用程序逻辑的密码。 因为输入的文本不以任何方式进行加密，你应将其像任何其他机密数据。 即使没有这种情况下出现，密码是仍被视为纯文本字符串 （除非您已实施了其他安全措施）。  
  
    ```vb  
    Private Sub InitializeMyControl()  
       ' Set to no text.  
       TextBox1.Text = ""  
       ' The password character is an asterisk.  
       TextBox1.PasswordChar = "*"  
       ' The control will allow no more than 14 characters.  
       TextBox1.MaxLength = 14  
    End Sub  
    ```  
  
    ```csharp  
    private void InitializeMyControl()  
    {  
       // Set to no text.  
       textBox1.Text = "";  
       // The password character is an asterisk.  
       textBox1.PasswordChar = '*';  
       // The control will allow no more than 14 characters.  
       textBox1.MaxLength = 14;  
    }  
    ```  
  
    ```cpp  
    private:  
       void InitializeMyControl()  
       {  
          // Set to no text.  
          textBox1->Text = "";  
          // The password character is an asterisk.  
          textBox1->PasswordChar = '*';  
          // The control will allow no more than 14 characters.  
          textBox1->MaxLength = 14;  
       }  
    ```  
  
## <a name="see-also"></a>另请参阅  
 <xref:System.Windows.Forms.TextBox>  
 [TextBox 控件概述](../../../../docs/framework/winforms/controls/textbox-control-overview-windows-forms.md)  
 [如何：在 Windows 窗体 TextBox 控件中控制插入点](../../../../docs/framework/winforms/controls/how-to-control-the-insertion-point-in-a-windows-forms-textbox-control.md)  
 [如何：创建只读文本框](../../../../docs/framework/winforms/controls/how-to-create-a-read-only-text-box-windows-forms.md)  
 [如何：在字符串中添加引号](../../../../docs/framework/winforms/controls/how-to-put-quotation-marks-in-a-string-windows-forms.md)  
 [如何：在 Windows 窗体 TextBox 控件中选择文本](../../../../docs/framework/winforms/controls/how-to-select-text-in-the-windows-forms-textbox-control.md)  
 [如何：在 Windows 窗体 TextBox 控件中查看多个行](../../../../docs/framework/winforms/controls/how-to-view-multiple-lines-in-the-windows-forms-textbox-control.md)  
 [TextBox 控件](../../../../docs/framework/winforms/controls/textbox-control-windows-forms.md)
