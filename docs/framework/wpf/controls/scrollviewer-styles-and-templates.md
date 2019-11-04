---
title: ScrollViewer 样式和模板
ms.date: 03/30/2017
helpviewer_keywords:
- parts [WPF], ScrollViewer
- states [WPF], ScrollViewer
- styles [WPF], ScrollViewer
- templates [WPF], ScrollViewer
- ControlTemplate [WPF], ScrollViewer
- ScrollViewer [WPF], styles and templates
ms.assetid: dffdd822-ae69-4946-abaf-710860cd65b2
ms.openlocfilehash: 70a2002ab114f2bbd6a4e550ae9006e214ee27a5
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2019
ms.locfileid: "73458414"
---
# <a name="scrollviewer-styles-and-templates"></a><span data-ttu-id="11eae-102">ScrollViewer 样式和模板</span><span class="sxs-lookup"><span data-stu-id="11eae-102">ScrollViewer Styles and Templates</span></span>
<span data-ttu-id="11eae-103">本主题介绍 <xref:System.Windows.Controls.ScrollViewer> 控件的样式和模板。</span><span class="sxs-lookup"><span data-stu-id="11eae-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.ScrollViewer> control.</span></span> <span data-ttu-id="11eae-104">您可以修改默认 <xref:System.Windows.Controls.ControlTemplate> 以使控件具有独特的外观。</span><span class="sxs-lookup"><span data-stu-id="11eae-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="11eae-105">有关详细信息，请参阅[通过创建 ControlTemplate 自定义现有控件的外观](customizing-the-appearance-of-an-existing-control.md)。</span><span class="sxs-lookup"><span data-stu-id="11eae-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="scrollviewer-parts"></a><span data-ttu-id="11eae-106">ScrollViewer 部件</span><span class="sxs-lookup"><span data-stu-id="11eae-106">ScrollViewer Parts</span></span>  
 <span data-ttu-id="11eae-107">下表列出了 <xref:System.Windows.Controls.ScrollViewer> 控件的已命名部分。</span><span class="sxs-lookup"><span data-stu-id="11eae-107">The following table lists the named parts for the <xref:System.Windows.Controls.ScrollViewer> control.</span></span>  
  
|<span data-ttu-id="11eae-108">部件</span><span class="sxs-lookup"><span data-stu-id="11eae-108">Part</span></span>|<span data-ttu-id="11eae-109">键入</span><span class="sxs-lookup"><span data-stu-id="11eae-109">Type</span></span>|<span data-ttu-id="11eae-110">描述</span><span class="sxs-lookup"><span data-stu-id="11eae-110">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="11eae-111">PART_ScrollContentPresenter</span><span class="sxs-lookup"><span data-stu-id="11eae-111">PART_ScrollContentPresenter</span></span>|<xref:System.Windows.Controls.ScrollContentPresenter>|<span data-ttu-id="11eae-112"><xref:System.Windows.Controls.ScrollViewer>中的内容的占位符。</span><span class="sxs-lookup"><span data-stu-id="11eae-112">The placeholder for content in the <xref:System.Windows.Controls.ScrollViewer>.</span></span>|  
|<span data-ttu-id="11eae-113">PART_HorizontalScrollBar</span><span class="sxs-lookup"><span data-stu-id="11eae-113">PART_HorizontalScrollBar</span></span>|<xref:System.Windows.Controls.Primitives.ScrollBar>|<span data-ttu-id="11eae-114">用于水平滚动内容的 <xref:System.Windows.Controls.Primitives.ScrollBar>。</span><span class="sxs-lookup"><span data-stu-id="11eae-114">The <xref:System.Windows.Controls.Primitives.ScrollBar> used to scroll the content horizontally.</span></span>|  
|<span data-ttu-id="11eae-115">PART_VerticalScrollBar</span><span class="sxs-lookup"><span data-stu-id="11eae-115">PART_VerticalScrollBar</span></span>|<xref:System.Windows.Controls.Primitives.ScrollBar>|<span data-ttu-id="11eae-116">用于垂直滚动内容的 <xref:System.Windows.Controls.Primitives.ScrollBar>。</span><span class="sxs-lookup"><span data-stu-id="11eae-116">The <xref:System.Windows.Controls.Primitives.ScrollBar> used to scroll the content vertically.</span></span>|  
  
## <a name="scrollviewer-states"></a><span data-ttu-id="11eae-117">ScrollViewer 状态</span><span class="sxs-lookup"><span data-stu-id="11eae-117">ScrollViewer States</span></span>  
 <span data-ttu-id="11eae-118">下表列出了 <xref:System.Windows.Controls.ScrollViewer> 控件的可视状态。</span><span class="sxs-lookup"><span data-stu-id="11eae-118">The following table lists the visual states for the <xref:System.Windows.Controls.ScrollViewer> control.</span></span>  
  
|<span data-ttu-id="11eae-119">VisualState 名称</span><span class="sxs-lookup"><span data-stu-id="11eae-119">VisualState Name</span></span>|<span data-ttu-id="11eae-120">VisualStateGroup 名称</span><span class="sxs-lookup"><span data-stu-id="11eae-120">VisualStateGroup Name</span></span>|<span data-ttu-id="11eae-121">描述</span><span class="sxs-lookup"><span data-stu-id="11eae-121">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="11eae-122">有效</span><span class="sxs-lookup"><span data-stu-id="11eae-122">Valid</span></span>|<span data-ttu-id="11eae-123">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="11eae-123">ValidationStates</span></span>|<span data-ttu-id="11eae-124">控件使用 <xref:System.Windows.Controls.Validation> 类，并且 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 附加属性是 `false`。</span><span class="sxs-lookup"><span data-stu-id="11eae-124">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="11eae-125">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="11eae-125">InvalidFocused</span></span>|<span data-ttu-id="11eae-126">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="11eae-126">ValidationStates</span></span>|<span data-ttu-id="11eae-127"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 附加属性是控件具有焦点 `true`。</span><span class="sxs-lookup"><span data-stu-id="11eae-127">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="11eae-128">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="11eae-128">InvalidUnfocused</span></span>|<span data-ttu-id="11eae-129">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="11eae-129">ValidationStates</span></span>|<span data-ttu-id="11eae-130"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 附加属性是 `true` 控件没有焦点。</span><span class="sxs-lookup"><span data-stu-id="11eae-130">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="scrollviewer-controltemplate-example"></a><span data-ttu-id="11eae-131">ScrollViewer System.windows.controls.controltemplate> 示例</span><span class="sxs-lookup"><span data-stu-id="11eae-131">ScrollViewer ControlTemplate Example</span></span>  
 <span data-ttu-id="11eae-132">下面的示例演示如何为 <xref:System.Windows.Controls.ScrollViewer> 控件定义 <xref:System.Windows.Controls.ControlTemplate>。</span><span class="sxs-lookup"><span data-stu-id="11eae-132">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.ScrollViewer> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#ScrollViewer](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/scrollviewer.xaml#scrollviewer)]  
  
 <span data-ttu-id="11eae-133">上一示例使用了一个或多个以下资源。</span><span class="sxs-lookup"><span data-stu-id="11eae-133">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="11eae-134">有关完整示例，请参阅[使用 ControlTemplates 设置样式示例](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating)。</span><span class="sxs-lookup"><span data-stu-id="11eae-134">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="11eae-135">请参阅</span><span class="sxs-lookup"><span data-stu-id="11eae-135">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="11eae-136">控件样式和模板</span><span class="sxs-lookup"><span data-stu-id="11eae-136">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="11eae-137">控件自定义</span><span class="sxs-lookup"><span data-stu-id="11eae-137">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="11eae-138">样式设置和模板化</span><span class="sxs-lookup"><span data-stu-id="11eae-138">Styling and Templating</span></span>](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [<span data-ttu-id="11eae-139">通过创建 ControlTemplate 自定义现有控件的外观</span><span class="sxs-lookup"><span data-stu-id="11eae-139">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](customizing-the-appearance-of-an-existing-control.md)
