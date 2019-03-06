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
ms.openlocfilehash: 586af00dee64cdc9eae1a9c927d079502b0b009a
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/05/2019
ms.locfileid: "57363473"
---
# <a name="navigationwindow-styles-and-templates"></a><span data-ttu-id="b242f-102">NavigationWindow 样式和模板</span><span class="sxs-lookup"><span data-stu-id="b242f-102">NavigationWindow Styles and Templates</span></span>
<span data-ttu-id="b242f-103">本主题介绍的样式和模板的<xref:System.Windows.Navigation.NavigationWindow>控件。</span><span class="sxs-lookup"><span data-stu-id="b242f-103">This topic describes the styles and templates for the <xref:System.Windows.Navigation.NavigationWindow> control.</span></span> <span data-ttu-id="b242f-104">可以修改默认<xref:System.Windows.Controls.ControlTemplate>为控件提供唯一外观。</span><span class="sxs-lookup"><span data-stu-id="b242f-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="b242f-105">有关详细信息，请参阅[通过创建 ControlTemplate 自定义现有控件的外观](customizing-the-appearance-of-an-existing-control.md)。</span><span class="sxs-lookup"><span data-stu-id="b242f-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="navigationwindow-parts"></a><span data-ttu-id="b242f-106">NavigationWindow 部件</span><span class="sxs-lookup"><span data-stu-id="b242f-106">NavigationWindow Parts</span></span>  
 <span data-ttu-id="b242f-107">下表列出了用于命名的部件<xref:System.Windows.Navigation.NavigationWindow>控件。</span><span class="sxs-lookup"><span data-stu-id="b242f-107">The following table lists the named parts for the <xref:System.Windows.Navigation.NavigationWindow> control.</span></span>  
  
|<span data-ttu-id="b242f-108">部件</span><span class="sxs-lookup"><span data-stu-id="b242f-108">Part</span></span>|<span data-ttu-id="b242f-109">类型</span><span class="sxs-lookup"><span data-stu-id="b242f-109">Type</span></span>|<span data-ttu-id="b242f-110">描述</span><span class="sxs-lookup"><span data-stu-id="b242f-110">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="b242f-111">PART_NavWinCP</span><span class="sxs-lookup"><span data-stu-id="b242f-111">PART_NavWinCP</span></span>|<xref:System.Windows.Controls.ContentPresenter>|<span data-ttu-id="b242f-112">用于内容的区域。</span><span class="sxs-lookup"><span data-stu-id="b242f-112">The area for the content.</span></span>|  
  
## <a name="navigationwindow-states"></a><span data-ttu-id="b242f-113">NavigationWindow 状态</span><span class="sxs-lookup"><span data-stu-id="b242f-113">NavigationWindow States</span></span>  
 <span data-ttu-id="b242f-114">下表列出了的可视状态<xref:System.Windows.Navigation.NavigationWindow>控件。</span><span class="sxs-lookup"><span data-stu-id="b242f-114">The following table lists the visual states for the <xref:System.Windows.Navigation.NavigationWindow> control.</span></span>  
  
|<span data-ttu-id="b242f-115">VisualState 名称</span><span class="sxs-lookup"><span data-stu-id="b242f-115">VisualState Name</span></span>|<span data-ttu-id="b242f-116">VisualStateGroup 名称</span><span class="sxs-lookup"><span data-stu-id="b242f-116">VisualStateGroup Name</span></span>|<span data-ttu-id="b242f-117">描述</span><span class="sxs-lookup"><span data-stu-id="b242f-117">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="b242f-118">有效</span><span class="sxs-lookup"><span data-stu-id="b242f-118">Valid</span></span>|<span data-ttu-id="b242f-119">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="b242f-119">ValidationStates</span></span>|<span data-ttu-id="b242f-120">该控件使用<xref:System.Windows.Controls.Validation>类和<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>附加的属性是`false`。</span><span class="sxs-lookup"><span data-stu-id="b242f-120">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="b242f-121">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="b242f-121">InvalidFocused</span></span>|<span data-ttu-id="b242f-122">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="b242f-122">ValidationStates</span></span>|<span data-ttu-id="b242f-123"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>附加的属性是`true`已在控件有焦点。</span><span class="sxs-lookup"><span data-stu-id="b242f-123">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="b242f-124">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="b242f-124">InvalidUnfocused</span></span>|<span data-ttu-id="b242f-125">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="b242f-125">ValidationStates</span></span>|<span data-ttu-id="b242f-126"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>附加的属性是`true`具有该控件没有焦点。</span><span class="sxs-lookup"><span data-stu-id="b242f-126">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="navigationwindow-controltemplate-example"></a><span data-ttu-id="b242f-127">NavigationWindow ControlTemplate 示例</span><span class="sxs-lookup"><span data-stu-id="b242f-127">NavigationWindow ControlTemplate Example</span></span>  
 <span data-ttu-id="b242f-128">尽管此示例中包含的所有元素中定义的<xref:System.Windows.Controls.ControlTemplate>的<xref:System.Windows.Navigation.NavigationWindow>默认情况下，特定的值应被视为示例。</span><span class="sxs-lookup"><span data-stu-id="b242f-128">Although this example contains all of the elements that are defined in the <xref:System.Windows.Controls.ControlTemplate> of a <xref:System.Windows.Navigation.NavigationWindow> by default, the specific values should be thought of as examples.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#NavigationWindow](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/navigationwindow.xaml#navigationwindow)]  
  
 <span data-ttu-id="b242f-129">上一示例使用了一个或多个以下资源。</span><span class="sxs-lookup"><span data-stu-id="b242f-129">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#ResizeGrip](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/resizegrip.xaml#resizegrip)]  
[!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="b242f-130">有关完整示例，请参阅[使用 ControlTemplates 设置样式示例](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating)。</span><span class="sxs-lookup"><span data-stu-id="b242f-130">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b242f-131">请参阅</span><span class="sxs-lookup"><span data-stu-id="b242f-131">See also</span></span>
- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="b242f-132">控件样式和模板</span><span class="sxs-lookup"><span data-stu-id="b242f-132">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="b242f-133">控件自定义</span><span class="sxs-lookup"><span data-stu-id="b242f-133">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="b242f-134">样式设置和模板化</span><span class="sxs-lookup"><span data-stu-id="b242f-134">Styling and Templating</span></span>](styling-and-templating.md)
- [<span data-ttu-id="b242f-135">通过创建 ControlTemplate 自定义现有控件的外观</span><span class="sxs-lookup"><span data-stu-id="b242f-135">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](customizing-the-appearance-of-an-existing-control.md)
