---
title: NavigationWindow 样式和模板
ms.date: 03/30/2017
helpviewer_keywords:
- states [WPF], NavigationWindow
- NavigationWindow [WPF], styles and templates
- ControlTemplate [WPF], NavigationWindow
- parts [WPF], NavigationWindow
- styles [WPF], NavigationWindow
- templates [WPF], NavigationWindow
ms.assetid: 3656055e-3222-43c8-b868-fd0c90cc31a3
ms.openlocfilehash: 4aae14299b3959e7d2122991954cc62505d2a19e
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2019
ms.locfileid: "73460202"
---
# <a name="navigationwindow-styles-and-templates"></a><span data-ttu-id="37f0f-102">NavigationWindow 样式和模板</span><span class="sxs-lookup"><span data-stu-id="37f0f-102">NavigationWindow Styles and Templates</span></span>
<span data-ttu-id="37f0f-103">本主题介绍 <xref:System.Windows.Navigation.NavigationWindow> 控件的样式和模板。</span><span class="sxs-lookup"><span data-stu-id="37f0f-103">This topic describes the styles and templates for the <xref:System.Windows.Navigation.NavigationWindow> control.</span></span> <span data-ttu-id="37f0f-104">您可以修改默认 <xref:System.Windows.Controls.ControlTemplate> 以使控件具有独特的外观。</span><span class="sxs-lookup"><span data-stu-id="37f0f-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="37f0f-105">有关详细信息，请参阅[通过创建 ControlTemplate 自定义现有控件的外观](customizing-the-appearance-of-an-existing-control.md)。</span><span class="sxs-lookup"><span data-stu-id="37f0f-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="navigationwindow-parts"></a><span data-ttu-id="37f0f-106">System.windows.navigation.navigationwindow> 部件</span><span class="sxs-lookup"><span data-stu-id="37f0f-106">NavigationWindow Parts</span></span>  
 <span data-ttu-id="37f0f-107">下表列出了 <xref:System.Windows.Navigation.NavigationWindow> 控件的已命名部分。</span><span class="sxs-lookup"><span data-stu-id="37f0f-107">The following table lists the named parts for the <xref:System.Windows.Navigation.NavigationWindow> control.</span></span>  
  
|<span data-ttu-id="37f0f-108">部件</span><span class="sxs-lookup"><span data-stu-id="37f0f-108">Part</span></span>|<span data-ttu-id="37f0f-109">键入</span><span class="sxs-lookup"><span data-stu-id="37f0f-109">Type</span></span>|<span data-ttu-id="37f0f-110">描述</span><span class="sxs-lookup"><span data-stu-id="37f0f-110">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="37f0f-111">PART_NavWinCP</span><span class="sxs-lookup"><span data-stu-id="37f0f-111">PART_NavWinCP</span></span>|<xref:System.Windows.Controls.ContentPresenter>|<span data-ttu-id="37f0f-112">内容的区域。</span><span class="sxs-lookup"><span data-stu-id="37f0f-112">The area for the content.</span></span>|  
  
## <a name="navigationwindow-states"></a><span data-ttu-id="37f0f-113">System.windows.navigation.navigationwindow> 状态</span><span class="sxs-lookup"><span data-stu-id="37f0f-113">NavigationWindow States</span></span>  
 <span data-ttu-id="37f0f-114">下表列出了 <xref:System.Windows.Navigation.NavigationWindow> 控件的可视状态。</span><span class="sxs-lookup"><span data-stu-id="37f0f-114">The following table lists the visual states for the <xref:System.Windows.Navigation.NavigationWindow> control.</span></span>  
  
|<span data-ttu-id="37f0f-115">VisualState 名称</span><span class="sxs-lookup"><span data-stu-id="37f0f-115">VisualState Name</span></span>|<span data-ttu-id="37f0f-116">VisualStateGroup 名称</span><span class="sxs-lookup"><span data-stu-id="37f0f-116">VisualStateGroup Name</span></span>|<span data-ttu-id="37f0f-117">描述</span><span class="sxs-lookup"><span data-stu-id="37f0f-117">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="37f0f-118">有效</span><span class="sxs-lookup"><span data-stu-id="37f0f-118">Valid</span></span>|<span data-ttu-id="37f0f-119">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="37f0f-119">ValidationStates</span></span>|<span data-ttu-id="37f0f-120">控件使用 <xref:System.Windows.Controls.Validation> 类，并且 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 附加属性是 `false`。</span><span class="sxs-lookup"><span data-stu-id="37f0f-120">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="37f0f-121">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="37f0f-121">InvalidFocused</span></span>|<span data-ttu-id="37f0f-122">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="37f0f-122">ValidationStates</span></span>|<span data-ttu-id="37f0f-123"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 附加属性是控件具有焦点 `true`。</span><span class="sxs-lookup"><span data-stu-id="37f0f-123">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="37f0f-124">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="37f0f-124">InvalidUnfocused</span></span>|<span data-ttu-id="37f0f-125">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="37f0f-125">ValidationStates</span></span>|<span data-ttu-id="37f0f-126"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 附加属性是 `true` 控件没有焦点。</span><span class="sxs-lookup"><span data-stu-id="37f0f-126">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="navigationwindow-controltemplate-example"></a><span data-ttu-id="37f0f-127">System.windows.navigation.navigationwindow> System.windows.controls.controltemplate> 示例</span><span class="sxs-lookup"><span data-stu-id="37f0f-127">NavigationWindow ControlTemplate Example</span></span>  
 <span data-ttu-id="37f0f-128">尽管此示例包含默认情况下在 <xref:System.Windows.Navigation.NavigationWindow> 的 <xref:System.Windows.Controls.ControlTemplate> 中定义的所有元素，但应将特定值视为示例。</span><span class="sxs-lookup"><span data-stu-id="37f0f-128">Although this example contains all of the elements that are defined in the <xref:System.Windows.Controls.ControlTemplate> of a <xref:System.Windows.Navigation.NavigationWindow> by default, the specific values should be thought of as examples.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#NavigationWindow](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/navigationwindow.xaml#navigationwindow)]  
  
 <span data-ttu-id="37f0f-129">上一示例使用了一个或多个以下资源。</span><span class="sxs-lookup"><span data-stu-id="37f0f-129">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#ResizeGrip](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/resizegrip.xaml#resizegrip)]  
[!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="37f0f-130">有关完整示例，请参阅[使用 ControlTemplates 设置样式示例](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating)。</span><span class="sxs-lookup"><span data-stu-id="37f0f-130">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="37f0f-131">请参阅</span><span class="sxs-lookup"><span data-stu-id="37f0f-131">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="37f0f-132">控件样式和模板</span><span class="sxs-lookup"><span data-stu-id="37f0f-132">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="37f0f-133">控件自定义</span><span class="sxs-lookup"><span data-stu-id="37f0f-133">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="37f0f-134">样式设置和模板化</span><span class="sxs-lookup"><span data-stu-id="37f0f-134">Styling and Templating</span></span>](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [<span data-ttu-id="37f0f-135">通过创建 ControlTemplate 自定义现有控件的外观</span><span class="sxs-lookup"><span data-stu-id="37f0f-135">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](customizing-the-appearance-of-an-existing-control.md)
