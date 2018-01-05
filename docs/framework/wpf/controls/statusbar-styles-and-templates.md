---
title: "StatusBar 样式和模板"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- ControlTemplate [WPF], StatusBar
- styles [WPF], StatusBar
- templates [WPF], StatusBar
- states [WPF], StatusBar
- parts [WPF], StatusBar
- StatusBar [WPF], styles and templates
ms.assetid: 9f5e1c25-81eb-4756-a0ac-d9e1fbe33ee2
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 370f8f9bc61ffbdd3b98743d11f61613803e6d98
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="statusbar-styles-and-templates"></a><span data-ttu-id="65804-102">StatusBar 样式和模板</span><span class="sxs-lookup"><span data-stu-id="65804-102">StatusBar Styles and Templates</span></span>
<span data-ttu-id="65804-103">本主题介绍的样式和模板的<xref:System.Windows.Controls.Primitives.StatusBar>控件。</span><span class="sxs-lookup"><span data-stu-id="65804-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.Primitives.StatusBar> control.</span></span> <span data-ttu-id="65804-104">你可以修改默认<xref:System.Windows.Controls.ControlTemplate>提供独特外观的控件。</span><span class="sxs-lookup"><span data-stu-id="65804-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="65804-105">有关详细信息，请参阅[通过创建 ControlTemplate 自定义现有控件的外观](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)。</span><span class="sxs-lookup"><span data-stu-id="65804-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="statusbar-parts"></a><span data-ttu-id="65804-106">StatusBar 部件</span><span class="sxs-lookup"><span data-stu-id="65804-106">StatusBar Parts</span></span>  
 <span data-ttu-id="65804-107"><xref:System.Windows.Controls.Primitives.StatusBar>控件不具有任何已命名的部件。</span><span class="sxs-lookup"><span data-stu-id="65804-107">The <xref:System.Windows.Controls.Primitives.StatusBar> control does not have any named parts.</span></span>  
  
## <a name="statusbar-states"></a><span data-ttu-id="65804-108">StatusBar 状态</span><span class="sxs-lookup"><span data-stu-id="65804-108">StatusBar States</span></span>  
 <span data-ttu-id="65804-109">下表列出的可视状态<xref:System.Windows.Controls.Primitives.StatusBar>控件。</span><span class="sxs-lookup"><span data-stu-id="65804-109">The following table lists the visual states for the <xref:System.Windows.Controls.Primitives.StatusBar> control.</span></span>  
  
|<span data-ttu-id="65804-110">VisualState 名称</span><span class="sxs-lookup"><span data-stu-id="65804-110">VisualState Name</span></span>|<span data-ttu-id="65804-111">VisualStateGroup 名称</span><span class="sxs-lookup"><span data-stu-id="65804-111">VisualStateGroup Name</span></span>|<span data-ttu-id="65804-112">描述</span><span class="sxs-lookup"><span data-stu-id="65804-112">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="65804-113">有效</span><span class="sxs-lookup"><span data-stu-id="65804-113">Valid</span></span>|<span data-ttu-id="65804-114">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="65804-114">ValidationStates</span></span>|<span data-ttu-id="65804-115">该控件使用<xref:System.Windows.Controls.Validation>类和<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>附加的属性`false`。</span><span class="sxs-lookup"><span data-stu-id="65804-115">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="65804-116">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="65804-116">InvalidFocused</span></span>|<span data-ttu-id="65804-117">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="65804-117">ValidationStates</span></span>|<span data-ttu-id="65804-118"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>附加的属性`true`已在控件有焦点。</span><span class="sxs-lookup"><span data-stu-id="65804-118">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="65804-119">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="65804-119">InvalidUnfocused</span></span>|<span data-ttu-id="65804-120">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="65804-120">ValidationStates</span></span>|<span data-ttu-id="65804-121"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>附加的属性`true`具有该控件没有焦点。</span><span class="sxs-lookup"><span data-stu-id="65804-121">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="statusbaritem-parts"></a><span data-ttu-id="65804-122">StatusBarItem 部件</span><span class="sxs-lookup"><span data-stu-id="65804-122">StatusBarItem Parts</span></span>  
 <span data-ttu-id="65804-123"><xref:System.Windows.Controls.Primitives.StatusBarItem>控件不具有任何已命名的部件。</span><span class="sxs-lookup"><span data-stu-id="65804-123">The <xref:System.Windows.Controls.Primitives.StatusBarItem> control does not have any named parts.</span></span>  
  
## <a name="statusbar-states"></a><span data-ttu-id="65804-124">StatusBar 状态</span><span class="sxs-lookup"><span data-stu-id="65804-124">StatusBar States</span></span>  
 <span data-ttu-id="65804-125">下表列出的可视状态<xref:System.Windows.Controls.Primitives.StatusBarItem>控件。</span><span class="sxs-lookup"><span data-stu-id="65804-125">The following table lists the visual states for the <xref:System.Windows.Controls.Primitives.StatusBarItem> control.</span></span>  
  
|<span data-ttu-id="65804-126">VisualState 名称</span><span class="sxs-lookup"><span data-stu-id="65804-126">VisualState Name</span></span>|<span data-ttu-id="65804-127">VisualStateGroup 名称</span><span class="sxs-lookup"><span data-stu-id="65804-127">VisualStateGroup Name</span></span>|<span data-ttu-id="65804-128">描述</span><span class="sxs-lookup"><span data-stu-id="65804-128">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="65804-129">有效</span><span class="sxs-lookup"><span data-stu-id="65804-129">Valid</span></span>|<span data-ttu-id="65804-130">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="65804-130">ValidationStates</span></span>|<span data-ttu-id="65804-131">该控件使用<xref:System.Windows.Controls.Validation>类和<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>附加的属性`false`。</span><span class="sxs-lookup"><span data-stu-id="65804-131">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="65804-132">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="65804-132">InvalidFocused</span></span>|<span data-ttu-id="65804-133">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="65804-133">ValidationStates</span></span>|<span data-ttu-id="65804-134"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>附加的属性`true`已在控件有焦点。</span><span class="sxs-lookup"><span data-stu-id="65804-134">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="65804-135">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="65804-135">InvalidUnfocused</span></span>|<span data-ttu-id="65804-136">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="65804-136">ValidationStates</span></span>|<span data-ttu-id="65804-137"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>附加的属性`true`具有该控件没有焦点。</span><span class="sxs-lookup"><span data-stu-id="65804-137">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="statusbar-controltemplate-example"></a><span data-ttu-id="65804-138">StatusBar ControlTemplate 示例</span><span class="sxs-lookup"><span data-stu-id="65804-138">StatusBar ControlTemplate Example</span></span>  
 <span data-ttu-id="65804-139">下面的示例演示如何定义<xref:System.Windows.Controls.ControlTemplate>为<xref:System.Windows.Controls.Primitives.StatusBar>控件。</span><span class="sxs-lookup"><span data-stu-id="65804-139">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.Primitives.StatusBar> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#StatusBar](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/statusbar.xaml#statusbar)]  
  
 <span data-ttu-id="65804-140"><xref:System.Windows.Controls.ControlTemplate>使用一个或多个以下资源。</span><span class="sxs-lookup"><span data-stu-id="65804-140">The <xref:System.Windows.Controls.ControlTemplate> uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="65804-141">有关完整示例，请参阅[使用 ControlTemplates 设置样式示例](http://go.microsoft.com/fwlink/?LinkID=160041)。</span><span class="sxs-lookup"><span data-stu-id="65804-141">For the complete sample, see [Styling with ControlTemplates Sample](http://go.microsoft.com/fwlink/?LinkID=160041).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="65804-142">请参阅</span><span class="sxs-lookup"><span data-stu-id="65804-142">See Also</span></span>  
 <xref:System.Windows.FrameworkElement.Style%2A>  
 <xref:System.Windows.Controls.ControlTemplate>  
 [<span data-ttu-id="65804-143">控件样式和模板</span><span class="sxs-lookup"><span data-stu-id="65804-143">Control Styles and Templates</span></span>](../../../../docs/framework/wpf/controls/control-styles-and-templates.md)  
 [<span data-ttu-id="65804-144">控件自定义</span><span class="sxs-lookup"><span data-stu-id="65804-144">Control Customization</span></span>](../../../../docs/framework/wpf/controls/control-customization.md)  
 [<span data-ttu-id="65804-145">样式设置和模板化</span><span class="sxs-lookup"><span data-stu-id="65804-145">Styling and Templating</span></span>](../../../../docs/framework/wpf/controls/styling-and-templating.md)  
 [<span data-ttu-id="65804-146">通过创建 ControlTemplate 自定义现有控件的外观</span><span class="sxs-lookup"><span data-stu-id="65804-146">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)
