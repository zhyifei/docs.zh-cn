---
title: TextBox 控件概述（Windows 窗体）
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
f1_keywords:
- TextBox
helpviewer_keywords:
- TextBox control [Windows Forms], about TextBox controls
- text boxes [Windows Forms], adding
ms.assetid: d1a9c7f5-fa53-480a-a75c-158f8649ea2f
ms.openlocfilehash: b15de762b166fb66ff926706e93cbac6d0c6ba9b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33539862"
---
# <a name="textbox-control-overview-windows-forms"></a>TextBox 控件概述（Windows 窗体）
若要获取用户输入或显示文本使用 Windows 窗体的文本框。 <xref:System.Windows.Forms.TextBox>控件通常用于可编辑文本，虽然也可使其成为只读的。 文本框可以显示多个行，为该控件的大小的文本换行并添加基本格式设置。 <xref:System.Windows.Forms.TextBox>控件提供单个格式样式显示或文本框控件中输入的文本。 若要显示多种类型的格式化文本，请使用<xref:System.Windows.Forms.RichTextBox>控件。 有关详细信息，请参阅[RichTextBox 控件概述](../../../../docs/framework/winforms/controls/richtextbox-control-overview-windows-forms.md)。  
  
## <a name="working-with-the-textbox-control"></a>使用文本框控件  
 中包含由控件显示的文本<xref:System.Windows.Forms.TextBox.Text%2A>属性。 默认情况下，你可以输入最多 2048年个字符，在文本框中。 如果你设置<xref:System.Windows.Forms.TextBox.Multiline%2A>属性`true`，你可以输入最多为 32 KB 的文本。 <xref:System.Windows.Forms.TextBox.Text%2A>属性可以设置在设计时使用属性窗口中，在运行时运行时在代码中，或根据用户的输入。 文本框中的当前内容可以在运行时检索通过阅读<xref:System.Windows.Forms.TextBox.Text%2A>属性。  
  
 下面的代码示例在运行时设置控件中的文本。 `InitializeMyControl`不会自动执行过程，必须调用它。  
  
```vb  
Private Sub InitializeMyControl()  
   ' Put some text into the control first.  
   TextBox1.Text = "This is a TextBox control."  
End Sub  
```  
  
```csharp  
private void InitializeMyControl() {  
   // Put some text into the control first.  
   textBox1.Text = "This is a TextBox control.";  
}  
```  
  
```cpp  
private:  
   void InitializeMyControl()  
   {  
      // Put some text into the control first.  
      textBox1->Text = "This is a TextBox control.";  
   }  
```  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Windows.Forms.TextBox>  
 [如何：在 Windows 窗体 TextBox 控件中控制插入点](../../../../docs/framework/winforms/controls/how-to-control-the-insertion-point-in-a-windows-forms-textbox-control.md)  
 [如何：使用 Windows 窗体 TextBox 控件创建密码文本框](../../../../docs/framework/winforms/controls/how-to-create-a-password-text-box-with-the-windows-forms-textbox-control.md)  
 [如何：创建只读文本框](../../../../docs/framework/winforms/controls/how-to-create-a-read-only-text-box-windows-forms.md)  
 [如何：在字符串中添加引号](../../../../docs/framework/winforms/controls/how-to-put-quotation-marks-in-a-string-windows-forms.md)  
 [如何：在 Windows 窗体 TextBox 控件中选择文本](../../../../docs/framework/winforms/controls/how-to-select-text-in-the-windows-forms-textbox-control.md)  
 [如何：在 Windows 窗体 TextBox 控件中查看多个行](../../../../docs/framework/winforms/controls/how-to-view-multiple-lines-in-the-windows-forms-textbox-control.md)  
 [TextBox 控件](../../../../docs/framework/winforms/controls/textbox-control-windows-forms.md)
