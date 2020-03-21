---
title: 将按钮指定为"接受按钮"
ms.date: 03/30/2017
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
ms.openlocfilehash: ca5f691fb26db5c4adcb48405c9600b54827104c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79142142"
---
# <a name="how-to-designate-a-windows-forms-button-as-the-accept-button"></a>如何：将 Windows 窗体按钮指定为“接受”按钮
在任何 Windows 窗体上，都可以将<xref:System.Windows.Forms.Button>控件指定为接受按钮，也称为默认按钮。 每当用户按下 ENTER 键时，无论窗体上哪个其他控件具有焦点，都会单击默认按钮。  
  
> [!NOTE]
> 例外情况是，具有焦点的控件是另一个按钮（在这种情况下，将单击具有焦点的按钮）或多行文本框或捕获 ENTER 键的自定义控件。  
  
### <a name="to-designate-the-accept-button"></a>指定接受按钮  
  
1. 将窗体的属性<xref:System.Windows.Forms.Form.AcceptButton%2A>设置为相应的<xref:System.Windows.Forms.Button>控件。  
  
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

- <xref:System.Windows.Forms.Form.AcceptButton%2A>
- [Button 控件概述](button-control-overview-windows-forms.md)
- [选择 Windows 窗体 Button 控件的方法](ways-to-select-a-windows-forms-button-control.md)
- [如何：响应 Windows 窗体按钮的单击](how-to-respond-to-windows-forms-button-clicks.md)
- [如何：将 Windows 窗体按钮指定为“取消”按钮](how-to-designate-a-windows-forms-button-as-the-cancel-button.md)
- [Button 控件](button-control-windows-forms.md)
