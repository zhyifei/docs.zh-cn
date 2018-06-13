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
ms.openlocfilehash: 926fc3373bb40eb12462dcead278d458cefad7cf
ms.sourcegitcommit: 43924acbdbb3981d103e11049bbe460457d42073
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/23/2018
ms.locfileid: "34457550"
---
# <a name="scrollbar-styles-and-templates"></a><span data-ttu-id="23b03-102">ScrollBar 样式和模板</span><span class="sxs-lookup"><span data-stu-id="23b03-102">ScrollBar Styles and Templates</span></span>
<span data-ttu-id="23b03-103">本主题介绍的样式和模板的<xref:System.Windows.Controls.Primitives.ScrollBar>控件。</span><span class="sxs-lookup"><span data-stu-id="23b03-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.Primitives.ScrollBar> control.</span></span> <span data-ttu-id="23b03-104">你可以修改默认<xref:System.Windows.Controls.ControlTemplate>提供独特外观的控件。</span><span class="sxs-lookup"><span data-stu-id="23b03-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="23b03-105">有关详细信息，请参阅[通过创建 ControlTemplate 自定义现有控件的外观](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)。</span><span class="sxs-lookup"><span data-stu-id="23b03-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="scrollbar-parts"></a><span data-ttu-id="23b03-106">滚动条部件</span><span class="sxs-lookup"><span data-stu-id="23b03-106">ScrollBar Parts</span></span>  
 <span data-ttu-id="23b03-107">下表列出的命名的部件<xref:System.Windows.Controls.Primitives.ScrollBar>控件。</span><span class="sxs-lookup"><span data-stu-id="23b03-107">The following table lists the named parts for the <xref:System.Windows.Controls.Primitives.ScrollBar> control.</span></span>  
  
|<span data-ttu-id="23b03-108">部件</span><span class="sxs-lookup"><span data-stu-id="23b03-108">Part</span></span>|<span data-ttu-id="23b03-109">类型</span><span class="sxs-lookup"><span data-stu-id="23b03-109">Type</span></span>|<span data-ttu-id="23b03-110">描述</span><span class="sxs-lookup"><span data-stu-id="23b03-110">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="23b03-111">PART_Track</span><span class="sxs-lookup"><span data-stu-id="23b03-111">PART_Track</span></span>|<xref:System.Windows.Controls.Primitives.Track>|<span data-ttu-id="23b03-112">指示的位置的元素的容器<xref:System.Windows.Controls.Primitives.ScrollBar>。</span><span class="sxs-lookup"><span data-stu-id="23b03-112">The container for the element that indicates the position of the <xref:System.Windows.Controls.Primitives.ScrollBar>.</span></span>|  
  
## <a name="scrollbar-states"></a><span data-ttu-id="23b03-113">滚动条状态</span><span class="sxs-lookup"><span data-stu-id="23b03-113">ScrollBar States</span></span>  
 <span data-ttu-id="23b03-114">下表列出的可视状态<xref:System.Windows.Controls.Primitives.ScrollBar>控件。</span><span class="sxs-lookup"><span data-stu-id="23b03-114">The following table lists the visual states for the <xref:System.Windows.Controls.Primitives.ScrollBar> control.</span></span>  
  
|<span data-ttu-id="23b03-115">VisualState 名称</span><span class="sxs-lookup"><span data-stu-id="23b03-115">VisualState Name</span></span>|<span data-ttu-id="23b03-116">VisualStateGroup 名称</span><span class="sxs-lookup"><span data-stu-id="23b03-116">VisualStateGroup Name</span></span>|<span data-ttu-id="23b03-117">描述</span><span class="sxs-lookup"><span data-stu-id="23b03-117">Description</span></span>|  
|----------------------|---------------------------|-----------------|  
|<span data-ttu-id="23b03-118">普通</span><span class="sxs-lookup"><span data-stu-id="23b03-118">Normal</span></span>|<span data-ttu-id="23b03-119">CommonStates</span><span class="sxs-lookup"><span data-stu-id="23b03-119">CommonStates</span></span>|<span data-ttu-id="23b03-120">默认状态。</span><span class="sxs-lookup"><span data-stu-id="23b03-120">The default state.</span></span>|  
|<span data-ttu-id="23b03-121">MouseOver</span><span class="sxs-lookup"><span data-stu-id="23b03-121">MouseOver</span></span>|<span data-ttu-id="23b03-122">CommonStates</span><span class="sxs-lookup"><span data-stu-id="23b03-122">CommonStates</span></span>|<span data-ttu-id="23b03-123">鼠标指针悬停在控件上。</span><span class="sxs-lookup"><span data-stu-id="23b03-123">The mouse pointer is positioned over the control.</span></span>|  
|<span data-ttu-id="23b03-124">已禁用</span><span class="sxs-lookup"><span data-stu-id="23b03-124">Disabled</span></span>|<span data-ttu-id="23b03-125">CommonStates</span><span class="sxs-lookup"><span data-stu-id="23b03-125">CommonStates</span></span>|<span data-ttu-id="23b03-126">已禁用控件。</span><span class="sxs-lookup"><span data-stu-id="23b03-126">The control is disabled.</span></span>|  
|<span data-ttu-id="23b03-127">有效</span><span class="sxs-lookup"><span data-stu-id="23b03-127">Valid</span></span>|<span data-ttu-id="23b03-128">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="23b03-128">ValidationStates</span></span>|<span data-ttu-id="23b03-129">该控件使用<xref:System.Windows.Controls.Validation>类和<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>附加的属性`false`。</span><span class="sxs-lookup"><span data-stu-id="23b03-129">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="23b03-130">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="23b03-130">InvalidFocused</span></span>|<span data-ttu-id="23b03-131">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="23b03-131">ValidationStates</span></span>|<span data-ttu-id="23b03-132"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>附加的属性`true`已在控件有焦点。</span><span class="sxs-lookup"><span data-stu-id="23b03-132">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="23b03-133">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="23b03-133">InvalidUnfocused</span></span>|<span data-ttu-id="23b03-134">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="23b03-134">ValidationStates</span></span>|<span data-ttu-id="23b03-135"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>附加的属性`true`具有该控件没有焦点。</span><span class="sxs-lookup"><span data-stu-id="23b03-135">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="scrollbar-controltemplate-example"></a><span data-ttu-id="23b03-136">滚动条 ControlTemplate 示例</span><span class="sxs-lookup"><span data-stu-id="23b03-136">ScrollBar ControlTemplate Example</span></span>  
 <span data-ttu-id="23b03-137">下面的示例演示如何定义<xref:System.Windows.Controls.ControlTemplate>为<xref:System.Windows.Controls.Primitives.ScrollBar>控件。</span><span class="sxs-lookup"><span data-stu-id="23b03-137">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.Primitives.ScrollBar> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#ScrollBar](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/scrollbar.xaml#scrollbar)]  
  
 <span data-ttu-id="23b03-138">上一示例使用了一个或多个以下资源。</span><span class="sxs-lookup"><span data-stu-id="23b03-138">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="23b03-139">有关完整示例，请参阅[使用 ControlTemplates 设置样式示例](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating)。</span><span class="sxs-lookup"><span data-stu-id="23b03-139">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="23b03-140">请参阅</span><span class="sxs-lookup"><span data-stu-id="23b03-140">See Also</span></span>  
 <xref:System.Windows.FrameworkElement.Style%2A>  
 <xref:System.Windows.Controls.ControlTemplate>  
 [<span data-ttu-id="23b03-141">控件样式和模板</span><span class="sxs-lookup"><span data-stu-id="23b03-141">Control Styles and Templates</span></span>](../../../../docs/framework/wpf/controls/control-styles-and-templates.md)  
 [<span data-ttu-id="23b03-142">控件自定义</span><span class="sxs-lookup"><span data-stu-id="23b03-142">Control Customization</span></span>](../../../../docs/framework/wpf/controls/control-customization.md)  
 [<span data-ttu-id="23b03-143">样式设置和模板化</span><span class="sxs-lookup"><span data-stu-id="23b03-143">Styling and Templating</span></span>](../../../../docs/framework/wpf/controls/styling-and-templating.md)  
 [<span data-ttu-id="23b03-144">通过创建 ControlTemplate 自定义现有控件的外观</span><span class="sxs-lookup"><span data-stu-id="23b03-144">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)
