---
title: "Thumb 样式和模板"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- states [WPF], Thumb
- styles [WPF], Thumb
- templates [WPF], Thumb
- Thumb [WPF], styles and templates
- ControlTemplate [WPF], Thumb
- parts [WPF], Thumb
ms.assetid: 86a49235-62d9-414e-923e-53126e3f930a
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 7d9f0b8559497939737b97568a679953d392d5be
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="thumb-syles-and-templates"></a><span data-ttu-id="c9df8-102">Thumb 样式和模板</span><span class="sxs-lookup"><span data-stu-id="c9df8-102">Thumb Syles and Templates</span></span>
<span data-ttu-id="c9df8-103">本主题介绍的样式和模板的<xref:System.Windows.Controls.Primitives.Thumb>控件。</span><span class="sxs-lookup"><span data-stu-id="c9df8-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.Primitives.Thumb> control.</span></span> <span data-ttu-id="c9df8-104">你可以修改默认<xref:System.Windows.Controls.ControlTemplate>提供独特外观的控件。</span><span class="sxs-lookup"><span data-stu-id="c9df8-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="c9df8-105">有关详细信息，请参阅[通过创建 ControlTemplate 自定义现有控件的外观](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)。</span><span class="sxs-lookup"><span data-stu-id="c9df8-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="thumb-parts"></a><span data-ttu-id="c9df8-106">Thumb 部件</span><span class="sxs-lookup"><span data-stu-id="c9df8-106">Thumb Parts</span></span>  
 <span data-ttu-id="c9df8-107"><xref:System.Windows.Controls.Primitives.Thumb>控件不具有任何已命名的部件。</span><span class="sxs-lookup"><span data-stu-id="c9df8-107">The <xref:System.Windows.Controls.Primitives.Thumb> control does not have any named parts.</span></span>  
  
## <a name="thumb-states"></a><span data-ttu-id="c9df8-108">Thumb 状态</span><span class="sxs-lookup"><span data-stu-id="c9df8-108">Thumb States</span></span>  
 <span data-ttu-id="c9df8-109">下表列出的可视状态<xref:System.Windows.Controls.Primitives.Thumb>控件。</span><span class="sxs-lookup"><span data-stu-id="c9df8-109">The following table lists the visual states for the <xref:System.Windows.Controls.Primitives.Thumb> control.</span></span>  
  
|<span data-ttu-id="c9df8-110">VisualState 名称</span><span class="sxs-lookup"><span data-stu-id="c9df8-110">VisualState Name</span></span>|<span data-ttu-id="c9df8-111">VisualStateGroup 名称</span><span class="sxs-lookup"><span data-stu-id="c9df8-111">VisualStateGroup Name</span></span>|<span data-ttu-id="c9df8-112">描述</span><span class="sxs-lookup"><span data-stu-id="c9df8-112">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="c9df8-113">普通</span><span class="sxs-lookup"><span data-stu-id="c9df8-113">Normal</span></span>|<span data-ttu-id="c9df8-114">CommonStates</span><span class="sxs-lookup"><span data-stu-id="c9df8-114">CommonStates</span></span>|<span data-ttu-id="c9df8-115">默认状态。</span><span class="sxs-lookup"><span data-stu-id="c9df8-115">The default state.</span></span>|  
|<span data-ttu-id="c9df8-116">MouseOver</span><span class="sxs-lookup"><span data-stu-id="c9df8-116">MouseOver</span></span>|<span data-ttu-id="c9df8-117">CommonStates</span><span class="sxs-lookup"><span data-stu-id="c9df8-117">CommonStates</span></span>|<span data-ttu-id="c9df8-118">鼠标指针悬停在控件上方。</span><span class="sxs-lookup"><span data-stu-id="c9df8-118">The mouse pointer is positioned over the control.</span></span>|  
|<span data-ttu-id="c9df8-119">已按下</span><span class="sxs-lookup"><span data-stu-id="c9df8-119">Pressed</span></span>|<span data-ttu-id="c9df8-120">CommonStates</span><span class="sxs-lookup"><span data-stu-id="c9df8-120">CommonStates</span></span>|<span data-ttu-id="c9df8-121">已按下控件。</span><span class="sxs-lookup"><span data-stu-id="c9df8-121">The control is pressed.</span></span>|  
|<span data-ttu-id="c9df8-122">已禁用</span><span class="sxs-lookup"><span data-stu-id="c9df8-122">Disabled</span></span>|<span data-ttu-id="c9df8-123">CommonStates</span><span class="sxs-lookup"><span data-stu-id="c9df8-123">CommonStates</span></span>|<span data-ttu-id="c9df8-124">已禁用控件。</span><span class="sxs-lookup"><span data-stu-id="c9df8-124">The control is disabled.</span></span>|  
|<span data-ttu-id="c9df8-125">已设定焦点</span><span class="sxs-lookup"><span data-stu-id="c9df8-125">Focused</span></span>|<span data-ttu-id="c9df8-126">FocusStates</span><span class="sxs-lookup"><span data-stu-id="c9df8-126">FocusStates</span></span>|<span data-ttu-id="c9df8-127">控件有焦点。</span><span class="sxs-lookup"><span data-stu-id="c9df8-127">The control has focus.</span></span>|  
|<span data-ttu-id="c9df8-128">失去焦点</span><span class="sxs-lookup"><span data-stu-id="c9df8-128">Unfocused</span></span>|<span data-ttu-id="c9df8-129">FocusStates</span><span class="sxs-lookup"><span data-stu-id="c9df8-129">FocusStates</span></span>|<span data-ttu-id="c9df8-130">控件没有焦点。</span><span class="sxs-lookup"><span data-stu-id="c9df8-130">The control does not have focus.</span></span>|  
|<span data-ttu-id="c9df8-131">有效</span><span class="sxs-lookup"><span data-stu-id="c9df8-131">Valid</span></span>|<span data-ttu-id="c9df8-132">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="c9df8-132">ValidationStates</span></span>|<span data-ttu-id="c9df8-133">该控件使用<xref:System.Windows.Controls.Validation>类和<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>附加的属性`false`。</span><span class="sxs-lookup"><span data-stu-id="c9df8-133">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="c9df8-134">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="c9df8-134">InvalidFocused</span></span>|<span data-ttu-id="c9df8-135">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="c9df8-135">ValidationStates</span></span>|<span data-ttu-id="c9df8-136"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>附加的属性`true`已在控件有焦点。</span><span class="sxs-lookup"><span data-stu-id="c9df8-136">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="c9df8-137">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="c9df8-137">InvalidUnfocused</span></span>|<span data-ttu-id="c9df8-138">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="c9df8-138">ValidationStates</span></span>|<span data-ttu-id="c9df8-139"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>附加的属性`true`具有该控件没有焦点。</span><span class="sxs-lookup"><span data-stu-id="c9df8-139">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="thumb-controltemplate-example"></a><span data-ttu-id="c9df8-140">Thumb ControlTemplate 示例</span><span class="sxs-lookup"><span data-stu-id="c9df8-140">Thumb ControlTemplate Example</span></span>  
 <span data-ttu-id="c9df8-141">下面的示例演示如何定义<xref:System.Windows.Controls.ControlTemplate>为<xref:System.Windows.Controls.Primitives.Thumb>控件。</span><span class="sxs-lookup"><span data-stu-id="c9df8-141">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.Primitives.Thumb> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Thumb](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/slider.xaml#thumb)]  
  
 <span data-ttu-id="c9df8-142">上一示例使用了一个或多个以下资源。</span><span class="sxs-lookup"><span data-stu-id="c9df8-142">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="c9df8-143">有关完整示例，请参阅[使用 ControlTemplates 设置样式示例](http://go.microsoft.com/fwlink/?LinkID=160041)。</span><span class="sxs-lookup"><span data-stu-id="c9df8-143">For the complete sample, see [Styling with ControlTemplates Sample](http://go.microsoft.com/fwlink/?LinkID=160041).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c9df8-144">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c9df8-144">See Also</span></span>  
 <xref:System.Windows.FrameworkElement.Style%2A>  
 <xref:System.Windows.Controls.ControlTemplate>  
 [<span data-ttu-id="c9df8-145">控件样式和模板</span><span class="sxs-lookup"><span data-stu-id="c9df8-145">Control Styles and Templates</span></span>](../../../../docs/framework/wpf/controls/control-styles-and-templates.md)  
 [<span data-ttu-id="c9df8-146">控件自定义</span><span class="sxs-lookup"><span data-stu-id="c9df8-146">Control Customization</span></span>](../../../../docs/framework/wpf/controls/control-customization.md)  
 [<span data-ttu-id="c9df8-147">样式设置和模板化</span><span class="sxs-lookup"><span data-stu-id="c9df8-147">Styling and Templating</span></span>](../../../../docs/framework/wpf/controls/styling-and-templating.md)  
 [<span data-ttu-id="c9df8-148">通过创建 ControlTemplate 自定义现有控件的外观</span><span class="sxs-lookup"><span data-stu-id="c9df8-148">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)
