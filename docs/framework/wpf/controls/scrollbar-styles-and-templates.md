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
ms.openlocfilehash: 22b2206067302f621a94a1e9abca1607792b3393
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59144503"
---
# <a name="scrollbar-styles-and-templates"></a><span data-ttu-id="28c28-102">ScrollBar 样式和模板</span><span class="sxs-lookup"><span data-stu-id="28c28-102">ScrollBar Styles and Templates</span></span>
<span data-ttu-id="28c28-103">本主题介绍的样式和模板的<xref:System.Windows.Controls.Primitives.ScrollBar>控件。</span><span class="sxs-lookup"><span data-stu-id="28c28-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.Primitives.ScrollBar> control.</span></span> <span data-ttu-id="28c28-104">可以修改默认<xref:System.Windows.Controls.ControlTemplate>为控件提供唯一外观。</span><span class="sxs-lookup"><span data-stu-id="28c28-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="28c28-105">有关详细信息，请参阅[通过创建 ControlTemplate 自定义现有控件的外观](customizing-the-appearance-of-an-existing-control.md)。</span><span class="sxs-lookup"><span data-stu-id="28c28-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="scrollbar-parts"></a><span data-ttu-id="28c28-106">滚动条部分</span><span class="sxs-lookup"><span data-stu-id="28c28-106">ScrollBar Parts</span></span>  
 <span data-ttu-id="28c28-107">下表列出了用于命名的部件<xref:System.Windows.Controls.Primitives.ScrollBar>控件。</span><span class="sxs-lookup"><span data-stu-id="28c28-107">The following table lists the named parts for the <xref:System.Windows.Controls.Primitives.ScrollBar> control.</span></span>  
  
|<span data-ttu-id="28c28-108">部件</span><span class="sxs-lookup"><span data-stu-id="28c28-108">Part</span></span>|<span data-ttu-id="28c28-109">类型</span><span class="sxs-lookup"><span data-stu-id="28c28-109">Type</span></span>|<span data-ttu-id="28c28-110">描述</span><span class="sxs-lookup"><span data-stu-id="28c28-110">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="28c28-111">PART_Track</span><span class="sxs-lookup"><span data-stu-id="28c28-111">PART_Track</span></span>|<xref:System.Windows.Controls.Primitives.Track>|<span data-ttu-id="28c28-112">指示的位置的元素的容器<xref:System.Windows.Controls.Primitives.ScrollBar>。</span><span class="sxs-lookup"><span data-stu-id="28c28-112">The container for the element that indicates the position of the <xref:System.Windows.Controls.Primitives.ScrollBar>.</span></span>|  
  
## <a name="scrollbar-states"></a><span data-ttu-id="28c28-113">滚动条状态</span><span class="sxs-lookup"><span data-stu-id="28c28-113">ScrollBar States</span></span>  
 <span data-ttu-id="28c28-114">下表列出了的可视状态<xref:System.Windows.Controls.Primitives.ScrollBar>控件。</span><span class="sxs-lookup"><span data-stu-id="28c28-114">The following table lists the visual states for the <xref:System.Windows.Controls.Primitives.ScrollBar> control.</span></span>  
  
|<span data-ttu-id="28c28-115">VisualState 名称</span><span class="sxs-lookup"><span data-stu-id="28c28-115">VisualState Name</span></span>|<span data-ttu-id="28c28-116">VisualStateGroup 名称</span><span class="sxs-lookup"><span data-stu-id="28c28-116">VisualStateGroup Name</span></span>|<span data-ttu-id="28c28-117">描述</span><span class="sxs-lookup"><span data-stu-id="28c28-117">Description</span></span>|  
|----------------------|---------------------------|-----------------|  
|<span data-ttu-id="28c28-118">普通</span><span class="sxs-lookup"><span data-stu-id="28c28-118">Normal</span></span>|<span data-ttu-id="28c28-119">CommonStates</span><span class="sxs-lookup"><span data-stu-id="28c28-119">CommonStates</span></span>|<span data-ttu-id="28c28-120">默认状态。</span><span class="sxs-lookup"><span data-stu-id="28c28-120">The default state.</span></span>|  
|<span data-ttu-id="28c28-121">MouseOver</span><span class="sxs-lookup"><span data-stu-id="28c28-121">MouseOver</span></span>|<span data-ttu-id="28c28-122">CommonStates</span><span class="sxs-lookup"><span data-stu-id="28c28-122">CommonStates</span></span>|<span data-ttu-id="28c28-123">鼠标指针悬停在控件上。</span><span class="sxs-lookup"><span data-stu-id="28c28-123">The mouse pointer is positioned over the control.</span></span>|  
|<span data-ttu-id="28c28-124">已禁用</span><span class="sxs-lookup"><span data-stu-id="28c28-124">Disabled</span></span>|<span data-ttu-id="28c28-125">CommonStates</span><span class="sxs-lookup"><span data-stu-id="28c28-125">CommonStates</span></span>|<span data-ttu-id="28c28-126">已禁用控件。</span><span class="sxs-lookup"><span data-stu-id="28c28-126">The control is disabled.</span></span>|  
|<span data-ttu-id="28c28-127">有效</span><span class="sxs-lookup"><span data-stu-id="28c28-127">Valid</span></span>|<span data-ttu-id="28c28-128">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="28c28-128">ValidationStates</span></span>|<span data-ttu-id="28c28-129">该控件使用<xref:System.Windows.Controls.Validation>类和<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>附加的属性是`false`。</span><span class="sxs-lookup"><span data-stu-id="28c28-129">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="28c28-130">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="28c28-130">InvalidFocused</span></span>|<span data-ttu-id="28c28-131">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="28c28-131">ValidationStates</span></span>|<span data-ttu-id="28c28-132"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>附加的属性是`true`已在控件有焦点。</span><span class="sxs-lookup"><span data-stu-id="28c28-132">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="28c28-133">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="28c28-133">InvalidUnfocused</span></span>|<span data-ttu-id="28c28-134">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="28c28-134">ValidationStates</span></span>|<span data-ttu-id="28c28-135"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>附加的属性是`true`具有该控件没有焦点。</span><span class="sxs-lookup"><span data-stu-id="28c28-135">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="scrollbar-controltemplate-example"></a><span data-ttu-id="28c28-136">滚动条 ControlTemplate 示例</span><span class="sxs-lookup"><span data-stu-id="28c28-136">ScrollBar ControlTemplate Example</span></span>  
 <span data-ttu-id="28c28-137">下面的示例演示如何定义<xref:System.Windows.Controls.ControlTemplate>为<xref:System.Windows.Controls.Primitives.ScrollBar>控件。</span><span class="sxs-lookup"><span data-stu-id="28c28-137">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.Primitives.ScrollBar> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#ScrollBar](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/scrollbar.xaml#scrollbar)]  
  
 <span data-ttu-id="28c28-138">上一示例使用了一个或多个以下资源。</span><span class="sxs-lookup"><span data-stu-id="28c28-138">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="28c28-139">有关完整示例，请参阅[使用 ControlTemplates 设置样式示例](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating)。</span><span class="sxs-lookup"><span data-stu-id="28c28-139">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="28c28-140">请参阅</span><span class="sxs-lookup"><span data-stu-id="28c28-140">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="28c28-141">控件样式和模板</span><span class="sxs-lookup"><span data-stu-id="28c28-141">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="28c28-142">控件自定义</span><span class="sxs-lookup"><span data-stu-id="28c28-142">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="28c28-143">样式设置和模板化</span><span class="sxs-lookup"><span data-stu-id="28c28-143">Styling and Templating</span></span>](styling-and-templating.md)
- [<span data-ttu-id="28c28-144">通过创建 ControlTemplate 自定义现有控件的外观</span><span class="sxs-lookup"><span data-stu-id="28c28-144">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](customizing-the-appearance-of-an-existing-control.md)
