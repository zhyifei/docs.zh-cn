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
ms.openlocfilehash: 016556fb825ddf60af7dc572d6fda7323b9bb09d
ms.sourcegitcommit: 3eeea78f52ca771087a6736c23f74600cc662658
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/31/2019
ms.locfileid: "68671973"
---
# <a name="scrollbar-styles-and-templates"></a><span data-ttu-id="77bc4-102">ScrollBar 样式和模板</span><span class="sxs-lookup"><span data-stu-id="77bc4-102">ScrollBar Styles and Templates</span></span>
<span data-ttu-id="77bc4-103">本主题描述<xref:System.Windows.Controls.Primitives.ScrollBar>控件的样式和模板。</span><span class="sxs-lookup"><span data-stu-id="77bc4-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.Primitives.ScrollBar> control.</span></span> <span data-ttu-id="77bc4-104">您可以修改默认值<xref:System.Windows.Controls.ControlTemplate> , 为控件指定独特的外观。</span><span class="sxs-lookup"><span data-stu-id="77bc4-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="77bc4-105">有关详细信息，请参阅[通过创建 ControlTemplate 自定义现有控件的外观](customizing-the-appearance-of-an-existing-control.md)。</span><span class="sxs-lookup"><span data-stu-id="77bc4-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="scrollbar-parts"></a><span data-ttu-id="77bc4-106">滚动条部件</span><span class="sxs-lookup"><span data-stu-id="77bc4-106">ScrollBar Parts</span></span>  
 <span data-ttu-id="77bc4-107">下表列出了<xref:System.Windows.Controls.Primitives.ScrollBar>控件的已命名部件。</span><span class="sxs-lookup"><span data-stu-id="77bc4-107">The following table lists the named parts for the <xref:System.Windows.Controls.Primitives.ScrollBar> control.</span></span>  
  
|<span data-ttu-id="77bc4-108">部件</span><span class="sxs-lookup"><span data-stu-id="77bc4-108">Part</span></span>|<span data-ttu-id="77bc4-109">类型</span><span class="sxs-lookup"><span data-stu-id="77bc4-109">Type</span></span>|<span data-ttu-id="77bc4-110">描述</span><span class="sxs-lookup"><span data-stu-id="77bc4-110">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="77bc4-111">PART_Track</span><span class="sxs-lookup"><span data-stu-id="77bc4-111">PART_Track</span></span>|<xref:System.Windows.Controls.Primitives.Track>|<span data-ttu-id="77bc4-112">指示的位置<xref:System.Windows.Controls.Primitives.ScrollBar>的元素的容器。</span><span class="sxs-lookup"><span data-stu-id="77bc4-112">The container for the element that indicates the position of the <xref:System.Windows.Controls.Primitives.ScrollBar>.</span></span>|  
  
## <a name="scrollbar-states"></a><span data-ttu-id="77bc4-113">滚动条状态</span><span class="sxs-lookup"><span data-stu-id="77bc4-113">ScrollBar States</span></span>  
 <span data-ttu-id="77bc4-114">下表列出了<xref:System.Windows.Controls.Primitives.ScrollBar>控件的可视状态。</span><span class="sxs-lookup"><span data-stu-id="77bc4-114">The following table lists the visual states for the <xref:System.Windows.Controls.Primitives.ScrollBar> control.</span></span>  
  
|<span data-ttu-id="77bc4-115">VisualState 名称</span><span class="sxs-lookup"><span data-stu-id="77bc4-115">VisualState Name</span></span>|<span data-ttu-id="77bc4-116">VisualStateGroup 名称</span><span class="sxs-lookup"><span data-stu-id="77bc4-116">VisualStateGroup Name</span></span>|<span data-ttu-id="77bc4-117">描述</span><span class="sxs-lookup"><span data-stu-id="77bc4-117">Description</span></span>|  
|----------------------|---------------------------|-----------------|  
|<span data-ttu-id="77bc4-118">普通</span><span class="sxs-lookup"><span data-stu-id="77bc4-118">Normal</span></span>|<span data-ttu-id="77bc4-119">CommonStates</span><span class="sxs-lookup"><span data-stu-id="77bc4-119">CommonStates</span></span>|<span data-ttu-id="77bc4-120">默认状态。</span><span class="sxs-lookup"><span data-stu-id="77bc4-120">The default state.</span></span>|  
|<span data-ttu-id="77bc4-121">MouseOver</span><span class="sxs-lookup"><span data-stu-id="77bc4-121">MouseOver</span></span>|<span data-ttu-id="77bc4-122">CommonStates</span><span class="sxs-lookup"><span data-stu-id="77bc4-122">CommonStates</span></span>|<span data-ttu-id="77bc4-123">鼠标指针悬停在控件上。</span><span class="sxs-lookup"><span data-stu-id="77bc4-123">The mouse pointer is positioned over the control.</span></span>|  
|<span data-ttu-id="77bc4-124">已禁用</span><span class="sxs-lookup"><span data-stu-id="77bc4-124">Disabled</span></span>|<span data-ttu-id="77bc4-125">CommonStates</span><span class="sxs-lookup"><span data-stu-id="77bc4-125">CommonStates</span></span>|<span data-ttu-id="77bc4-126">已禁用控件。</span><span class="sxs-lookup"><span data-stu-id="77bc4-126">The control is disabled.</span></span>|  
|<span data-ttu-id="77bc4-127">有效</span><span class="sxs-lookup"><span data-stu-id="77bc4-127">Valid</span></span>|<span data-ttu-id="77bc4-128">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="77bc4-128">ValidationStates</span></span>|<span data-ttu-id="77bc4-129">控件使用<xref:System.Windows.Controls.Validation>类<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> , 附加属性为`false`。</span><span class="sxs-lookup"><span data-stu-id="77bc4-129">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="77bc4-130">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="77bc4-130">InvalidFocused</span></span>|<span data-ttu-id="77bc4-131">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="77bc4-131">ValidationStates</span></span>|<span data-ttu-id="77bc4-132">附加属性为`true` , 并且控件具有焦点。 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="77bc4-132">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` and the control has focus.</span></span>|  
|<span data-ttu-id="77bc4-133">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="77bc4-133">InvalidUnfocused</span></span>|<span data-ttu-id="77bc4-134">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="77bc4-134">ValidationStates</span></span>|<span data-ttu-id="77bc4-135">附加<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>的属性为`true` , 并且该控件没有焦点。</span><span class="sxs-lookup"><span data-stu-id="77bc4-135">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` and the control does not have focus.</span></span>|  
  
## <a name="scrollbar-controltemplate-example"></a><span data-ttu-id="77bc4-136">滚动条 System.windows.controls.controltemplate> 示例</span><span class="sxs-lookup"><span data-stu-id="77bc4-136">ScrollBar ControlTemplate Example</span></span>  
 <span data-ttu-id="77bc4-137">下面的示例演示如何为<xref:System.Windows.Controls.ControlTemplate> <xref:System.Windows.Controls.Primitives.ScrollBar>控件定义。</span><span class="sxs-lookup"><span data-stu-id="77bc4-137">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.Primitives.ScrollBar> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#ScrollBar](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/scrollbar.xaml#scrollbar)]  
  
 <span data-ttu-id="77bc4-138">上一示例使用了一个或多个以下资源。</span><span class="sxs-lookup"><span data-stu-id="77bc4-138">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="77bc4-139">有关完整示例，请参阅[使用 ControlTemplates 设置样式示例](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating)。</span><span class="sxs-lookup"><span data-stu-id="77bc4-139">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="77bc4-140">请参阅</span><span class="sxs-lookup"><span data-stu-id="77bc4-140">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="77bc4-141">控件样式和模板</span><span class="sxs-lookup"><span data-stu-id="77bc4-141">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="77bc4-142">控件自定义</span><span class="sxs-lookup"><span data-stu-id="77bc4-142">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="77bc4-143">样式设置和模板化</span><span class="sxs-lookup"><span data-stu-id="77bc4-143">Styling and Templating</span></span>](styling-and-templating.md)
- [<span data-ttu-id="77bc4-144">通过创建 ControlTemplate 自定义现有控件的外观</span><span class="sxs-lookup"><span data-stu-id="77bc4-144">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](customizing-the-appearance-of-an-existing-control.md)
