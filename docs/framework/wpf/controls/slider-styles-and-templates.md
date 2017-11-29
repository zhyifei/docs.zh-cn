---
title: "Slider 样式和模板"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- parts [WPF], Slider
- states [WPF], Slider
- Slider [WPF], styles and templates
- styles [WPF], Slider
- templates [WPF], Slider
- ControlTemplate [WPF], Slider
ms.assetid: d89aa97b-075a-4752-9c41-9679df65c491
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 9dfa340cf42e5e7ed105bf14eb0f7a24ea85a1b4
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="slider-styles-and-templates"></a><span data-ttu-id="ed0a6-102">Slider 样式和模板</span><span class="sxs-lookup"><span data-stu-id="ed0a6-102">Slider Styles and Templates</span></span>
<span data-ttu-id="ed0a6-103">本主题介绍的样式和模板的<xref:System.Windows.Controls.Slider>控件。</span><span class="sxs-lookup"><span data-stu-id="ed0a6-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.Slider> control.</span></span> <span data-ttu-id="ed0a6-104">你可以修改默认<xref:System.Windows.Controls.ControlTemplate>提供独特外观的控件。</span><span class="sxs-lookup"><span data-stu-id="ed0a6-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="ed0a6-105">有关详细信息，请参阅[通过创建 ControlTemplate 自定义现有控件的外观](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)。</span><span class="sxs-lookup"><span data-stu-id="ed0a6-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="slider-parts"></a><span data-ttu-id="ed0a6-106">滑块部件</span><span class="sxs-lookup"><span data-stu-id="ed0a6-106">Slider Parts</span></span>  
 <span data-ttu-id="ed0a6-107">下表列出的命名的部件<xref:System.Windows.Controls.Slider>控件。</span><span class="sxs-lookup"><span data-stu-id="ed0a6-107">The following table lists the named parts for the <xref:System.Windows.Controls.Slider> control.</span></span>  
  
|<span data-ttu-id="ed0a6-108">部件</span><span class="sxs-lookup"><span data-stu-id="ed0a6-108">Part</span></span>|<span data-ttu-id="ed0a6-109">类型</span><span class="sxs-lookup"><span data-stu-id="ed0a6-109">Type</span></span>|<span data-ttu-id="ed0a6-110">描述</span><span class="sxs-lookup"><span data-stu-id="ed0a6-110">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="ed0a6-111">PART_Track</span><span class="sxs-lookup"><span data-stu-id="ed0a6-111">PART_Track</span></span>|<xref:System.Windows.Controls.Primitives.Track>|<span data-ttu-id="ed0a6-112">指示的位置的元素的容器<xref:System.Windows.Controls.Slider>。</span><span class="sxs-lookup"><span data-stu-id="ed0a6-112">The container for the element that indicates the position of the <xref:System.Windows.Controls.Slider>.</span></span>|  
|<span data-ttu-id="ed0a6-113">PART_SelectionRange</span><span class="sxs-lookup"><span data-stu-id="ed0a6-113">PART_SelectionRange</span></span>|<xref:System.Windows.FrameworkElement>|<span data-ttu-id="ed0a6-114">显示选择范围沿元素<xref:System.Windows.Controls.Slider>。</span><span class="sxs-lookup"><span data-stu-id="ed0a6-114">The element that displays a selection range along the <xref:System.Windows.Controls.Slider>.</span></span>  <span data-ttu-id="ed0a6-115">选择范围才可见才<xref:System.Windows.Controls.Slider.IsSelectionRangeEnabled%2A>属性是`true`。</span><span class="sxs-lookup"><span data-stu-id="ed0a6-115">The selection range is visible only if the <xref:System.Windows.Controls.Slider.IsSelectionRangeEnabled%2A> property is `true`.</span></span>|  
  
## <a name="slider-states"></a><span data-ttu-id="ed0a6-116">滑块状态</span><span class="sxs-lookup"><span data-stu-id="ed0a6-116">Slider States</span></span>  
 <span data-ttu-id="ed0a6-117">下表列出的可视状态<xref:System.Windows.Controls.Slider>控件。</span><span class="sxs-lookup"><span data-stu-id="ed0a6-117">The following table lists the visual states for the <xref:System.Windows.Controls.Slider> control.</span></span>  
  
|<span data-ttu-id="ed0a6-118">VisualState 名称</span><span class="sxs-lookup"><span data-stu-id="ed0a6-118">VisualState Name</span></span>|<span data-ttu-id="ed0a6-119">VisualStateGroup 名称</span><span class="sxs-lookup"><span data-stu-id="ed0a6-119">VisualStateGroup Name</span></span>|<span data-ttu-id="ed0a6-120">描述</span><span class="sxs-lookup"><span data-stu-id="ed0a6-120">Description</span></span>|  
|----------------------|---------------------------|-----------------|  
|<span data-ttu-id="ed0a6-121">普通</span><span class="sxs-lookup"><span data-stu-id="ed0a6-121">Normal</span></span>|<span data-ttu-id="ed0a6-122">CommonStates</span><span class="sxs-lookup"><span data-stu-id="ed0a6-122">CommonStates</span></span>|<span data-ttu-id="ed0a6-123">默认状态。</span><span class="sxs-lookup"><span data-stu-id="ed0a6-123">The default state.</span></span>|  
|<span data-ttu-id="ed0a6-124">MouseOver</span><span class="sxs-lookup"><span data-stu-id="ed0a6-124">MouseOver</span></span>|<span data-ttu-id="ed0a6-125">CommonStates</span><span class="sxs-lookup"><span data-stu-id="ed0a6-125">CommonStates</span></span>|<span data-ttu-id="ed0a6-126">鼠标指针悬停在控件上。</span><span class="sxs-lookup"><span data-stu-id="ed0a6-126">The mouse pointer is positioned over the control.</span></span>|  
|<span data-ttu-id="ed0a6-127">已禁用</span><span class="sxs-lookup"><span data-stu-id="ed0a6-127">Disabled</span></span>|<span data-ttu-id="ed0a6-128">CommonStates</span><span class="sxs-lookup"><span data-stu-id="ed0a6-128">CommonStates</span></span>|<span data-ttu-id="ed0a6-129">已禁用控件。</span><span class="sxs-lookup"><span data-stu-id="ed0a6-129">The control is disabled.</span></span>|  
|<span data-ttu-id="ed0a6-130">已设定焦点</span><span class="sxs-lookup"><span data-stu-id="ed0a6-130">Focused</span></span>|<span data-ttu-id="ed0a6-131">FocusStates</span><span class="sxs-lookup"><span data-stu-id="ed0a6-131">FocusStates</span></span>|<span data-ttu-id="ed0a6-132">控件有焦点。</span><span class="sxs-lookup"><span data-stu-id="ed0a6-132">The control has focus.</span></span>|  
|<span data-ttu-id="ed0a6-133">失去焦点</span><span class="sxs-lookup"><span data-stu-id="ed0a6-133">Unfocused</span></span>|<span data-ttu-id="ed0a6-134">FocusStates</span><span class="sxs-lookup"><span data-stu-id="ed0a6-134">FocusStates</span></span>|<span data-ttu-id="ed0a6-135">控件没有焦点。</span><span class="sxs-lookup"><span data-stu-id="ed0a6-135">The control does not have focus.</span></span>|  
|<span data-ttu-id="ed0a6-136">有效</span><span class="sxs-lookup"><span data-stu-id="ed0a6-136">Valid</span></span>|<span data-ttu-id="ed0a6-137">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="ed0a6-137">ValidationStates</span></span>|<span data-ttu-id="ed0a6-138">该控件使用<xref:System.Windows.Controls.Validation>类和<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>附加的属性`false`。</span><span class="sxs-lookup"><span data-stu-id="ed0a6-138">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="ed0a6-139">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="ed0a6-139">InvalidFocused</span></span>|<span data-ttu-id="ed0a6-140">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="ed0a6-140">ValidationStates</span></span>|<span data-ttu-id="ed0a6-141"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>附加的属性`true`已在控件有焦点。</span><span class="sxs-lookup"><span data-stu-id="ed0a6-141">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="ed0a6-142">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="ed0a6-142">InvalidUnfocused</span></span>|<span data-ttu-id="ed0a6-143">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="ed0a6-143">ValidationStates</span></span>|<span data-ttu-id="ed0a6-144"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>附加的属性`true`具有该控件没有焦点。</span><span class="sxs-lookup"><span data-stu-id="ed0a6-144">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="slider-controltemplate-example"></a><span data-ttu-id="ed0a6-145">滑块 ControlTemplate 示例</span><span class="sxs-lookup"><span data-stu-id="ed0a6-145">Slider ControlTemplate Example</span></span>  
 <span data-ttu-id="ed0a6-146">下面的示例演示如何定义<xref:System.Windows.Controls.ControlTemplate>为<xref:System.Windows.Controls.Slider>控件。</span><span class="sxs-lookup"><span data-stu-id="ed0a6-146">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.Slider> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Slider](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/slider.xaml#slider)]  
  
 <span data-ttu-id="ed0a6-147">上一示例使用了一个或多个以下资源。</span><span class="sxs-lookup"><span data-stu-id="ed0a6-147">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="ed0a6-148">有关完整示例，请参阅[使用 ControlTemplates 设置样式示例](http://go.microsoft.com/fwlink/?LinkID=160041)。</span><span class="sxs-lookup"><span data-stu-id="ed0a6-148">For the complete sample, see [Styling with ControlTemplates Sample](http://go.microsoft.com/fwlink/?LinkID=160041).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ed0a6-149">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ed0a6-149">See Also</span></span>  
 <xref:System.Windows.FrameworkElement.Style%2A>  
 <xref:System.Windows.Controls.ControlTemplate>  
 [<span data-ttu-id="ed0a6-150">控件样式和模板</span><span class="sxs-lookup"><span data-stu-id="ed0a6-150">Control Styles and Templates</span></span>](../../../../docs/framework/wpf/controls/control-styles-and-templates.md)  
 [<span data-ttu-id="ed0a6-151">控件自定义</span><span class="sxs-lookup"><span data-stu-id="ed0a6-151">Control Customization</span></span>](../../../../docs/framework/wpf/controls/control-customization.md)  
 [<span data-ttu-id="ed0a6-152">样式设置和模板化</span><span class="sxs-lookup"><span data-stu-id="ed0a6-152">Styling and Templating</span></span>](../../../../docs/framework/wpf/controls/styling-and-templating.md)  
 [<span data-ttu-id="ed0a6-153">通过创建 ControlTemplate 自定义现有控件的外观</span><span class="sxs-lookup"><span data-stu-id="ed0a6-153">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)
