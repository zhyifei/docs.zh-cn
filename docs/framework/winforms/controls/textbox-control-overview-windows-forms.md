---
title: TextBox 控件概述
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
ms.openlocfilehash: 06ab460d720d17331881b5ba653263160eaf3cb3
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742802"
---
# <a name="textbox-control-overview-windows-forms"></a>TextBox 控件概述（Windows 窗体）
Windows 窗体文本框用于获取用户的输入或显示文本。 <xref:System.Windows.Forms.TextBox> 控件通常用于可编辑文本，但也可将其设为只读。 文本框可显示多个行，将文本自动换行到控件大小，并添加基本格式设置。 <xref:System.Windows.Forms.TextBox> 控件为显示的文本或输入到控件中的文本提供单一格式样式。 若要显示多种类型的格式化文本，请使用 <xref:System.Windows.Forms.RichTextBox> 控件。 有关详细信息，请参阅[RichTextBox 控件概述](richtextbox-control-overview-windows-forms.md)。  
  
## <a name="working-with-the-textbox-control"></a>使用 TextBox 控件  
 控件显示的文本包含在 <xref:System.Windows.Forms.TextBox.Text%2A> 属性中。 默认情况下，最多可以在一个文本框中输入2048个字符。 如果将 <xref:System.Windows.Forms.TextBox.Multiline%2A> 属性设置为 `true`，则最多可以输入 32 KB 的文本。 在设计时，可以使用 "属性" 窗口、在运行时在代码中或在运行时通过用户输入来设置 <xref:System.Windows.Forms.TextBox.Text%2A> 属性。 通过读取 <xref:System.Windows.Forms.TextBox.Text%2A> 属性，可以在运行时检索文本框的当前内容。  
  
 下面的代码示例在运行时设置控件中的文本。 `InitializeMyControl` 过程不会自动执行;必须调用它。  
  
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
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Forms.TextBox>
- [如何：在 Windows 窗体 TextBox 控件中控制插入点](how-to-control-the-insertion-point-in-a-windows-forms-textbox-control.md)
- [如何：使用 Windows 窗体 TextBox 控件创建密码文本框](how-to-create-a-password-text-box-with-the-windows-forms-textbox-control.md)
- [如何：创建只读文本框](how-to-create-a-read-only-text-box-windows-forms.md)
- [如何：在字符串中添加引号](how-to-put-quotation-marks-in-a-string-windows-forms.md)
- [如何：在 Windows 窗体 TextBox 控件中选择文本](how-to-select-text-in-the-windows-forms-textbox-control.md)
- [如何：在 Windows 窗体 TextBox 控件中查看多个行](how-to-view-multiple-lines-in-the-windows-forms-textbox-control.md)
- [TextBox 控件](textbox-control-windows-forms.md)
