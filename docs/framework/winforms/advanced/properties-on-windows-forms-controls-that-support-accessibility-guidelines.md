---
title: 支持辅助功能准则的 Windows 窗体控件上的属性
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms, accessibility properties of controls
- accessibility [Windows Forms], Windows Forms control properties
ms.assetid: ad3567a6-313b-4708-9e15-f487a831f049
ms.openlocfilehash: b731f277620925a333c8d9eba64c8900674327da
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54552200"
---
# <a name="properties-on-windows-forms-controls-that-support-accessibility-guidelines"></a><span data-ttu-id="33c8d-102">支持辅助功能准则的 Windows 窗体控件上的属性</span><span class="sxs-lookup"><span data-stu-id="33c8d-102">Properties on Windows Forms Controls That Support Accessibility Guidelines</span></span>
<span data-ttu-id="33c8d-103">标准 Windows 窗体的工具箱上的控件支持许多辅助功能准则，包括公开键盘焦点和屏幕元素。</span><span class="sxs-lookup"><span data-stu-id="33c8d-103">Controls on the standard toolbox for Windows Forms support many of the accessibility guidelines, including exposing the keyboard focus and exposing the screen elements.</span></span>  
  
## <a name="planning-ahead-for-accessibility"></a><span data-ttu-id="33c8d-104">提前规划可访问性</span><span class="sxs-lookup"><span data-stu-id="33c8d-104">Planning Ahead for Accessibility</span></span>  
 <span data-ttu-id="33c8d-105">可以使用控件的属性，以支持其他可访问性准则下, 表中所示。</span><span class="sxs-lookup"><span data-stu-id="33c8d-105">The controls' properties can be used to support other accessibility guidelines as shown in the following table.</span></span> <span data-ttu-id="33c8d-106">此外，您应使用菜单来访问程序功能。</span><span class="sxs-lookup"><span data-stu-id="33c8d-106">Additionally, you should use menus to provide access to program features.</span></span>  
  
|<span data-ttu-id="33c8d-107">控件属性</span><span class="sxs-lookup"><span data-stu-id="33c8d-107">Control Property</span></span>|<span data-ttu-id="33c8d-108">有关辅助功能注意事项</span><span class="sxs-lookup"><span data-stu-id="33c8d-108">Considerations for Accessibility</span></span>|  
|----------------------|--------------------------------------|  
|<span data-ttu-id="33c8d-109">AccessibleDescription</span><span class="sxs-lookup"><span data-stu-id="33c8d-109">AccessibleDescription</span></span>|<span data-ttu-id="33c8d-110">说明报告给屏幕阅读器等辅助工具。</span><span class="sxs-lookup"><span data-stu-id="33c8d-110">The description is reported to accessibility aids such as screen readers.</span></span> <span data-ttu-id="33c8d-111">辅助工具是专用的程序和设备，用于帮助残障人士更加有效地使用计算机。</span><span class="sxs-lookup"><span data-stu-id="33c8d-111">Accessibility aids are specialized programs and devices that help people with disabilities use computers more effectively.</span></span>|  
|<span data-ttu-id="33c8d-112">AccessibleName</span><span class="sxs-lookup"><span data-stu-id="33c8d-112">AccessibleName</span></span>|<span data-ttu-id="33c8d-113">将报告给辅助工具的名称。</span><span class="sxs-lookup"><span data-stu-id="33c8d-113">The name that will be reported to the accessibility aids.</span></span>|  
|<span data-ttu-id="33c8d-114">AccessibleRole</span><span class="sxs-lookup"><span data-stu-id="33c8d-114">AccessibleRole</span></span>|<span data-ttu-id="33c8d-115">介绍如何使用用户界面中的元素。</span><span class="sxs-lookup"><span data-stu-id="33c8d-115">Describes the use of the element in the user interface.</span></span>|  
|<span data-ttu-id="33c8d-116">TabIndex</span><span class="sxs-lookup"><span data-stu-id="33c8d-116">TabIndex</span></span>|<span data-ttu-id="33c8d-117">创建一个通过窗体的合理的导航路径。</span><span class="sxs-lookup"><span data-stu-id="33c8d-117">Creates a sensible navigational path through the form.</span></span> <span data-ttu-id="33c8d-118">务必没有内部函数的标签，如文本框中，必须按 tab 键顺序紧跟及其关联的标签的控件。</span><span class="sxs-lookup"><span data-stu-id="33c8d-118">It is important for controls without intrinsic labels, such as text boxes, to have their associated label immediately precede them in the tab order.</span></span>|  
|<span data-ttu-id="33c8d-119">Text</span><span class="sxs-lookup"><span data-stu-id="33c8d-119">Text</span></span>|<span data-ttu-id="33c8d-120">使用"&"字符来创建访问键。</span><span class="sxs-lookup"><span data-stu-id="33c8d-120">Use the "&" character to create access keys.</span></span> <span data-ttu-id="33c8d-121">使用访问密钥是提供有案可稽的键盘访问功能的一部分。</span><span class="sxs-lookup"><span data-stu-id="33c8d-121">Using access keys is part of providing documented keyboard access to features.</span></span>|  
|<span data-ttu-id="33c8d-122">字号</span><span class="sxs-lookup"><span data-stu-id="33c8d-122">Font Size</span></span>|<span data-ttu-id="33c8d-123">如果字体大小不是可调整的则应将它设为 10 磅或更大。</span><span class="sxs-lookup"><span data-stu-id="33c8d-123">If the font size is not adjustable, then it should be set to 10 points or larger.</span></span> <span data-ttu-id="33c8d-124">一旦设置窗体的字体大小，此后添加到窗体的所有控件将都具有相同的大小。</span><span class="sxs-lookup"><span data-stu-id="33c8d-124">Once the form's font size is set, all the controls added to the form thereafter will have the same size.</span></span>|  
|<span data-ttu-id="33c8d-125">前景色</span><span class="sxs-lookup"><span data-stu-id="33c8d-125">Forecolor</span></span>|<span data-ttu-id="33c8d-126">如果此属性设置为默认值，则将在窗体上使用用户的颜色首选项。</span><span class="sxs-lookup"><span data-stu-id="33c8d-126">If this property is set to the default, then the user's color preferences will be used on the form.</span></span>|  
|<span data-ttu-id="33c8d-127">背景色</span><span class="sxs-lookup"><span data-stu-id="33c8d-127">Backcolor</span></span>|<span data-ttu-id="33c8d-128">如果此属性设置为默认值，则将在窗体上使用用户的颜色首选项。</span><span class="sxs-lookup"><span data-stu-id="33c8d-128">If this property is set to the default, then the user's color preferences will be used on the form.</span></span>|  
|<span data-ttu-id="33c8d-129">BackgroundImage</span><span class="sxs-lookup"><span data-stu-id="33c8d-129">BackgroundImage</span></span>|<span data-ttu-id="33c8d-130">将此属性为空，以使文本更具可读性。</span><span class="sxs-lookup"><span data-stu-id="33c8d-130">Leave this property blank to make text more readable.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="33c8d-131">请参阅</span><span class="sxs-lookup"><span data-stu-id="33c8d-131">See also</span></span>
- [<span data-ttu-id="33c8d-132">演练：创建可访问的基于 Windows 的应用程序</span><span class="sxs-lookup"><span data-stu-id="33c8d-132">Walkthrough: Creating an Accessible Windows-based Application</span></span>](../../../../docs/framework/winforms/advanced/walkthrough-creating-an-accessible-windows-based-application.md)
