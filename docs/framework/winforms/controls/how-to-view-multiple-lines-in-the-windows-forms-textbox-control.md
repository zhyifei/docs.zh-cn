---
title: 如何：在 Windows 窗体 TextBox 控件中查看多个行
ms.date: 03/30/2017
helpviewer_keywords:
- newline
- end of line
- ScrollBars property [Windows Forms], in TextBox control
- CRLF
- MultiLine property in TextBox control
- line-feed
- TextBox control [Windows Forms], viewing multiple lines
- carriage return
ms.assetid: 43173201-0b74-4067-a472-605029ca5f35
ms.openlocfilehash: c826a519d8be05430eb6e2434209424514347b5e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-view-multiple-lines-in-the-windows-forms-textbox-control"></a>如何：在 Windows 窗体 TextBox 控件中查看多个行
默认情况下，Windows 窗体<xref:System.Windows.Forms.TextBox>控件显示单个文本行，并不会显示滚动条。 文本的长度超过可用空间，部分的文本可见。 你可以通过设置来更改此默认行为<xref:System.Windows.Forms.TextBox.Multiline%2A>， <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A>，和<xref:System.Windows.Forms.TextBox.ScrollBars%2A>为适当的值的属性。  
  
### <a name="to-display-a-carriage-return-in-the-textbox-control"></a>若要显示在文本框控件中返回一个回车符  
  
-   若要显示多行中返回一个回车符<xref:System.Windows.Forms.TextBox>，使用<xref:System.Environment.NewLine%2A>属性。  
  
     请注意，转义字符的解释 (\\) 是特定于语言的。 Visual Basic 使用`Chr$(13) & Chr$(10)`的回车符和换行符字符组合。  
  
### <a name="to-view-multiple-lines-in-the-textbox-control"></a>若要查看多行文本框控件中  
  
1.  将 <xref:System.Windows.Forms.TextBox.Multiline%2A> 属性设置为 `true`。 如果<xref:System.Windows.Forms.TextBoxBase.WordWrap%2A>是`true`（默认值），然后控件中的文本将显示为一个或多个段落中; 否则它将显示为列表中，在其中某些行可能会剪裁在控件的边缘。  
  
2.  将 <xref:System.Windows.Forms.TextBox.ScrollBars%2A> 属性设置为适当的值。  
  
    |值|描述|  
    |-----------|-----------------|  
    |<xref:System.Windows.Forms.ScrollBars.None>|使用此值，如果文本将是一个段落，几乎始终适合控件。 用户可以使用鼠标指针在控件内移动，如果文本是很长时间才能显示在一次。|  
    |<xref:System.Windows.Forms.ScrollBars.Horizontal>|使用此值，如果你想要显示的行，其中一些可能超过的宽度列表<xref:System.Windows.Forms.TextBox>控件。|  
    |<xref:System.Windows.Forms.ScrollBars.Both>|如果该列表可能会超过控件的高度，则使用此值。|  
  
3.  将 <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A> 属性设置为适当的值。  
  
    |值|描述|  
    |-----------|-----------------|  
    |`false`|控件中的文本不会自动换行，所以它将向右滚动，直到到达一个分行符。 使用此值，如果你选择了<xref:System.Windows.Forms.ScrollBars.Horizontal>滚动条或<xref:System.Windows.Forms.ScrollBars.Both>上面。|  
    |`true`（默认值）|水平滚动条将不会出现。 使用此值，如果你选择了<xref:System.Windows.Forms.ScrollBars.Vertical>滚动条或<xref:System.Windows.Forms.ScrollBars.None>、 更高版本，以显示一个或多个段落。|  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Windows.Forms.TextBox>  
 [TextBox 控件概述](../../../../docs/framework/winforms/controls/textbox-control-overview-windows-forms.md)  
 [如何：在 Windows 窗体 TextBox 控件中控制插入点](../../../../docs/framework/winforms/controls/how-to-control-the-insertion-point-in-a-windows-forms-textbox-control.md)  
 [如何：使用 Windows 窗体 TextBox 控件创建密码文本框](../../../../docs/framework/winforms/controls/how-to-create-a-password-text-box-with-the-windows-forms-textbox-control.md)  
 [如何：创建只读文本框](../../../../docs/framework/winforms/controls/how-to-create-a-read-only-text-box-windows-forms.md)  
 [如何：在字符串中添加引号](../../../../docs/framework/winforms/controls/how-to-put-quotation-marks-in-a-string-windows-forms.md)  
 [如何：在 Windows 窗体 TextBox 控件中选择文本](../../../../docs/framework/winforms/controls/how-to-select-text-in-the-windows-forms-textbox-control.md)  
 [TextBox 控件](../../../../docs/framework/winforms/controls/textbox-control-windows-forms.md)
