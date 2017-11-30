---
title: "Button 控件概述（Windows 窗体）"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: Button
helpviewer_keywords:
- Button control [Windows Forms], about Button control
- buttons [Windows Forms], about buttons
ms.assetid: 255b291b-51a9-4a92-a1a4-2400cd82443f
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: ff98eb39113a2fa8117d091645ac04526e2983c1
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="button-control-overview-windows-forms"></a><span data-ttu-id="3f59d-102">Button 控件概述（Windows 窗体）</span><span class="sxs-lookup"><span data-stu-id="3f59d-102">Button Control Overview (Windows Forms)</span></span>
<span data-ttu-id="3f59d-103">Windows 窗体 <xref:System.Windows.Forms.Button> 控件允许用户通过单击来执行某项操作。</span><span class="sxs-lookup"><span data-stu-id="3f59d-103">The Windows Forms <xref:System.Windows.Forms.Button> control allows the user to click it to perform an action.</span></span> <span data-ttu-id="3f59d-104">单击该按钮时，看上去它像是被按下并释放。</span><span class="sxs-lookup"><span data-stu-id="3f59d-104">When the button is clicked, it looks as if it is being pushed in and released.</span></span> <span data-ttu-id="3f59d-105">无论何时用户单击按钮，<xref:System.Windows.Forms.Control.Click>调用事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="3f59d-105">Whenever the user clicks a button, the <xref:System.Windows.Forms.Control.Click> event handler is invoked.</span></span> <span data-ttu-id="3f59d-106">你将代码放置在<xref:System.Windows.Forms.Control.Click>事件处理程序来执行你选择的任何操作。</span><span class="sxs-lookup"><span data-stu-id="3f59d-106">You place code in the <xref:System.Windows.Forms.Control.Click> event handler to perform any action you choose.</span></span>  
  
 <span data-ttu-id="3f59d-107">按钮上显示的文本包含在<xref:System.Windows.Forms.Control.Text%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="3f59d-107">The text displayed on the button is contained in the <xref:System.Windows.Forms.Control.Text%2A> property.</span></span> <span data-ttu-id="3f59d-108">如果你的文本超过按钮的宽度，它将换行到下一行。</span><span class="sxs-lookup"><span data-stu-id="3f59d-108">If your text exceeds the width of the button, it will wrap to the next line.</span></span> <span data-ttu-id="3f59d-109">但是，它将剪切如果该控件所能容纳的窗体的整体高度。</span><span class="sxs-lookup"><span data-stu-id="3f59d-109">However, it will be clipped if the control cannot accommodate its overall height.</span></span> <span data-ttu-id="3f59d-110">有关详细信息，请参阅[如何： 设置 Windows 窗体控件显示的文本](../../../../docs/framework/winforms/controls/how-to-set-the-text-displayed-by-a-windows-forms-control.md)。</span><span class="sxs-lookup"><span data-stu-id="3f59d-110">For more information, see [How to: Set the Text Displayed by a Windows Forms Control](../../../../docs/framework/winforms/controls/how-to-set-the-text-displayed-by-a-windows-forms-control.md).</span></span> <span data-ttu-id="3f59d-111"><xref:System.Windows.Forms.Control.Text%2A>属性可以包含的访问密钥，这样用户就可以通过按 ALT 键和访问密钥"单击"的控件。</span><span class="sxs-lookup"><span data-stu-id="3f59d-111">The <xref:System.Windows.Forms.Control.Text%2A> property can contain an access key, which allows a user to "click" the control by pressing the ALT key with the access key.</span></span> <span data-ttu-id="3f59d-112">有关详细信息，请参阅[如何： 为 Windows 窗体控件创建访问键](../../../../docs/framework/winforms/controls/how-to-create-access-keys-for-windows-forms-controls.md)。</span><span class="sxs-lookup"><span data-stu-id="3f59d-112">For details, see [How to: Create Access Keys for Windows Forms Controls](../../../../docs/framework/winforms/controls/how-to-create-access-keys-for-windows-forms-controls.md).</span></span> <span data-ttu-id="3f59d-113">由控制文本的外观<xref:System.Windows.Forms.Control.Font%2A>属性和<xref:System.Windows.Forms.ButtonBase.TextAlign%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="3f59d-113">The appearance of the text is controlled by the <xref:System.Windows.Forms.Control.Font%2A> property and the <xref:System.Windows.Forms.ButtonBase.TextAlign%2A> property.</span></span>  
  
 <span data-ttu-id="3f59d-114"><xref:System.Windows.Forms.Button>控件还可以显示使用的图像<xref:System.Windows.Forms.ButtonBase.Image%2A>和<xref:System.Windows.Forms.ButtonBase.ImageList%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="3f59d-114">The <xref:System.Windows.Forms.Button> control can also display images using the <xref:System.Windows.Forms.ButtonBase.Image%2A> and <xref:System.Windows.Forms.ButtonBase.ImageList%2A> properties.</span></span> <span data-ttu-id="3f59d-115">有关详细信息，请参阅[如何： 设置 Windows 窗体控件显示的图像](../../../../docs/framework/winforms/controls/how-to-set-the-image-displayed-by-a-windows-forms-control.md)。</span><span class="sxs-lookup"><span data-stu-id="3f59d-115">For more information, see [How to: Set the Image Displayed by a Windows Forms Control](../../../../docs/framework/winforms/controls/how-to-set-the-image-displayed-by-a-windows-forms-control.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3f59d-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3f59d-116">See Also</span></span>  
 <xref:System.Windows.Forms.Button>  
 [<span data-ttu-id="3f59d-117">如何：响应 Windows 窗体 Button 控件单击</span><span class="sxs-lookup"><span data-stu-id="3f59d-117">How to: Respond to Windows Forms Button Clicks</span></span>](../../../../docs/framework/winforms/controls/how-to-respond-to-windows-forms-button-clicks.md)  
 [<span data-ttu-id="3f59d-118">如何选择 Windows 窗体 Button 控件</span><span class="sxs-lookup"><span data-stu-id="3f59d-118">Ways to Select a Windows Forms Button Control</span></span>](../../../../docs/framework/winforms/controls/ways-to-select-a-windows-forms-button-control.md)  
 [<span data-ttu-id="3f59d-119">如何：使用设计器将 Windows 窗体按钮指定为“接受”按钮</span><span class="sxs-lookup"><span data-stu-id="3f59d-119">How to: Designate a Windows Forms Button as the Accept Button Using the Designer</span></span>](../../../../docs/framework/winforms/controls/designate-a-wf-button-as-the-accept-button-using-the-designer.md)  
 [<span data-ttu-id="3f59d-120">如何：使用设计器将 Windows 窗体按钮指定为“取消”按钮</span><span class="sxs-lookup"><span data-stu-id="3f59d-120">How to: Designate a Windows Forms Button as the Cancel Button Using the Designer</span></span>](../../../../docs/framework/winforms/controls/designate-a-wf-button-as-the-cancel-button-using-the-designer.md)  
 [<span data-ttu-id="3f59d-121">Button 控件</span><span class="sxs-lookup"><span data-stu-id="3f59d-121">Button Control</span></span>](../../../../docs/framework/winforms/controls/button-control-windows-forms.md)
