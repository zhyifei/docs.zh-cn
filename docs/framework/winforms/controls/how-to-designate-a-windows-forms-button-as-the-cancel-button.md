---
title: 如何：将 Windows 窗体按钮指定为取消按钮
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- buttons [Windows Forms], cancel buttons
- Button control [Windows Forms], designating as cancel button
ms.assetid: 252f0834-e54b-44d9-96f7-ee5f50e94f2c
ms.openlocfilehash: f8eacea0d21159d30d48e48be3093ddf8ca3d7d7
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/09/2019
ms.locfileid: "57722375"
---
# <a name="how-to-designate-a-windows-forms-button-as-the-cancel-button"></a><span data-ttu-id="e5e6b-102">如何：将 Windows 窗体按钮指定为取消按钮</span><span class="sxs-lookup"><span data-stu-id="e5e6b-102">How to: Designate a Windows Forms Button as the Cancel Button</span></span>
<span data-ttu-id="e5e6b-103">在任何 Windows 窗体中，可以将指定<xref:System.Windows.Forms.Button>控件为取消按钮。</span><span class="sxs-lookup"><span data-stu-id="e5e6b-103">On any Windows Form, you can designate a <xref:System.Windows.Forms.Button> control to be the cancel button.</span></span> <span data-ttu-id="e5e6b-104">每当用户按 ESC 键时，无论哪个窗体上的其他控件具有焦点时，单击取消按钮。</span><span class="sxs-lookup"><span data-stu-id="e5e6b-104">A cancel button is clicked whenever the user presses the ESC key, regardless of which other control on the form has the focus.</span></span> <span data-ttu-id="e5e6b-105">通常，设计这样的按钮，使用户能够快速退出操作而无须执行任何操作。</span><span class="sxs-lookup"><span data-stu-id="e5e6b-105">Such a button is usually programmed to enable the user to quickly exit an operation without committing to any action.</span></span>  
  
### <a name="to-designate-the-cancel-button"></a><span data-ttu-id="e5e6b-106">若要指定取消按钮</span><span class="sxs-lookup"><span data-stu-id="e5e6b-106">To designate the cancel button</span></span>  
  
1.  <span data-ttu-id="e5e6b-107">设置窗体的<xref:System.Windows.Forms.Form.CancelButton%2A>属性设置为相应<xref:System.Windows.Forms.Button>控件。</span><span class="sxs-lookup"><span data-stu-id="e5e6b-107">Set the form's <xref:System.Windows.Forms.Form.CancelButton%2A> property to the appropriate <xref:System.Windows.Forms.Button> control.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="e5e6b-108">请参阅</span><span class="sxs-lookup"><span data-stu-id="e5e6b-108">See also</span></span>
- <xref:System.Windows.Forms.Form.CancelButton%2A>
- [<span data-ttu-id="e5e6b-109">Button 控件概述</span><span class="sxs-lookup"><span data-stu-id="e5e6b-109">Button Control Overview</span></span>](button-control-overview-windows-forms.md)
- [<span data-ttu-id="e5e6b-110">如何选择 Windows 窗体 Button 控件</span><span class="sxs-lookup"><span data-stu-id="e5e6b-110">Ways to Select a Windows Forms Button Control</span></span>](ways-to-select-a-windows-forms-button-control.md)
- [<span data-ttu-id="e5e6b-111">如何：响应 Windows 窗体按钮单击</span><span class="sxs-lookup"><span data-stu-id="e5e6b-111">How to: Respond to Windows Forms Button Clicks</span></span>](how-to-respond-to-windows-forms-button-clicks.md)
- [<span data-ttu-id="e5e6b-112">如何：将 Windows 窗体按钮指定为接受按钮</span><span class="sxs-lookup"><span data-stu-id="e5e6b-112">How to: Designate a Windows Forms Button as the Accept Button</span></span>](how-to-designate-a-windows-forms-button-as-the-accept-button.md)
- [<span data-ttu-id="e5e6b-113">Button 控件</span><span class="sxs-lookup"><span data-stu-id="e5e6b-113">Button Control</span></span>](button-control-windows-forms.md)
