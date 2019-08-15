---
title: 如何：使用设计器将 Windows 窗体按钮指定为“接受”按钮
ms.date: 03/30/2017
helpviewer_keywords:
- buttons [Windows Forms], default on Windows Forms
- Accept button on Windows Forms
- Button control [Windows Forms], designating as default
- Windows Forms controls, default button on form
ms.assetid: a1da0590-755f-49f2-aca7-609fac6351bf
ms.openlocfilehash: 27ecb26c493232bcfb996d012f9760b7ef91e5b2
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/15/2019
ms.locfileid: "69039662"
---
# <a name="how-to-designate-a-windows-forms-button-as-the-accept-button-using-the-designer"></a><span data-ttu-id="80768-102">如何：使用设计器将 Windows 窗体按钮指定为“接受”按钮</span><span class="sxs-lookup"><span data-stu-id="80768-102">How to: Designate a Windows Forms Button as the Accept Button Using the Designer</span></span>
<span data-ttu-id="80768-103">在任何 Windows 窗体上, 都可以<xref:System.Windows.Forms.Button>将控件指定为 "接受" 按钮, 也称为 "默认" 按钮。</span><span class="sxs-lookup"><span data-stu-id="80768-103">On any Windows Form, you can designate a <xref:System.Windows.Forms.Button> control to be the accept button, also known as the default button.</span></span> <span data-ttu-id="80768-104">用户按 ENTER 键时, 将单击默认按钮, 而不考虑窗体上的其他哪个控件具有焦点。</span><span class="sxs-lookup"><span data-stu-id="80768-104">Whenever the user presses the ENTER key, the default button is clicked regardless of which other control on the form has the focus.</span></span> <span data-ttu-id="80768-105">这种情况的例外是, 具有焦点的控件是另一个按钮, 在这种情况下, 将单击带有焦点的按钮 (或多行文本框) 或捕获 ENTER 键的自定义控件。</span><span class="sxs-lookup"><span data-stu-id="80768-105">The exceptions to this are when the control with focus is another button — in that case, the button with the focus will be clicked — or a multiline text box, or a custom control that traps the ENTER key.</span></span>

## <a name="to-designate-the-accept-button"></a><span data-ttu-id="80768-106">指定 "接受" 按钮</span><span class="sxs-lookup"><span data-stu-id="80768-106">To designate the accept button</span></span>

1. <span data-ttu-id="80768-107">选择该按钮所在的窗体。</span><span class="sxs-lookup"><span data-stu-id="80768-107">Select the form on which the button resides.</span></span>

2. <span data-ttu-id="80768-108">在 "**属性**" 窗口中, 将窗<xref:System.Windows.Forms.Form.AcceptButton%2A>体的属性<xref:System.Windows.Forms.Button>设置为控件的名称。</span><span class="sxs-lookup"><span data-stu-id="80768-108">In the **Properties** window, set the form's <xref:System.Windows.Forms.Form.AcceptButton%2A> property to the <xref:System.Windows.Forms.Button> control's name.</span></span>

## <a name="see-also"></a><span data-ttu-id="80768-109">请参阅</span><span class="sxs-lookup"><span data-stu-id="80768-109">See also</span></span>

- <xref:System.Windows.Forms.Form.AcceptButton%2A>
- [<span data-ttu-id="80768-110">Button 控件概述</span><span class="sxs-lookup"><span data-stu-id="80768-110">Button Control Overview</span></span>](button-control-overview-windows-forms.md)
- [<span data-ttu-id="80768-111">如何选择 Windows 窗体 Button 控件</span><span class="sxs-lookup"><span data-stu-id="80768-111">Ways to Select a Windows Forms Button Control</span></span>](ways-to-select-a-windows-forms-button-control.md)
- [<span data-ttu-id="80768-112">如何：响应 Windows 窗体按钮单击</span><span class="sxs-lookup"><span data-stu-id="80768-112">How to: Respond to Windows Forms Button Clicks</span></span>](how-to-respond-to-windows-forms-button-clicks.md)
- [<span data-ttu-id="80768-113">如何：使用设计器将 Windows 窗体按钮指定为 "取消" 按钮</span><span class="sxs-lookup"><span data-stu-id="80768-113">How to: Designate a Windows Forms Button as the Cancel Button Using the Designer</span></span>](designate-a-wf-button-as-the-cancel-button-using-the-designer.md)
- [<span data-ttu-id="80768-114">Button 控件</span><span class="sxs-lookup"><span data-stu-id="80768-114">Button Control</span></span>](button-control-windows-forms.md)
