---
title: ToolTip 样式和模板
ms.date: 03/30/2017
helpviewer_keywords:
- parts [WPF], ToolTip
- styles [WPF], ToolTip
- states [WPF], ToolTip
- ToolTip [WPF], styles and templates
- ControlTemplate [WPF], ToolTip
- templates [WPF], ToolTip
ms.assetid: 405fe385-4de9-49ee-a448-d8f4d1f740dd
ms.openlocfilehash: 24def466509c12eb69307de139e83dd5a1ed5ce4
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59211616"
---
# <a name="tooltip-styles-and-templates"></a><span data-ttu-id="5fa34-102">ToolTip 样式和模板</span><span class="sxs-lookup"><span data-stu-id="5fa34-102">ToolTip Styles and Templates</span></span>
<span data-ttu-id="5fa34-103">本主题介绍的样式和模板的<xref:System.Windows.Controls.ToolTip>控件。</span><span class="sxs-lookup"><span data-stu-id="5fa34-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.ToolTip> control.</span></span> <span data-ttu-id="5fa34-104">可以修改默认<xref:System.Windows.Controls.ControlTemplate>为控件提供唯一外观。</span><span class="sxs-lookup"><span data-stu-id="5fa34-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="5fa34-105">有关详细信息，请参阅[通过创建 ControlTemplate 自定义现有控件的外观](customizing-the-appearance-of-an-existing-control.md)。</span><span class="sxs-lookup"><span data-stu-id="5fa34-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="tooltip-parts"></a><span data-ttu-id="5fa34-106">工具提示部分</span><span class="sxs-lookup"><span data-stu-id="5fa34-106">ToolTip Parts</span></span>  
 <span data-ttu-id="5fa34-107"><xref:System.Windows.Controls.ToolTip>控件没有任何命名的部件。</span><span class="sxs-lookup"><span data-stu-id="5fa34-107">The <xref:System.Windows.Controls.ToolTip> control does not have any named parts.</span></span>  
  
## <a name="tooltip-states"></a><span data-ttu-id="5fa34-108">工具提示的状态</span><span class="sxs-lookup"><span data-stu-id="5fa34-108">ToolTip States</span></span>  
 <span data-ttu-id="5fa34-109">下表列出了的可视状态<xref:System.Windows.Controls.ToolTip>控件。</span><span class="sxs-lookup"><span data-stu-id="5fa34-109">The following table lists the visual states for the <xref:System.Windows.Controls.ToolTip> control.</span></span>  
  
|<span data-ttu-id="5fa34-110">VisualState 名称</span><span class="sxs-lookup"><span data-stu-id="5fa34-110">VisualState Name</span></span>|<span data-ttu-id="5fa34-111">VisualStateGroup 名称</span><span class="sxs-lookup"><span data-stu-id="5fa34-111">VisualStateGroup Name</span></span>|<span data-ttu-id="5fa34-112">描述</span><span class="sxs-lookup"><span data-stu-id="5fa34-112">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="5fa34-113">Closed</span><span class="sxs-lookup"><span data-stu-id="5fa34-113">Closed</span></span>|<span data-ttu-id="5fa34-114">OpenStates</span><span class="sxs-lookup"><span data-stu-id="5fa34-114">OpenStates</span></span>|<span data-ttu-id="5fa34-115">默认状态。</span><span class="sxs-lookup"><span data-stu-id="5fa34-115">The default state.</span></span>|  
|<span data-ttu-id="5fa34-116">打开</span><span class="sxs-lookup"><span data-stu-id="5fa34-116">Open</span></span>|<span data-ttu-id="5fa34-117">OpenStates</span><span class="sxs-lookup"><span data-stu-id="5fa34-117">OpenStates</span></span>|<span data-ttu-id="5fa34-118"><xref:System.Windows.Controls.ToolTip>可见。</span><span class="sxs-lookup"><span data-stu-id="5fa34-118">The <xref:System.Windows.Controls.ToolTip> is visible.</span></span>|  
|<span data-ttu-id="5fa34-119">有效</span><span class="sxs-lookup"><span data-stu-id="5fa34-119">Valid</span></span>|<span data-ttu-id="5fa34-120">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="5fa34-120">ValidationStates</span></span>|<span data-ttu-id="5fa34-121">该控件使用<xref:System.Windows.Controls.Validation>类和<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>附加的属性是`false`。</span><span class="sxs-lookup"><span data-stu-id="5fa34-121">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="5fa34-122">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="5fa34-122">InvalidFocused</span></span>|<span data-ttu-id="5fa34-123">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="5fa34-123">ValidationStates</span></span>|<span data-ttu-id="5fa34-124"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>附加的属性是`true`已在控件有焦点。</span><span class="sxs-lookup"><span data-stu-id="5fa34-124">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="5fa34-125">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="5fa34-125">InvalidUnfocused</span></span>|<span data-ttu-id="5fa34-126">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="5fa34-126">ValidationStates</span></span>|<span data-ttu-id="5fa34-127"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>附加的属性是`true`具有该控件没有焦点。</span><span class="sxs-lookup"><span data-stu-id="5fa34-127">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="tooltip-controltemplate-example"></a><span data-ttu-id="5fa34-128">工具提示的 ControlTemplate 示例</span><span class="sxs-lookup"><span data-stu-id="5fa34-128">ToolTip ControlTemplate Example</span></span>  
 <span data-ttu-id="5fa34-129">下面的示例演示如何定义<xref:System.Windows.Controls.ControlTemplate>为<xref:System.Windows.Controls.ToolTip>控件。</span><span class="sxs-lookup"><span data-stu-id="5fa34-129">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.ToolTip> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#ToolTip](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/tooltip.xaml#tooltip)]  
  
 <span data-ttu-id="5fa34-130">上一示例使用了一个或多个以下资源。</span><span class="sxs-lookup"><span data-stu-id="5fa34-130">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="5fa34-131">有关完整示例，请参阅[使用 ControlTemplates 设置样式示例](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating)。</span><span class="sxs-lookup"><span data-stu-id="5fa34-131">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5fa34-132">请参阅</span><span class="sxs-lookup"><span data-stu-id="5fa34-132">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="5fa34-133">Control 样式和模板</span><span class="sxs-lookup"><span data-stu-id="5fa34-133">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="5fa34-134">控件自定义</span><span class="sxs-lookup"><span data-stu-id="5fa34-134">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="5fa34-135">样式设置和模板化</span><span class="sxs-lookup"><span data-stu-id="5fa34-135">Styling and Templating</span></span>](styling-and-templating.md)
- [<span data-ttu-id="5fa34-136">通过创建 ControlTemplate 自定义现有控件的外观</span><span class="sxs-lookup"><span data-stu-id="5fa34-136">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](customizing-the-appearance-of-an-existing-control.md)
