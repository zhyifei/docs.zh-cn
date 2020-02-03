---
title: Button 控件概述
ms.date: 03/30/2017
f1_keywords:
- Button
helpviewer_keywords:
- Button control [Windows Forms], about Button control
- buttons [Windows Forms], about buttons
ms.assetid: 255b291b-51a9-4a92-a1a4-2400cd82443f
ms.openlocfilehash: 4ba7b333e5414efb4814d64ce50c55e08b27f859
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76747075"
---
# <a name="button-control-overview-windows-forms"></a><span data-ttu-id="7aa89-102">Button 控件概述（Windows 窗体）</span><span class="sxs-lookup"><span data-stu-id="7aa89-102">Button Control Overview (Windows Forms)</span></span>
<span data-ttu-id="7aa89-103">Windows 窗体 <xref:System.Windows.Forms.Button> 控件允许用户通过单击来执行某项操作。</span><span class="sxs-lookup"><span data-stu-id="7aa89-103">The Windows Forms <xref:System.Windows.Forms.Button> control allows the user to click it to perform an action.</span></span> <span data-ttu-id="7aa89-104">单击该按钮时，看上去它像是被按下并释放。</span><span class="sxs-lookup"><span data-stu-id="7aa89-104">When the button is clicked, it looks as if it is being pushed in and released.</span></span> <span data-ttu-id="7aa89-105">每当用户单击某个按钮时，就会调用 <xref:System.Windows.Forms.Control.Click> 事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="7aa89-105">Whenever the user clicks a button, the <xref:System.Windows.Forms.Control.Click> event handler is invoked.</span></span> <span data-ttu-id="7aa89-106">将代码放在 <xref:System.Windows.Forms.Control.Click> 事件处理程序中，以执行您选择的任何操作。</span><span class="sxs-lookup"><span data-stu-id="7aa89-106">You place code in the <xref:System.Windows.Forms.Control.Click> event handler to perform any action you choose.</span></span>  
  
 <span data-ttu-id="7aa89-107">按钮上显示的文本包含在 <xref:System.Windows.Forms.Control.Text%2A> 属性中。</span><span class="sxs-lookup"><span data-stu-id="7aa89-107">The text displayed on the button is contained in the <xref:System.Windows.Forms.Control.Text%2A> property.</span></span> <span data-ttu-id="7aa89-108">如果文本超出按钮宽度，则会换行到下一行。</span><span class="sxs-lookup"><span data-stu-id="7aa89-108">If your text exceeds the width of the button, it will wrap to the next line.</span></span> <span data-ttu-id="7aa89-109">但是，如果控件无法容纳其整体高度，则会将其剪切。</span><span class="sxs-lookup"><span data-stu-id="7aa89-109">However, it will be clipped if the control cannot accommodate its overall height.</span></span> <span data-ttu-id="7aa89-110">有关详细信息，请参阅[如何：设置 Windows 窗体控件显示的文本](how-to-set-the-text-displayed-by-a-windows-forms-control.md)。</span><span class="sxs-lookup"><span data-stu-id="7aa89-110">For more information, see [How to: Set the Text Displayed by a Windows Forms Control](how-to-set-the-text-displayed-by-a-windows-forms-control.md).</span></span> <span data-ttu-id="7aa89-111"><xref:System.Windows.Forms.Control.Text%2A> 属性可以包含访问键，这允许用户通过按 ALT 键和访问键来 "单击" 控件。</span><span class="sxs-lookup"><span data-stu-id="7aa89-111">The <xref:System.Windows.Forms.Control.Text%2A> property can contain an access key, which allows a user to "click" the control by pressing the ALT key with the access key.</span></span> <span data-ttu-id="7aa89-112">有关详细信息，请参阅[如何：创建 Windows 窗体控件的访问键](how-to-create-access-keys-for-windows-forms-controls.md)。</span><span class="sxs-lookup"><span data-stu-id="7aa89-112">For details, see [How to: Create Access Keys for Windows Forms Controls](how-to-create-access-keys-for-windows-forms-controls.md).</span></span> <span data-ttu-id="7aa89-113">文本的外观由 <xref:System.Windows.Forms.Control.Font%2A> 属性和 <xref:System.Windows.Forms.ButtonBase.TextAlign%2A> 属性控制。</span><span class="sxs-lookup"><span data-stu-id="7aa89-113">The appearance of the text is controlled by the <xref:System.Windows.Forms.Control.Font%2A> property and the <xref:System.Windows.Forms.ButtonBase.TextAlign%2A> property.</span></span>  
  
 <span data-ttu-id="7aa89-114"><xref:System.Windows.Forms.Button> 控件还可以使用 <xref:System.Windows.Forms.ButtonBase.Image%2A> 和 <xref:System.Windows.Forms.ButtonBase.ImageList%2A> 属性来显示图像。</span><span class="sxs-lookup"><span data-stu-id="7aa89-114">The <xref:System.Windows.Forms.Button> control can also display images using the <xref:System.Windows.Forms.ButtonBase.Image%2A> and <xref:System.Windows.Forms.ButtonBase.ImageList%2A> properties.</span></span> <span data-ttu-id="7aa89-115">有关详细信息，请参阅[如何：设置 Windows 窗体控件显示的图像](how-to-set-the-image-displayed-by-a-windows-forms-control.md)。</span><span class="sxs-lookup"><span data-stu-id="7aa89-115">For more information, see [How to: Set the Image Displayed by a Windows Forms Control](how-to-set-the-image-displayed-by-a-windows-forms-control.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7aa89-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7aa89-116">See also</span></span>

- <xref:System.Windows.Forms.Button>
- [<span data-ttu-id="7aa89-117">如何：响应 Windows 窗体 Button 控件单击</span><span class="sxs-lookup"><span data-stu-id="7aa89-117">How to: Respond to Windows Forms Button Clicks</span></span>](how-to-respond-to-windows-forms-button-clicks.md)
- [<span data-ttu-id="7aa89-118">如何选择 Windows 窗体 Button 控件</span><span class="sxs-lookup"><span data-stu-id="7aa89-118">Ways to Select a Windows Forms Button Control</span></span>](ways-to-select-a-windows-forms-button-control.md)
- [<span data-ttu-id="7aa89-119">如何：使用设计器将 Windows 窗体按钮指定为“接受”按钮</span><span class="sxs-lookup"><span data-stu-id="7aa89-119">How to: Designate a Windows Forms Button as the Accept Button Using the Designer</span></span>](designate-a-wf-button-as-the-accept-button-using-the-designer.md)
- [<span data-ttu-id="7aa89-120">如何：使用设计器将 Windows 窗体按钮指定为“取消”按钮</span><span class="sxs-lookup"><span data-stu-id="7aa89-120">How to: Designate a Windows Forms Button as the Cancel Button Using the Designer</span></span>](designate-a-wf-button-as-the-cancel-button-using-the-designer.md)
- [<span data-ttu-id="7aa89-121">Button 控件</span><span class="sxs-lookup"><span data-stu-id="7aa89-121">Button Control</span></span>](button-control-windows-forms.md)
