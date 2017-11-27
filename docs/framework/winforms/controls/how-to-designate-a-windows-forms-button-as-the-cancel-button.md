---
title: "如何：将 Windows 窗体按钮指定为“取消”按钮"
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
- buttons [Windows Forms], cancel buttons
- Button control [Windows Forms], designating as cancel button
ms.assetid: 252f0834-e54b-44d9-96f7-ee5f50e94f2c
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 3bbdf2ec4f2353662f1077b9d95966e0a2ebd316
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-designate-a-windows-forms-button-as-the-cancel-button"></a>如何：将 Windows 窗体按钮指定为“取消”按钮
在任何 Windows 窗体中，你可以指定<xref:System.Windows.Forms.Button>控件取消按钮。 每当用户按 ESC 键时，无论哪个窗体上的其他控件具有焦点，则单击取消按钮。 通常，这样的按钮进行编程，使用户能够快速退出操作，而无须执行任何操作。  
  
### <a name="to-designate-the-cancel-button"></a>若要指定取消按钮  
  
1.  设置窗体的<xref:System.Windows.Forms.Form.CancelButton%2A>到适当的属性<xref:System.Windows.Forms.Button>控件。  
  
    ```vb  
    Private Sub SetCancelButton(ByVal myCancelBtn As Button)  
       Me.CancelButton = myCancelBtn  
    End Sub  
    ```  
  
    ```csharp  
    private void SetCancelButton(Button myCancelBtn)  
    {  
       this.CancelButton = myCancelBtn;  
    }  
    ```  
  
    ```cpp  
    private:  
       void SetCancelButton(Button ^ myCancelBtn)  
       {  
          this->CancelButton = myCancelBtn;  
       }  
    ```  
  
## <a name="see-also"></a>另请参阅  
 <xref:System.Windows.Forms.Form.CancelButton%2A>  
 [Button 控件概述](../../../../docs/framework/winforms/controls/button-control-overview-windows-forms.md)  
 [如何选择 Windows 窗体 Button 控件](../../../../docs/framework/winforms/controls/ways-to-select-a-windows-forms-button-control.md)  
 [如何：响应 Windows 窗体 Button 控件单击](../../../../docs/framework/winforms/controls/how-to-respond-to-windows-forms-button-clicks.md)  
 [如何：将 Windows 窗体 Button 控件指定为“接受”按钮](../../../../docs/framework/winforms/controls/how-to-designate-a-windows-forms-button-as-the-accept-button.md)  
 [Button 控件](../../../../docs/framework/winforms/controls/button-control-windows-forms.md)
