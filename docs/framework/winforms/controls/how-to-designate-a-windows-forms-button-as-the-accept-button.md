---
title: 将一个按钮指定为 "接受" 按钮
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
ms.openlocfilehash: 1063f649768cac2c866390718b261a21e18ec4d3
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743269"
---
# <a name="how-to-designate-a-windows-forms-button-as-the-accept-button"></a>如何：将 Windows 窗体按钮指定为“接受”按钮
在任意 Windows 窗体上，可以将 <xref:System.Windows.Forms.Button> 控件指定为 "接受" 按钮，也称为 "默认" 按钮。 用户按 ENTER 键时，将单击默认按钮，而不考虑窗体上的其他哪个控件具有焦点。  
  
> [!NOTE]
> 这种情况的例外是，具有焦点的控件是另一个按钮，在这种情况下，将单击带有焦点的按钮（或多行文本框）或捕获 ENTER 键的自定义控件。  
  
### <a name="to-designate-the-accept-button"></a>指定 "接受" 按钮  
  
1. 将窗体的 <xref:System.Windows.Forms.Form.AcceptButton%2A> 属性设置为相应的 <xref:System.Windows.Forms.Button> 控件。  
  
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
- [如何选择 Windows 窗体 Button 控件](ways-to-select-a-windows-forms-button-control.md)
- [如何：响应 Windows 窗体 Button 控件单击](how-to-respond-to-windows-forms-button-clicks.md)
- [如何：将 Windows 窗体 Button 控件指定为“取消”按钮](how-to-designate-a-windows-forms-button-as-the-cancel-button.md)
- [Button 控件](button-control-windows-forms.md)
