---
title: "PasswordBox 样式和模板"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- styles [WPF], PasswordBox
- templates [WPF], PasswordBox
- ControlTemplate [WPF], PasswordBox
- states [WPF], PasswordBox
- PasswordBox [WPF], styles and templates
- parts [WPF], PasswordBox
ms.assetid: deb52107-959f-4a60-b303-d21a0a933060
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f22b73704d21fa719a678799c1d95fc266c661e4
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="passwordbox-syles-and-templates"></a><span data-ttu-id="52340-102">PasswordBox 样式和模板</span><span class="sxs-lookup"><span data-stu-id="52340-102">PasswordBox Syles and Templates</span></span>
<span data-ttu-id="52340-103">本主题介绍的样式和模板的<xref:System.Windows.Controls.PasswordBox>控件。</span><span class="sxs-lookup"><span data-stu-id="52340-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.PasswordBox> control.</span></span> <span data-ttu-id="52340-104">你可以修改默认<xref:System.Windows.Controls.ControlTemplate>提供独特外观的控件。</span><span class="sxs-lookup"><span data-stu-id="52340-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="52340-105">有关详细信息，请参阅[通过创建 ControlTemplate 自定义现有控件的外观](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)。</span><span class="sxs-lookup"><span data-stu-id="52340-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="passwordbox-parts"></a><span data-ttu-id="52340-106">PasswordBox 部件</span><span class="sxs-lookup"><span data-stu-id="52340-106">PasswordBox Parts</span></span>  
 <span data-ttu-id="52340-107">下表列出的命名的部件<xref:System.Windows.Controls.PasswordBox>控件。</span><span class="sxs-lookup"><span data-stu-id="52340-107">The following table lists the named parts for the <xref:System.Windows.Controls.PasswordBox> control.</span></span>  
  
|<span data-ttu-id="52340-108">部件</span><span class="sxs-lookup"><span data-stu-id="52340-108">Part</span></span>|<span data-ttu-id="52340-109">类型</span><span class="sxs-lookup"><span data-stu-id="52340-109">Type</span></span>|<span data-ttu-id="52340-110">描述</span><span class="sxs-lookup"><span data-stu-id="52340-110">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="52340-111">PART_ContentHost</span><span class="sxs-lookup"><span data-stu-id="52340-111">PART_ContentHost</span></span>|<xref:System.Windows.FrameworkElement>|<span data-ttu-id="52340-112">可以包含一个可见元素<xref:System.Windows.FrameworkElement>。</span><span class="sxs-lookup"><span data-stu-id="52340-112">A visual element that can contain a <xref:System.Windows.FrameworkElement>.</span></span> <span data-ttu-id="52340-113">文本<xref:System.Windows.Controls.PasswordBox>显示在此元素。</span><span class="sxs-lookup"><span data-stu-id="52340-113">The text of the <xref:System.Windows.Controls.PasswordBox> is displayed in this element.</span></span>|  
  
## <a name="passwordbox-states"></a><span data-ttu-id="52340-114">PasswordBox 状态</span><span class="sxs-lookup"><span data-stu-id="52340-114">PasswordBox States</span></span>  
 <span data-ttu-id="52340-115">下表列出的可视状态<xref:System.Windows.Controls.PasswordBox>控件。</span><span class="sxs-lookup"><span data-stu-id="52340-115">The following table lists the visual states for the <xref:System.Windows.Controls.PasswordBox> control.</span></span>  
  
|<span data-ttu-id="52340-116">VisualState 名称</span><span class="sxs-lookup"><span data-stu-id="52340-116">VisualState Name</span></span>|<span data-ttu-id="52340-117">VisualStateGroup 名称</span><span class="sxs-lookup"><span data-stu-id="52340-117">VisualStateGroup Name</span></span>|<span data-ttu-id="52340-118">描述</span><span class="sxs-lookup"><span data-stu-id="52340-118">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="52340-119">普通</span><span class="sxs-lookup"><span data-stu-id="52340-119">Normal</span></span>|<span data-ttu-id="52340-120">CommonStates</span><span class="sxs-lookup"><span data-stu-id="52340-120">CommonStates</span></span>|<span data-ttu-id="52340-121">默认状态。</span><span class="sxs-lookup"><span data-stu-id="52340-121">The default state.</span></span>|  
|<span data-ttu-id="52340-122">MouseOver</span><span class="sxs-lookup"><span data-stu-id="52340-122">MouseOver</span></span>|<span data-ttu-id="52340-123">CommonStates</span><span class="sxs-lookup"><span data-stu-id="52340-123">CommonStates</span></span>|<span data-ttu-id="52340-124">鼠标指针悬停在控件上。</span><span class="sxs-lookup"><span data-stu-id="52340-124">The mouse pointer is positioned over the control.</span></span>|  
|<span data-ttu-id="52340-125">已禁用</span><span class="sxs-lookup"><span data-stu-id="52340-125">Disabled</span></span>|<span data-ttu-id="52340-126">CommonStates</span><span class="sxs-lookup"><span data-stu-id="52340-126">CommonStates</span></span>|<span data-ttu-id="52340-127">已禁用控件。</span><span class="sxs-lookup"><span data-stu-id="52340-127">The control is disabled.</span></span>|  
|<span data-ttu-id="52340-128">已设定焦点</span><span class="sxs-lookup"><span data-stu-id="52340-128">Focused</span></span>|<span data-ttu-id="52340-129">FocusStates</span><span class="sxs-lookup"><span data-stu-id="52340-129">FocusStates</span></span>|<span data-ttu-id="52340-130">控件有焦点。</span><span class="sxs-lookup"><span data-stu-id="52340-130">The control has focus.</span></span>|  
|<span data-ttu-id="52340-131">失去焦点</span><span class="sxs-lookup"><span data-stu-id="52340-131">Unfocused</span></span>|<span data-ttu-id="52340-132">FocusStates</span><span class="sxs-lookup"><span data-stu-id="52340-132">FocusStates</span></span>|<span data-ttu-id="52340-133">控件没有焦点。</span><span class="sxs-lookup"><span data-stu-id="52340-133">The control does not have focus.</span></span>|  
|<span data-ttu-id="52340-134">有效</span><span class="sxs-lookup"><span data-stu-id="52340-134">Valid</span></span>|<span data-ttu-id="52340-135">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="52340-135">ValidationStates</span></span>|<span data-ttu-id="52340-136">该控件使用<xref:System.Windows.Controls.Validation>类和<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>附加的属性`false`。</span><span class="sxs-lookup"><span data-stu-id="52340-136">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="52340-137">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="52340-137">InvalidFocused</span></span>|<span data-ttu-id="52340-138">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="52340-138">ValidationStates</span></span>|<span data-ttu-id="52340-139"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>附加的属性`true`已在控件有焦点。</span><span class="sxs-lookup"><span data-stu-id="52340-139">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="52340-140">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="52340-140">InvalidUnfocused</span></span>|<span data-ttu-id="52340-141">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="52340-141">ValidationStates</span></span>|<span data-ttu-id="52340-142"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>附加的属性`true`具有该控件没有焦点。</span><span class="sxs-lookup"><span data-stu-id="52340-142">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="passwordbox-controltemplate-example"></a><span data-ttu-id="52340-143">PasswordBox ControlTemplate 示例</span><span class="sxs-lookup"><span data-stu-id="52340-143">PasswordBox ControlTemplate Example</span></span>  
 <span data-ttu-id="52340-144">下面的示例演示如何定义<xref:System.Windows.Controls.ControlTemplate>为<xref:System.Windows.Controls.PasswordBox>控件。</span><span class="sxs-lookup"><span data-stu-id="52340-144">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.PasswordBox> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#PasswordBox](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/textbox.xaml#passwordbox)]  
  
 <span data-ttu-id="52340-145">上一示例使用了一个或多个以下资源。</span><span class="sxs-lookup"><span data-stu-id="52340-145">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="52340-146">有关完整示例，请参阅[使用 ControlTemplates 设置样式示例](http://go.microsoft.com/fwlink/?LinkID=160041)。</span><span class="sxs-lookup"><span data-stu-id="52340-146">For the complete sample, see [Styling with ControlTemplates Sample](http://go.microsoft.com/fwlink/?LinkID=160041).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="52340-147">请参阅</span><span class="sxs-lookup"><span data-stu-id="52340-147">See Also</span></span>  
 <xref:System.Windows.FrameworkElement.Style%2A>  
 <xref:System.Windows.Controls.ControlTemplate>  
 [<span data-ttu-id="52340-148">控件样式和模板</span><span class="sxs-lookup"><span data-stu-id="52340-148">Control Styles and Templates</span></span>](../../../../docs/framework/wpf/controls/control-styles-and-templates.md)  
 [<span data-ttu-id="52340-149">控件自定义</span><span class="sxs-lookup"><span data-stu-id="52340-149">Control Customization</span></span>](../../../../docs/framework/wpf/controls/control-customization.md)  
 [<span data-ttu-id="52340-150">样式设置和模板化</span><span class="sxs-lookup"><span data-stu-id="52340-150">Styling and Templating</span></span>](../../../../docs/framework/wpf/controls/styling-and-templating.md)  
 [<span data-ttu-id="52340-151">通过创建 ControlTemplate 自定义现有控件的外观</span><span class="sxs-lookup"><span data-stu-id="52340-151">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)
