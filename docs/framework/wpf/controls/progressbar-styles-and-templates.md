---
title: ProgressBar 样式和模板
ms.date: 03/30/2017
helpviewer_keywords:
- parts [WPF], ProgressBar
- ProgressBar [WPF], styles and templates
- styles [WPF], ProgressBar
- ControlTemplate [WPF], ProgressBar
- templates [WPF], ProgressBar
- states [WPF], ProgressBar
ms.assetid: 935aa600-16e6-4947-a905-37a189a583dd
ms.openlocfilehash: f948cf2b4f4cd2a4cb73b0cd5fc754240c850b83
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61770521"
---
# <a name="progressbar-styles-and-templates"></a><span data-ttu-id="f9220-102">ProgressBar 样式和模板</span><span class="sxs-lookup"><span data-stu-id="f9220-102">ProgressBar Styles and Templates</span></span>
<span data-ttu-id="f9220-103">本主题介绍的样式和模板的<xref:System.Windows.Controls.ProgressBar>控件。</span><span class="sxs-lookup"><span data-stu-id="f9220-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.ProgressBar> control.</span></span> <span data-ttu-id="f9220-104">可以修改默认<xref:System.Windows.Controls.ControlTemplate>为控件提供唯一外观。</span><span class="sxs-lookup"><span data-stu-id="f9220-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="f9220-105">有关详细信息，请参阅[通过创建 ControlTemplate 自定义现有控件的外观](customizing-the-appearance-of-an-existing-control.md)。</span><span class="sxs-lookup"><span data-stu-id="f9220-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="progressbar-parts"></a><span data-ttu-id="f9220-106">ProgressBar 部件</span><span class="sxs-lookup"><span data-stu-id="f9220-106">ProgressBar Parts</span></span>  
 <span data-ttu-id="f9220-107">下表列出了用于命名的部件<xref:System.Windows.Controls.ProgressBar>控件。</span><span class="sxs-lookup"><span data-stu-id="f9220-107">The following table lists the named parts for the <xref:System.Windows.Controls.ProgressBar> control.</span></span>  
  
|<span data-ttu-id="f9220-108">部件</span><span class="sxs-lookup"><span data-stu-id="f9220-108">Part</span></span>|<span data-ttu-id="f9220-109">类型</span><span class="sxs-lookup"><span data-stu-id="f9220-109">Type</span></span>|<span data-ttu-id="f9220-110">描述</span><span class="sxs-lookup"><span data-stu-id="f9220-110">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="f9220-111">PART_Indicator</span><span class="sxs-lookup"><span data-stu-id="f9220-111">PART_Indicator</span></span>|<xref:System.Windows.FrameworkElement>|<span data-ttu-id="f9220-112">一个对象，它指示进度。</span><span class="sxs-lookup"><span data-stu-id="f9220-112">The object that indicates progress.</span></span>|  
|<span data-ttu-id="f9220-113">PART_Track</span><span class="sxs-lookup"><span data-stu-id="f9220-113">PART_Track</span></span>|<xref:System.Windows.FrameworkElement>|<span data-ttu-id="f9220-114">定义进度指示器的路径的对象。</span><span class="sxs-lookup"><span data-stu-id="f9220-114">The object that defines the path of the progress indicator.</span></span>|  
|<span data-ttu-id="f9220-115">PART_GlowRect</span><span class="sxs-lookup"><span data-stu-id="f9220-115">PART_GlowRect</span></span>|<xref:System.Windows.FrameworkElement>|<span data-ttu-id="f9220-116">一个对象，修饰进度栏。</span><span class="sxs-lookup"><span data-stu-id="f9220-116">An object that embellishes the progress bar.</span></span>|  
  
## <a name="progressbar-states"></a><span data-ttu-id="f9220-117">进度栏状态</span><span class="sxs-lookup"><span data-stu-id="f9220-117">ProgressBar States</span></span>  
 <span data-ttu-id="f9220-118">下表列出了的可视状态<xref:System.Windows.Controls.ProgressBar>控件。</span><span class="sxs-lookup"><span data-stu-id="f9220-118">The following table lists the visual states for the <xref:System.Windows.Controls.ProgressBar> control.</span></span>  
  
|<span data-ttu-id="f9220-119">VisualState 名称</span><span class="sxs-lookup"><span data-stu-id="f9220-119">VisualState Name</span></span>|<span data-ttu-id="f9220-120">VisualStateGroup 名称</span><span class="sxs-lookup"><span data-stu-id="f9220-120">VisualStateGroup Name</span></span>|<span data-ttu-id="f9220-121">描述</span><span class="sxs-lookup"><span data-stu-id="f9220-121">Description</span></span>|  
|----------------------|---------------------------|-----------------|  
|<span data-ttu-id="f9220-122">确定</span><span class="sxs-lookup"><span data-stu-id="f9220-122">Determinate</span></span>|<span data-ttu-id="f9220-123">CommonStates</span><span class="sxs-lookup"><span data-stu-id="f9220-123">CommonStates</span></span>|<span data-ttu-id="f9220-124"><xref:System.Windows.Controls.ProgressBar> 报告进度基于<xref:System.Windows.Controls.Primitives.RangeBase.Value%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="f9220-124"><xref:System.Windows.Controls.ProgressBar> reports progress based on the <xref:System.Windows.Controls.Primitives.RangeBase.Value%2A> property.</span></span>|  
|<span data-ttu-id="f9220-125">不确定</span><span class="sxs-lookup"><span data-stu-id="f9220-125">Indeterminate</span></span>|<span data-ttu-id="f9220-126">CommonStates</span><span class="sxs-lookup"><span data-stu-id="f9220-126">CommonStates</span></span>|<span data-ttu-id="f9220-127"><xref:System.Windows.Controls.ProgressBar> 报告由重复图案泛型进度。</span><span class="sxs-lookup"><span data-stu-id="f9220-127"><xref:System.Windows.Controls.ProgressBar> reports generic progress with a repeating pattern.</span></span>|  
|<span data-ttu-id="f9220-128">有效</span><span class="sxs-lookup"><span data-stu-id="f9220-128">Valid</span></span>|<span data-ttu-id="f9220-129">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="f9220-129">ValidationStates</span></span>|<span data-ttu-id="f9220-130">该控件使用<xref:System.Windows.Controls.Validation>类和<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>附加的属性是`false`。</span><span class="sxs-lookup"><span data-stu-id="f9220-130">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="f9220-131">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="f9220-131">InvalidFocused</span></span>|<span data-ttu-id="f9220-132">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="f9220-132">ValidationStates</span></span>|<span data-ttu-id="f9220-133"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>附加的属性是`true`已在控件有焦点。</span><span class="sxs-lookup"><span data-stu-id="f9220-133">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="f9220-134">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="f9220-134">InvalidUnfocused</span></span>|<span data-ttu-id="f9220-135">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="f9220-135">ValidationStates</span></span>|<span data-ttu-id="f9220-136"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>附加的属性是`true`具有该控件没有焦点。</span><span class="sxs-lookup"><span data-stu-id="f9220-136">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="progressbar-controltemplate-example"></a><span data-ttu-id="f9220-137">ProgressBar ControlTemplate 示例</span><span class="sxs-lookup"><span data-stu-id="f9220-137">ProgressBar ControlTemplate Example</span></span>  
 <span data-ttu-id="f9220-138">下面的示例演示如何定义<xref:System.Windows.Controls.ControlTemplate>为<xref:System.Windows.Controls.ProgressBar>控件。</span><span class="sxs-lookup"><span data-stu-id="f9220-138">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.ProgressBar> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#ProgressBar](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/progressbar.xaml#progressbar)]  
  
 <span data-ttu-id="f9220-139">上一示例使用了一个或多个以下资源。</span><span class="sxs-lookup"><span data-stu-id="f9220-139">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="f9220-140">有关完整示例，请参阅[使用 ControlTemplates 设置样式示例](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating)。</span><span class="sxs-lookup"><span data-stu-id="f9220-140">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f9220-141">请参阅</span><span class="sxs-lookup"><span data-stu-id="f9220-141">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="f9220-142">控件样式和模板</span><span class="sxs-lookup"><span data-stu-id="f9220-142">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="f9220-143">控件自定义</span><span class="sxs-lookup"><span data-stu-id="f9220-143">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="f9220-144">样式设置和模板化</span><span class="sxs-lookup"><span data-stu-id="f9220-144">Styling and Templating</span></span>](styling-and-templating.md)
- [<span data-ttu-id="f9220-145">通过创建 ControlTemplate 自定义现有控件的外观</span><span class="sxs-lookup"><span data-stu-id="f9220-145">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](customizing-the-appearance-of-an-existing-control.md)
