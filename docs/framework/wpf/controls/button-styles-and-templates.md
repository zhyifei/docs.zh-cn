---
title: Button 样式和模板
ms.date: 03/30/2017
helpviewer_keywords:
- states [WPF], Button
- parts [WPF], Button
- styles [WPF], Button
- Button [WPF], styles and templates
- templates [WPF], Button
- ControlTemplate [WPF], Button
ms.assetid: e223c759-f8c4-4717-acfb-b1e40bdf5f3b
ms.openlocfilehash: 982a1497748883d55938f975164adb44822216cd
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="button-styles-and-templates"></a><span data-ttu-id="1494a-102">Button 样式和模板</span><span class="sxs-lookup"><span data-stu-id="1494a-102">Button Styles and Templates</span></span>
<span data-ttu-id="1494a-103">本主题介绍的样式和模板的<xref:System.Windows.Controls.Button>控件。</span><span class="sxs-lookup"><span data-stu-id="1494a-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.Button> control.</span></span> <span data-ttu-id="1494a-104">你可以修改默认<xref:System.Windows.Controls.ControlTemplate>提供独特外观的控件。</span><span class="sxs-lookup"><span data-stu-id="1494a-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="1494a-105">有关详细信息，请参阅[通过创建 ControlTemplate 自定义现有控件的外观](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)。</span><span class="sxs-lookup"><span data-stu-id="1494a-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="button-parts"></a><span data-ttu-id="1494a-106">按钮部件</span><span class="sxs-lookup"><span data-stu-id="1494a-106">Button Parts</span></span>  
 <span data-ttu-id="1494a-107"><xref:System.Windows.Controls.Button>控件不具有任何已命名的部件。</span><span class="sxs-lookup"><span data-stu-id="1494a-107">The <xref:System.Windows.Controls.Button> control does not have any named parts.</span></span>  
  
## <a name="button-states"></a><span data-ttu-id="1494a-108">按钮状态</span><span class="sxs-lookup"><span data-stu-id="1494a-108">Button States</span></span>  
 <span data-ttu-id="1494a-109">下表列出的可视状态<xref:System.Windows.Controls.Button>控件。</span><span class="sxs-lookup"><span data-stu-id="1494a-109">The following table lists the visual states for the <xref:System.Windows.Controls.Button> control.</span></span>  
  
|<span data-ttu-id="1494a-110">VisualState 名称</span><span class="sxs-lookup"><span data-stu-id="1494a-110">VisualState Name</span></span>|<span data-ttu-id="1494a-111">VisualStateGroup 名称</span><span class="sxs-lookup"><span data-stu-id="1494a-111">VisualStateGroup Name</span></span>|<span data-ttu-id="1494a-112">描述</span><span class="sxs-lookup"><span data-stu-id="1494a-112">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="1494a-113">普通</span><span class="sxs-lookup"><span data-stu-id="1494a-113">Normal</span></span>|<span data-ttu-id="1494a-114">CommonStates</span><span class="sxs-lookup"><span data-stu-id="1494a-114">CommonStates</span></span>|<span data-ttu-id="1494a-115">默认状态。</span><span class="sxs-lookup"><span data-stu-id="1494a-115">The default state.</span></span>|  
|<span data-ttu-id="1494a-116">MouseOver</span><span class="sxs-lookup"><span data-stu-id="1494a-116">MouseOver</span></span>|<span data-ttu-id="1494a-117">CommonStates</span><span class="sxs-lookup"><span data-stu-id="1494a-117">CommonStates</span></span>|<span data-ttu-id="1494a-118">鼠标指针悬停在控件上方。</span><span class="sxs-lookup"><span data-stu-id="1494a-118">The mouse pointer is positioned over the control.</span></span>|  
|<span data-ttu-id="1494a-119">已按下</span><span class="sxs-lookup"><span data-stu-id="1494a-119">Pressed</span></span>|<span data-ttu-id="1494a-120">CommonStates</span><span class="sxs-lookup"><span data-stu-id="1494a-120">CommonStates</span></span>|<span data-ttu-id="1494a-121">已按下控件。</span><span class="sxs-lookup"><span data-stu-id="1494a-121">The control is pressed.</span></span>|  
|<span data-ttu-id="1494a-122">已禁用</span><span class="sxs-lookup"><span data-stu-id="1494a-122">Disabled</span></span>|<span data-ttu-id="1494a-123">CommonStates</span><span class="sxs-lookup"><span data-stu-id="1494a-123">CommonStates</span></span>|<span data-ttu-id="1494a-124">已禁用控件。</span><span class="sxs-lookup"><span data-stu-id="1494a-124">The control is disabled.</span></span>|  
|<span data-ttu-id="1494a-125">已设定焦点</span><span class="sxs-lookup"><span data-stu-id="1494a-125">Focused</span></span>|<span data-ttu-id="1494a-126">FocusStates</span><span class="sxs-lookup"><span data-stu-id="1494a-126">FocusStates</span></span>|<span data-ttu-id="1494a-127">控件有焦点。</span><span class="sxs-lookup"><span data-stu-id="1494a-127">The control has focus.</span></span>|  
|<span data-ttu-id="1494a-128">失去焦点</span><span class="sxs-lookup"><span data-stu-id="1494a-128">Unfocused</span></span>|<span data-ttu-id="1494a-129">FocusStates</span><span class="sxs-lookup"><span data-stu-id="1494a-129">FocusStates</span></span>|<span data-ttu-id="1494a-130">控件没有焦点。</span><span class="sxs-lookup"><span data-stu-id="1494a-130">The control does not have focus.</span></span>|  
|<span data-ttu-id="1494a-131">有效</span><span class="sxs-lookup"><span data-stu-id="1494a-131">Valid</span></span>|<span data-ttu-id="1494a-132">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="1494a-132">ValidationStates</span></span>|<span data-ttu-id="1494a-133">该控件使用<xref:System.Windows.Controls.Validation>类和<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>附加的属性`false`。</span><span class="sxs-lookup"><span data-stu-id="1494a-133">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="1494a-134">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="1494a-134">InvalidFocused</span></span>|<span data-ttu-id="1494a-135">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="1494a-135">ValidationStates</span></span>|<span data-ttu-id="1494a-136"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>附加的属性`true`和在控件有焦点。</span><span class="sxs-lookup"><span data-stu-id="1494a-136">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` and the control has focus.</span></span>|  
|<span data-ttu-id="1494a-137">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="1494a-137">InvalidUnfocused</span></span>|<span data-ttu-id="1494a-138">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="1494a-138">ValidationStates</span></span>|<span data-ttu-id="1494a-139"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>附加的属性`true`和控件没有焦点。</span><span class="sxs-lookup"><span data-stu-id="1494a-139">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` and the control does not have focus.</span></span>|  
  
## <a name="button-controltemplate-example"></a><span data-ttu-id="1494a-140">按钮 ControlTemplate 示例</span><span class="sxs-lookup"><span data-stu-id="1494a-140">Button ControlTemplate Example</span></span>  
 <span data-ttu-id="1494a-141">下面的示例演示如何定义<xref:System.Windows.Controls.ControlTemplate>为<xref:System.Windows.Controls.Button>控件。</span><span class="sxs-lookup"><span data-stu-id="1494a-141">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.Button> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Button](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/button.xaml#button)]  
  
 <span data-ttu-id="1494a-142">上一示例使用了一个或多个以下资源。</span><span class="sxs-lookup"><span data-stu-id="1494a-142">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="1494a-143">有关完整示例，请参阅[使用 ControlTemplates 设置样式示例](http://go.microsoft.com/fwlink/?LinkID=160041)。</span><span class="sxs-lookup"><span data-stu-id="1494a-143">For the complete sample, see [Styling with ControlTemplates Sample](http://go.microsoft.com/fwlink/?LinkID=160041).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1494a-144">请参阅</span><span class="sxs-lookup"><span data-stu-id="1494a-144">See Also</span></span>  
 <xref:System.Windows.FrameworkElement.Style%2A>  
 <xref:System.Windows.Controls.ControlTemplate>  
 [<span data-ttu-id="1494a-145">控件样式和模板</span><span class="sxs-lookup"><span data-stu-id="1494a-145">Control Styles and Templates</span></span>](../../../../docs/framework/wpf/controls/control-styles-and-templates.md)  
 [<span data-ttu-id="1494a-146">控件自定义</span><span class="sxs-lookup"><span data-stu-id="1494a-146">Control Customization</span></span>](../../../../docs/framework/wpf/controls/control-customization.md)  
 [<span data-ttu-id="1494a-147">样式设置和模板化</span><span class="sxs-lookup"><span data-stu-id="1494a-147">Styling and Templating</span></span>](../../../../docs/framework/wpf/controls/styling-and-templating.md)  
 [<span data-ttu-id="1494a-148">通过创建 ControlTemplate 自定义现有控件的外观</span><span class="sxs-lookup"><span data-stu-id="1494a-148">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)
