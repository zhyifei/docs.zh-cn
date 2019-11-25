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
ms.openlocfilehash: 6551701e86dd6abcd42f143f146c7bdadfeabbcf
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2019
ms.locfileid: "74283456"
---
# <a name="progressbar-styles-and-templates"></a><span data-ttu-id="45772-102">ProgressBar 样式和模板</span><span class="sxs-lookup"><span data-stu-id="45772-102">ProgressBar Styles and Templates</span></span>
<span data-ttu-id="45772-103">本主题介绍 <xref:System.Windows.Controls.ProgressBar> 控件的样式和模板。</span><span class="sxs-lookup"><span data-stu-id="45772-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.ProgressBar> control.</span></span> <span data-ttu-id="45772-104">您可以修改默认 <xref:System.Windows.Controls.ControlTemplate> 以使控件具有独特的外观。</span><span class="sxs-lookup"><span data-stu-id="45772-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="45772-105">有关详细信息，请参阅为[控件创建模板](../../../desktop-wpf/themes/how-to-create-apply-template.md)。</span><span class="sxs-lookup"><span data-stu-id="45772-105">For more information, see [Create a template for a control](../../../desktop-wpf/themes/how-to-create-apply-template.md).</span></span>  
  
## <a name="progressbar-parts"></a><span data-ttu-id="45772-106">ProgressBar 部件</span><span class="sxs-lookup"><span data-stu-id="45772-106">ProgressBar Parts</span></span>  
 <span data-ttu-id="45772-107">下表列出了 <xref:System.Windows.Controls.ProgressBar> 控件的已命名部分。</span><span class="sxs-lookup"><span data-stu-id="45772-107">The following table lists the named parts for the <xref:System.Windows.Controls.ProgressBar> control.</span></span>  
  
|<span data-ttu-id="45772-108">部件</span><span class="sxs-lookup"><span data-stu-id="45772-108">Part</span></span>|<span data-ttu-id="45772-109">Type</span><span class="sxs-lookup"><span data-stu-id="45772-109">Type</span></span>|<span data-ttu-id="45772-110">描述</span><span class="sxs-lookup"><span data-stu-id="45772-110">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="45772-111">PART_Indicator</span><span class="sxs-lookup"><span data-stu-id="45772-111">PART_Indicator</span></span>|<xref:System.Windows.FrameworkElement>|<span data-ttu-id="45772-112">指示进度的对象。</span><span class="sxs-lookup"><span data-stu-id="45772-112">The object that indicates progress.</span></span>|  
|<span data-ttu-id="45772-113">PART_Track</span><span class="sxs-lookup"><span data-stu-id="45772-113">PART_Track</span></span>|<xref:System.Windows.FrameworkElement>|<span data-ttu-id="45772-114">定义进度指示器的路径的对象。</span><span class="sxs-lookup"><span data-stu-id="45772-114">The object that defines the path of the progress indicator.</span></span>|  
|<span data-ttu-id="45772-115">PART_GlowRect</span><span class="sxs-lookup"><span data-stu-id="45772-115">PART_GlowRect</span></span>|<xref:System.Windows.FrameworkElement>|<span data-ttu-id="45772-116">Embellishes 进度栏的对象。</span><span class="sxs-lookup"><span data-stu-id="45772-116">An object that embellishes the progress bar.</span></span>|  
  
## <a name="progressbar-states"></a><span data-ttu-id="45772-117">ProgressBar 状态</span><span class="sxs-lookup"><span data-stu-id="45772-117">ProgressBar States</span></span>  
 <span data-ttu-id="45772-118">下表列出了 <xref:System.Windows.Controls.ProgressBar> 控件的可视状态。</span><span class="sxs-lookup"><span data-stu-id="45772-118">The following table lists the visual states for the <xref:System.Windows.Controls.ProgressBar> control.</span></span>  
  
|<span data-ttu-id="45772-119">VisualState 名称</span><span class="sxs-lookup"><span data-stu-id="45772-119">VisualState Name</span></span>|<span data-ttu-id="45772-120">VisualStateGroup 名称</span><span class="sxs-lookup"><span data-stu-id="45772-120">VisualStateGroup Name</span></span>|<span data-ttu-id="45772-121">描述</span><span class="sxs-lookup"><span data-stu-id="45772-121">Description</span></span>|  
|----------------------|---------------------------|-----------------|  
|<span data-ttu-id="45772-122">确定性</span><span class="sxs-lookup"><span data-stu-id="45772-122">Determinate</span></span>|<span data-ttu-id="45772-123">CommonStates</span><span class="sxs-lookup"><span data-stu-id="45772-123">CommonStates</span></span>|<span data-ttu-id="45772-124"><xref:System.Windows.Controls.ProgressBar> 基于 <xref:System.Windows.Controls.Primitives.RangeBase.Value%2A> 属性报告进度。</span><span class="sxs-lookup"><span data-stu-id="45772-124"><xref:System.Windows.Controls.ProgressBar> reports progress based on the <xref:System.Windows.Controls.Primitives.RangeBase.Value%2A> property.</span></span>|  
|<span data-ttu-id="45772-125">尚</span><span class="sxs-lookup"><span data-stu-id="45772-125">Indeterminate</span></span>|<span data-ttu-id="45772-126">CommonStates</span><span class="sxs-lookup"><span data-stu-id="45772-126">CommonStates</span></span>|<span data-ttu-id="45772-127"><xref:System.Windows.Controls.ProgressBar> 使用重复模式报告一般进度。</span><span class="sxs-lookup"><span data-stu-id="45772-127"><xref:System.Windows.Controls.ProgressBar> reports generic progress with a repeating pattern.</span></span>|  
|<span data-ttu-id="45772-128">有效</span><span class="sxs-lookup"><span data-stu-id="45772-128">Valid</span></span>|<span data-ttu-id="45772-129">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="45772-129">ValidationStates</span></span>|<span data-ttu-id="45772-130">控件使用 <xref:System.Windows.Controls.Validation> 类，并且 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 附加属性是 `false`。</span><span class="sxs-lookup"><span data-stu-id="45772-130">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="45772-131">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="45772-131">InvalidFocused</span></span>|<span data-ttu-id="45772-132">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="45772-132">ValidationStates</span></span>|<span data-ttu-id="45772-133"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 附加属性是控件具有焦点 `true`。</span><span class="sxs-lookup"><span data-stu-id="45772-133">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="45772-134">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="45772-134">InvalidUnfocused</span></span>|<span data-ttu-id="45772-135">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="45772-135">ValidationStates</span></span>|<span data-ttu-id="45772-136"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 附加属性是 `true` 控件没有焦点。</span><span class="sxs-lookup"><span data-stu-id="45772-136">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="progressbar-controltemplate-example"></a><span data-ttu-id="45772-137">ProgressBar System.windows.controls.controltemplate> 示例</span><span class="sxs-lookup"><span data-stu-id="45772-137">ProgressBar ControlTemplate Example</span></span>  
 <span data-ttu-id="45772-138">下面的示例演示如何为 <xref:System.Windows.Controls.ProgressBar> 控件定义 <xref:System.Windows.Controls.ControlTemplate>。</span><span class="sxs-lookup"><span data-stu-id="45772-138">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.ProgressBar> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#ProgressBar](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/progressbar.xaml#progressbar)]  
  
 <span data-ttu-id="45772-139">上一示例使用了一个或多个以下资源。</span><span class="sxs-lookup"><span data-stu-id="45772-139">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="45772-140">有关完整示例，请参阅[使用 ControlTemplates 设置样式示例](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating)。</span><span class="sxs-lookup"><span data-stu-id="45772-140">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="45772-141">另请参阅</span><span class="sxs-lookup"><span data-stu-id="45772-141">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="45772-142">控件样式和模板</span><span class="sxs-lookup"><span data-stu-id="45772-142">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="45772-143">控件自定义</span><span class="sxs-lookup"><span data-stu-id="45772-143">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="45772-144">样式设置和模板化</span><span class="sxs-lookup"><span data-stu-id="45772-144">Styling and Templating</span></span>](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [<span data-ttu-id="45772-145">为控件创建模板</span><span class="sxs-lookup"><span data-stu-id="45772-145">Create a template for a control</span></span>](../../../desktop-wpf/themes/how-to-create-apply-template.md)
