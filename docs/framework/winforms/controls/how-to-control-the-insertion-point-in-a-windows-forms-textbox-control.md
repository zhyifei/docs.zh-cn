---
title: "如何：控制 Windows 窗体 TextBox 控件中的插入点"
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
- TextBox control [Windows Forms], insertion point
- insertion points [Windows Forms], TextBox controls
- text boxes [Windows Forms], controlling insertion point
ms.assetid: 5bee7d34-5121-429e-ab1f-d8ff67bc74c1
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 5cc3dab3acafdb151cf14f81145ef47e5a6ff689
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-control-the-insertion-point-in-a-windows-forms-textbox-control"></a>如何：控制 Windows 窗体 TextBox 控件中的插入点
在 Windows 窗体时<xref:System.Windows.Forms.TextBox>控件首先获得焦点时，文本框内的默认插入位于任何现有的文本的左边。 用户可以移动鼠标或键盘的插入点。 如果文本框失去并且然后重新获得焦点，插入点将用户上次放置的任何位置它。  
  
 在某些情况下，此行为可能给用户带来不便。 在文字处理应用程序，用户可能希望新字符后任何现有的文本显示。 在数据输入应用程序中，用户可能会要替换任何现有项的新字符。 <xref:System.Windows.Forms.TextBoxBase.SelectionStart%2A>和<xref:System.Windows.Forms.TextBoxBase.SelectionLength%2A>属性使您能够修改以满足你的目的的行为。  
  
### <a name="to-control-the-insertion-point-in-a-textbox-control"></a>若要控制文本框控件中的插入点  
  
1.  将 <xref:System.Windows.Forms.TextBoxBase.SelectionStart%2A> 属性设置为适当的值。 零放置插入点的第一个字符左侧。  
  
2.  （可选）设置<xref:System.Windows.Forms.TextBoxBase.SelectionLength%2A>属性设置为你想要选择的文本的长度。  
  
     下面的代码始终为 0 返回插入点。 `TextBox1_Enter`事件处理程序必须绑定到控件; 有关详细信息，请参阅[Windows 窗体中创建事件处理程序](../../../../docs/framework/winforms/creating-event-handlers-in-windows-forms.md)。  
  
    ```vb  
    Private Sub TextBox1_Enter(ByVal sender As Object, ByVal e As System.EventArgs) Handles TextBox1.Enter  
       TextBox1.SelectionStart = 0  
       TextBox1.SelectionLength = 0  
    End Sub  
    ```  
  
    ```csharp  
    private void textBox1_Enter(Object sender, System.EventArgs e) {  
       textBox1.SelectionStart = 0;  
       textBox1.SelectionLength = 0;  
    }  
    ```  
  
    ```cpp  
    private:  
       void textBox1_Enter(System::Object ^  sender,  
          System::EventArgs ^  e)  
       {  
          textBox1->SelectionStart = 0;  
          textBox1->SelectionLength = 0;  
       }  
    ```  
  
## <a name="making-the-insertion-point-visible-by-default"></a>使插入点默认情况下可见  
 <xref:System.Windows.Forms.TextBox>插入点，则默认情况下，在新的窗体才可见<xref:System.Windows.Forms.TextBox>控件是第一个 tab 键顺序。 否则，插入点将显示仅当为<xref:System.Windows.Forms.TextBox>使用鼠标或键盘焦点。  
  
#### <a name="to-make-the-text-box-insertion-point-visible-by-default-on-a-new-form"></a>若要使文本框将插入点默认情况下，新的窗体上可见  
  
-   设置<xref:System.Windows.Forms.TextBox>控件的<xref:System.Windows.Forms.Control.TabIndex%2A>属性`0`。  
  
## <a name="see-also"></a>另请参阅  
 <xref:System.Windows.Forms.TextBox>  
 [TextBox 控件概述](../../../../docs/framework/winforms/controls/textbox-control-overview-windows-forms.md)  
 [如何：使用 Windows 窗体 TextBox 控件创建密码文本框](../../../../docs/framework/winforms/controls/how-to-create-a-password-text-box-with-the-windows-forms-textbox-control.md)  
 [如何：创建只读文本框](../../../../docs/framework/winforms/controls/how-to-create-a-read-only-text-box-windows-forms.md)  
 [如何：在字符串中添加引号](../../../../docs/framework/winforms/controls/how-to-put-quotation-marks-in-a-string-windows-forms.md)  
 [如何：在 Windows 窗体 TextBox 控件中选择文本](../../../../docs/framework/winforms/controls/how-to-select-text-in-the-windows-forms-textbox-control.md)  
 [如何：在 Windows 窗体 TextBox 控件中查看多个行](../../../../docs/framework/winforms/controls/how-to-view-multiple-lines-in-the-windows-forms-textbox-control.md)  
 [TextBox 控件](../../../../docs/framework/winforms/controls/textbox-control-windows-forms.md)
