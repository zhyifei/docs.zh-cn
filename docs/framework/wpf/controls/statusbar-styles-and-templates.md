---
title: StatusBar 样式和模板
ms.date: 03/30/2017
helpviewer_keywords:
- ControlTemplate [WPF], StatusBar
- styles [WPF], StatusBar
- templates [WPF], StatusBar
- states [WPF], StatusBar
- parts [WPF], StatusBar
- StatusBar [WPF], styles and templates
ms.assetid: 9f5e1c25-81eb-4756-a0ac-d9e1fbe33ee2
ms.openlocfilehash: 843c9003edbe94115719a63a968eda3833515a85
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2019
ms.locfileid: "74283373"
---
# <a name="statusbar-styles-and-templates"></a><span data-ttu-id="c21c5-102">StatusBar 样式和模板</span><span class="sxs-lookup"><span data-stu-id="c21c5-102">StatusBar Styles and Templates</span></span>
<span data-ttu-id="c21c5-103">本主题介绍 <xref:System.Windows.Controls.Primitives.StatusBar> 控件的样式和模板。</span><span class="sxs-lookup"><span data-stu-id="c21c5-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.Primitives.StatusBar> control.</span></span> <span data-ttu-id="c21c5-104">您可以修改默认 <xref:System.Windows.Controls.ControlTemplate> 以使控件具有独特的外观。</span><span class="sxs-lookup"><span data-stu-id="c21c5-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="c21c5-105">有关详细信息，请参阅为[控件创建模板](../../../desktop-wpf/themes/how-to-create-apply-template.md)。</span><span class="sxs-lookup"><span data-stu-id="c21c5-105">For more information, see [Create a template for a control](../../../desktop-wpf/themes/how-to-create-apply-template.md).</span></span>  
  
## <a name="statusbar-parts"></a><span data-ttu-id="c21c5-106">状态栏部分</span><span class="sxs-lookup"><span data-stu-id="c21c5-106">StatusBar Parts</span></span>  
 <span data-ttu-id="c21c5-107"><xref:System.Windows.Controls.Primitives.StatusBar> 控件没有任何命名部分。</span><span class="sxs-lookup"><span data-stu-id="c21c5-107">The <xref:System.Windows.Controls.Primitives.StatusBar> control does not have any named parts.</span></span>  
  
## <a name="statusbar-states"></a><span data-ttu-id="c21c5-108">状态栏状态</span><span class="sxs-lookup"><span data-stu-id="c21c5-108">StatusBar States</span></span>  
 <span data-ttu-id="c21c5-109">下表列出了 <xref:System.Windows.Controls.Primitives.StatusBar> 控件的可视状态。</span><span class="sxs-lookup"><span data-stu-id="c21c5-109">The following table lists the visual states for the <xref:System.Windows.Controls.Primitives.StatusBar> control.</span></span>  
  
|<span data-ttu-id="c21c5-110">VisualState 名称</span><span class="sxs-lookup"><span data-stu-id="c21c5-110">VisualState Name</span></span>|<span data-ttu-id="c21c5-111">VisualStateGroup 名称</span><span class="sxs-lookup"><span data-stu-id="c21c5-111">VisualStateGroup Name</span></span>|<span data-ttu-id="c21c5-112">说明</span><span class="sxs-lookup"><span data-stu-id="c21c5-112">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="c21c5-113">有效</span><span class="sxs-lookup"><span data-stu-id="c21c5-113">Valid</span></span>|<span data-ttu-id="c21c5-114">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="c21c5-114">ValidationStates</span></span>|<span data-ttu-id="c21c5-115">控件使用 <xref:System.Windows.Controls.Validation> 类，并且 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 附加属性是 `false`。</span><span class="sxs-lookup"><span data-stu-id="c21c5-115">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="c21c5-116">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="c21c5-116">InvalidFocused</span></span>|<span data-ttu-id="c21c5-117">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="c21c5-117">ValidationStates</span></span>|<span data-ttu-id="c21c5-118"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 附加属性是控件具有焦点 `true`。</span><span class="sxs-lookup"><span data-stu-id="c21c5-118">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="c21c5-119">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="c21c5-119">InvalidUnfocused</span></span>|<span data-ttu-id="c21c5-120">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="c21c5-120">ValidationStates</span></span>|<span data-ttu-id="c21c5-121"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 附加属性是 `true` 控件没有焦点。</span><span class="sxs-lookup"><span data-stu-id="c21c5-121">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="statusbaritem-parts"></a><span data-ttu-id="c21c5-122">StatusBarItem 部件</span><span class="sxs-lookup"><span data-stu-id="c21c5-122">StatusBarItem Parts</span></span>  
 <span data-ttu-id="c21c5-123"><xref:System.Windows.Controls.Primitives.StatusBarItem> 控件没有任何命名部分。</span><span class="sxs-lookup"><span data-stu-id="c21c5-123">The <xref:System.Windows.Controls.Primitives.StatusBarItem> control does not have any named parts.</span></span>  
  
## <a name="statusbar-states"></a><span data-ttu-id="c21c5-124">状态栏状态</span><span class="sxs-lookup"><span data-stu-id="c21c5-124">StatusBar States</span></span>  
 <span data-ttu-id="c21c5-125">下表列出了 <xref:System.Windows.Controls.Primitives.StatusBarItem> 控件的可视状态。</span><span class="sxs-lookup"><span data-stu-id="c21c5-125">The following table lists the visual states for the <xref:System.Windows.Controls.Primitives.StatusBarItem> control.</span></span>  
  
|<span data-ttu-id="c21c5-126">VisualState 名称</span><span class="sxs-lookup"><span data-stu-id="c21c5-126">VisualState Name</span></span>|<span data-ttu-id="c21c5-127">VisualStateGroup 名称</span><span class="sxs-lookup"><span data-stu-id="c21c5-127">VisualStateGroup Name</span></span>|<span data-ttu-id="c21c5-128">说明</span><span class="sxs-lookup"><span data-stu-id="c21c5-128">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="c21c5-129">有效</span><span class="sxs-lookup"><span data-stu-id="c21c5-129">Valid</span></span>|<span data-ttu-id="c21c5-130">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="c21c5-130">ValidationStates</span></span>|<span data-ttu-id="c21c5-131">控件使用 <xref:System.Windows.Controls.Validation> 类，并且 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 附加属性是 `false`。</span><span class="sxs-lookup"><span data-stu-id="c21c5-131">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="c21c5-132">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="c21c5-132">InvalidFocused</span></span>|<span data-ttu-id="c21c5-133">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="c21c5-133">ValidationStates</span></span>|<span data-ttu-id="c21c5-134"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 附加属性是控件具有焦点 `true`。</span><span class="sxs-lookup"><span data-stu-id="c21c5-134">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="c21c5-135">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="c21c5-135">InvalidUnfocused</span></span>|<span data-ttu-id="c21c5-136">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="c21c5-136">ValidationStates</span></span>|<span data-ttu-id="c21c5-137"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 附加属性是 `true` 控件没有焦点。</span><span class="sxs-lookup"><span data-stu-id="c21c5-137">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="statusbar-controltemplate-example"></a><span data-ttu-id="c21c5-138">状态栏 System.windows.controls.controltemplate> 示例</span><span class="sxs-lookup"><span data-stu-id="c21c5-138">StatusBar ControlTemplate Example</span></span>  
 <span data-ttu-id="c21c5-139">下面的示例演示如何为 <xref:System.Windows.Controls.Primitives.StatusBar> 控件定义 <xref:System.Windows.Controls.ControlTemplate>。</span><span class="sxs-lookup"><span data-stu-id="c21c5-139">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.Primitives.StatusBar> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#StatusBar](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/statusbar.xaml#statusbar)]  
  
 <span data-ttu-id="c21c5-140"><xref:System.Windows.Controls.ControlTemplate> 使用以下一个或多个资源。</span><span class="sxs-lookup"><span data-stu-id="c21c5-140">The <xref:System.Windows.Controls.ControlTemplate> uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="c21c5-141">有关完整示例，请参阅[使用 ControlTemplates 设置样式示例](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating)。</span><span class="sxs-lookup"><span data-stu-id="c21c5-141">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c21c5-142">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c21c5-142">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="c21c5-143">控件样式和模板</span><span class="sxs-lookup"><span data-stu-id="c21c5-143">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="c21c5-144">控件自定义</span><span class="sxs-lookup"><span data-stu-id="c21c5-144">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="c21c5-145">样式设置和模板化</span><span class="sxs-lookup"><span data-stu-id="c21c5-145">Styling and Templating</span></span>](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [<span data-ttu-id="c21c5-146">为控件创建模板</span><span class="sxs-lookup"><span data-stu-id="c21c5-146">Create a template for a control</span></span>](../../../desktop-wpf/themes/how-to-create-apply-template.md)
