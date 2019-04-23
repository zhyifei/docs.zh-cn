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
ms.openlocfilehash: ec64c7c2051b12cba01135054a90e54864b7386a
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59116332"
---
# <a name="button-styles-and-templates"></a><span data-ttu-id="f0f09-102">Button 样式和模板</span><span class="sxs-lookup"><span data-stu-id="f0f09-102">Button Styles and Templates</span></span>
<span data-ttu-id="f0f09-103">本主题介绍的样式和模板的<xref:System.Windows.Controls.Button>控件。</span><span class="sxs-lookup"><span data-stu-id="f0f09-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.Button> control.</span></span> <span data-ttu-id="f0f09-104">可以修改默认<xref:System.Windows.Controls.ControlTemplate>为控件提供唯一外观。</span><span class="sxs-lookup"><span data-stu-id="f0f09-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="f0f09-105">有关详细信息，请参阅[通过创建 ControlTemplate 自定义现有控件的外观](customizing-the-appearance-of-an-existing-control.md)。</span><span class="sxs-lookup"><span data-stu-id="f0f09-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="button-parts"></a><span data-ttu-id="f0f09-106">按钮部件</span><span class="sxs-lookup"><span data-stu-id="f0f09-106">Button Parts</span></span>  
 <span data-ttu-id="f0f09-107"><xref:System.Windows.Controls.Button>控件没有任何命名的部件。</span><span class="sxs-lookup"><span data-stu-id="f0f09-107">The <xref:System.Windows.Controls.Button> control does not have any named parts.</span></span>  
  
## <a name="button-states"></a><span data-ttu-id="f0f09-108">按钮状态</span><span class="sxs-lookup"><span data-stu-id="f0f09-108">Button States</span></span>  
 <span data-ttu-id="f0f09-109">下表列出了的可视状态<xref:System.Windows.Controls.Button>控件。</span><span class="sxs-lookup"><span data-stu-id="f0f09-109">The following table lists the visual states for the <xref:System.Windows.Controls.Button> control.</span></span>  
  
|<span data-ttu-id="f0f09-110">VisualState 名称</span><span class="sxs-lookup"><span data-stu-id="f0f09-110">VisualState Name</span></span>|<span data-ttu-id="f0f09-111">VisualStateGroup 名称</span><span class="sxs-lookup"><span data-stu-id="f0f09-111">VisualStateGroup Name</span></span>|<span data-ttu-id="f0f09-112">描述</span><span class="sxs-lookup"><span data-stu-id="f0f09-112">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="f0f09-113">普通</span><span class="sxs-lookup"><span data-stu-id="f0f09-113">Normal</span></span>|<span data-ttu-id="f0f09-114">CommonStates</span><span class="sxs-lookup"><span data-stu-id="f0f09-114">CommonStates</span></span>|<span data-ttu-id="f0f09-115">默认状态。</span><span class="sxs-lookup"><span data-stu-id="f0f09-115">The default state.</span></span>|  
|<span data-ttu-id="f0f09-116">MouseOver</span><span class="sxs-lookup"><span data-stu-id="f0f09-116">MouseOver</span></span>|<span data-ttu-id="f0f09-117">CommonStates</span><span class="sxs-lookup"><span data-stu-id="f0f09-117">CommonStates</span></span>|<span data-ttu-id="f0f09-118">鼠标指针悬停在控件上方。</span><span class="sxs-lookup"><span data-stu-id="f0f09-118">The mouse pointer is positioned over the control.</span></span>|  
|<span data-ttu-id="f0f09-119">已按下</span><span class="sxs-lookup"><span data-stu-id="f0f09-119">Pressed</span></span>|<span data-ttu-id="f0f09-120">CommonStates</span><span class="sxs-lookup"><span data-stu-id="f0f09-120">CommonStates</span></span>|<span data-ttu-id="f0f09-121">已按下控件。</span><span class="sxs-lookup"><span data-stu-id="f0f09-121">The control is pressed.</span></span>|  
|<span data-ttu-id="f0f09-122">已禁用</span><span class="sxs-lookup"><span data-stu-id="f0f09-122">Disabled</span></span>|<span data-ttu-id="f0f09-123">CommonStates</span><span class="sxs-lookup"><span data-stu-id="f0f09-123">CommonStates</span></span>|<span data-ttu-id="f0f09-124">已禁用控件。</span><span class="sxs-lookup"><span data-stu-id="f0f09-124">The control is disabled.</span></span>|  
|<span data-ttu-id="f0f09-125">已设定焦点</span><span class="sxs-lookup"><span data-stu-id="f0f09-125">Focused</span></span>|<span data-ttu-id="f0f09-126">FocusStates</span><span class="sxs-lookup"><span data-stu-id="f0f09-126">FocusStates</span></span>|<span data-ttu-id="f0f09-127">控件有焦点。</span><span class="sxs-lookup"><span data-stu-id="f0f09-127">The control has focus.</span></span>|  
|<span data-ttu-id="f0f09-128">失去焦点</span><span class="sxs-lookup"><span data-stu-id="f0f09-128">Unfocused</span></span>|<span data-ttu-id="f0f09-129">FocusStates</span><span class="sxs-lookup"><span data-stu-id="f0f09-129">FocusStates</span></span>|<span data-ttu-id="f0f09-130">控件没有焦点。</span><span class="sxs-lookup"><span data-stu-id="f0f09-130">The control does not have focus.</span></span>|  
|<span data-ttu-id="f0f09-131">有效</span><span class="sxs-lookup"><span data-stu-id="f0f09-131">Valid</span></span>|<span data-ttu-id="f0f09-132">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="f0f09-132">ValidationStates</span></span>|<span data-ttu-id="f0f09-133">该控件使用<xref:System.Windows.Controls.Validation>类和<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>附加的属性是`false`。</span><span class="sxs-lookup"><span data-stu-id="f0f09-133">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="f0f09-134">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="f0f09-134">InvalidFocused</span></span>|<span data-ttu-id="f0f09-135">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="f0f09-135">ValidationStates</span></span>|<span data-ttu-id="f0f09-136"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>附加的属性是`true`和控件有焦点。</span><span class="sxs-lookup"><span data-stu-id="f0f09-136">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` and the control has focus.</span></span>|  
|<span data-ttu-id="f0f09-137">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="f0f09-137">InvalidUnfocused</span></span>|<span data-ttu-id="f0f09-138">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="f0f09-138">ValidationStates</span></span>|<span data-ttu-id="f0f09-139"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>附加的属性是`true`和控件没有焦点。</span><span class="sxs-lookup"><span data-stu-id="f0f09-139">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` and the control does not have focus.</span></span>|  
  
## <a name="button-controltemplate-example"></a><span data-ttu-id="f0f09-140">按钮 ControlTemplate 示例</span><span class="sxs-lookup"><span data-stu-id="f0f09-140">Button ControlTemplate Example</span></span>  
 <span data-ttu-id="f0f09-141">下面的示例演示如何定义<xref:System.Windows.Controls.ControlTemplate>为<xref:System.Windows.Controls.Button>控件。</span><span class="sxs-lookup"><span data-stu-id="f0f09-141">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.Button> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Button](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/button.xaml#button)]  
  
 <span data-ttu-id="f0f09-142">上一示例使用了一个或多个以下资源。</span><span class="sxs-lookup"><span data-stu-id="f0f09-142">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="f0f09-143">有关完整示例，请参阅[使用 ControlTemplates 设置样式示例](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating)。</span><span class="sxs-lookup"><span data-stu-id="f0f09-143">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f0f09-144">请参阅</span><span class="sxs-lookup"><span data-stu-id="f0f09-144">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="f0f09-145">控件样式和模板</span><span class="sxs-lookup"><span data-stu-id="f0f09-145">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="f0f09-146">控件自定义</span><span class="sxs-lookup"><span data-stu-id="f0f09-146">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="f0f09-147">样式设置和模板化</span><span class="sxs-lookup"><span data-stu-id="f0f09-147">Styling and Templating</span></span>](styling-and-templating.md)
- [<span data-ttu-id="f0f09-148">通过创建 ControlTemplate 自定义现有控件的外观</span><span class="sxs-lookup"><span data-stu-id="f0f09-148">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](customizing-the-appearance-of-an-existing-control.md)
