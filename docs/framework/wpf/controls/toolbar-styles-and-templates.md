---
title: ToolBar 样式和模板
ms.date: 03/30/2017
helpviewer_keywords:
- states [WPF], ToolBar
- styles [WPF], ToolBar
- ControlTemplate [WPF], ToolBar
- parts [WPF], ToolBar
- ToolBar [WPF], styles and templates
- templates [WPF], ToolBar
ms.assetid: bd875f46-4690-46f5-81e0-f11a9822484f
ms.openlocfilehash: 1cbb8d54a544b70b4a484c06c6bb2e9ca25029da
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61790736"
---
# <a name="toolbar-styles-and-templates"></a><span data-ttu-id="becf8-102">ToolBar 样式和模板</span><span class="sxs-lookup"><span data-stu-id="becf8-102">ToolBar Styles and Templates</span></span>
<span data-ttu-id="becf8-103">本主题介绍的样式和模板的<xref:System.Windows.Controls.ToolBar>控件。</span><span class="sxs-lookup"><span data-stu-id="becf8-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.ToolBar> control.</span></span> <span data-ttu-id="becf8-104">可以修改默认<xref:System.Windows.Controls.ControlTemplate>为控件提供唯一外观。</span><span class="sxs-lookup"><span data-stu-id="becf8-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="becf8-105">有关详细信息，请参阅[通过创建 ControlTemplate 自定义现有控件的外观](customizing-the-appearance-of-an-existing-control.md)。</span><span class="sxs-lookup"><span data-stu-id="becf8-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="toolbar-parts"></a><span data-ttu-id="becf8-106">工具栏部件</span><span class="sxs-lookup"><span data-stu-id="becf8-106">ToolBar Parts</span></span>  
 <span data-ttu-id="becf8-107">下表列出了用于命名的部件<xref:System.Windows.Controls.ToolBar>控件。</span><span class="sxs-lookup"><span data-stu-id="becf8-107">The following table lists the named parts for the <xref:System.Windows.Controls.ToolBar> control.</span></span>  
  
|<span data-ttu-id="becf8-108">部件</span><span class="sxs-lookup"><span data-stu-id="becf8-108">Part</span></span>|<span data-ttu-id="becf8-109">类型</span><span class="sxs-lookup"><span data-stu-id="becf8-109">Type</span></span>|<span data-ttu-id="becf8-110">描述</span><span class="sxs-lookup"><span data-stu-id="becf8-110">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="becf8-111">PART_ToolBarPanel</span><span class="sxs-lookup"><span data-stu-id="becf8-111">PART_ToolBarPanel</span></span>|<xref:System.Windows.Controls.Primitives.ToolBarPanel>|<span data-ttu-id="becf8-112">包含的控件的对象<xref:System.Windows.Controls.ToolBar>。</span><span class="sxs-lookup"><span data-stu-id="becf8-112">The object that contains the controls on the <xref:System.Windows.Controls.ToolBar>.</span></span>|  
|<span data-ttu-id="becf8-113">PART_ToolBarOverflowPanel</span><span class="sxs-lookup"><span data-stu-id="becf8-113">PART_ToolBarOverflowPanel</span></span>|<xref:System.Windows.Controls.Primitives.ToolBarOverflowPanel>|<span data-ttu-id="becf8-114">对象，包含控件中的溢出区域的<xref:System.Windows.Controls.ToolBar>。</span><span class="sxs-lookup"><span data-stu-id="becf8-114">The object that contains the controls that are in the overflow area of the <xref:System.Windows.Controls.ToolBar>.</span></span>|  
  
 <span data-ttu-id="becf8-115">当您创建<xref:System.Windows.Controls.ControlTemplate>有关<xref:System.Windows.Controls.ToolBar>，模板可能包含<xref:System.Windows.Controls.ItemsPresenter>内<xref:System.Windows.Controls.ScrollViewer>。</span><span class="sxs-lookup"><span data-stu-id="becf8-115">When you create a <xref:System.Windows.Controls.ControlTemplate> for a <xref:System.Windows.Controls.ToolBar>, your template might contain an <xref:System.Windows.Controls.ItemsPresenter> within a <xref:System.Windows.Controls.ScrollViewer>.</span></span> <span data-ttu-id="becf8-116">(<xref:System.Windows.Controls.ItemsPresenter>显示在每个项<xref:System.Windows.Controls.ToolBar>;<xref:System.Windows.Controls.ScrollViewer>控件内实现滚动)。</span><span class="sxs-lookup"><span data-stu-id="becf8-116">(The <xref:System.Windows.Controls.ItemsPresenter> displays each item in the <xref:System.Windows.Controls.ToolBar>; the <xref:System.Windows.Controls.ScrollViewer> enables scrolling within the control).</span></span>  <span data-ttu-id="becf8-117">如果<xref:System.Windows.Controls.ItemsPresenter>不是直接子级<xref:System.Windows.Controls.ScrollViewer>，必须授予<xref:System.Windows.Controls.ItemsPresenter>名称， `ItemsPresenter`。</span><span class="sxs-lookup"><span data-stu-id="becf8-117">If the <xref:System.Windows.Controls.ItemsPresenter> is not the direct child of the <xref:System.Windows.Controls.ScrollViewer>, you must give the <xref:System.Windows.Controls.ItemsPresenter> the name, `ItemsPresenter`.</span></span>  
  
## <a name="toolbar-states"></a><span data-ttu-id="becf8-118">工具栏状态</span><span class="sxs-lookup"><span data-stu-id="becf8-118">ToolBar States</span></span>  
 <span data-ttu-id="becf8-119">下表列出了的可视状态<xref:System.Windows.Controls.ToolBar>控件。</span><span class="sxs-lookup"><span data-stu-id="becf8-119">The following table lists the visual states for the <xref:System.Windows.Controls.ToolBar> control.</span></span>  
  
|<span data-ttu-id="becf8-120">VisualState 名称</span><span class="sxs-lookup"><span data-stu-id="becf8-120">VisualState Name</span></span>|<span data-ttu-id="becf8-121">VisualStateGroup 名称</span><span class="sxs-lookup"><span data-stu-id="becf8-121">VisualStateGroup Name</span></span>|<span data-ttu-id="becf8-122">描述</span><span class="sxs-lookup"><span data-stu-id="becf8-122">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="becf8-123">有效</span><span class="sxs-lookup"><span data-stu-id="becf8-123">Valid</span></span>|<span data-ttu-id="becf8-124">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="becf8-124">ValidationStates</span></span>|<span data-ttu-id="becf8-125">该控件使用<xref:System.Windows.Controls.Validation>类和<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>附加的属性是`false`。</span><span class="sxs-lookup"><span data-stu-id="becf8-125">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="becf8-126">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="becf8-126">InvalidFocused</span></span>|<span data-ttu-id="becf8-127">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="becf8-127">ValidationStates</span></span>|<span data-ttu-id="becf8-128"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>附加的属性是`true`已在控件有焦点。</span><span class="sxs-lookup"><span data-stu-id="becf8-128">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="becf8-129">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="becf8-129">InvalidUnfocused</span></span>|<span data-ttu-id="becf8-130">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="becf8-130">ValidationStates</span></span>|<span data-ttu-id="becf8-131"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>附加的属性是`true`具有该控件没有焦点。</span><span class="sxs-lookup"><span data-stu-id="becf8-131">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="toolbar-controltemplate-example"></a><span data-ttu-id="becf8-132">工具栏 ControlTemplate 示例</span><span class="sxs-lookup"><span data-stu-id="becf8-132">ToolBar ControlTemplate Example</span></span>  
 <span data-ttu-id="becf8-133">下面的示例演示如何定义<xref:System.Windows.Controls.ControlTemplate>为<xref:System.Windows.Controls.ToolBar>控件。</span><span class="sxs-lookup"><span data-stu-id="becf8-133">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.ToolBar> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#ToolBar](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/toolbar.xaml#toolbar)]  
  
 <span data-ttu-id="becf8-134">上一示例使用了一个或多个以下资源。</span><span class="sxs-lookup"><span data-stu-id="becf8-134">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="becf8-135">有关完整示例，请参阅[使用 ControlTemplates 设置样式示例](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating)。</span><span class="sxs-lookup"><span data-stu-id="becf8-135">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="becf8-136">请参阅</span><span class="sxs-lookup"><span data-stu-id="becf8-136">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="becf8-137">控件样式和模板</span><span class="sxs-lookup"><span data-stu-id="becf8-137">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="becf8-138">控件自定义</span><span class="sxs-lookup"><span data-stu-id="becf8-138">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="becf8-139">样式设置和模板化</span><span class="sxs-lookup"><span data-stu-id="becf8-139">Styling and Templating</span></span>](styling-and-templating.md)
- [<span data-ttu-id="becf8-140">通过创建 ControlTemplate 自定义现有控件的外观</span><span class="sxs-lookup"><span data-stu-id="becf8-140">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](customizing-the-appearance-of-an-existing-control.md)
