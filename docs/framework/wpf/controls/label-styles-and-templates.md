---
title: Label 样式和模板
ms.date: 03/30/2017
helpviewer_keywords:
- templates [WPF], Label
- parts [WPF], Label
- ControlTemplate [WPF], Label
- styles [WPF], Label
- Label [WPF], styles and templates
- states [WPF], Label
ms.assetid: c1d5359a-8e4a-4925-ab3e-e92bf6694859
ms.openlocfilehash: d2bb348fc9c0348fd8093452e022df7ab4e0b3f2
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61696244"
---
# <a name="label-styles-and-templates"></a><span data-ttu-id="9f8f2-102">Label 样式和模板</span><span class="sxs-lookup"><span data-stu-id="9f8f2-102">Label Styles and Templates</span></span>
<span data-ttu-id="9f8f2-103">本主题介绍的样式和模板的<xref:System.Windows.Controls.Label>控件。</span><span class="sxs-lookup"><span data-stu-id="9f8f2-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.Label> control.</span></span> <span data-ttu-id="9f8f2-104">可以修改默认<xref:System.Windows.Controls.ControlTemplate>为控件提供唯一外观。</span><span class="sxs-lookup"><span data-stu-id="9f8f2-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="9f8f2-105">有关详细信息，请参阅[通过创建 ControlTemplate 自定义现有控件的外观](customizing-the-appearance-of-an-existing-control.md)。</span><span class="sxs-lookup"><span data-stu-id="9f8f2-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="label-parts"></a><span data-ttu-id="9f8f2-106">标签部分</span><span class="sxs-lookup"><span data-stu-id="9f8f2-106">Label Parts</span></span>  
 <span data-ttu-id="9f8f2-107"><xref:System.Windows.Controls.Label>控件没有任何命名的部件。</span><span class="sxs-lookup"><span data-stu-id="9f8f2-107">The <xref:System.Windows.Controls.Label> control does not have any named parts.</span></span>  
  
## <a name="label-states"></a><span data-ttu-id="9f8f2-108">标签状态</span><span class="sxs-lookup"><span data-stu-id="9f8f2-108">Label States</span></span>  
 <span data-ttu-id="9f8f2-109">下表列出了的可视状态<xref:System.Windows.Controls.Label>控件。</span><span class="sxs-lookup"><span data-stu-id="9f8f2-109">The following table lists the visual states for the <xref:System.Windows.Controls.Label> control.</span></span>  
  
|<span data-ttu-id="9f8f2-110">VisualState 名称</span><span class="sxs-lookup"><span data-stu-id="9f8f2-110">VisualState Name</span></span>|<span data-ttu-id="9f8f2-111">VisualStateGroup 名称</span><span class="sxs-lookup"><span data-stu-id="9f8f2-111">VisualStateGroup Name</span></span>|<span data-ttu-id="9f8f2-112">描述</span><span class="sxs-lookup"><span data-stu-id="9f8f2-112">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="9f8f2-113">有效</span><span class="sxs-lookup"><span data-stu-id="9f8f2-113">Valid</span></span>|<span data-ttu-id="9f8f2-114">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="9f8f2-114">ValidationStates</span></span>|<span data-ttu-id="9f8f2-115">该控件使用<xref:System.Windows.Controls.Validation>类和<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>附加的属性是`false`。</span><span class="sxs-lookup"><span data-stu-id="9f8f2-115">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="9f8f2-116">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="9f8f2-116">InvalidFocused</span></span>|<span data-ttu-id="9f8f2-117">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="9f8f2-117">ValidationStates</span></span>|<span data-ttu-id="9f8f2-118"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>附加的属性是`true`已在控件有焦点。</span><span class="sxs-lookup"><span data-stu-id="9f8f2-118">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="9f8f2-119">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="9f8f2-119">InvalidUnfocused</span></span>|<span data-ttu-id="9f8f2-120">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="9f8f2-120">ValidationStates</span></span>|<span data-ttu-id="9f8f2-121"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>附加的属性是`true`具有该控件没有焦点。</span><span class="sxs-lookup"><span data-stu-id="9f8f2-121">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="label-controltemplate-example"></a><span data-ttu-id="9f8f2-122">标签 ControlTemplate 示例</span><span class="sxs-lookup"><span data-stu-id="9f8f2-122">Label ControlTemplate Example</span></span>  
 <span data-ttu-id="9f8f2-123">下面的示例演示如何定义<xref:System.Windows.Controls.ControlTemplate>为<xref:System.Windows.Controls.Label>控件。</span><span class="sxs-lookup"><span data-stu-id="9f8f2-123">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.Label> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Label](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/label.xaml#label)]  
  
 <span data-ttu-id="9f8f2-124"><xref:System.Windows.Controls.ControlTemplate>使用一个或多个以下资源。</span><span class="sxs-lookup"><span data-stu-id="9f8f2-124">The <xref:System.Windows.Controls.ControlTemplate> uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="9f8f2-125">有关完整示例，请参阅[使用 ControlTemplates 设置样式示例](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating)。</span><span class="sxs-lookup"><span data-stu-id="9f8f2-125">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9f8f2-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="9f8f2-126">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="9f8f2-127">控件样式和模板</span><span class="sxs-lookup"><span data-stu-id="9f8f2-127">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="9f8f2-128">控件自定义</span><span class="sxs-lookup"><span data-stu-id="9f8f2-128">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="9f8f2-129">样式设置和模板化</span><span class="sxs-lookup"><span data-stu-id="9f8f2-129">Styling and Templating</span></span>](styling-and-templating.md)
- [<span data-ttu-id="9f8f2-130">通过创建 ControlTemplate 自定义现有控件的外观</span><span class="sxs-lookup"><span data-stu-id="9f8f2-130">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](customizing-the-appearance-of-an-existing-control.md)
