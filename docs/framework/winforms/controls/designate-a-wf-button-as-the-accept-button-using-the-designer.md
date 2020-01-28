---
title: 使用设计器将一个按钮指定为 "接受" 按钮
ms.date: 03/30/2017
helpviewer_keywords:
- buttons [Windows Forms], default on Windows Forms
- Accept button on Windows Forms
- Button control [Windows Forms], designating as default
- Windows Forms controls, default button on form
ms.assetid: a1da0590-755f-49f2-aca7-609fac6351bf
ms.openlocfilehash: 27a5de51f8c5b2c84cc205e09ac1a2179c315752
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746060"
---
# <a name="how-to-designate-a-windows-forms-button-as-the-accept-button-using-the-designer"></a><span data-ttu-id="76755-102">방법: 디자이너를 사용하여 Windows Forms 단추를 적용 단추로 지정</span><span class="sxs-lookup"><span data-stu-id="76755-102">How to: Designate a Windows Forms Button as the Accept Button Using the Designer</span></span>
<span data-ttu-id="76755-103">在任意 Windows 窗体上，可以将 <xref:System.Windows.Forms.Button> 控件指定为 "接受" 按钮，也称为 "默认" 按钮。</span><span class="sxs-lookup"><span data-stu-id="76755-103">On any Windows Form, you can designate a <xref:System.Windows.Forms.Button> control to be the accept button, also known as the default button.</span></span> <span data-ttu-id="76755-104">用户按 ENTER 键时，将单击默认按钮，而不考虑窗体上的其他哪个控件具有焦点。</span><span class="sxs-lookup"><span data-stu-id="76755-104">Whenever the user presses the ENTER key, the default button is clicked regardless of which other control on the form has the focus.</span></span> <span data-ttu-id="76755-105">这种情况的例外是，具有焦点的控件是另一个按钮，在这种情况下，将单击带有焦点的按钮（或多行文本框）或捕获 ENTER 键的自定义控件。</span><span class="sxs-lookup"><span data-stu-id="76755-105">The exceptions to this are when the control with focus is another button — in that case, the button with the focus will be clicked — or a multiline text box, or a custom control that traps the ENTER key.</span></span>

## <a name="to-designate-the-accept-button"></a><span data-ttu-id="76755-106">指定 "接受" 按钮</span><span class="sxs-lookup"><span data-stu-id="76755-106">To designate the accept button</span></span>

1. <span data-ttu-id="76755-107">选择该按钮所在的窗体。</span><span class="sxs-lookup"><span data-stu-id="76755-107">Select the form on which the button resides.</span></span>

2. <span data-ttu-id="76755-108">在 "**属性**" 窗口中，将窗体的 <xref:System.Windows.Forms.Form.AcceptButton%2A> 属性设置为 <xref:System.Windows.Forms.Button> 控件的名称。</span><span class="sxs-lookup"><span data-stu-id="76755-108">In the **Properties** window, set the form's <xref:System.Windows.Forms.Form.AcceptButton%2A> property to the <xref:System.Windows.Forms.Button> control's name.</span></span>

## <a name="see-also"></a><span data-ttu-id="76755-109">另请参阅</span><span class="sxs-lookup"><span data-stu-id="76755-109">See also</span></span>

- <xref:System.Windows.Forms.Form.AcceptButton%2A>
- [<span data-ttu-id="76755-110">Button 컨트롤 개요</span><span class="sxs-lookup"><span data-stu-id="76755-110">Button Control Overview</span></span>](button-control-overview-windows-forms.md)
- [<span data-ttu-id="76755-111">Windows Forms Button 컨트롤 선택 방법</span><span class="sxs-lookup"><span data-stu-id="76755-111">Ways to Select a Windows Forms Button Control</span></span>](ways-to-select-a-windows-forms-button-control.md)
- [<span data-ttu-id="76755-112">방법: Windows Forms 단추 클릭에 응답</span><span class="sxs-lookup"><span data-stu-id="76755-112">How to: Respond to Windows Forms Button Clicks</span></span>](how-to-respond-to-windows-forms-button-clicks.md)
- [<span data-ttu-id="76755-113">방법: 디자이너를 사용하여 Windows Forms 단추를 취소 단추로 지정</span><span class="sxs-lookup"><span data-stu-id="76755-113">How to: Designate a Windows Forms Button as the Cancel Button Using the Designer</span></span>](designate-a-wf-button-as-the-cancel-button-using-the-designer.md)
- [<span data-ttu-id="76755-114">Button 컨트롤</span><span class="sxs-lookup"><span data-stu-id="76755-114">Button Control</span></span>](button-control-windows-forms.md)
