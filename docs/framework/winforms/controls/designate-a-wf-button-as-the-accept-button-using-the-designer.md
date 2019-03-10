---
title: 如何：将 Windows 窗体按钮指定为接受按钮使用设计器
ms.date: 03/30/2017
helpviewer_keywords:
- buttons [Windows Forms], default on Windows Forms
- Accept button on Windows Forms
- Button control [Windows Forms], designating as default
- Windows Forms controls, default button on form
ms.assetid: a1da0590-755f-49f2-aca7-609fac6351bf
ms.openlocfilehash: 61f0c99560d008cc10c94403ac936e5b97267d3a
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/09/2019
ms.locfileid: "57707646"
---
# <a name="how-to-designate-a-windows-forms-button-as-the-accept-button-using-the-designer"></a><span data-ttu-id="a54f2-102">如何：将 Windows 窗体按钮指定为接受按钮使用设计器</span><span class="sxs-lookup"><span data-stu-id="a54f2-102">How to: Designate a Windows Forms Button as the Accept Button Using the Designer</span></span>
<span data-ttu-id="a54f2-103">在任何 Windows 窗体中，可以将指定<xref:System.Windows.Forms.Button>控件成为接受按钮，也称为默认按钮。</span><span class="sxs-lookup"><span data-stu-id="a54f2-103">On any Windows Form, you can designate a <xref:System.Windows.Forms.Button> control to be the accept button, also known as the default button.</span></span> <span data-ttu-id="a54f2-104">每当用户按 ENTER 键，无论哪个窗体上的其他控件具有焦点单击默认按钮。</span><span class="sxs-lookup"><span data-stu-id="a54f2-104">Whenever the user presses the ENTER key, the default button is clicked regardless of which other control on the form has the focus.</span></span> <span data-ttu-id="a54f2-105">为以下情形时具有焦点的控件是另一个按钮的异常，将在这种情况下，单击具有焦点的按钮，或多行文本框中或捕获 ENTER 键的自定义控件。</span><span class="sxs-lookup"><span data-stu-id="a54f2-105">The exceptions to this are when the control with focus is another button — in that case, the button with the focus will be clicked — or a multiline text box, or a custom control that traps the ENTER key.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a54f2-106">显示的对话框和菜单命令可能会与“帮助”中的描述不同，具体取决于你现用的设置或版本。</span><span class="sxs-lookup"><span data-stu-id="a54f2-106">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="a54f2-107">若要更改设置，请在 **“工具”** 菜单上选择 **“导入和导出设置”** 。</span><span class="sxs-lookup"><span data-stu-id="a54f2-107">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="a54f2-108">有关详细信息，请参阅[个性化设置 Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide)。</span><span class="sxs-lookup"><span data-stu-id="a54f2-108">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-designate-the-accept-button"></a><span data-ttu-id="a54f2-109">若要指定接受按钮</span><span class="sxs-lookup"><span data-stu-id="a54f2-109">To designate the accept button</span></span>  
  
1.  <span data-ttu-id="a54f2-110">选择该按钮所驻留的窗体。</span><span class="sxs-lookup"><span data-stu-id="a54f2-110">Select the form on which the button resides.</span></span>  
  
2.  <span data-ttu-id="a54f2-111">在中**属性**窗口中，将窗体的<xref:System.Windows.Forms.Form.AcceptButton%2A>属性设置为<xref:System.Windows.Forms.Button>控件的名称。</span><span class="sxs-lookup"><span data-stu-id="a54f2-111">In the **Properties** window, set the form's <xref:System.Windows.Forms.Form.AcceptButton%2A> property to the <xref:System.Windows.Forms.Button> control's name.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a54f2-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="a54f2-112">See also</span></span>
- <xref:System.Windows.Forms.Form.AcceptButton%2A>
- [<span data-ttu-id="a54f2-113">Button 控件概述</span><span class="sxs-lookup"><span data-stu-id="a54f2-113">Button Control Overview</span></span>](button-control-overview-windows-forms.md)
- [<span data-ttu-id="a54f2-114">如何选择 Windows 窗体 Button 控件</span><span class="sxs-lookup"><span data-stu-id="a54f2-114">Ways to Select a Windows Forms Button Control</span></span>](ways-to-select-a-windows-forms-button-control.md)
- [<span data-ttu-id="a54f2-115">如何：响应 Windows 窗体按钮单击</span><span class="sxs-lookup"><span data-stu-id="a54f2-115">How to: Respond to Windows Forms Button Clicks</span></span>](how-to-respond-to-windows-forms-button-clicks.md)
- [<span data-ttu-id="a54f2-116">如何：将 Windows 窗体按钮指定为使用设计器的取消按钮</span><span class="sxs-lookup"><span data-stu-id="a54f2-116">How to: Designate a Windows Forms Button as the Cancel Button Using the Designer</span></span>](designate-a-wf-button-as-the-cancel-button-using-the-designer.md)
- [<span data-ttu-id="a54f2-117">Button 控件</span><span class="sxs-lookup"><span data-stu-id="a54f2-117">Button Control</span></span>](button-control-windows-forms.md)
