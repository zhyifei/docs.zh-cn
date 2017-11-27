---
title: "RadioButton 控件概述（Windows 窗体）"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: RadioButton
helpviewer_keywords:
- RadioButton control [Windows Forms], about RadioButton control
- RadioButton control [Windows Forms], determining state
- radio buttons [Windows Forms], determining state
- radio buttons [Windows Forms], about radio buttons
ms.assetid: cd11f0c2-d098-4022-adf9-1455bc166a13
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: ac0a04c506919ef807a3f8c5ed5aa75ee998f64a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="radiobutton-control-overview-windows-forms"></a><span data-ttu-id="0490f-102">RadioButton 控件概述（Windows 窗体）</span><span class="sxs-lookup"><span data-stu-id="0490f-102">RadioButton Control Overview (Windows Forms)</span></span>
<span data-ttu-id="0490f-103">Windows 窗体<xref:System.Windows.Forms.RadioButton>控件向用户显示一组两个或多个互相排斥的选择。</span><span class="sxs-lookup"><span data-stu-id="0490f-103">Windows Forms <xref:System.Windows.Forms.RadioButton> controls present a set of two or more mutually exclusive choices to the user.</span></span> <span data-ttu-id="0490f-104">尽管单选按钮和复选框可能看起来作用类似，但还有一项重大差异： 当用户选择一个单选按钮时，不能也选择同一组中的其他单选按钮。</span><span class="sxs-lookup"><span data-stu-id="0490f-104">While radio buttons and check boxes may appear to function similarly, there is an important difference: when a user selects a radio button, the other radio buttons in the same group cannot be selected as well.</span></span> <span data-ttu-id="0490f-105">与此相反，可以选择任意数量的复选框。</span><span class="sxs-lookup"><span data-stu-id="0490f-105">In contrast, any number of check boxes can be selected.</span></span> <span data-ttu-id="0490f-106">定义单选按钮组将告诉用户:"这是一组选项，您可以从中选择一个且只有一个。"</span><span class="sxs-lookup"><span data-stu-id="0490f-106">Defining a radio button group tells the user, "Here is a set of choices from which you can choose one and only one."</span></span>  
  
## <a name="using-the-control"></a><span data-ttu-id="0490f-107">使用控件</span><span class="sxs-lookup"><span data-stu-id="0490f-107">Using the Control</span></span>  
 <span data-ttu-id="0490f-108">当<xref:System.Windows.Forms.RadioButton>单击控件时，其<xref:System.Windows.Forms.RadioButton.Checked%2A>属性设置为`true`和<xref:System.Windows.Forms.Control.Click>调用事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="0490f-108">When a <xref:System.Windows.Forms.RadioButton> control is clicked, its <xref:System.Windows.Forms.RadioButton.Checked%2A> property is set to `true` and the <xref:System.Windows.Forms.Control.Click> event handler is called.</span></span> <span data-ttu-id="0490f-109"><xref:System.Windows.Forms.RadioButton.CheckedChanged>引发事件时的值<xref:System.Windows.Forms.RadioButton.Checked%2A>属性更改。</span><span class="sxs-lookup"><span data-stu-id="0490f-109">The <xref:System.Windows.Forms.RadioButton.CheckedChanged> event is raised when the value of the <xref:System.Windows.Forms.RadioButton.Checked%2A> property changes.</span></span> <span data-ttu-id="0490f-110">如果<xref:System.Windows.Forms.RadioButton.AutoCheck%2A>属性设置为`true`（默认值），当选择单选按钮组中的所有其他会自动清除。</span><span class="sxs-lookup"><span data-stu-id="0490f-110">If the <xref:System.Windows.Forms.RadioButton.AutoCheck%2A> property is set to `true` (the default), when the radio button is selected all others in the group are automatically cleared.</span></span> <span data-ttu-id="0490f-111">此属性通常是只将设置为`false`验证代码用于确保单选按钮处于选中状态的时是允许的选项。</span><span class="sxs-lookup"><span data-stu-id="0490f-111">This property is usually only set to `false` when validation code is used to make sure the radio button selected is an allowable option.</span></span> <span data-ttu-id="0490f-112">设置控件中显示的文本<xref:System.Windows.Forms.Control.Text%2A>属性，它可以包含访问键快捷方式。</span><span class="sxs-lookup"><span data-stu-id="0490f-112">The text displayed within the control is set with the <xref:System.Windows.Forms.Control.Text%2A> property, which can contain access key shortcuts.</span></span> <span data-ttu-id="0490f-113">访问密钥使用户可以通过按 ALT 键和访问密钥"单击"的控件。</span><span class="sxs-lookup"><span data-stu-id="0490f-113">An access key enables a user to "click" the control by pressing the ALT key with the access key.</span></span> <span data-ttu-id="0490f-114">有关详细信息，请参阅[如何： 为 Windows 窗体控件创建访问键](../../../../docs/framework/winforms/controls/how-to-create-access-keys-for-windows-forms-controls.md)和[如何： 设置 Windows 窗体控件显示的文本](../../../../docs/framework/winforms/controls/how-to-set-the-text-displayed-by-a-windows-forms-control.md)。</span><span class="sxs-lookup"><span data-stu-id="0490f-114">For more information, see [How to: Create Access Keys for Windows Forms Controls](../../../../docs/framework/winforms/controls/how-to-create-access-keys-for-windows-forms-controls.md) and [How to: Set the Text Displayed by a Windows Forms Control](../../../../docs/framework/winforms/controls/how-to-set-the-text-displayed-by-a-windows-forms-control.md).</span></span>  
  
 <span data-ttu-id="0490f-115"><xref:System.Windows.Forms.RadioButton>控件可以显示类似于命令按钮，它看起来已按下，如果选择，如果<xref:System.Windows.Forms.RadioButton.Appearance%2A>属性设置为<xref:System.Windows.Forms.Appearance.Button>。</span><span class="sxs-lookup"><span data-stu-id="0490f-115">The <xref:System.Windows.Forms.RadioButton> control can appear like a command button, which appears to have been depressed if selected, if the <xref:System.Windows.Forms.RadioButton.Appearance%2A> property is set to <xref:System.Windows.Forms.Appearance.Button>.</span></span> <span data-ttu-id="0490f-116">单选按钮还可以显示使用的图像<xref:System.Windows.Forms.ButtonBase.Image%2A>和<xref:System.Windows.Forms.ButtonBase.ImageList%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="0490f-116">Radio buttons can also display images using the <xref:System.Windows.Forms.ButtonBase.Image%2A> and <xref:System.Windows.Forms.ButtonBase.ImageList%2A> properties.</span></span> <span data-ttu-id="0490f-117">有关详细信息，请参阅[如何： 设置 Windows 窗体控件显示的图像](../../../../docs/framework/winforms/controls/how-to-set-the-image-displayed-by-a-windows-forms-control.md)。</span><span class="sxs-lookup"><span data-stu-id="0490f-117">For more information, see [How to: Set the Image Displayed by a Windows Forms Control](../../../../docs/framework/winforms/controls/how-to-set-the-image-displayed-by-a-windows-forms-control.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0490f-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0490f-118">See Also</span></span>  
 <xref:System.Windows.Forms.RadioButton>  
 [<span data-ttu-id="0490f-119">Panel 控件概述</span><span class="sxs-lookup"><span data-stu-id="0490f-119">Panel Control Overview</span></span>](../../../../docs/framework/winforms/controls/panel-control-overview-windows-forms.md)  
 [<span data-ttu-id="0490f-120">GroupBox 控件概述</span><span class="sxs-lookup"><span data-stu-id="0490f-120">GroupBox Control Overview</span></span>](../../../../docs/framework/winforms/controls/groupbox-control-overview-windows-forms.md)  
 [<span data-ttu-id="0490f-121">CheckBox 控件概述</span><span class="sxs-lookup"><span data-stu-id="0490f-121">CheckBox Control Overview</span></span>](../../../../docs/framework/winforms/controls/checkbox-control-overview-windows-forms.md)  
 [<span data-ttu-id="0490f-122">如何：创建 Windows 窗体控件的访问键</span><span class="sxs-lookup"><span data-stu-id="0490f-122">How to: Create Access Keys for Windows Forms Controls</span></span>](../../../../docs/framework/winforms/controls/how-to-create-access-keys-for-windows-forms-controls.md)  
 [<span data-ttu-id="0490f-123">如何：设置 Windows 窗体控件显示的文本</span><span class="sxs-lookup"><span data-stu-id="0490f-123">How to: Set the Text Displayed by a Windows Forms Control</span></span>](../../../../docs/framework/winforms/controls/how-to-set-the-text-displayed-by-a-windows-forms-control.md)  
 [<span data-ttu-id="0490f-124">如何：按功能分组 Windows 窗体 RadioButton 控件</span><span class="sxs-lookup"><span data-stu-id="0490f-124">How to: Group Windows Forms RadioButton Controls to Function as a Set</span></span>](../../../../docs/framework/winforms/controls/how-to-group-windows-forms-radiobutton-controls-to-function-as-a-set.md)  
 [<span data-ttu-id="0490f-125">RadioButton 控件</span><span class="sxs-lookup"><span data-stu-id="0490f-125">RadioButton Control</span></span>](../../../../docs/framework/winforms/controls/radiobutton-control-windows-forms.md)
