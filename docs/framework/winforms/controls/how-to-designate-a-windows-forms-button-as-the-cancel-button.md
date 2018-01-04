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
ms.workload: dotnet
ms.openlocfilehash: f3f61828b4c8b65ae984685610d6d8609953376a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-designate-a-windows-forms-button-as-the-cancel-button"></a><span data-ttu-id="f0840-102">如何：将 Windows 窗体按钮指定为“取消”按钮</span><span class="sxs-lookup"><span data-stu-id="f0840-102">How to: Designate a Windows Forms Button as the Cancel Button</span></span>
<span data-ttu-id="f0840-103">在任何 Windows 窗体中，你可以指定<xref:System.Windows.Forms.Button>控件取消按钮。</span><span class="sxs-lookup"><span data-stu-id="f0840-103">On any Windows Form, you can designate a <xref:System.Windows.Forms.Button> control to be the cancel button.</span></span> <span data-ttu-id="f0840-104">每当用户按 ESC 键时，无论哪个窗体上的其他控件具有焦点，则单击取消按钮。</span><span class="sxs-lookup"><span data-stu-id="f0840-104">A cancel button is clicked whenever the user presses the ESC key, regardless of which other control on the form has the focus.</span></span> <span data-ttu-id="f0840-105">通常，这样的按钮进行编程，使用户能够快速退出操作，而无须执行任何操作。</span><span class="sxs-lookup"><span data-stu-id="f0840-105">Such a button is usually programmed to enable the user to quickly exit an operation without committing to any action.</span></span>  
  
### <a name="to-designate-the-cancel-button"></a><span data-ttu-id="f0840-106">若要指定取消按钮</span><span class="sxs-lookup"><span data-stu-id="f0840-106">To designate the cancel button</span></span>  
  
1.  <span data-ttu-id="f0840-107">设置窗体的<xref:System.Windows.Forms.Form.CancelButton%2A>到适当的属性<xref:System.Windows.Forms.Button>控件。</span><span class="sxs-lookup"><span data-stu-id="f0840-107">Set the form's <xref:System.Windows.Forms.Form.CancelButton%2A> property to the appropriate <xref:System.Windows.Forms.Button> control.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="f0840-108">请参阅</span><span class="sxs-lookup"><span data-stu-id="f0840-108">See Also</span></span>  
 <xref:System.Windows.Forms.Form.CancelButton%2A>  
 [<span data-ttu-id="f0840-109">Button 控件概述</span><span class="sxs-lookup"><span data-stu-id="f0840-109">Button Control Overview</span></span>](../../../../docs/framework/winforms/controls/button-control-overview-windows-forms.md)  
 [<span data-ttu-id="f0840-110">如何选择 Windows 窗体 Button 控件</span><span class="sxs-lookup"><span data-stu-id="f0840-110">Ways to Select a Windows Forms Button Control</span></span>](../../../../docs/framework/winforms/controls/ways-to-select-a-windows-forms-button-control.md)  
 [<span data-ttu-id="f0840-111">如何：响应 Windows 窗体 Button 控件单击</span><span class="sxs-lookup"><span data-stu-id="f0840-111">How to: Respond to Windows Forms Button Clicks</span></span>](../../../../docs/framework/winforms/controls/how-to-respond-to-windows-forms-button-clicks.md)  
 [<span data-ttu-id="f0840-112">如何：将 Windows 窗体 Button 控件指定为“接受”按钮</span><span class="sxs-lookup"><span data-stu-id="f0840-112">How to: Designate a Windows Forms Button as the Accept Button</span></span>](../../../../docs/framework/winforms/controls/how-to-designate-a-windows-forms-button-as-the-accept-button.md)  
 [<span data-ttu-id="f0840-113">Button 控件</span><span class="sxs-lookup"><span data-stu-id="f0840-113">Button Control</span></span>](../../../../docs/framework/winforms/controls/button-control-windows-forms.md)
