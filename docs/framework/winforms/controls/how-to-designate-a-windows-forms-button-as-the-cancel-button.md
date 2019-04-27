---
title: 如何：将 Windows 窗体按钮指定为“取消”按钮
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- buttons [Windows Forms], cancel buttons
- Button control [Windows Forms], designating as cancel button
ms.assetid: 252f0834-e54b-44d9-96f7-ee5f50e94f2c
ms.openlocfilehash: 8170190145e76a86f5343bc42b39be7fb9d61a0f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "62010717"
---
# <a name="how-to-designate-a-windows-forms-button-as-the-cancel-button"></a>如何：将 Windows 窗体按钮指定为“取消”按钮
在任何 Windows 窗体中，可以将指定<xref:System.Windows.Forms.Button>控件为取消按钮。 每当用户按 ESC 键时，无论哪个窗体上的其他控件具有焦点时，单击取消按钮。 通常，设计这样的按钮，使用户能够快速退出操作而无须执行任何操作。  
  
### <a name="to-designate-the-cancel-button"></a>若要指定取消按钮  
  
1. 设置窗体的<xref:System.Windows.Forms.Form.CancelButton%2A>属性设置为相应<xref:System.Windows.Forms.Button>控件。  
  
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
  
## <a name="see-also"></a>请参阅

- <xref:System.Windows.Forms.Form.CancelButton%2A>
- [Button 控件概述](button-control-overview-windows-forms.md)
- [如何选择 Windows 窗体 Button 控件](ways-to-select-a-windows-forms-button-control.md)
- [如何：响应 Windows 窗体按钮单击](how-to-respond-to-windows-forms-button-clicks.md)
- [如何：将 Windows 窗体按钮指定为接受按钮](how-to-designate-a-windows-forms-button-as-the-accept-button.md)
- [Button 控件](button-control-windows-forms.md)
