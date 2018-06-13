---
title: GroupBox 样式和模板
ms.date: 03/30/2017
helpviewer_keywords:
- ControlTemplate [WPF], GroupBox
- parts [WPF], GroupBox
- GroupBox [WPF], styles and templates
- states [WPF], GroupBox
- styles [WPF], GroupBox
- templates [WPF], GroupBox
ms.assetid: 33df7037-0a1b-476f-b9d0-41566a777699
ms.openlocfilehash: 539bf5b0ef8772ea469123442d152726d0948be9
ms.sourcegitcommit: 43924acbdbb3981d103e11049bbe460457d42073
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/23/2018
ms.locfileid: "34457782"
---
# <a name="groupbox-styles-and-templates"></a><span data-ttu-id="c389e-102">GroupBox 样式和模板</span><span class="sxs-lookup"><span data-stu-id="c389e-102">GroupBox Styles and Templates</span></span>
<a name="introduction"></a> <span data-ttu-id="c389e-103">本主题介绍的样式和模板的<xref:System.Windows.Controls.GroupBox>控件。</span><span class="sxs-lookup"><span data-stu-id="c389e-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.GroupBox> control.</span></span> <span data-ttu-id="c389e-104">你可以修改默认<xref:System.Windows.Controls.ControlTemplate>提供独特外观的控件。</span><span class="sxs-lookup"><span data-stu-id="c389e-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="c389e-105">有关详细信息，请参阅[通过创建 ControlTemplate 自定义现有控件的外观](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)。</span><span class="sxs-lookup"><span data-stu-id="c389e-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
<a name="groupbox_parts"></a>   
## <a name="groupbox-parts"></a><span data-ttu-id="c389e-106">GroupBox 部件</span><span class="sxs-lookup"><span data-stu-id="c389e-106">GroupBox Parts</span></span>  
 <span data-ttu-id="c389e-107"><xref:System.Windows.Controls.GroupBox>控件不具有任何已命名的部件。</span><span class="sxs-lookup"><span data-stu-id="c389e-107">The <xref:System.Windows.Controls.GroupBox> control does not have any named parts.</span></span>  
  
<a name="groupbox_states"></a>   
## <a name="groupbox-states"></a><span data-ttu-id="c389e-108">GroupBox 状态</span><span class="sxs-lookup"><span data-stu-id="c389e-108">GroupBox States</span></span>  
 <span data-ttu-id="c389e-109">下表列出的可视状态<xref:System.Windows.Controls.GroupBox>控件。</span><span class="sxs-lookup"><span data-stu-id="c389e-109">The following table lists the visual states for the <xref:System.Windows.Controls.GroupBox> control.</span></span>  
  
|<span data-ttu-id="c389e-110">VisualState 名称</span><span class="sxs-lookup"><span data-stu-id="c389e-110">VisualState Name</span></span>|<span data-ttu-id="c389e-111">VisualStateGroup 名称</span><span class="sxs-lookup"><span data-stu-id="c389e-111">VisualStateGroup Name</span></span>|<span data-ttu-id="c389e-112">描述</span><span class="sxs-lookup"><span data-stu-id="c389e-112">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="c389e-113">有效</span><span class="sxs-lookup"><span data-stu-id="c389e-113">Valid</span></span>|<span data-ttu-id="c389e-114">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="c389e-114">ValidationStates</span></span>|<span data-ttu-id="c389e-115">该控件使用<xref:System.Windows.Controls.Validation>类和<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>附加的属性`false`。</span><span class="sxs-lookup"><span data-stu-id="c389e-115">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="c389e-116">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="c389e-116">InvalidFocused</span></span>|<span data-ttu-id="c389e-117">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="c389e-117">ValidationStates</span></span>|<span data-ttu-id="c389e-118"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>附加的属性`true`已在控件有焦点。</span><span class="sxs-lookup"><span data-stu-id="c389e-118">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="c389e-119">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="c389e-119">InvalidUnfocused</span></span>|<span data-ttu-id="c389e-120">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="c389e-120">ValidationStates</span></span>|<span data-ttu-id="c389e-121"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>附加的属性`true`具有该控件没有焦点。</span><span class="sxs-lookup"><span data-stu-id="c389e-121">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
<a name="groupbox_controltemplate_example"></a>   
## <a name="groupbox-controltemplate-example"></a><span data-ttu-id="c389e-122">GroupBox ControlTemplate 示例</span><span class="sxs-lookup"><span data-stu-id="c389e-122">GroupBox ControlTemplate Example</span></span>  
 <span data-ttu-id="c389e-123">下面的示例演示如何定义<xref:System.Windows.Controls.ControlTemplate>为<xref:System.Windows.Controls.GroupBox>控件。</span><span class="sxs-lookup"><span data-stu-id="c389e-123">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.GroupBox> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#GroupBox](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/groupbox.xaml#groupbox)]  
  
 <span data-ttu-id="c389e-124"><xref:System.Windows.Controls.ControlTemplate>使用一个或多个以下资源。</span><span class="sxs-lookup"><span data-stu-id="c389e-124">The <xref:System.Windows.Controls.ControlTemplate> uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="c389e-125">有关完整示例，请参阅[使用 ControlTemplates 设置样式示例](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating)。</span><span class="sxs-lookup"><span data-stu-id="c389e-125">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c389e-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="c389e-126">See Also</span></span>  
 <xref:System.Windows.FrameworkElement.Style%2A>  
 <xref:System.Windows.Controls.ControlTemplate>  
 [<span data-ttu-id="c389e-127">控件样式和模板</span><span class="sxs-lookup"><span data-stu-id="c389e-127">Control Styles and Templates</span></span>](../../../../docs/framework/wpf/controls/control-styles-and-templates.md)  
 [<span data-ttu-id="c389e-128">控件自定义</span><span class="sxs-lookup"><span data-stu-id="c389e-128">Control Customization</span></span>](../../../../docs/framework/wpf/controls/control-customization.md)  
 [<span data-ttu-id="c389e-129">样式设置和模板化</span><span class="sxs-lookup"><span data-stu-id="c389e-129">Styling and Templating</span></span>](../../../../docs/framework/wpf/controls/styling-and-templating.md)  
 [<span data-ttu-id="c389e-130">通过创建 ControlTemplate 自定义现有控件的外观</span><span class="sxs-lookup"><span data-stu-id="c389e-130">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)
