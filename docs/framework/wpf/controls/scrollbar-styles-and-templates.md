---
title: ScrollBar 样式和模板
ms.date: 03/30/2017
helpviewer_keywords:
- styles [WPF], ScrollBar
- ControlTemplate [WPF], ScrollBar
- states [WPF], ScrollBar
- ScrollBar [WPF], styles and templates
- templates [WPF], ScrollBar
- parts [WPF], ScrollBar
ms.assetid: 066ea45a-e27d-43b0-adfe-cce6934c22f5
ms.openlocfilehash: 7093a78555aefd73f9bb05c0a7b5fab6b66176fc
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2019
ms.locfileid: "74283417"
---
# <a name="scrollbar-styles-and-templates"></a><span data-ttu-id="4b6bf-102">ScrollBar 样式和模板</span><span class="sxs-lookup"><span data-stu-id="4b6bf-102">ScrollBar Styles and Templates</span></span>
<span data-ttu-id="4b6bf-103">本主题介绍 <xref:System.Windows.Controls.Primitives.ScrollBar> 控件的样式和模板。</span><span class="sxs-lookup"><span data-stu-id="4b6bf-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.Primitives.ScrollBar> control.</span></span> <span data-ttu-id="4b6bf-104">您可以修改默认 <xref:System.Windows.Controls.ControlTemplate> 以使控件具有独特的外观。</span><span class="sxs-lookup"><span data-stu-id="4b6bf-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="4b6bf-105">有关详细信息，请参阅为[控件创建模板](../../../desktop-wpf/themes/how-to-create-apply-template.md)。</span><span class="sxs-lookup"><span data-stu-id="4b6bf-105">For more information, see [Create a template for a control](../../../desktop-wpf/themes/how-to-create-apply-template.md).</span></span>  
  
## <a name="scrollbar-parts"></a><span data-ttu-id="4b6bf-106">滚动条部件</span><span class="sxs-lookup"><span data-stu-id="4b6bf-106">ScrollBar Parts</span></span>  
 <span data-ttu-id="4b6bf-107">下表列出了 <xref:System.Windows.Controls.Primitives.ScrollBar> 控件的已命名部分。</span><span class="sxs-lookup"><span data-stu-id="4b6bf-107">The following table lists the named parts for the <xref:System.Windows.Controls.Primitives.ScrollBar> control.</span></span>  
  
|<span data-ttu-id="4b6bf-108">部件</span><span class="sxs-lookup"><span data-stu-id="4b6bf-108">Part</span></span>|<span data-ttu-id="4b6bf-109">类型</span><span class="sxs-lookup"><span data-stu-id="4b6bf-109">Type</span></span>|<span data-ttu-id="4b6bf-110">说明</span><span class="sxs-lookup"><span data-stu-id="4b6bf-110">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="4b6bf-111">PART_Track</span><span class="sxs-lookup"><span data-stu-id="4b6bf-111">PART_Track</span></span>|<xref:System.Windows.Controls.Primitives.Track>|<span data-ttu-id="4b6bf-112">指示 <xref:System.Windows.Controls.Primitives.ScrollBar>位置的元素的容器。</span><span class="sxs-lookup"><span data-stu-id="4b6bf-112">The container for the element that indicates the position of the <xref:System.Windows.Controls.Primitives.ScrollBar>.</span></span>|  
  
## <a name="scrollbar-states"></a><span data-ttu-id="4b6bf-113">滚动条状态</span><span class="sxs-lookup"><span data-stu-id="4b6bf-113">ScrollBar States</span></span>  
 <span data-ttu-id="4b6bf-114">下表列出了 <xref:System.Windows.Controls.Primitives.ScrollBar> 控件的可视状态。</span><span class="sxs-lookup"><span data-stu-id="4b6bf-114">The following table lists the visual states for the <xref:System.Windows.Controls.Primitives.ScrollBar> control.</span></span>  
  
|<span data-ttu-id="4b6bf-115">VisualState 名称</span><span class="sxs-lookup"><span data-stu-id="4b6bf-115">VisualState Name</span></span>|<span data-ttu-id="4b6bf-116">VisualStateGroup 名称</span><span class="sxs-lookup"><span data-stu-id="4b6bf-116">VisualStateGroup Name</span></span>|<span data-ttu-id="4b6bf-117">说明</span><span class="sxs-lookup"><span data-stu-id="4b6bf-117">Description</span></span>|  
|----------------------|---------------------------|-----------------|  
|<span data-ttu-id="4b6bf-118">正常</span><span class="sxs-lookup"><span data-stu-id="4b6bf-118">Normal</span></span>|<span data-ttu-id="4b6bf-119">CommonStates</span><span class="sxs-lookup"><span data-stu-id="4b6bf-119">CommonStates</span></span>|<span data-ttu-id="4b6bf-120">默认状态。</span><span class="sxs-lookup"><span data-stu-id="4b6bf-120">The default state.</span></span>|  
|<span data-ttu-id="4b6bf-121">MouseOver</span><span class="sxs-lookup"><span data-stu-id="4b6bf-121">MouseOver</span></span>|<span data-ttu-id="4b6bf-122">CommonStates</span><span class="sxs-lookup"><span data-stu-id="4b6bf-122">CommonStates</span></span>|<span data-ttu-id="4b6bf-123">鼠标指针悬停在控件上。</span><span class="sxs-lookup"><span data-stu-id="4b6bf-123">The mouse pointer is positioned over the control.</span></span>|  
|<span data-ttu-id="4b6bf-124">已禁用</span><span class="sxs-lookup"><span data-stu-id="4b6bf-124">Disabled</span></span>|<span data-ttu-id="4b6bf-125">CommonStates</span><span class="sxs-lookup"><span data-stu-id="4b6bf-125">CommonStates</span></span>|<span data-ttu-id="4b6bf-126">已禁用控件。</span><span class="sxs-lookup"><span data-stu-id="4b6bf-126">The control is disabled.</span></span>|  
|<span data-ttu-id="4b6bf-127">有效</span><span class="sxs-lookup"><span data-stu-id="4b6bf-127">Valid</span></span>|<span data-ttu-id="4b6bf-128">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="4b6bf-128">ValidationStates</span></span>|<span data-ttu-id="4b6bf-129">控件使用 <xref:System.Windows.Controls.Validation> 类，并且 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 附加属性是 `false`。</span><span class="sxs-lookup"><span data-stu-id="4b6bf-129">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="4b6bf-130">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="4b6bf-130">InvalidFocused</span></span>|<span data-ttu-id="4b6bf-131">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="4b6bf-131">ValidationStates</span></span>|<span data-ttu-id="4b6bf-132"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 附加属性是 `true` 并且控件具有焦点。</span><span class="sxs-lookup"><span data-stu-id="4b6bf-132">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` and the control has focus.</span></span>|  
|<span data-ttu-id="4b6bf-133">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="4b6bf-133">InvalidUnfocused</span></span>|<span data-ttu-id="4b6bf-134">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="4b6bf-134">ValidationStates</span></span>|<span data-ttu-id="4b6bf-135"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 附加属性是 `true` 的，该控件没有焦点。</span><span class="sxs-lookup"><span data-stu-id="4b6bf-135">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` and the control does not have focus.</span></span>|  
  
## <a name="scrollbar-controltemplate-example"></a><span data-ttu-id="4b6bf-136">滚动条 System.windows.controls.controltemplate> 示例</span><span class="sxs-lookup"><span data-stu-id="4b6bf-136">ScrollBar ControlTemplate Example</span></span>  
 <span data-ttu-id="4b6bf-137">下面的示例演示如何为 <xref:System.Windows.Controls.Primitives.ScrollBar> 控件定义 <xref:System.Windows.Controls.ControlTemplate>。</span><span class="sxs-lookup"><span data-stu-id="4b6bf-137">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.Primitives.ScrollBar> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#ScrollBar](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/scrollbar.xaml#scrollbar)]  
  
 <span data-ttu-id="4b6bf-138">上一示例使用了一个或多个以下资源。</span><span class="sxs-lookup"><span data-stu-id="4b6bf-138">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="4b6bf-139">有关完整示例，请参阅[使用 ControlTemplates 设置样式示例](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating)。</span><span class="sxs-lookup"><span data-stu-id="4b6bf-139">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4b6bf-140">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4b6bf-140">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="4b6bf-141">控件样式和模板</span><span class="sxs-lookup"><span data-stu-id="4b6bf-141">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="4b6bf-142">控件自定义</span><span class="sxs-lookup"><span data-stu-id="4b6bf-142">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="4b6bf-143">样式设置和模板化</span><span class="sxs-lookup"><span data-stu-id="4b6bf-143">Styling and Templating</span></span>](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [<span data-ttu-id="4b6bf-144">为控件创建模板</span><span class="sxs-lookup"><span data-stu-id="4b6bf-144">Create a template for a control</span></span>](../../../desktop-wpf/themes/how-to-create-apply-template.md)
