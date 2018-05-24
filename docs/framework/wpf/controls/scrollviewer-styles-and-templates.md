---
title: ScrollViewer 样式和模板
ms.date: 03/30/2017
helpviewer_keywords:
- parts [WPF], ScrollViewer
- states [WPF], ScrollViewer
- styles [WPF], ScrollViewer
- templates [WPF], ScrollViewer
- ControlTemplate [WPF], ScrollViewer
- ScrollViewer [WPF], styles and templates
ms.assetid: dffdd822-ae69-4946-abaf-710860cd65b2
ms.openlocfilehash: 5ad3738972ae9b33764d3b710077f6d4a0526a13
ms.sourcegitcommit: 43924acbdbb3981d103e11049bbe460457d42073
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/23/2018
---
# <a name="scrollviewer-styles-and-templates"></a><span data-ttu-id="91b2e-102">ScrollViewer 样式和模板</span><span class="sxs-lookup"><span data-stu-id="91b2e-102">ScrollViewer Styles and Templates</span></span>
<span data-ttu-id="91b2e-103">本主题介绍的样式和模板的<xref:System.Windows.Controls.ScrollViewer>控件。</span><span class="sxs-lookup"><span data-stu-id="91b2e-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.ScrollViewer> control.</span></span> <span data-ttu-id="91b2e-104">你可以修改默认<xref:System.Windows.Controls.ControlTemplate>提供独特外观的控件。</span><span class="sxs-lookup"><span data-stu-id="91b2e-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="91b2e-105">有关详细信息，请参阅[通过创建 ControlTemplate 自定义现有控件的外观](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)。</span><span class="sxs-lookup"><span data-stu-id="91b2e-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="scrollviewer-parts"></a><span data-ttu-id="91b2e-106">ScrollViewer 部件</span><span class="sxs-lookup"><span data-stu-id="91b2e-106">ScrollViewer Parts</span></span>  
 <span data-ttu-id="91b2e-107">下表列出的命名的部件<xref:System.Windows.Controls.ScrollViewer>控件。</span><span class="sxs-lookup"><span data-stu-id="91b2e-107">The following table lists the named parts for the <xref:System.Windows.Controls.ScrollViewer> control.</span></span>  
  
|<span data-ttu-id="91b2e-108">部件</span><span class="sxs-lookup"><span data-stu-id="91b2e-108">Part</span></span>|<span data-ttu-id="91b2e-109">类型</span><span class="sxs-lookup"><span data-stu-id="91b2e-109">Type</span></span>|<span data-ttu-id="91b2e-110">描述</span><span class="sxs-lookup"><span data-stu-id="91b2e-110">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="91b2e-111">PART_ScrollContentPresenter</span><span class="sxs-lookup"><span data-stu-id="91b2e-111">PART_ScrollContentPresenter</span></span>|<xref:System.Windows.Controls.ScrollContentPresenter>|<span data-ttu-id="91b2e-112">中的内容的占位符<xref:System.Windows.Controls.ScrollViewer>。</span><span class="sxs-lookup"><span data-stu-id="91b2e-112">The placeholder for content in the <xref:System.Windows.Controls.ScrollViewer>.</span></span>|  
|<span data-ttu-id="91b2e-113">PART_HorizontalScrollBar</span><span class="sxs-lookup"><span data-stu-id="91b2e-113">PART_HorizontalScrollBar</span></span>|<xref:System.Windows.Controls.Primitives.ScrollBar>|<span data-ttu-id="91b2e-114"><xref:System.Windows.Controls.Primitives.ScrollBar>用于水平滚动内容。</span><span class="sxs-lookup"><span data-stu-id="91b2e-114">The <xref:System.Windows.Controls.Primitives.ScrollBar> used to scroll the content horizontally.</span></span>|  
|<span data-ttu-id="91b2e-115">PART_VerticalScrollBar</span><span class="sxs-lookup"><span data-stu-id="91b2e-115">PART_VerticalScrollBar</span></span>|<xref:System.Windows.Controls.Primitives.ScrollBar>|<span data-ttu-id="91b2e-116"><xref:System.Windows.Controls.Primitives.ScrollBar>使用垂直滚动内容。</span><span class="sxs-lookup"><span data-stu-id="91b2e-116">The <xref:System.Windows.Controls.Primitives.ScrollBar> used to scroll the content vertically.</span></span>|  
  
## <a name="scrollviewer-states"></a><span data-ttu-id="91b2e-117">ScrollViewer 状态</span><span class="sxs-lookup"><span data-stu-id="91b2e-117">ScrollViewer States</span></span>  
 <span data-ttu-id="91b2e-118">下表列出的可视状态<xref:System.Windows.Controls.ScrollViewer>控件。</span><span class="sxs-lookup"><span data-stu-id="91b2e-118">The following table lists the visual states for the <xref:System.Windows.Controls.ScrollViewer> control.</span></span>  
  
|<span data-ttu-id="91b2e-119">VisualState 名称</span><span class="sxs-lookup"><span data-stu-id="91b2e-119">VisualState Name</span></span>|<span data-ttu-id="91b2e-120">VisualStateGroup 名称</span><span class="sxs-lookup"><span data-stu-id="91b2e-120">VisualStateGroup Name</span></span>|<span data-ttu-id="91b2e-121">描述</span><span class="sxs-lookup"><span data-stu-id="91b2e-121">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="91b2e-122">有效</span><span class="sxs-lookup"><span data-stu-id="91b2e-122">Valid</span></span>|<span data-ttu-id="91b2e-123">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="91b2e-123">ValidationStates</span></span>|<span data-ttu-id="91b2e-124">该控件使用<xref:System.Windows.Controls.Validation>类和<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>附加的属性`false`。</span><span class="sxs-lookup"><span data-stu-id="91b2e-124">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="91b2e-125">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="91b2e-125">InvalidFocused</span></span>|<span data-ttu-id="91b2e-126">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="91b2e-126">ValidationStates</span></span>|<span data-ttu-id="91b2e-127"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>附加的属性`true`已在控件有焦点。</span><span class="sxs-lookup"><span data-stu-id="91b2e-127">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="91b2e-128">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="91b2e-128">InvalidUnfocused</span></span>|<span data-ttu-id="91b2e-129">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="91b2e-129">ValidationStates</span></span>|<span data-ttu-id="91b2e-130"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>附加的属性`true`具有该控件没有焦点。</span><span class="sxs-lookup"><span data-stu-id="91b2e-130">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="scrollviewer-controltemplate-example"></a><span data-ttu-id="91b2e-131">ScrollViewer ControlTemplate 示例</span><span class="sxs-lookup"><span data-stu-id="91b2e-131">ScrollViewer ControlTemplate Example</span></span>  
 <span data-ttu-id="91b2e-132">下面的示例演示如何定义<xref:System.Windows.Controls.ControlTemplate>为<xref:System.Windows.Controls.ScrollViewer>控件。</span><span class="sxs-lookup"><span data-stu-id="91b2e-132">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.ScrollViewer> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#ScrollViewer](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/scrollviewer.xaml#scrollviewer)]  
  
 <span data-ttu-id="91b2e-133">上一示例使用了一个或多个以下资源。</span><span class="sxs-lookup"><span data-stu-id="91b2e-133">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="91b2e-134">有关完整示例，请参阅[使用 ControlTemplates 设置样式示例](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating)。</span><span class="sxs-lookup"><span data-stu-id="91b2e-134">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="91b2e-135">请参阅</span><span class="sxs-lookup"><span data-stu-id="91b2e-135">See Also</span></span>  
 <xref:System.Windows.FrameworkElement.Style%2A>  
 <xref:System.Windows.Controls.ControlTemplate>  
 [<span data-ttu-id="91b2e-136">控件样式和模板</span><span class="sxs-lookup"><span data-stu-id="91b2e-136">Control Styles and Templates</span></span>](../../../../docs/framework/wpf/controls/control-styles-and-templates.md)  
 [<span data-ttu-id="91b2e-137">控件自定义</span><span class="sxs-lookup"><span data-stu-id="91b2e-137">Control Customization</span></span>](../../../../docs/framework/wpf/controls/control-customization.md)  
 [<span data-ttu-id="91b2e-138">样式设置和模板化</span><span class="sxs-lookup"><span data-stu-id="91b2e-138">Styling and Templating</span></span>](../../../../docs/framework/wpf/controls/styling-and-templating.md)  
 [<span data-ttu-id="91b2e-139">通过创建 ControlTemplate 自定义现有控件的外观</span><span class="sxs-lookup"><span data-stu-id="91b2e-139">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)
