---
title: "NavigationWindow 样式和模板"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- states [WPF], NavigationWindow
- NavigationWindow [WPF], styles and templates
- ControlTemplate [WPF], NavigationWindow
- parts [WPF], NavigationWindow
- styles [WPF], NavigationWindow
- templates [WPF], NavigationWindow
ms.assetid: 3656055e-3222-43c8-b868-fd0c90cc31a3
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b638d43fb59506572e2ccddd9da7188639bff279
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="navigationwindow-styles-and-templates"></a><span data-ttu-id="9e39b-102">NavigationWindow 样式和模板</span><span class="sxs-lookup"><span data-stu-id="9e39b-102">NavigationWindow Styles and Templates</span></span>
<span data-ttu-id="9e39b-103">本主题介绍的样式和模板的<xref:System.Windows.Navigation.NavigationWindow>控件。</span><span class="sxs-lookup"><span data-stu-id="9e39b-103">This topic describes the styles and templates for the <xref:System.Windows.Navigation.NavigationWindow> control.</span></span> <span data-ttu-id="9e39b-104">你可以修改默认<xref:System.Windows.Controls.ControlTemplate>提供独特外观的控件。</span><span class="sxs-lookup"><span data-stu-id="9e39b-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="9e39b-105">有关详细信息，请参阅[通过创建 ControlTemplate 自定义现有控件的外观](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)。</span><span class="sxs-lookup"><span data-stu-id="9e39b-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="navigationwindow-parts"></a><span data-ttu-id="9e39b-106">NavigationWindow 部件</span><span class="sxs-lookup"><span data-stu-id="9e39b-106">NavigationWindow Parts</span></span>  
 <span data-ttu-id="9e39b-107">下表列出的命名的部件<xref:System.Windows.Navigation.NavigationWindow>控件。</span><span class="sxs-lookup"><span data-stu-id="9e39b-107">The following table lists the named parts for the <xref:System.Windows.Navigation.NavigationWindow> control.</span></span>  
  
|<span data-ttu-id="9e39b-108">部件</span><span class="sxs-lookup"><span data-stu-id="9e39b-108">Part</span></span>|<span data-ttu-id="9e39b-109">类型</span><span class="sxs-lookup"><span data-stu-id="9e39b-109">Type</span></span>|<span data-ttu-id="9e39b-110">描述</span><span class="sxs-lookup"><span data-stu-id="9e39b-110">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="9e39b-111">PART_NavWinCP</span><span class="sxs-lookup"><span data-stu-id="9e39b-111">PART_NavWinCP</span></span>|<xref:System.Windows.Controls.ContentPresenter>|<span data-ttu-id="9e39b-112">内容区域。</span><span class="sxs-lookup"><span data-stu-id="9e39b-112">The area for the content.</span></span>|  
  
## <a name="navigationwindow-states"></a><span data-ttu-id="9e39b-113">NavigationWindow 状态</span><span class="sxs-lookup"><span data-stu-id="9e39b-113">NavigationWindow States</span></span>  
 <span data-ttu-id="9e39b-114">下表列出的可视状态<xref:System.Windows.Navigation.NavigationWindow>控件。</span><span class="sxs-lookup"><span data-stu-id="9e39b-114">The following table lists the visual states for the <xref:System.Windows.Navigation.NavigationWindow> control.</span></span>  
  
|<span data-ttu-id="9e39b-115">VisualState 名称</span><span class="sxs-lookup"><span data-stu-id="9e39b-115">VisualState Name</span></span>|<span data-ttu-id="9e39b-116">VisualStateGroup 名称</span><span class="sxs-lookup"><span data-stu-id="9e39b-116">VisualStateGroup Name</span></span>|<span data-ttu-id="9e39b-117">描述</span><span class="sxs-lookup"><span data-stu-id="9e39b-117">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="9e39b-118">有效</span><span class="sxs-lookup"><span data-stu-id="9e39b-118">Valid</span></span>|<span data-ttu-id="9e39b-119">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="9e39b-119">ValidationStates</span></span>|<span data-ttu-id="9e39b-120">该控件使用<xref:System.Windows.Controls.Validation>类和<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>附加的属性`false`。</span><span class="sxs-lookup"><span data-stu-id="9e39b-120">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="9e39b-121">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="9e39b-121">InvalidFocused</span></span>|<span data-ttu-id="9e39b-122">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="9e39b-122">ValidationStates</span></span>|<span data-ttu-id="9e39b-123"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>附加的属性`true`已在控件有焦点。</span><span class="sxs-lookup"><span data-stu-id="9e39b-123">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="9e39b-124">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="9e39b-124">InvalidUnfocused</span></span>|<span data-ttu-id="9e39b-125">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="9e39b-125">ValidationStates</span></span>|<span data-ttu-id="9e39b-126"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>附加的属性`true`具有该控件没有焦点。</span><span class="sxs-lookup"><span data-stu-id="9e39b-126">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="navigationwindow-controltemplate-example"></a><span data-ttu-id="9e39b-127">NavigationWindow ControlTemplate 示例</span><span class="sxs-lookup"><span data-stu-id="9e39b-127">NavigationWindow ControlTemplate Example</span></span>  
 <span data-ttu-id="9e39b-128">虽然此示例包含的所有元素中定义<xref:System.Windows.Controls.ControlTemplate>的<xref:System.Windows.Navigation.NavigationWindow>默认情况下，特定的值应被视为示例。</span><span class="sxs-lookup"><span data-stu-id="9e39b-128">Although this example contains all of the elements that are defined in the <xref:System.Windows.Controls.ControlTemplate> of a <xref:System.Windows.Navigation.NavigationWindow> by default, the specific values should be thought of as examples.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#NavigationWindow](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/navigationwindow.xaml#navigationwindow)]  
  
 <span data-ttu-id="9e39b-129">上一示例使用了一个或多个以下资源。</span><span class="sxs-lookup"><span data-stu-id="9e39b-129">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#ResizeGrip](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/resizegrip.xaml#resizegrip)]  
[!code-xaml[ControlTemplateExamples#Resources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="9e39b-130">有关完整示例，请参阅[使用 ControlTemplates 设置样式示例](http://go.microsoft.com/fwlink/?LinkID=160041)。</span><span class="sxs-lookup"><span data-stu-id="9e39b-130">For the complete sample, see [Styling with ControlTemplates Sample](http://go.microsoft.com/fwlink/?LinkID=160041).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9e39b-131">请参阅</span><span class="sxs-lookup"><span data-stu-id="9e39b-131">See Also</span></span>  
 <xref:System.Windows.FrameworkElement.Style%2A>  
 <xref:System.Windows.Controls.ControlTemplate>  
 [<span data-ttu-id="9e39b-132">控件样式和模板</span><span class="sxs-lookup"><span data-stu-id="9e39b-132">Control Styles and Templates</span></span>](../../../../docs/framework/wpf/controls/control-styles-and-templates.md)  
 [<span data-ttu-id="9e39b-133">控件自定义</span><span class="sxs-lookup"><span data-stu-id="9e39b-133">Control Customization</span></span>](../../../../docs/framework/wpf/controls/control-customization.md)  
 [<span data-ttu-id="9e39b-134">样式设置和模板化</span><span class="sxs-lookup"><span data-stu-id="9e39b-134">Styling and Templating</span></span>](../../../../docs/framework/wpf/controls/styling-and-templating.md)  
 [<span data-ttu-id="9e39b-135">通过创建 ControlTemplate 自定义现有控件的外观</span><span class="sxs-lookup"><span data-stu-id="9e39b-135">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)
