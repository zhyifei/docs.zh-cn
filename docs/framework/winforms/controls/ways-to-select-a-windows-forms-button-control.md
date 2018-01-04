---
title: "选择 Windows 窗体 Button 控件的方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: Button control [Windows Forms], selecting
ms.assetid: fe2fc058-5118-4f70-b264-6147d64a7a8d
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 0b6fa31b89b8fbe50077933cf04aa3c17db86438
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="ways-to-select-a-windows-forms-button-control"></a><span data-ttu-id="93826-102">选择 Windows 窗体 Button 控件的方法</span><span class="sxs-lookup"><span data-stu-id="93826-102">Ways to Select a Windows Forms Button Control</span></span>
<span data-ttu-id="93826-103">Windows 窗体按钮可以选择通过以下方式：</span><span class="sxs-lookup"><span data-stu-id="93826-103">A Windows Forms button can be selected in the following ways:</span></span>  
  
-   <span data-ttu-id="93826-104">使用鼠标单击的按钮。</span><span class="sxs-lookup"><span data-stu-id="93826-104">Use a mouse to click the button.</span></span>  
  
-   <span data-ttu-id="93826-105">调用该按钮的<xref:System.Windows.Forms.Control.Click>在代码中的事件。</span><span class="sxs-lookup"><span data-stu-id="93826-105">Invoke the button's <xref:System.Windows.Forms.Control.Click> event in code.</span></span>  
  
-   <span data-ttu-id="93826-106">将焦点移到按钮，通过按 TAB 键，并按空格键或 enter 键，然后选择该按钮。</span><span class="sxs-lookup"><span data-stu-id="93826-106">Move the focus to the button by pressing the TAB key, and then choose the button by pressing the SPACEBAR or ENTER.</span></span>  
  
-   <span data-ttu-id="93826-107">按该按钮的访问密钥 （ALT + 带下划线的字母）。</span><span class="sxs-lookup"><span data-stu-id="93826-107">Press the access key (ALT + the underlined letter) for the button.</span></span> <span data-ttu-id="93826-108">有关访问密钥的详细信息，请参阅[如何： 为 Windows 窗体控件创建访问键](../../../../docs/framework/winforms/controls/how-to-create-access-keys-for-windows-forms-controls.md)。</span><span class="sxs-lookup"><span data-stu-id="93826-108">For more information about access keys, see [How to: Create Access Keys for Windows Forms Controls](../../../../docs/framework/winforms/controls/how-to-create-access-keys-for-windows-forms-controls.md).</span></span>  
  
-   <span data-ttu-id="93826-109">如果按钮是窗体的"接受"按钮，并按 enter 键选择此按钮时，即使另一个控件具有焦点，但该控件可以是另一个按钮、 多行文本框中或捕获 enter 键的自定义控件。</span><span class="sxs-lookup"><span data-stu-id="93826-109">If the button is the "accept" button of the form, pressing ENTER chooses the button, even if another control has the focus — except if that other control is another button, a multi-line text box, or a custom control that traps the enter key.</span></span>  
  
-   <span data-ttu-id="93826-110">如果按钮是窗体的"取消"按钮，按 esc 键选择此按钮时，即使另一个控件具有焦点。</span><span class="sxs-lookup"><span data-stu-id="93826-110">If the button is the "cancel" button of the form, pressing ESC chooses the button, even if another control has the focus.</span></span>  
  
-   <span data-ttu-id="93826-111">调用<xref:System.Windows.Forms.Button.PerformClick%2A>方法以编程方式选择按钮。</span><span class="sxs-lookup"><span data-stu-id="93826-111">Call the <xref:System.Windows.Forms.Button.PerformClick%2A> method to select the button programmatically.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="93826-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="93826-112">See Also</span></span>  
 [<span data-ttu-id="93826-113">Button 控件概述</span><span class="sxs-lookup"><span data-stu-id="93826-113">Button Control Overview</span></span>](../../../../docs/framework/winforms/controls/button-control-overview-windows-forms.md)  
 [<span data-ttu-id="93826-114">如何：响应 Windows 窗体 Button 控件单击</span><span class="sxs-lookup"><span data-stu-id="93826-114">How to: Respond to Windows Forms Button Clicks</span></span>](../../../../docs/framework/winforms/controls/how-to-respond-to-windows-forms-button-clicks.md)  
 [<span data-ttu-id="93826-115">Button 控件</span><span class="sxs-lookup"><span data-stu-id="93826-115">Button Control</span></span>](../../../../docs/framework/winforms/controls/button-control-windows-forms.md)
