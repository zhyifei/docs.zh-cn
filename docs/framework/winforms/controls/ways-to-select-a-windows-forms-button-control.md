---
title: 选择 Windows 窗体 Button 控件的方法
ms.date: 03/30/2017
helpviewer_keywords:
- Button control [Windows Forms], selecting
ms.assetid: fe2fc058-5118-4f70-b264-6147d64a7a8d
ms.openlocfilehash: 908751401d812be0403af5517d9bbf2ad7344f35
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54573798"
---
# <a name="ways-to-select-a-windows-forms-button-control"></a><span data-ttu-id="74a4b-102">选择 Windows 窗体 Button 控件的方法</span><span class="sxs-lookup"><span data-stu-id="74a4b-102">Ways to Select a Windows Forms Button Control</span></span>
<span data-ttu-id="74a4b-103">Windows 窗体按钮可以选择以下方面：</span><span class="sxs-lookup"><span data-stu-id="74a4b-103">A Windows Forms button can be selected in the following ways:</span></span>  
  
-   <span data-ttu-id="74a4b-104">使用鼠标单击的按钮。</span><span class="sxs-lookup"><span data-stu-id="74a4b-104">Use a mouse to click the button.</span></span>  
  
-   <span data-ttu-id="74a4b-105">调用该按钮的<xref:System.Windows.Forms.Control.Click>在代码中的事件。</span><span class="sxs-lookup"><span data-stu-id="74a4b-105">Invoke the button's <xref:System.Windows.Forms.Control.Click> event in code.</span></span>  
  
-   <span data-ttu-id="74a4b-106">通过按 TAB 键将焦点移到按钮并按空格键或 ENTER 键，然后选择该按钮。</span><span class="sxs-lookup"><span data-stu-id="74a4b-106">Move the focus to the button by pressing the TAB key, and then choose the button by pressing the SPACEBAR or ENTER.</span></span>  
  
-   <span data-ttu-id="74a4b-107">按该按钮的访问密钥 （ALT + 带下划线的字母）。</span><span class="sxs-lookup"><span data-stu-id="74a4b-107">Press the access key (ALT + the underlined letter) for the button.</span></span> <span data-ttu-id="74a4b-108">有关访问密钥的详细信息，请参阅[如何：Windows 窗体控件的创建访问键](../../../../docs/framework/winforms/controls/how-to-create-access-keys-for-windows-forms-controls.md)。</span><span class="sxs-lookup"><span data-stu-id="74a4b-108">For more information about access keys, see [How to: Create Access Keys for Windows Forms Controls](../../../../docs/framework/winforms/controls/how-to-create-access-keys-for-windows-forms-controls.md).</span></span>  
  
-   <span data-ttu-id="74a4b-109">如果按钮是窗体的"接受"按钮，并按 enter 键选择按钮，即使另一个控件具有焦点，但该控件可以是另一个按钮、 多行文本框中或捕获 enter 键的自定义控件。</span><span class="sxs-lookup"><span data-stu-id="74a4b-109">If the button is the "accept" button of the form, pressing ENTER chooses the button, even if another control has the focus — except if that other control is another button, a multi-line text box, or a custom control that traps the enter key.</span></span>  
  
-   <span data-ttu-id="74a4b-110">如果该按钮的窗体的"取消"按钮，按 esc 键选择按钮，即使另一个控件具有焦点。</span><span class="sxs-lookup"><span data-stu-id="74a4b-110">If the button is the "cancel" button of the form, pressing ESC chooses the button, even if another control has the focus.</span></span>  
  
-   <span data-ttu-id="74a4b-111">调用<xref:System.Windows.Forms.Button.PerformClick%2A>方法以编程方式选择的按钮。</span><span class="sxs-lookup"><span data-stu-id="74a4b-111">Call the <xref:System.Windows.Forms.Button.PerformClick%2A> method to select the button programmatically.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="74a4b-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="74a4b-112">See also</span></span>
- [<span data-ttu-id="74a4b-113">Button 控件概述</span><span class="sxs-lookup"><span data-stu-id="74a4b-113">Button Control Overview</span></span>](../../../../docs/framework/winforms/controls/button-control-overview-windows-forms.md)
- [<span data-ttu-id="74a4b-114">如何：响应 Windows 窗体按钮单击</span><span class="sxs-lookup"><span data-stu-id="74a4b-114">How to: Respond to Windows Forms Button Clicks</span></span>](../../../../docs/framework/winforms/controls/how-to-respond-to-windows-forms-button-clicks.md)
- [<span data-ttu-id="74a4b-115">Button 控件</span><span class="sxs-lookup"><span data-stu-id="74a4b-115">Button Control</span></span>](../../../../docs/framework/winforms/controls/button-control-windows-forms.md)
