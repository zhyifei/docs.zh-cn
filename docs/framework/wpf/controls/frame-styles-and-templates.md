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
ms.openlocfilehash: fbe49ae98e0fe281500ae37d53a3d47ff1d0b03a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54700258"
---
# <a name="frame-styles-and-templates"></a><span data-ttu-id="4b575-102">Frame 样式和模板</span><span class="sxs-lookup"><span data-stu-id="4b575-102">Frame Styles and Templates</span></span>
<span data-ttu-id="4b575-103">本主题介绍的样式和模板的<xref:System.Windows.Controls.Frame>控件。</span><span class="sxs-lookup"><span data-stu-id="4b575-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.Frame> control.</span></span> <span data-ttu-id="4b575-104">可以修改默认<xref:System.Windows.Controls.ControlTemplate>为控件提供唯一外观。</span><span class="sxs-lookup"><span data-stu-id="4b575-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="4b575-105">有关详细信息，请参阅[通过创建 ControlTemplate 自定义现有控件的外观](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)。</span><span class="sxs-lookup"><span data-stu-id="4b575-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="frame-parts"></a><span data-ttu-id="4b575-106">帧部件</span><span class="sxs-lookup"><span data-stu-id="4b575-106">Frame Parts</span></span>  
 <span data-ttu-id="4b575-107">下表列出了用于命名的部件<xref:System.Windows.Controls.Frame>控件。</span><span class="sxs-lookup"><span data-stu-id="4b575-107">The following table lists the named parts for the <xref:System.Windows.Controls.Frame> control.</span></span>  
  
|<span data-ttu-id="4b575-108">部件</span><span class="sxs-lookup"><span data-stu-id="4b575-108">Part</span></span>|<span data-ttu-id="4b575-109">类型</span><span class="sxs-lookup"><span data-stu-id="4b575-109">Type</span></span>|<span data-ttu-id="4b575-110">描述</span><span class="sxs-lookup"><span data-stu-id="4b575-110">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="4b575-111">PART_FrameCP</span><span class="sxs-lookup"><span data-stu-id="4b575-111">PART_FrameCP</span></span>|<xref:System.Windows.Controls.ContentPresenter>|<span data-ttu-id="4b575-112">内容区域。</span><span class="sxs-lookup"><span data-stu-id="4b575-112">The content area.</span></span>|  
  
## <a name="frame-states"></a><span data-ttu-id="4b575-113">帧状态</span><span class="sxs-lookup"><span data-stu-id="4b575-113">Frame States</span></span>  
 <span data-ttu-id="4b575-114">下表列出了的可视状态<xref:System.Windows.Controls.Frame>控件。</span><span class="sxs-lookup"><span data-stu-id="4b575-114">The following table lists the visual states for the <xref:System.Windows.Controls.Frame> control.</span></span>  
  
|<span data-ttu-id="4b575-115">VisualState 名称</span><span class="sxs-lookup"><span data-stu-id="4b575-115">VisualState Name</span></span>|<span data-ttu-id="4b575-116">VisualStateGroup 名称</span><span class="sxs-lookup"><span data-stu-id="4b575-116">VisualStateGroup Name</span></span>|<span data-ttu-id="4b575-117">描述</span><span class="sxs-lookup"><span data-stu-id="4b575-117">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="4b575-118">有效</span><span class="sxs-lookup"><span data-stu-id="4b575-118">Valid</span></span>|<span data-ttu-id="4b575-119">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="4b575-119">ValidationStates</span></span>|<span data-ttu-id="4b575-120">该控件使用<xref:System.Windows.Controls.Validation>类和<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>附加的属性是`false`。</span><span class="sxs-lookup"><span data-stu-id="4b575-120">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="4b575-121">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="4b575-121">InvalidFocused</span></span>|<span data-ttu-id="4b575-122">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="4b575-122">ValidationStates</span></span>|<span data-ttu-id="4b575-123"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>附加的属性是`true`已在控件有焦点。</span><span class="sxs-lookup"><span data-stu-id="4b575-123">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="4b575-124">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="4b575-124">InvalidUnfocused</span></span>|<span data-ttu-id="4b575-125">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="4b575-125">ValidationStates</span></span>|<span data-ttu-id="4b575-126"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>附加的属性是`true`具有该控件没有焦点。</span><span class="sxs-lookup"><span data-stu-id="4b575-126">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="frame-controltemplate-example"></a><span data-ttu-id="4b575-127">帧 ControlTemplate 示例</span><span class="sxs-lookup"><span data-stu-id="4b575-127">Frame ControlTemplate Example</span></span>  
 <span data-ttu-id="4b575-128">下面的示例演示如何定义<xref:System.Windows.Controls.ControlTemplate>为<xref:System.Windows.Controls.Frame>控件。</span><span class="sxs-lookup"><span data-stu-id="4b575-128">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.Frame> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Frame](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/frame.xaml#frame)]  
  
 <span data-ttu-id="4b575-129">上一示例使用了一个或多个以下资源。</span><span class="sxs-lookup"><span data-stu-id="4b575-129">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="4b575-130">有关完整示例，请参阅[使用 ControlTemplates 设置样式示例](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating)。</span><span class="sxs-lookup"><span data-stu-id="4b575-130">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4b575-131">请参阅</span><span class="sxs-lookup"><span data-stu-id="4b575-131">See also</span></span>
- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="4b575-132">控件样式和模板</span><span class="sxs-lookup"><span data-stu-id="4b575-132">Control Styles and Templates</span></span>](../../../../docs/framework/wpf/controls/control-styles-and-templates.md)
- [<span data-ttu-id="4b575-133">控件自定义</span><span class="sxs-lookup"><span data-stu-id="4b575-133">Control Customization</span></span>](../../../../docs/framework/wpf/controls/control-customization.md)
- [<span data-ttu-id="4b575-134">样式设置和模板化</span><span class="sxs-lookup"><span data-stu-id="4b575-134">Styling and Templating</span></span>](../../../../docs/framework/wpf/controls/styling-and-templating.md)
- [<span data-ttu-id="4b575-135">通过创建 ControlTemplate 自定义现有控件的外观</span><span class="sxs-lookup"><span data-stu-id="4b575-135">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)
