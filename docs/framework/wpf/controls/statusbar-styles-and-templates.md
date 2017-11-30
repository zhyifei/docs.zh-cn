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
ms.openlocfilehash: 570edc023467fb6e95cdcba23b75ac53397797c2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="statusbar-styles-and-templates"></a><span data-ttu-id="f4dde-102">StatusBar 样式和模板</span><span class="sxs-lookup"><span data-stu-id="f4dde-102">StatusBar Styles and Templates</span></span>
<span data-ttu-id="f4dde-103">本主题介绍的样式和模板的<xref:System.Windows.Controls.Primitives.StatusBar>控件。</span><span class="sxs-lookup"><span data-stu-id="f4dde-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.Primitives.StatusBar> control.</span></span> <span data-ttu-id="f4dde-104">你可以修改默认<xref:System.Windows.Controls.ControlTemplate>提供独特外观的控件。</span><span class="sxs-lookup"><span data-stu-id="f4dde-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="f4dde-105">有关详细信息，请参阅[通过创建 ControlTemplate 自定义现有控件的外观](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)。</span><span class="sxs-lookup"><span data-stu-id="f4dde-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="statusbar-parts"></a><span data-ttu-id="f4dde-106">StatusBar 部件</span><span class="sxs-lookup"><span data-stu-id="f4dde-106">StatusBar Parts</span></span>  
 <span data-ttu-id="f4dde-107"><xref:System.Windows.Controls.Primitives.StatusBar>控件不具有任何已命名的部件。</span><span class="sxs-lookup"><span data-stu-id="f4dde-107">The <xref:System.Windows.Controls.Primitives.StatusBar> control does not have any named parts.</span></span>  
  
## <a name="statusbar-states"></a><span data-ttu-id="f4dde-108">StatusBar 状态</span><span class="sxs-lookup"><span data-stu-id="f4dde-108">StatusBar States</span></span>  
 <span data-ttu-id="f4dde-109">下表列出的可视状态<xref:System.Windows.Controls.Primitives.StatusBar>控件。</span><span class="sxs-lookup"><span data-stu-id="f4dde-109">The following table lists the visual states for the <xref:System.Windows.Controls.Primitives.StatusBar> control.</span></span>  
  
|<span data-ttu-id="f4dde-110">VisualState 名称</span><span class="sxs-lookup"><span data-stu-id="f4dde-110">VisualState Name</span></span>|<span data-ttu-id="f4dde-111">VisualStateGroup 名称</span><span class="sxs-lookup"><span data-stu-id="f4dde-111">VisualStateGroup Name</span></span>|<span data-ttu-id="f4dde-112">描述</span><span class="sxs-lookup"><span data-stu-id="f4dde-112">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="f4dde-113">有效</span><span class="sxs-lookup"><span data-stu-id="f4dde-113">Valid</span></span>|<span data-ttu-id="f4dde-114">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="f4dde-114">ValidationStates</span></span>|<span data-ttu-id="f4dde-115">该控件使用<xref:System.Windows.Controls.Validation>类和<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>附加的属性`false`。</span><span class="sxs-lookup"><span data-stu-id="f4dde-115">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="f4dde-116">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="f4dde-116">InvalidFocused</span></span>|<span data-ttu-id="f4dde-117">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="f4dde-117">ValidationStates</span></span>|<span data-ttu-id="f4dde-118"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>附加的属性`true`已在控件有焦点。</span><span class="sxs-lookup"><span data-stu-id="f4dde-118">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="f4dde-119">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="f4dde-119">InvalidUnfocused</span></span>|<span data-ttu-id="f4dde-120">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="f4dde-120">ValidationStates</span></span>|<span data-ttu-id="f4dde-121"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>附加的属性`true`具有该控件没有焦点。</span><span class="sxs-lookup"><span data-stu-id="f4dde-121">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="statusbaritem-parts"></a><span data-ttu-id="f4dde-122">StatusBarItem 部件</span><span class="sxs-lookup"><span data-stu-id="f4dde-122">StatusBarItem Parts</span></span>  
 <span data-ttu-id="f4dde-123"><xref:System.Windows.Controls.Primitives.StatusBarItem>控件不具有任何已命名的部件。</span><span class="sxs-lookup"><span data-stu-id="f4dde-123">The <xref:System.Windows.Controls.Primitives.StatusBarItem> control does not have any named parts.</span></span>  
  
## <a name="statusbar-states"></a><span data-ttu-id="f4dde-124">StatusBar 状态</span><span class="sxs-lookup"><span data-stu-id="f4dde-124">StatusBar States</span></span>  
 <span data-ttu-id="f4dde-125">下表列出的可视状态<xref:System.Windows.Controls.Primitives.StatusBarItem>控件。</span><span class="sxs-lookup"><span data-stu-id="f4dde-125">The following table lists the visual states for the <xref:System.Windows.Controls.Primitives.StatusBarItem> control.</span></span>  
  
|<span data-ttu-id="f4dde-126">VisualState 名称</span><span class="sxs-lookup"><span data-stu-id="f4dde-126">VisualState Name</span></span>|<span data-ttu-id="f4dde-127">VisualStateGroup 名称</span><span class="sxs-lookup"><span data-stu-id="f4dde-127">VisualStateGroup Name</span></span>|<span data-ttu-id="f4dde-128">描述</span><span class="sxs-lookup"><span data-stu-id="f4dde-128">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="f4dde-129">有效</span><span class="sxs-lookup"><span data-stu-id="f4dde-129">Valid</span></span>|<span data-ttu-id="f4dde-130">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="f4dde-130">ValidationStates</span></span>|<span data-ttu-id="f4dde-131">该控件使用<xref:System.Windows.Controls.Validation>类和<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>附加的属性`false`。</span><span class="sxs-lookup"><span data-stu-id="f4dde-131">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="f4dde-132">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="f4dde-132">InvalidFocused</span></span>|<span data-ttu-id="f4dde-133">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="f4dde-133">ValidationStates</span></span>|<span data-ttu-id="f4dde-134"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>附加的属性`true`已在控件有焦点。</span><span class="sxs-lookup"><span data-stu-id="f4dde-134">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="f4dde-135">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="f4dde-135">InvalidUnfocused</span></span>|<span data-ttu-id="f4dde-136">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="f4dde-136">ValidationStates</span></span>|<span data-ttu-id="f4dde-137"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>附加的属性`true`具有该控件没有焦点。</span><span class="sxs-lookup"><span data-stu-id="f4dde-137">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="statusbar-controltemplate-example"></a><span data-ttu-id="f4dde-138">StatusBar ControlTemplate 示例</span><span class="sxs-lookup"><span data-stu-id="f4dde-138">StatusBar ControlTemplate Example</span></span>  
 <span data-ttu-id="f4dde-139">下面的示例演示如何定义<xref:System.Windows.Controls.ControlTemplate>为<xref:System.Windows.Controls.Primitives.StatusBar>控件。</span><span class="sxs-lookup"><span data-stu-id="f4dde-139">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.Primitives.StatusBar> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#StatusBar](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/statusbar.xaml#statusbar)]  
  
 <span data-ttu-id="f4dde-140"><xref:System.Windows.Controls.ControlTemplate>使用一个或多个以下资源。</span><span class="sxs-lookup"><span data-stu-id="f4dde-140">The <xref:System.Windows.Controls.ControlTemplate> uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="f4dde-141">有关完整示例，请参阅[使用 ControlTemplates 设置样式示例](http://go.microsoft.com/fwlink/?LinkID=160041)。</span><span class="sxs-lookup"><span data-stu-id="f4dde-141">For the complete sample, see [Styling with ControlTemplates Sample](http://go.microsoft.com/fwlink/?LinkID=160041).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f4dde-142">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f4dde-142">See Also</span></span>  
 <xref:System.Windows.FrameworkElement.Style%2A>  
 <xref:System.Windows.Controls.ControlTemplate>  
 [<span data-ttu-id="f4dde-143">控件样式和模板</span><span class="sxs-lookup"><span data-stu-id="f4dde-143">Control Styles and Templates</span></span>](../../../../docs/framework/wpf/controls/control-styles-and-templates.md)  
 [<span data-ttu-id="f4dde-144">控件自定义</span><span class="sxs-lookup"><span data-stu-id="f4dde-144">Control Customization</span></span>](../../../../docs/framework/wpf/controls/control-customization.md)  
 [<span data-ttu-id="f4dde-145">样式设置和模板化</span><span class="sxs-lookup"><span data-stu-id="f4dde-145">Styling and Templating</span></span>](../../../../docs/framework/wpf/controls/styling-and-templating.md)  
 [<span data-ttu-id="f4dde-146">通过创建 ControlTemplate 自定义现有控件的外观</span><span class="sxs-lookup"><span data-stu-id="f4dde-146">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)
