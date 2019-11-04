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
ms.openlocfilehash: 626d0b4d49d653f820d1506f0aa09f06d26352c2
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2019
ms.locfileid: "73458647"
---
# <a name="tooltip-styles-and-templates"></a><span data-ttu-id="9f687-102">ToolTip 样式和模板</span><span class="sxs-lookup"><span data-stu-id="9f687-102">ToolTip Styles and Templates</span></span>
<span data-ttu-id="9f687-103">本主题介绍 <xref:System.Windows.Controls.ToolTip> 控件的样式和模板。</span><span class="sxs-lookup"><span data-stu-id="9f687-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.ToolTip> control.</span></span> <span data-ttu-id="9f687-104">您可以修改默认 <xref:System.Windows.Controls.ControlTemplate> 以使控件具有独特的外观。</span><span class="sxs-lookup"><span data-stu-id="9f687-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="9f687-105">有关详细信息，请参阅[通过创建 ControlTemplate 自定义现有控件的外观](customizing-the-appearance-of-an-existing-control.md)。</span><span class="sxs-lookup"><span data-stu-id="9f687-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="tooltip-parts"></a><span data-ttu-id="9f687-106">ToolTip 部分</span><span class="sxs-lookup"><span data-stu-id="9f687-106">ToolTip Parts</span></span>  
 <span data-ttu-id="9f687-107"><xref:System.Windows.Controls.ToolTip> 控件没有任何命名部分。</span><span class="sxs-lookup"><span data-stu-id="9f687-107">The <xref:System.Windows.Controls.ToolTip> control does not have any named parts.</span></span>  
  
## <a name="tooltip-states"></a><span data-ttu-id="9f687-108">工具提示状态</span><span class="sxs-lookup"><span data-stu-id="9f687-108">ToolTip States</span></span>  
 <span data-ttu-id="9f687-109">下表列出了 <xref:System.Windows.Controls.ToolTip> 控件的可视状态。</span><span class="sxs-lookup"><span data-stu-id="9f687-109">The following table lists the visual states for the <xref:System.Windows.Controls.ToolTip> control.</span></span>  
  
|<span data-ttu-id="9f687-110">VisualState 名称</span><span class="sxs-lookup"><span data-stu-id="9f687-110">VisualState Name</span></span>|<span data-ttu-id="9f687-111">VisualStateGroup 名称</span><span class="sxs-lookup"><span data-stu-id="9f687-111">VisualStateGroup Name</span></span>|<span data-ttu-id="9f687-112">描述</span><span class="sxs-lookup"><span data-stu-id="9f687-112">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="9f687-113">Closed</span><span class="sxs-lookup"><span data-stu-id="9f687-113">Closed</span></span>|<span data-ttu-id="9f687-114">OpenStates</span><span class="sxs-lookup"><span data-stu-id="9f687-114">OpenStates</span></span>|<span data-ttu-id="9f687-115">默认状态。</span><span class="sxs-lookup"><span data-stu-id="9f687-115">The default state.</span></span>|  
|<span data-ttu-id="9f687-116">打开</span><span class="sxs-lookup"><span data-stu-id="9f687-116">Open</span></span>|<span data-ttu-id="9f687-117">OpenStates</span><span class="sxs-lookup"><span data-stu-id="9f687-117">OpenStates</span></span>|<span data-ttu-id="9f687-118"><xref:System.Windows.Controls.ToolTip> 可见。</span><span class="sxs-lookup"><span data-stu-id="9f687-118">The <xref:System.Windows.Controls.ToolTip> is visible.</span></span>|  
|<span data-ttu-id="9f687-119">有效</span><span class="sxs-lookup"><span data-stu-id="9f687-119">Valid</span></span>|<span data-ttu-id="9f687-120">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="9f687-120">ValidationStates</span></span>|<span data-ttu-id="9f687-121">控件使用 <xref:System.Windows.Controls.Validation> 类，并且 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 附加属性是 `false`。</span><span class="sxs-lookup"><span data-stu-id="9f687-121">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="9f687-122">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="9f687-122">InvalidFocused</span></span>|<span data-ttu-id="9f687-123">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="9f687-123">ValidationStates</span></span>|<span data-ttu-id="9f687-124"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 附加属性是控件具有焦点 `true`。</span><span class="sxs-lookup"><span data-stu-id="9f687-124">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="9f687-125">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="9f687-125">InvalidUnfocused</span></span>|<span data-ttu-id="9f687-126">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="9f687-126">ValidationStates</span></span>|<span data-ttu-id="9f687-127"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 附加属性是 `true` 控件没有焦点。</span><span class="sxs-lookup"><span data-stu-id="9f687-127">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="tooltip-controltemplate-example"></a><span data-ttu-id="9f687-128">ToolTip System.windows.controls.controltemplate> 示例</span><span class="sxs-lookup"><span data-stu-id="9f687-128">ToolTip ControlTemplate Example</span></span>  
 <span data-ttu-id="9f687-129">下面的示例演示如何为 <xref:System.Windows.Controls.ToolTip> 控件定义 <xref:System.Windows.Controls.ControlTemplate>。</span><span class="sxs-lookup"><span data-stu-id="9f687-129">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.ToolTip> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#ToolTip](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/tooltip.xaml#tooltip)]  
  
 <span data-ttu-id="9f687-130">上一示例使用了一个或多个以下资源。</span><span class="sxs-lookup"><span data-stu-id="9f687-130">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="9f687-131">有关完整示例，请参阅[使用 ControlTemplates 设置样式示例](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating)。</span><span class="sxs-lookup"><span data-stu-id="9f687-131">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9f687-132">请参阅</span><span class="sxs-lookup"><span data-stu-id="9f687-132">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="9f687-133">控件样式和模板</span><span class="sxs-lookup"><span data-stu-id="9f687-133">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="9f687-134">控件自定义</span><span class="sxs-lookup"><span data-stu-id="9f687-134">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="9f687-135">样式设置和模板化</span><span class="sxs-lookup"><span data-stu-id="9f687-135">Styling and Templating</span></span>](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [<span data-ttu-id="9f687-136">通过创建 ControlTemplate 自定义现有控件的外观</span><span class="sxs-lookup"><span data-stu-id="9f687-136">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](customizing-the-appearance-of-an-existing-control.md)
