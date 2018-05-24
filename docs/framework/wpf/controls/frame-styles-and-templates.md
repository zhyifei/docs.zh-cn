---
title: Frame 样式和模板
ms.date: 03/30/2017
helpviewer_keywords:
- parts [WPF], Frame
- templates [WPF], Frame
- ControlTemplate [WPF], Frame
- Frame [WPF], styles and templates
- states [WPF], Frame
- styles [WPF], Frame
ms.assetid: a01c32e2-c951-46a0-a82f-2614ca241f0b
ms.openlocfilehash: 78bbeb915e17bcd59480b921efa1b6a51fa67762
ms.sourcegitcommit: 43924acbdbb3981d103e11049bbe460457d42073
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/23/2018
---
# <a name="frame-styles-and-templates"></a><span data-ttu-id="33403-102">Frame 样式和模板</span><span class="sxs-lookup"><span data-stu-id="33403-102">Frame Styles and Templates</span></span>
<span data-ttu-id="33403-103">本主题介绍的样式和模板的<xref:System.Windows.Controls.Frame>控件。</span><span class="sxs-lookup"><span data-stu-id="33403-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.Frame> control.</span></span> <span data-ttu-id="33403-104">你可以修改默认<xref:System.Windows.Controls.ControlTemplate>提供独特外观的控件。</span><span class="sxs-lookup"><span data-stu-id="33403-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="33403-105">有关详细信息，请参阅[通过创建 ControlTemplate 自定义现有控件的外观](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)。</span><span class="sxs-lookup"><span data-stu-id="33403-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="frame-parts"></a><span data-ttu-id="33403-106">框架部件</span><span class="sxs-lookup"><span data-stu-id="33403-106">Frame Parts</span></span>  
 <span data-ttu-id="33403-107">下表列出的命名的部件<xref:System.Windows.Controls.Frame>控件。</span><span class="sxs-lookup"><span data-stu-id="33403-107">The following table lists the named parts for the <xref:System.Windows.Controls.Frame> control.</span></span>  
  
|<span data-ttu-id="33403-108">部件</span><span class="sxs-lookup"><span data-stu-id="33403-108">Part</span></span>|<span data-ttu-id="33403-109">类型</span><span class="sxs-lookup"><span data-stu-id="33403-109">Type</span></span>|<span data-ttu-id="33403-110">描述</span><span class="sxs-lookup"><span data-stu-id="33403-110">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="33403-111">PART_FrameCP</span><span class="sxs-lookup"><span data-stu-id="33403-111">PART_FrameCP</span></span>|<xref:System.Windows.Controls.ContentPresenter>|<span data-ttu-id="33403-112">内容区域中。</span><span class="sxs-lookup"><span data-stu-id="33403-112">The content area.</span></span>|  
  
## <a name="frame-states"></a><span data-ttu-id="33403-113">帧状态</span><span class="sxs-lookup"><span data-stu-id="33403-113">Frame States</span></span>  
 <span data-ttu-id="33403-114">下表列出的可视状态<xref:System.Windows.Controls.Frame>控件。</span><span class="sxs-lookup"><span data-stu-id="33403-114">The following table lists the visual states for the <xref:System.Windows.Controls.Frame> control.</span></span>  
  
|<span data-ttu-id="33403-115">VisualState 名称</span><span class="sxs-lookup"><span data-stu-id="33403-115">VisualState Name</span></span>|<span data-ttu-id="33403-116">VisualStateGroup 名称</span><span class="sxs-lookup"><span data-stu-id="33403-116">VisualStateGroup Name</span></span>|<span data-ttu-id="33403-117">描述</span><span class="sxs-lookup"><span data-stu-id="33403-117">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="33403-118">有效</span><span class="sxs-lookup"><span data-stu-id="33403-118">Valid</span></span>|<span data-ttu-id="33403-119">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="33403-119">ValidationStates</span></span>|<span data-ttu-id="33403-120">该控件使用<xref:System.Windows.Controls.Validation>类和<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>附加的属性`false`。</span><span class="sxs-lookup"><span data-stu-id="33403-120">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="33403-121">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="33403-121">InvalidFocused</span></span>|<span data-ttu-id="33403-122">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="33403-122">ValidationStates</span></span>|<span data-ttu-id="33403-123"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>附加的属性`true`已在控件有焦点。</span><span class="sxs-lookup"><span data-stu-id="33403-123">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="33403-124">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="33403-124">InvalidUnfocused</span></span>|<span data-ttu-id="33403-125">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="33403-125">ValidationStates</span></span>|<span data-ttu-id="33403-126"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>附加的属性`true`具有该控件没有焦点。</span><span class="sxs-lookup"><span data-stu-id="33403-126">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="frame-controltemplate-example"></a><span data-ttu-id="33403-127">帧 ControlTemplate 示例</span><span class="sxs-lookup"><span data-stu-id="33403-127">Frame ControlTemplate Example</span></span>  
 <span data-ttu-id="33403-128">下面的示例演示如何定义<xref:System.Windows.Controls.ControlTemplate>为<xref:System.Windows.Controls.Frame>控件。</span><span class="sxs-lookup"><span data-stu-id="33403-128">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.Frame> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Frame](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/frame.xaml#frame)]  
  
 <span data-ttu-id="33403-129">上一示例使用了一个或多个以下资源。</span><span class="sxs-lookup"><span data-stu-id="33403-129">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="33403-130">有关完整示例，请参阅[使用 ControlTemplates 设置样式示例](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating)。</span><span class="sxs-lookup"><span data-stu-id="33403-130">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="33403-131">请参阅</span><span class="sxs-lookup"><span data-stu-id="33403-131">See Also</span></span>  
 <xref:System.Windows.FrameworkElement.Style%2A>  
 <xref:System.Windows.Controls.ControlTemplate>  
 [<span data-ttu-id="33403-132">控件样式和模板</span><span class="sxs-lookup"><span data-stu-id="33403-132">Control Styles and Templates</span></span>](../../../../docs/framework/wpf/controls/control-styles-and-templates.md)  
 [<span data-ttu-id="33403-133">控件自定义</span><span class="sxs-lookup"><span data-stu-id="33403-133">Control Customization</span></span>](../../../../docs/framework/wpf/controls/control-customization.md)  
 [<span data-ttu-id="33403-134">样式设置和模板化</span><span class="sxs-lookup"><span data-stu-id="33403-134">Styling and Templating</span></span>](../../../../docs/framework/wpf/controls/styling-and-templating.md)  
 [<span data-ttu-id="33403-135">通过创建 ControlTemplate 自定义现有控件的外观</span><span class="sxs-lookup"><span data-stu-id="33403-135">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)
