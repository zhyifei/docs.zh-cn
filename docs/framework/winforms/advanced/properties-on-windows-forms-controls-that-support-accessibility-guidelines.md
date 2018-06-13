---
title: 支持辅助功能准则的 Windows 窗体控件上的属性
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms, accessibility properties of controls
- accessibility [Windows Forms], Windows Forms control properties
ms.assetid: ad3567a6-313b-4708-9e15-f487a831f049
ms.openlocfilehash: b466dcf42561d8ced7b224215538a807c94b174b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33524483"
---
# <a name="properties-on-windows-forms-controls-that-support-accessibility-guidelines"></a><span data-ttu-id="93217-102">支持辅助功能准则的 Windows 窗体控件上的属性</span><span class="sxs-lookup"><span data-stu-id="93217-102">Properties on Windows Forms Controls That Support Accessibility Guidelines</span></span>
<span data-ttu-id="93217-103">标准 Windows 窗体的工具箱上的控件都支持许多辅助功能准则，包括公开键盘焦点和公开屏幕元素。</span><span class="sxs-lookup"><span data-stu-id="93217-103">Controls on the standard toolbox for Windows Forms support many of the accessibility guidelines, including exposing the keyboard focus and exposing the screen elements.</span></span>  
  
## <a name="planning-ahead-for-accessibility"></a><span data-ttu-id="93217-104">预先规划辅助功能</span><span class="sxs-lookup"><span data-stu-id="93217-104">Planning Ahead for Accessibility</span></span>  
 <span data-ttu-id="93217-105">可以使用的控件的属性，以支持其他辅助功能准则下, 表中所示。</span><span class="sxs-lookup"><span data-stu-id="93217-105">The controls' properties can be used to support other accessibility guidelines as shown in the following table.</span></span> <span data-ttu-id="93217-106">此外，你应使用菜单提供对功能进行编程访问。</span><span class="sxs-lookup"><span data-stu-id="93217-106">Additionally, you should use menus to provide access to program features.</span></span>  
  
|<span data-ttu-id="93217-107">控件属性</span><span class="sxs-lookup"><span data-stu-id="93217-107">Control Property</span></span>|<span data-ttu-id="93217-108">有关辅助功能的注意事项</span><span class="sxs-lookup"><span data-stu-id="93217-108">Considerations for Accessibility</span></span>|  
|----------------------|--------------------------------------|  
|<span data-ttu-id="93217-109">AccessibleDescription</span><span class="sxs-lookup"><span data-stu-id="93217-109">AccessibleDescription</span></span>|<span data-ttu-id="93217-110">说明报告给辅助工具，如屏幕读取器。</span><span class="sxs-lookup"><span data-stu-id="93217-110">The description is reported to accessibility aids such as screen readers.</span></span> <span data-ttu-id="93217-111">辅助工具是专用的程序和设备，用于帮助残障人士更加有效地使用计算机。</span><span class="sxs-lookup"><span data-stu-id="93217-111">Accessibility aids are specialized programs and devices that help people with disabilities use computers more effectively.</span></span>|  
|<span data-ttu-id="93217-112">AccessibleName</span><span class="sxs-lookup"><span data-stu-id="93217-112">AccessibleName</span></span>|<span data-ttu-id="93217-113">将报告给辅助工具的名称。</span><span class="sxs-lookup"><span data-stu-id="93217-113">The name that will be reported to the accessibility aids.</span></span>|  
|<span data-ttu-id="93217-114">AccessibleRole</span><span class="sxs-lookup"><span data-stu-id="93217-114">AccessibleRole</span></span>|<span data-ttu-id="93217-115">描述如何使用用户界面中的元素。</span><span class="sxs-lookup"><span data-stu-id="93217-115">Describes the use of the element in the user interface.</span></span>|  
|<span data-ttu-id="93217-116">TabIndex</span><span class="sxs-lookup"><span data-stu-id="93217-116">TabIndex</span></span>|<span data-ttu-id="93217-117">创建窗体中导航的合理路径。</span><span class="sxs-lookup"><span data-stu-id="93217-117">Creates a sensible navigational path through the form.</span></span> <span data-ttu-id="93217-118">很重要没有内部函数的标签，例如文本框中，必须立即在它们之前的 tab 键顺序及其关联的标签的控件。</span><span class="sxs-lookup"><span data-stu-id="93217-118">It is important for controls without intrinsic labels, such as text boxes, to have their associated label immediately precede them in the tab order.</span></span>|  
|<span data-ttu-id="93217-119">Text</span><span class="sxs-lookup"><span data-stu-id="93217-119">Text</span></span>|<span data-ttu-id="93217-120">使用"&"符来创建访问键。</span><span class="sxs-lookup"><span data-stu-id="93217-120">Use the "&" character to create access keys.</span></span> <span data-ttu-id="93217-121">使用访问密钥是一部分提供的功能的已记录的键盘访问。</span><span class="sxs-lookup"><span data-stu-id="93217-121">Using access keys is part of providing documented keyboard access to features.</span></span>|  
|<span data-ttu-id="93217-122">字号</span><span class="sxs-lookup"><span data-stu-id="93217-122">Font Size</span></span>|<span data-ttu-id="93217-123">如果不调整字体大小，则应将它设为 10 磅或更大。</span><span class="sxs-lookup"><span data-stu-id="93217-123">If the font size is not adjustable, then it should be set to 10 points or larger.</span></span> <span data-ttu-id="93217-124">窗体的字体大小设置后，所有之后添加到窗体的控件将具有相同的大小。</span><span class="sxs-lookup"><span data-stu-id="93217-124">Once the form's font size is set, all the controls added to the form thereafter will have the same size.</span></span>|  
|<span data-ttu-id="93217-125">前景色</span><span class="sxs-lookup"><span data-stu-id="93217-125">Forecolor</span></span>|<span data-ttu-id="93217-126">如果此属性设置为默认值，然后将窗体上使用用户的颜色首选项。</span><span class="sxs-lookup"><span data-stu-id="93217-126">If this property is set to the default, then the user's color preferences will be used on the form.</span></span>|  
|<span data-ttu-id="93217-127">背景色</span><span class="sxs-lookup"><span data-stu-id="93217-127">Backcolor</span></span>|<span data-ttu-id="93217-128">如果此属性设置为默认值，然后将窗体上使用用户的颜色首选项。</span><span class="sxs-lookup"><span data-stu-id="93217-128">If this property is set to the default, then the user's color preferences will be used on the form.</span></span>|  
|<span data-ttu-id="93217-129">BackgroundImage</span><span class="sxs-lookup"><span data-stu-id="93217-129">BackgroundImage</span></span>|<span data-ttu-id="93217-130">将此属性保留为空，以使文本更具可读性。</span><span class="sxs-lookup"><span data-stu-id="93217-130">Leave this property blank to make text more readable.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="93217-131">请参阅</span><span class="sxs-lookup"><span data-stu-id="93217-131">See Also</span></span>  
 [<span data-ttu-id="93217-132">演练：创建基于 Windows 的可访问应用程序</span><span class="sxs-lookup"><span data-stu-id="93217-132">Walkthrough: Creating an Accessible Windows-based Application</span></span>](../../../../docs/framework/winforms/advanced/walkthrough-creating-an-accessible-windows-based-application.md)
