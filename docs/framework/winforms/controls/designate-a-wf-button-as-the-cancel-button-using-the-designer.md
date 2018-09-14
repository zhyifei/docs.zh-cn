---
title: 如何：使用设计器将 Windows 窗体按钮指定为“取消”按钮
ms.date: 03/30/2017
helpviewer_keywords:
- buttons [Windows Forms], cancel buttons
- Button control [Windows Forms], designating as cancel button
ms.assetid: 30e77d9c-d565-4ab5-a84a-62c043af8822
ms.openlocfilehash: faffeafc0cbe67c3b40297144ec85acd94956da9
ms.sourcegitcommit: 76a304c79a32aa13889ebcf4b9789a4542b48e3e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/13/2018
ms.locfileid: "45528253"
---
# <a name="how-to-designate-a-windows-forms-button-as-the-cancel-button-using-the-designer"></a><span data-ttu-id="dc664-102">如何：使用设计器将 Windows 窗体按钮指定为“取消”按钮</span><span class="sxs-lookup"><span data-stu-id="dc664-102">How to: Designate a Windows Forms Button as the Cancel Button Using the Designer</span></span>
<span data-ttu-id="dc664-103">在任何 Windows 窗体中，可以将指定<xref:System.Windows.Forms.Button>控件为取消按钮。</span><span class="sxs-lookup"><span data-stu-id="dc664-103">On any Windows Form, you can designate a <xref:System.Windows.Forms.Button> control to be the cancel button.</span></span> <span data-ttu-id="dc664-104">每当用户按 ESC 键时，无论哪个窗体上的其他控件具有焦点时，单击取消按钮。</span><span class="sxs-lookup"><span data-stu-id="dc664-104">A cancel button is clicked whenever the user presses the ESC key, regardless of which other control on the form has the focus.</span></span> <span data-ttu-id="dc664-105">通常，设计这样的按钮，使用户能够快速退出操作而无须执行任何操作。</span><span class="sxs-lookup"><span data-stu-id="dc664-105">Such a button is usually programmed to enable the user to quickly exit an operation without committing to any action.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="dc664-106">显示的对话框和菜单命令可能会与“帮助”中的描述不同，具体取决于你现用的设置或版本。</span><span class="sxs-lookup"><span data-stu-id="dc664-106">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="dc664-107">若要更改设置，请在 **“工具”** 菜单上选择 **“导入和导出设置”** 。</span><span class="sxs-lookup"><span data-stu-id="dc664-107">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="dc664-108">有关详细信息，请参阅[个性化设置 Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide)。</span><span class="sxs-lookup"><span data-stu-id="dc664-108">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-designate-the-cancel-button"></a><span data-ttu-id="dc664-109">若要指定取消按钮</span><span class="sxs-lookup"><span data-stu-id="dc664-109">To designate the cancel button</span></span>  
  
1.  <span data-ttu-id="dc664-110">选择该按钮所驻留的窗体。</span><span class="sxs-lookup"><span data-stu-id="dc664-110">Select the form on which the button resides.</span></span>  
  
2.  <span data-ttu-id="dc664-111">在中**属性**窗口中，将窗体的<xref:System.Windows.Forms.Form.CancelButton%2A>属性设置为<xref:System.Windows.Forms.Button>控件的名称。</span><span class="sxs-lookup"><span data-stu-id="dc664-111">In the **Properties** window, set the form's <xref:System.Windows.Forms.Form.CancelButton%2A> property to the <xref:System.Windows.Forms.Button> control's name.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dc664-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="dc664-112">See Also</span></span>  
 <xref:System.Windows.Forms.Form.CancelButton%2A>  
 [<span data-ttu-id="dc664-113">Button 控件概述</span><span class="sxs-lookup"><span data-stu-id="dc664-113">Button Control Overview</span></span>](../../../../docs/framework/winforms/controls/button-control-overview-windows-forms.md)  
 [<span data-ttu-id="dc664-114">如何选择 Windows 窗体 Button 控件</span><span class="sxs-lookup"><span data-stu-id="dc664-114">Ways to Select a Windows Forms Button Control</span></span>](../../../../docs/framework/winforms/controls/ways-to-select-a-windows-forms-button-control.md)  
 [<span data-ttu-id="dc664-115">如何：响应 Windows 窗体 Button 控件单击</span><span class="sxs-lookup"><span data-stu-id="dc664-115">How to: Respond to Windows Forms Button Clicks</span></span>](../../../../docs/framework/winforms/controls/how-to-respond-to-windows-forms-button-clicks.md)  
 [<span data-ttu-id="dc664-116">如何：使用设计器将 Windows 窗体按钮指定为“接受”按钮</span><span class="sxs-lookup"><span data-stu-id="dc664-116">How to: Designate a Windows Forms Button as the Accept Button Using the Designer</span></span>](../../../../docs/framework/winforms/controls/designate-a-wf-button-as-the-accept-button-using-the-designer.md)  
 [<span data-ttu-id="dc664-117">Button 控件</span><span class="sxs-lookup"><span data-stu-id="dc664-117">Button Control</span></span>](../../../../docs/framework/winforms/controls/button-control-windows-forms.md)
