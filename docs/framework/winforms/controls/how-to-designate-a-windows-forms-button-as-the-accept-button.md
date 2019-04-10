---
title: 如何：将 Windows 窗体按钮指定为“接受”按钮
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
ms.openlocfilehash: 8e608bb2cb4635ef1d29fd7a0aff3ac95fcd9af5
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2019
ms.locfileid: "59309818"
---
# <a name="how-to-designate-a-windows-forms-button-as-the-accept-button"></a><span data-ttu-id="f620f-102">如何：将 Windows 窗体按钮指定为“接受”按钮</span><span class="sxs-lookup"><span data-stu-id="f620f-102">How to: Designate a Windows Forms Button as the Accept Button</span></span>
<span data-ttu-id="f620f-103">在任何 Windows 窗体中，可以将指定<xref:System.Windows.Forms.Button>控件成为接受按钮，也称为默认按钮。</span><span class="sxs-lookup"><span data-stu-id="f620f-103">On any Windows Form, you can designate a <xref:System.Windows.Forms.Button> control to be the accept button, also known as the default button.</span></span> <span data-ttu-id="f620f-104">每当用户按 ENTER 键，无论哪个窗体上的其他控件具有焦点单击默认按钮。</span><span class="sxs-lookup"><span data-stu-id="f620f-104">Whenever the user presses the ENTER key, the default button is clicked regardless of which other control on the form has the focus.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f620f-105">为以下情形时具有焦点的控件是另一个按钮的异常，将在这种情况下，单击具有焦点的按钮，或多行文本框中或捕获 ENTER 键的自定义控件。</span><span class="sxs-lookup"><span data-stu-id="f620f-105">The exceptions to this are when the control with focus is another button — in that case, the button with the focus will be clicked — or a multiline text box, or a custom control that traps the ENTER key.</span></span>  
  
### <a name="to-designate-the-accept-button"></a><span data-ttu-id="f620f-106">若要指定接受按钮</span><span class="sxs-lookup"><span data-stu-id="f620f-106">To designate the accept button</span></span>  
  
1. <span data-ttu-id="f620f-107">设置窗体的<xref:System.Windows.Forms.Form.AcceptButton%2A>属性设置为相应<xref:System.Windows.Forms.Button>控件。</span><span class="sxs-lookup"><span data-stu-id="f620f-107">Set the form's <xref:System.Windows.Forms.Form.AcceptButton%2A> property to the appropriate <xref:System.Windows.Forms.Button> control.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="f620f-108">请参阅</span><span class="sxs-lookup"><span data-stu-id="f620f-108">See also</span></span>

- <xref:System.Windows.Forms.Form.AcceptButton%2A>
- [<span data-ttu-id="f620f-109">Button 控件概述</span><span class="sxs-lookup"><span data-stu-id="f620f-109">Button Control Overview</span></span>](button-control-overview-windows-forms.md)
- [<span data-ttu-id="f620f-110">选择 Windows 窗体 Button 控件的方法</span><span class="sxs-lookup"><span data-stu-id="f620f-110">Ways to Select a Windows Forms Button Control</span></span>](ways-to-select-a-windows-forms-button-control.md)
- [<span data-ttu-id="f620f-111">如何：响应 Windows 窗体按钮的单击</span><span class="sxs-lookup"><span data-stu-id="f620f-111">How to: Respond to Windows Forms Button Clicks</span></span>](how-to-respond-to-windows-forms-button-clicks.md)
- [<span data-ttu-id="f620f-112">如何：将 Windows 窗体按钮指定为“取消”按钮</span><span class="sxs-lookup"><span data-stu-id="f620f-112">How to: Designate a Windows Forms Button as the Cancel Button</span></span>](how-to-designate-a-windows-forms-button-as-the-cancel-button.md)
- [<span data-ttu-id="f620f-113">Button 控件</span><span class="sxs-lookup"><span data-stu-id="f620f-113">Button Control</span></span>](button-control-windows-forms.md)
