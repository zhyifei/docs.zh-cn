---
title: "支持辅助功能准则的 Windows 窗体控件上的属性"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Windows Forms, accessibility properties of controls
- accessibility [Windows Forms], Windows Forms control properties
ms.assetid: ad3567a6-313b-4708-9e15-f487a831f049
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 967b4a0e883338c756aceef37d11edecfb978527
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="properties-on-windows-forms-controls-that-support-accessibility-guidelines"></a><span data-ttu-id="86138-102">支持辅助功能准则的 Windows 窗体控件上的属性</span><span class="sxs-lookup"><span data-stu-id="86138-102">Properties on Windows Forms Controls That Support Accessibility Guidelines</span></span>
<span data-ttu-id="86138-103">标准 Windows 窗体的工具箱上的控件都支持许多辅助功能准则，包括公开键盘焦点和公开屏幕元素。</span><span class="sxs-lookup"><span data-stu-id="86138-103">Controls on the standard toolbox for Windows Forms support many of the accessibility guidelines, including exposing the keyboard focus and exposing the screen elements.</span></span>  
  
## <a name="planning-ahead-for-accessibility"></a><span data-ttu-id="86138-104">预先规划辅助功能</span><span class="sxs-lookup"><span data-stu-id="86138-104">Planning Ahead for Accessibility</span></span>  
 <span data-ttu-id="86138-105">可以使用的控件的属性，以支持其他辅助功能准则下, 表中所示。</span><span class="sxs-lookup"><span data-stu-id="86138-105">The controls' properties can be used to support other accessibility guidelines as shown in the following table.</span></span> <span data-ttu-id="86138-106">此外，你应使用菜单提供对功能进行编程访问。</span><span class="sxs-lookup"><span data-stu-id="86138-106">Additionally, you should use menus to provide access to program features.</span></span>  
  
|<span data-ttu-id="86138-107">控件属性</span><span class="sxs-lookup"><span data-stu-id="86138-107">Control Property</span></span>|<span data-ttu-id="86138-108">有关辅助功能的注意事项</span><span class="sxs-lookup"><span data-stu-id="86138-108">Considerations for Accessibility</span></span>|  
|----------------------|--------------------------------------|  
|<span data-ttu-id="86138-109">AccessibleDescription</span><span class="sxs-lookup"><span data-stu-id="86138-109">AccessibleDescription</span></span>|<span data-ttu-id="86138-110">说明报告给辅助工具，如屏幕读取器。</span><span class="sxs-lookup"><span data-stu-id="86138-110">The description is reported to accessibility aids such as screen readers.</span></span> <span data-ttu-id="86138-111">辅助工具是专用的程序和设备，用于帮助残障人士更加有效地使用计算机。</span><span class="sxs-lookup"><span data-stu-id="86138-111">Accessibility aids are specialized programs and devices that help people with disabilities use computers more effectively.</span></span>|  
|<span data-ttu-id="86138-112">AccessibleName</span><span class="sxs-lookup"><span data-stu-id="86138-112">AccessibleName</span></span>|<span data-ttu-id="86138-113">将报告给辅助工具的名称。</span><span class="sxs-lookup"><span data-stu-id="86138-113">The name that will be reported to the accessibility aids.</span></span>|  
|<span data-ttu-id="86138-114">AccessibleRole</span><span class="sxs-lookup"><span data-stu-id="86138-114">AccessibleRole</span></span>|<span data-ttu-id="86138-115">描述如何使用用户界面中的元素。</span><span class="sxs-lookup"><span data-stu-id="86138-115">Describes the use of the element in the user interface.</span></span>|  
|<span data-ttu-id="86138-116">TabIndex</span><span class="sxs-lookup"><span data-stu-id="86138-116">TabIndex</span></span>|<span data-ttu-id="86138-117">创建窗体中导航的合理路径。</span><span class="sxs-lookup"><span data-stu-id="86138-117">Creates a sensible navigational path through the form.</span></span> <span data-ttu-id="86138-118">很重要没有内部函数的标签，例如文本框中，必须立即在它们之前的 tab 键顺序及其关联的标签的控件。</span><span class="sxs-lookup"><span data-stu-id="86138-118">It is important for controls without intrinsic labels, such as text boxes, to have their associated label immediately precede them in the tab order.</span></span>|  
|<span data-ttu-id="86138-119">Text</span><span class="sxs-lookup"><span data-stu-id="86138-119">Text</span></span>|<span data-ttu-id="86138-120">使用"&"符来创建访问键。</span><span class="sxs-lookup"><span data-stu-id="86138-120">Use the "&" character to create access keys.</span></span> <span data-ttu-id="86138-121">使用访问密钥是一部分提供的功能的已记录的键盘访问。</span><span class="sxs-lookup"><span data-stu-id="86138-121">Using access keys is part of providing documented keyboard access to features.</span></span>|  
|<span data-ttu-id="86138-122">字号</span><span class="sxs-lookup"><span data-stu-id="86138-122">Font Size</span></span>|<span data-ttu-id="86138-123">如果不调整字体大小，则应将它设为 10 磅或更大。</span><span class="sxs-lookup"><span data-stu-id="86138-123">If the font size is not adjustable, then it should be set to 10 points or larger.</span></span> <span data-ttu-id="86138-124">窗体的字体大小设置后，所有之后添加到窗体的控件将具有相同的大小。</span><span class="sxs-lookup"><span data-stu-id="86138-124">Once the form's font size is set, all the controls added to the form thereafter will have the same size.</span></span>|  
|<span data-ttu-id="86138-125">前景色</span><span class="sxs-lookup"><span data-stu-id="86138-125">Forecolor</span></span>|<span data-ttu-id="86138-126">如果此属性设置为默认值，然后将窗体上使用用户的颜色首选项。</span><span class="sxs-lookup"><span data-stu-id="86138-126">If this property is set to the default, then the user's color preferences will be used on the form.</span></span>|  
|<span data-ttu-id="86138-127">背景色</span><span class="sxs-lookup"><span data-stu-id="86138-127">Backcolor</span></span>|<span data-ttu-id="86138-128">如果此属性设置为默认值，然后将窗体上使用用户的颜色首选项。</span><span class="sxs-lookup"><span data-stu-id="86138-128">If this property is set to the default, then the user's color preferences will be used on the form.</span></span>|  
|<span data-ttu-id="86138-129">BackgroundImage</span><span class="sxs-lookup"><span data-stu-id="86138-129">BackgroundImage</span></span>|<span data-ttu-id="86138-130">将此属性保留为空，以使文本更具可读性。</span><span class="sxs-lookup"><span data-stu-id="86138-130">Leave this property blank to make text more readable.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="86138-131">请参阅</span><span class="sxs-lookup"><span data-stu-id="86138-131">See Also</span></span>  
 [<span data-ttu-id="86138-132">演练：创建基于 Windows 的可访问应用程序</span><span class="sxs-lookup"><span data-stu-id="86138-132">Walkthrough: Creating an Accessible Windows-based Application</span></span>](../../../../docs/framework/winforms/advanced/walkthrough-creating-an-accessible-windows-based-application.md)
