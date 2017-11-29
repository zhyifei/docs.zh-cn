---
title: "如何：确定 Windows 窗体 RichTextBox 控件中的格式设置特性何时更改"
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
- examples [Windows Forms], text boxes
- RichTextBox control [Windows Forms], determining font changes
- text boxes [Windows Forms], determining font changes
- SelChange event
ms.assetid: bdfed015-f77a-41e5-b38f-f8629b2fa166
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 0dc272e26124acf5c6bd5cf3030941c26c021c49
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-determine-when-formatting-attributes-change-in-the-windows-forms-richtextbox-control"></a>如何：确定 Windows 窗体 RichTextBox 控件中的格式设置特性何时更改
一种常用的 Windows 窗体<xref:System.Windows.Forms.RichTextBox>控件格式化文本属性例如字体选项或段落样式。 你的应用程序可能需要跟踪的文本格式用于显示一个工具栏，如下所示许多字处理应用程序中的任何更改。  
  
### <a name="to-respond-to-changes-in-formatting-attributes"></a>若要响应的格式设置特性的更改  
  
1.  在中编写代码<xref:System.Windows.Forms.RichTextBox.SelectionChanged>事件处理程序来执行相应的措施具体取决于值的属性。 下面的示例更改的值根据工具栏按钮的外观<xref:System.Windows.Forms.RichTextBox.SelectionBullet%2A>属性。 插入点移动控件中时，将仅更新工具栏按钮。  
  
     下面的示例假定的窗体具有<xref:System.Windows.Forms.RichTextBox>控件和<xref:System.Windows.Forms.ToolBar>包含一个工具栏按钮控件。 工具栏和工具栏按钮有关的详细信息，请参阅[如何： 向 ToolBar 控件添加按钮](../../../../docs/framework/winforms/controls/how-to-add-buttons-to-a-toolbar-control.md)。  
  
    ```vb  
    ' The following code assumes the existence of a toolbar control  
    ' with at least one toolbar button.  
    Private Sub RichTextBox1_SelectionChanged(ByVal sender As Object, ByVal e As System.EventArgs) Handles RichTextBox1.SelectionChanged  
       If RichTextBox1.SelectionBullet = True Then  
          ' Bullet button on toolbar should appear pressed  
          ToolBarButton1.Pushed = True  
       Else  
           ' Bullet button on toolbar should appear unpressed  
           ToolBarButton1.Pushed = False  
       End If  
    End Sub  
    ```  
  
    ```csharp  
    // The following code assumes the existence of a toolbar control  
    // with at least one toolbar button.  
    private void richTextBox1_SelectionChanged(object sender,  
    System.EventArgs e)  
    {  
       if (richTextBox1.SelectionBullet == true)   
       {  
          // Bullet button on toolbar should appear pressed  
          toolBarButton1.Pushed = true;  
       }  
       else   
       {  
          // Bullet button on toolbar should appear unpressed  
          toolBarButton1.Pushed = false;  
       }  
    }  
    ```  
  
    ```cpp  
    // The following code assumes the existence of a toolbar control  
    // with at least one toolbar button.  
    private:  
       System::Void richTextBox1_SelectionChanged(  
          System::Object ^  sender, System::EventArgs ^  e)  
       {  
          if (richTextBox1->SelectionBullet == true)  
          {  
             // Bullet button on toolbar should appear pressed  
             toolBarButton1->Pushed = true;  
          }  
          else  
          {  
             // Bullet button on toolbar should appear unpressed  
             toolBarButton1->Pushed = false;  
          }  
       }  
    ```  
  
## <a name="see-also"></a>另请参阅  
 <xref:System.Windows.Forms.RichTextBox.SelectionChanged>  
 <xref:System.Windows.Forms.RichTextBox>  
 [RichTextBox 控件](../../../../docs/framework/winforms/controls/richtextbox-control-windows-forms.md)  
 [在 Windows 窗体上使用的控件](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)
