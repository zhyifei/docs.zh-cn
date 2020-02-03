---
title: 将某个按钮指定为 "取消" 按钮
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- buttons [Windows Forms], cancel buttons
- Button control [Windows Forms], designating as cancel button
ms.assetid: 252f0834-e54b-44d9-96f7-ee5f50e94f2c
ms.openlocfilehash: 123b3e275065efadd24815320ea7d855808e60b9
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743259"
---
# <a name="how-to-designate-a-windows-forms-button-as-the-cancel-button"></a>如何：将 Windows 窗体按钮指定为“取消”按钮
在任何 Windows 窗体上，都可以将 <xref:System.Windows.Forms.Button> 控件指定为 "取消" 按钮。 用户按 ESC 键时单击 "取消" 按钮，而不考虑窗体上的其他哪个控件具有焦点。 通常对此类按钮进行编程，使用户能够快速退出操作，而无需提交任何操作。  
  
### <a name="to-designate-the-cancel-button"></a>指定 "取消" 按钮  
  
1. 将窗体的 <xref:System.Windows.Forms.Form.CancelButton%2A> 属性设置为相应的 <xref:System.Windows.Forms.Button> 控件。  
  
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

- <xref:System.Windows.Forms.Form.CancelButton%2A>
- [Button 控件概述](button-control-overview-windows-forms.md)
- [如何选择 Windows 窗体 Button 控件](ways-to-select-a-windows-forms-button-control.md)
- [如何：响应 Windows 窗体 Button 控件单击](how-to-respond-to-windows-forms-button-clicks.md)
- [如何：将 Windows 窗体 Button 控件指定为“接受”按钮](how-to-designate-a-windows-forms-button-as-the-accept-button.md)
- [Button 控件](button-control-windows-forms.md)
