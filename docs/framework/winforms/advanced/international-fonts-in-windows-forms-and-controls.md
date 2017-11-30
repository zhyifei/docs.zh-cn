---
title: "Windows 窗体和控件中的国际字体"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- fonts [Windows Forms], international
- international applications [Windows Forms], character display
- fonts [Windows Forms], globalization considerations
- localization [Windows Forms], fonts
- Windows Forms controls, labels
- font fallback in Windows Forms
- globalization [Windows Forms], character sets
ms.assetid: 2c3066df-9bac-479a-82b2-79e484b346a3
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 5901113021deffd601b5325ff9a1b8912e74329d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="international-fonts-in-windows-forms-and-controls"></a>Windows 窗体和控件中的国际字体
国际应用程序中选择字体的推荐的方法是使用字体回退，只要有可能。 在系统确定哪一脚本字符的字体后备意味着属于。  
  
## <a name="using-font-fallback"></a>使用字体回退  
 若要利用此功能，不设置<xref:System.Drawing.Font>为你的窗体或任何其他元素的属性。 应用程序将自动使用不同的操作系统的一种本地化语言到另一个使用默认系统字体。 应用程序运行时，系统将自动为在操作系统中选定的区域性提供正确的字体。  
  
 没有不设置字体，即对于更改字体样式规则的例外。 这可能会在其中用户单击按钮以粗体使文字在文本框中显示的应用程序很重要。 为此，请将编写一个函数来更改文本框中的字体样式为加粗，基于任何窗体的字体。 务必要在两个位置中调用此函数： 中按钮的<xref:System.Windows.Forms.Control.Click>事件处理程序并在<xref:System.Windows.Forms.Control.FontChanged>事件处理程序。 如果仅在调用该函数<xref:System.Windows.Forms.Control.Click>事件处理程序和其他一些代码更改整个窗体的字体系列、 文本框中将不会更改与窗体的其余部分。  
  
```  
' Visual Basic  
Private Sub MakeBold()  
   ' Change the TextBox to a bold version of the form font  
   TextBox1.Font = New Font(Me.Font, FontStyle.Bold)  
End Sub  
  
Private Sub Button1_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles Button1.Click  
   ' Clicking this button makes the TextBox bold  
   MakeBold()  
End Sub  
  
Private Sub Form1_FontChanged(ByVal sender As Object, ByVal e As System.EventArgs) Handles MyBase.FontChanged  
   ' If the TextBox is already bold and the form's font changes,  
   ' change the TextBox to a bold version of the new form font  
   If (TextBox1.Font.Style = FontStyle.Bold) Then  
      MakeBold()  
   End If  
End Sub  
  
// C#  
private void button1_Click(object sender, System.EventArgs e)  
{  
   // Clicking this button makes the TextBox bold  
   MakeBold();  
}  
  
private void MakeBold()   
{  
   // Change the TextBox to a bold version of the form's font  
   textBox1.Font = new Font(this.Font, FontStyle.Bold);  
}  
  
private void Form1_FontChanged(object sender, System.EventArgs e)  
{  
   // If the TextBox is already bold and the form's font changes,  
   // change the TextBox to a bold version of the new form font  
   if (textBox1.Font.Style == FontStyle.Bold)   
   {  
      MakeBold();  
   }  
}  
```  
  
 但是，当你在本地化你的应用程序时, 加粗字体可能不佳对于某些语言显示。 如果这是一个问题，你想让本地化人员来切换从粗体到常规文本的字体的选项。 由于本地化人员通常不是开发人员，但没有访问源代码，仅对资源的文件，此选项需要在资源文件中设置。 若要执行此操作，将设置<xref:System.Drawing.Font.Bold%2A>属性`true`。 这会导致正在写出到资源文件，本地化人员可以在其中编辑字体设置。 然后，你编写代码之后`InitializeComponent`方法来重置字体基于任何窗体的字体，但使用的字体样式资源文件中指定。  
  
```  
' Visual Basic  
TextBox1.Font = New System.Drawing.Font(Me.Font, TextBox1.Font.Style)  
  
// C#  
textBox1.Font = new System.Drawing.Font(this.Font, textBox1.Font.Style);  
```  
  
## <a name="see-also"></a>另请参阅  
 [全球化 Windows 窗体](../../../../docs/framework/winforms/advanced/globalizing-windows-forms.md)  
 [使用字体和文本](../../../../docs/framework/winforms/advanced/using-fonts-and-text.md)
