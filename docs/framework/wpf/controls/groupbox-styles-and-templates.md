---
title: "GroupBox 样式和模板"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- ControlTemplate [WPF], GroupBox
- parts [WPF], GroupBox
- GroupBox [WPF], styles and templates
- states [WPF], GroupBox
- styles [WPF], GroupBox
- templates [WPF], GroupBox
ms.assetid: 33df7037-0a1b-476f-b9d0-41566a777699
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 8a39e09812c54df533fdac27b5bfcaedd3fb93ab
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="groupbox-styles-and-templates"></a><span data-ttu-id="583f5-102">GroupBox 样式和模板</span><span class="sxs-lookup"><span data-stu-id="583f5-102">GroupBox Styles and Templates</span></span>
<a name="introduction"></a><span data-ttu-id="583f5-103">本主题介绍的样式和模板的<xref:System.Windows.Controls.GroupBox>控件。</span><span class="sxs-lookup"><span data-stu-id="583f5-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.GroupBox> control.</span></span> <span data-ttu-id="583f5-104">你可以修改默认<xref:System.Windows.Controls.ControlTemplate>提供独特外观的控件。</span><span class="sxs-lookup"><span data-stu-id="583f5-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="583f5-105">有关详细信息，请参阅[通过创建 ControlTemplate 自定义现有控件的外观](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)。</span><span class="sxs-lookup"><span data-stu-id="583f5-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
<a name="groupbox_parts"></a>   
## <a name="groupbox-parts"></a><span data-ttu-id="583f5-106">GroupBox 部件</span><span class="sxs-lookup"><span data-stu-id="583f5-106">GroupBox Parts</span></span>  
 <span data-ttu-id="583f5-107"><xref:System.Windows.Controls.GroupBox>控件不具有任何已命名的部件。</span><span class="sxs-lookup"><span data-stu-id="583f5-107">The <xref:System.Windows.Controls.GroupBox> control does not have any named parts.</span></span>  
  
<a name="groupbox_states"></a>   
## <a name="groupbox-states"></a><span data-ttu-id="583f5-108">GroupBox 状态</span><span class="sxs-lookup"><span data-stu-id="583f5-108">GroupBox States</span></span>  
 <span data-ttu-id="583f5-109">下表列出的可视状态<xref:System.Windows.Controls.GroupBox>控件。</span><span class="sxs-lookup"><span data-stu-id="583f5-109">The following table lists the visual states for the <xref:System.Windows.Controls.GroupBox> control.</span></span>  
  
|<span data-ttu-id="583f5-110">VisualState 名称</span><span class="sxs-lookup"><span data-stu-id="583f5-110">VisualState Name</span></span>|<span data-ttu-id="583f5-111">VisualStateGroup 名称</span><span class="sxs-lookup"><span data-stu-id="583f5-111">VisualStateGroup Name</span></span>|<span data-ttu-id="583f5-112">描述</span><span class="sxs-lookup"><span data-stu-id="583f5-112">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="583f5-113">有效</span><span class="sxs-lookup"><span data-stu-id="583f5-113">Valid</span></span>|<span data-ttu-id="583f5-114">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="583f5-114">ValidationStates</span></span>|<span data-ttu-id="583f5-115">该控件使用<xref:System.Windows.Controls.Validation>类和<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>附加的属性`false`。</span><span class="sxs-lookup"><span data-stu-id="583f5-115">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="583f5-116">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="583f5-116">InvalidFocused</span></span>|<span data-ttu-id="583f5-117">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="583f5-117">ValidationStates</span></span>|<span data-ttu-id="583f5-118"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>附加的属性`true`已在控件有焦点。</span><span class="sxs-lookup"><span data-stu-id="583f5-118">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="583f5-119">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="583f5-119">InvalidUnfocused</span></span>|<span data-ttu-id="583f5-120">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="583f5-120">ValidationStates</span></span>|<span data-ttu-id="583f5-121"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>附加的属性`true`具有该控件没有焦点。</span><span class="sxs-lookup"><span data-stu-id="583f5-121">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
<a name="groupbox_controltemplate_example"></a>   
## <a name="groupbox-controltemplate-example"></a><span data-ttu-id="583f5-122">GroupBox ControlTemplate 示例</span><span class="sxs-lookup"><span data-stu-id="583f5-122">GroupBox ControlTemplate Example</span></span>  
 <span data-ttu-id="583f5-123">下面的示例演示如何定义<xref:System.Windows.Controls.ControlTemplate>为<xref:System.Windows.Controls.GroupBox>控件。</span><span class="sxs-lookup"><span data-stu-id="583f5-123">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.GroupBox> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#GroupBox](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/groupbox.xaml#groupbox)]  
  
 <span data-ttu-id="583f5-124"><xref:System.Windows.Controls.ControlTemplate>使用一个或多个以下资源。</span><span class="sxs-lookup"><span data-stu-id="583f5-124">The <xref:System.Windows.Controls.ControlTemplate> uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="583f5-125">有关完整示例，请参阅[使用 ControlTemplates 设置样式示例](http://go.microsoft.com/fwlink/?LinkID=160041)。</span><span class="sxs-lookup"><span data-stu-id="583f5-125">For the complete sample, see [Styling with ControlTemplates Sample](http://go.microsoft.com/fwlink/?LinkID=160041).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="583f5-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="583f5-126">See Also</span></span>  
 <xref:System.Windows.FrameworkElement.Style%2A>  
 <xref:System.Windows.Controls.ControlTemplate>  
 [<span data-ttu-id="583f5-127">控件样式和模板</span><span class="sxs-lookup"><span data-stu-id="583f5-127">Control Styles and Templates</span></span>](../../../../docs/framework/wpf/controls/control-styles-and-templates.md)  
 [<span data-ttu-id="583f5-128">控件自定义</span><span class="sxs-lookup"><span data-stu-id="583f5-128">Control Customization</span></span>](../../../../docs/framework/wpf/controls/control-customization.md)  
 [<span data-ttu-id="583f5-129">样式设置和模板化</span><span class="sxs-lookup"><span data-stu-id="583f5-129">Styling and Templating</span></span>](../../../../docs/framework/wpf/controls/styling-and-templating.md)  
 [<span data-ttu-id="583f5-130">通过创建 ControlTemplate 自定义现有控件的外观</span><span class="sxs-lookup"><span data-stu-id="583f5-130">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)
