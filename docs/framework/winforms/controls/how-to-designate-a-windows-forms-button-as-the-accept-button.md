---
title: "如何：将 Windows 窗体按钮指定为“接受”按钮"
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
- buttons [Windows Forms], default on Windows Forms
- Accept button on Windows Forms
- Button control [Windows Forms], designating as default
- Windows Forms controls, default button on form
ms.assetid: 22cc9da6-b913-4e04-9554-dee443ac5c3a
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 0bf5f8dbf8718cb6a30883395d54c5cbc6bafaff
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-designate-a-windows-forms-button-as-the-accept-button"></a>如何：将 Windows 窗体按钮指定为“接受”按钮
在任何 Windows 窗体中，你可以指定<xref:System.Windows.Forms.Button>控件接受按钮，也称为默认按钮。 每当用户按 ENTER 键，无论哪个窗体上的其他控件具有焦点单击默认按钮。  
  
> [!NOTE]
>  为以下情形时具有焦点的控件是另一个按钮的异常-将在这种情况下，单击具有焦点的按钮-/ 多行文本框中，或自定义控件捕获 ENTER 键。  
  
### <a name="to-designate-the-accept-button"></a>若要指定接受按钮  
  
1.  设置窗体的<xref:System.Windows.Forms.Form.AcceptButton%2A>到适当的属性<xref:System.Windows.Forms.Button>控件。  
  
    ```vb  
    Private Sub SetDefault(ByVal myDefaultBtn As Button)  
      Me.AcceptButton = myDefaultBtn   
    End Sub  
    ```  
  
    ```csharp  
    private void SetDefault(Button myDefaultBtn)  
    {  
       this.AcceptButton = myDefaultBtn;  
    }  
    ```  
  
    ```cpp  
    private:  
       void SetDefault(Button ^ myDefaultBtn)  
       {  
          this->AcceptButton = myDefaultBtn;  
       }  
    ```  
  
## <a name="see-also"></a>另请参阅  
 <xref:System.Windows.Forms.Form.AcceptButton%2A>  
 [Button 控件概述](../../../../docs/framework/winforms/controls/button-control-overview-windows-forms.md)  
 [如何选择 Windows 窗体 Button 控件](../../../../docs/framework/winforms/controls/ways-to-select-a-windows-forms-button-control.md)  
 [如何：响应 Windows 窗体 Button 控件单击](../../../../docs/framework/winforms/controls/how-to-respond-to-windows-forms-button-clicks.md)  
 [如何：将 Windows 窗体 Button 控件指定为“取消”按钮](../../../../docs/framework/winforms/controls/how-to-designate-a-windows-forms-button-as-the-cancel-button.md)  
 [Button 控件](../../../../docs/framework/winforms/controls/button-control-windows-forms.md)
