---
title: "Label 样式和模板"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- templates [WPF], Label
- parts [WPF], Label
- ControlTemplate [WPF], Label
- styles [WPF], Label
- Label [WPF], styles and templates
- states [WPF], Label
ms.assetid: c1d5359a-8e4a-4925-ab3e-e92bf6694859
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 6189470b5a0a01911bfe71ddfa003f72f64356c7
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="label-styles-and-templates"></a><span data-ttu-id="02e48-102">Label 样式和模板</span><span class="sxs-lookup"><span data-stu-id="02e48-102">Label Styles and Templates</span></span>
<span data-ttu-id="02e48-103">本主题介绍的样式和模板的<xref:System.Windows.Controls.Label>控件。</span><span class="sxs-lookup"><span data-stu-id="02e48-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.Label> control.</span></span> <span data-ttu-id="02e48-104">你可以修改默认<xref:System.Windows.Controls.ControlTemplate>提供独特外观的控件。</span><span class="sxs-lookup"><span data-stu-id="02e48-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="02e48-105">有关详细信息，请参阅[通过创建 ControlTemplate 自定义现有控件的外观](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)。</span><span class="sxs-lookup"><span data-stu-id="02e48-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="label-parts"></a><span data-ttu-id="02e48-106">标签部分</span><span class="sxs-lookup"><span data-stu-id="02e48-106">Label Parts</span></span>  
 <span data-ttu-id="02e48-107"><xref:System.Windows.Controls.Label>控件不具有任何已命名的部件。</span><span class="sxs-lookup"><span data-stu-id="02e48-107">The <xref:System.Windows.Controls.Label> control does not have any named parts.</span></span>  
  
## <a name="label-states"></a><span data-ttu-id="02e48-108">标签状态</span><span class="sxs-lookup"><span data-stu-id="02e48-108">Label States</span></span>  
 <span data-ttu-id="02e48-109">下表列出的可视状态<xref:System.Windows.Controls.Label>控件。</span><span class="sxs-lookup"><span data-stu-id="02e48-109">The following table lists the visual states for the <xref:System.Windows.Controls.Label> control.</span></span>  
  
|<span data-ttu-id="02e48-110">VisualState 名称</span><span class="sxs-lookup"><span data-stu-id="02e48-110">VisualState Name</span></span>|<span data-ttu-id="02e48-111">VisualStateGroup 名称</span><span class="sxs-lookup"><span data-stu-id="02e48-111">VisualStateGroup Name</span></span>|<span data-ttu-id="02e48-112">描述</span><span class="sxs-lookup"><span data-stu-id="02e48-112">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="02e48-113">有效</span><span class="sxs-lookup"><span data-stu-id="02e48-113">Valid</span></span>|<span data-ttu-id="02e48-114">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="02e48-114">ValidationStates</span></span>|<span data-ttu-id="02e48-115">该控件使用<xref:System.Windows.Controls.Validation>类和<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>附加的属性`false`。</span><span class="sxs-lookup"><span data-stu-id="02e48-115">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="02e48-116">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="02e48-116">InvalidFocused</span></span>|<span data-ttu-id="02e48-117">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="02e48-117">ValidationStates</span></span>|<span data-ttu-id="02e48-118"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>附加的属性`true`已在控件有焦点。</span><span class="sxs-lookup"><span data-stu-id="02e48-118">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="02e48-119">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="02e48-119">InvalidUnfocused</span></span>|<span data-ttu-id="02e48-120">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="02e48-120">ValidationStates</span></span>|<span data-ttu-id="02e48-121"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>附加的属性`true`具有该控件没有焦点。</span><span class="sxs-lookup"><span data-stu-id="02e48-121">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="label-controltemplate-example"></a><span data-ttu-id="02e48-122">标签 ControlTemplate 示例</span><span class="sxs-lookup"><span data-stu-id="02e48-122">Label ControlTemplate Example</span></span>  
 <span data-ttu-id="02e48-123">下面的示例演示如何定义<xref:System.Windows.Controls.ControlTemplate>为<xref:System.Windows.Controls.Label>控件。</span><span class="sxs-lookup"><span data-stu-id="02e48-123">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.Label> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Label](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/label.xaml#label)]  
  
 <span data-ttu-id="02e48-124"><xref:System.Windows.Controls.ControlTemplate>使用一个或多个以下资源。</span><span class="sxs-lookup"><span data-stu-id="02e48-124">The <xref:System.Windows.Controls.ControlTemplate> uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="02e48-125">有关完整示例，请参阅[使用 ControlTemplates 设置样式示例](http://go.microsoft.com/fwlink/?LinkID=160041)。</span><span class="sxs-lookup"><span data-stu-id="02e48-125">For the complete sample, see [Styling with ControlTemplates Sample](http://go.microsoft.com/fwlink/?LinkID=160041).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="02e48-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="02e48-126">See Also</span></span>  
 <xref:System.Windows.FrameworkElement.Style%2A>  
 <xref:System.Windows.Controls.ControlTemplate>  
 [<span data-ttu-id="02e48-127">控件样式和模板</span><span class="sxs-lookup"><span data-stu-id="02e48-127">Control Styles and Templates</span></span>](../../../../docs/framework/wpf/controls/control-styles-and-templates.md)  
 [<span data-ttu-id="02e48-128">控件自定义</span><span class="sxs-lookup"><span data-stu-id="02e48-128">Control Customization</span></span>](../../../../docs/framework/wpf/controls/control-customization.md)  
 [<span data-ttu-id="02e48-129">样式设置和模板化</span><span class="sxs-lookup"><span data-stu-id="02e48-129">Styling and Templating</span></span>](../../../../docs/framework/wpf/controls/styling-and-templating.md)  
 [<span data-ttu-id="02e48-130">通过创建 ControlTemplate 自定义现有控件的外观</span><span class="sxs-lookup"><span data-stu-id="02e48-130">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)
