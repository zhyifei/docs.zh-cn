---
title: TextBox 样式和模板
ms.date: 03/30/2017
helpviewer_keywords:
- ControlTemplate [WPF], TextBox
- parts [WPF], TextBox
- states [WPF], TextBox
- styles [WPF], TextBox
- templates [WPF], TextBox
- TextBox [WPF], styles and templates
ms.assetid: aa99130c-43a1-450f-9b46-c40ae0db0cca
ms.openlocfilehash: b18aa6798c2d7c66eaca6cb98b55e9050868f258
ms.sourcegitcommit: 43924acbdbb3981d103e11049bbe460457d42073
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/23/2018
---
# <a name="textbox-styles-and-templates"></a><span data-ttu-id="781d3-102">TextBox 样式和模板</span><span class="sxs-lookup"><span data-stu-id="781d3-102">TextBox Styles and Templates</span></span>
<span data-ttu-id="781d3-103">本主题介绍的样式和模板的<xref:System.Windows.Controls.TextBox>控件。</span><span class="sxs-lookup"><span data-stu-id="781d3-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.TextBox> control.</span></span> <span data-ttu-id="781d3-104">你可以修改默认<xref:System.Windows.Controls.ControlTemplate>提供独特外观的控件。</span><span class="sxs-lookup"><span data-stu-id="781d3-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="781d3-105">有关详细信息，请参阅[通过创建 ControlTemplate 自定义现有控件的外观](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)。</span><span class="sxs-lookup"><span data-stu-id="781d3-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="textbox-parts"></a><span data-ttu-id="781d3-106">文本框中部分</span><span class="sxs-lookup"><span data-stu-id="781d3-106">TextBox Parts</span></span>  
 <span data-ttu-id="781d3-107">下表列出的命名的部件<xref:System.Windows.Controls.TextBox>控件。</span><span class="sxs-lookup"><span data-stu-id="781d3-107">The following table lists the named parts for the <xref:System.Windows.Controls.TextBox> control.</span></span>  
  
|<span data-ttu-id="781d3-108">部件</span><span class="sxs-lookup"><span data-stu-id="781d3-108">Part</span></span>|<span data-ttu-id="781d3-109">类型</span><span class="sxs-lookup"><span data-stu-id="781d3-109">Type</span></span>|<span data-ttu-id="781d3-110">描述</span><span class="sxs-lookup"><span data-stu-id="781d3-110">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="781d3-111">PART_ContentHost</span><span class="sxs-lookup"><span data-stu-id="781d3-111">PART_ContentHost</span></span>|<xref:System.Windows.FrameworkElement>|<span data-ttu-id="781d3-112">可以包含一个可见元素<xref:System.Windows.FrameworkElement>。</span><span class="sxs-lookup"><span data-stu-id="781d3-112">A visual element that can contain a <xref:System.Windows.FrameworkElement>.</span></span> <span data-ttu-id="781d3-113">文本<xref:System.Windows.Controls.TextBox>显示在此元素。</span><span class="sxs-lookup"><span data-stu-id="781d3-113">The text of the <xref:System.Windows.Controls.TextBox> is displayed in this element.</span></span>|  
  
## <a name="textbox-states"></a><span data-ttu-id="781d3-114">文本框中状态</span><span class="sxs-lookup"><span data-stu-id="781d3-114">TextBox States</span></span>  
 <span data-ttu-id="781d3-115">下表列出的可视状态<xref:System.Windows.Controls.TextBox>控件。</span><span class="sxs-lookup"><span data-stu-id="781d3-115">The following table lists the visual states for the <xref:System.Windows.Controls.TextBox> control.</span></span>  
  
|<span data-ttu-id="781d3-116">VisualState 名称</span><span class="sxs-lookup"><span data-stu-id="781d3-116">VisualState Name</span></span>|<span data-ttu-id="781d3-117">VisualStateGroup 名称</span><span class="sxs-lookup"><span data-stu-id="781d3-117">VisualStateGroup Name</span></span>|<span data-ttu-id="781d3-118">描述</span><span class="sxs-lookup"><span data-stu-id="781d3-118">Description</span></span>|  
|----------------------|---------------------------|-----------------|  
|<span data-ttu-id="781d3-119">普通</span><span class="sxs-lookup"><span data-stu-id="781d3-119">Normal</span></span>|<span data-ttu-id="781d3-120">CommonStates</span><span class="sxs-lookup"><span data-stu-id="781d3-120">CommonStates</span></span>|<span data-ttu-id="781d3-121">默认状态。</span><span class="sxs-lookup"><span data-stu-id="781d3-121">The default state.</span></span>|  
|<span data-ttu-id="781d3-122">MouseOver</span><span class="sxs-lookup"><span data-stu-id="781d3-122">MouseOver</span></span>|<span data-ttu-id="781d3-123">CommonStates</span><span class="sxs-lookup"><span data-stu-id="781d3-123">CommonStates</span></span>|<span data-ttu-id="781d3-124">鼠标指针悬停在控件上。</span><span class="sxs-lookup"><span data-stu-id="781d3-124">The mouse pointer is positioned over the control.</span></span>|  
|<span data-ttu-id="781d3-125">已禁用</span><span class="sxs-lookup"><span data-stu-id="781d3-125">Disabled</span></span>|<span data-ttu-id="781d3-126">CommonStates</span><span class="sxs-lookup"><span data-stu-id="781d3-126">CommonStates</span></span>|<span data-ttu-id="781d3-127">已禁用控件。</span><span class="sxs-lookup"><span data-stu-id="781d3-127">The control is disabled.</span></span>|  
|<span data-ttu-id="781d3-128">ReadOnly</span><span class="sxs-lookup"><span data-stu-id="781d3-128">ReadOnly</span></span>|<span data-ttu-id="781d3-129">CommonStates</span><span class="sxs-lookup"><span data-stu-id="781d3-129">CommonStates</span></span>|<span data-ttu-id="781d3-130">用户不能更改中的文本<xref:System.Windows.Controls.TextBox>。</span><span class="sxs-lookup"><span data-stu-id="781d3-130">The user cannot change the text in the <xref:System.Windows.Controls.TextBox>.</span></span>|  
|<span data-ttu-id="781d3-131">已设定焦点</span><span class="sxs-lookup"><span data-stu-id="781d3-131">Focused</span></span>|<span data-ttu-id="781d3-132">FocusStates</span><span class="sxs-lookup"><span data-stu-id="781d3-132">FocusStates</span></span>|<span data-ttu-id="781d3-133">控件有焦点。</span><span class="sxs-lookup"><span data-stu-id="781d3-133">The control has focus.</span></span>|  
|<span data-ttu-id="781d3-134">失去焦点</span><span class="sxs-lookup"><span data-stu-id="781d3-134">Unfocused</span></span>|<span data-ttu-id="781d3-135">FocusStates</span><span class="sxs-lookup"><span data-stu-id="781d3-135">FocusStates</span></span>|<span data-ttu-id="781d3-136">控件没有焦点。</span><span class="sxs-lookup"><span data-stu-id="781d3-136">The control does not have focus.</span></span>|  
|<span data-ttu-id="781d3-137">有效</span><span class="sxs-lookup"><span data-stu-id="781d3-137">Valid</span></span>|<span data-ttu-id="781d3-138">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="781d3-138">ValidationStates</span></span>|<span data-ttu-id="781d3-139">该控件使用<xref:System.Windows.Controls.Validation>类和<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>附加的属性`false`。</span><span class="sxs-lookup"><span data-stu-id="781d3-139">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="781d3-140">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="781d3-140">InvalidFocused</span></span>|<span data-ttu-id="781d3-141">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="781d3-141">ValidationStates</span></span>|<span data-ttu-id="781d3-142"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>附加的属性`true`已在控件有焦点。</span><span class="sxs-lookup"><span data-stu-id="781d3-142">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="781d3-143">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="781d3-143">InvalidUnfocused</span></span>|<span data-ttu-id="781d3-144">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="781d3-144">ValidationStates</span></span>|<span data-ttu-id="781d3-145"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>附加的属性`true`具有该控件没有焦点。</span><span class="sxs-lookup"><span data-stu-id="781d3-145">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="textbox-controltemplate-example"></a><span data-ttu-id="781d3-146">文本框中 ControlTemplate 示例</span><span class="sxs-lookup"><span data-stu-id="781d3-146">TextBox ControlTemplate Example</span></span>  
 <span data-ttu-id="781d3-147">下面的示例演示如何定义<xref:System.Windows.Controls.ControlTemplate>为<xref:System.Windows.Controls.TextBox>控件。</span><span class="sxs-lookup"><span data-stu-id="781d3-147">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.TextBox> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#TextBox](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/textbox.xaml#textbox)]  
  
 <span data-ttu-id="781d3-148">上一示例使用了一个或多个以下资源。</span><span class="sxs-lookup"><span data-stu-id="781d3-148">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="781d3-149">有关完整示例，请参阅[使用 ControlTemplates 设置样式示例](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating)。</span><span class="sxs-lookup"><span data-stu-id="781d3-149">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="781d3-150">请参阅</span><span class="sxs-lookup"><span data-stu-id="781d3-150">See Also</span></span>  
 <xref:System.Windows.FrameworkElement.Style%2A>  
 <xref:System.Windows.Controls.ControlTemplate>  
 [<span data-ttu-id="781d3-151">控件样式和模板</span><span class="sxs-lookup"><span data-stu-id="781d3-151">Control Styles and Templates</span></span>](../../../../docs/framework/wpf/controls/control-styles-and-templates.md)  
 [<span data-ttu-id="781d3-152">控件自定义</span><span class="sxs-lookup"><span data-stu-id="781d3-152">Control Customization</span></span>](../../../../docs/framework/wpf/controls/control-customization.md)  
 [<span data-ttu-id="781d3-153">样式设置和模板化</span><span class="sxs-lookup"><span data-stu-id="781d3-153">Styling and Templating</span></span>](../../../../docs/framework/wpf/controls/styling-and-templating.md)  
 [<span data-ttu-id="781d3-154">通过创建 ControlTemplate 自定义现有控件的外观</span><span class="sxs-lookup"><span data-stu-id="781d3-154">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)
