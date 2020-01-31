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
# <a name="how-to-designate-a-windows-forms-button-as-the-accept-button"></a><span data-ttu-id="ac026-102">방법: Windows Forms Button을 적용 단추로 지정</span><span class="sxs-lookup"><span data-stu-id="ac026-102">How to: Designate a Windows Forms Button as the Accept Button</span></span>
<span data-ttu-id="ac026-103">在任意 Windows 窗体上，可以将 <xref:System.Windows.Forms.Button> 控件指定为 "接受" 按钮，也称为 "默认" 按钮。</span><span class="sxs-lookup"><span data-stu-id="ac026-103">On any Windows Form, you can designate a <xref:System.Windows.Forms.Button> control to be the accept button, also known as the default button.</span></span> <span data-ttu-id="ac026-104">用户按 ENTER 键时，将单击默认按钮，而不考虑窗体上的其他哪个控件具有焦点。</span><span class="sxs-lookup"><span data-stu-id="ac026-104">Whenever the user presses the ENTER key, the default button is clicked regardless of which other control on the form has the focus.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ac026-105">这种情况的例外是，具有焦点的控件是另一个按钮，在这种情况下，将单击带有焦点的按钮（或多行文本框）或捕获 ENTER 键的自定义控件。</span><span class="sxs-lookup"><span data-stu-id="ac026-105">The exceptions to this are when the control with focus is another button — in that case, the button with the focus will be clicked — or a multiline text box, or a custom control that traps the ENTER key.</span></span>  
  
### <a name="to-designate-the-accept-button"></a><span data-ttu-id="ac026-106">指定 "接受" 按钮</span><span class="sxs-lookup"><span data-stu-id="ac026-106">To designate the accept button</span></span>  
  
1. <span data-ttu-id="ac026-107">将窗体的 <xref:System.Windows.Forms.Form.AcceptButton%2A> 属性设置为相应的 <xref:System.Windows.Forms.Button> 控件。</span><span class="sxs-lookup"><span data-stu-id="ac026-107">Set the form's <xref:System.Windows.Forms.Form.AcceptButton%2A> property to the appropriate <xref:System.Windows.Forms.Button> control.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="ac026-108">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ac026-108">See also</span></span>

- <xref:System.Windows.Forms.Form.AcceptButton%2A>
- [<span data-ttu-id="ac026-109">Button 컨트롤 개요</span><span class="sxs-lookup"><span data-stu-id="ac026-109">Button Control Overview</span></span>](button-control-overview-windows-forms.md)
- [<span data-ttu-id="ac026-110">Windows Forms Button 컨트롤 선택 방법</span><span class="sxs-lookup"><span data-stu-id="ac026-110">Ways to Select a Windows Forms Button Control</span></span>](ways-to-select-a-windows-forms-button-control.md)
- [<span data-ttu-id="ac026-111">방법: Windows Forms 단추 클릭에 응답</span><span class="sxs-lookup"><span data-stu-id="ac026-111">How to: Respond to Windows Forms Button Clicks</span></span>](how-to-respond-to-windows-forms-button-clicks.md)
- [<span data-ttu-id="ac026-112">방법: Windows Forms Button을 취소 단추로 지정</span><span class="sxs-lookup"><span data-stu-id="ac026-112">How to: Designate a Windows Forms Button as the Cancel Button</span></span>](how-to-designate-a-windows-forms-button-as-the-cancel-button.md)
- [<span data-ttu-id="ac026-113">Button 컨트롤</span><span class="sxs-lookup"><span data-stu-id="ac026-113">Button Control</span></span>](button-control-windows-forms.md)
