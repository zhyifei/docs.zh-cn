---
title: DocumentViewer 样式和模板
ms.date: 03/30/2017
helpviewer_keywords:
- templates [WPF], DocumentViewer
- DocumentViewer [WPF], styles and templates
- states [WPF], DocumentViewer
- ControlTemplate [WPF], DocumentViewer
- parts [WPF], DocumentViewer
- styles [WPF], DocumentViewer
ms.assetid: 6bd4ff8f-ea6a-4084-ac58-e7a67446ce1c
ms.openlocfilehash: ac1dc4f74a8e8f3ad2e84c6d50239ec827306c28
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2019
ms.locfileid: "74283535"
---
# <a name="documentviewer-styles-and-templates"></a><span data-ttu-id="9b213-102">DocumentViewer 样式和模板</span><span class="sxs-lookup"><span data-stu-id="9b213-102">DocumentViewer Styles and Templates</span></span>
<span data-ttu-id="9b213-103">本主题介绍 <xref:System.Windows.Controls.DocumentViewer> 控件的样式和模板。</span><span class="sxs-lookup"><span data-stu-id="9b213-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.DocumentViewer> control.</span></span> <span data-ttu-id="9b213-104">您可以修改默认 <xref:System.Windows.Controls.ControlTemplate> 以使控件具有独特的外观。</span><span class="sxs-lookup"><span data-stu-id="9b213-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="9b213-105">有关详细信息，请参阅为[控件创建模板](../../../desktop-wpf/themes/how-to-create-apply-template.md)。</span><span class="sxs-lookup"><span data-stu-id="9b213-105">For more information, see [Create a template for a control](../../../desktop-wpf/themes/how-to-create-apply-template.md).</span></span>  
  
## <a name="documentviewer-parts"></a><span data-ttu-id="9b213-106">DocumentViewer 部件</span><span class="sxs-lookup"><span data-stu-id="9b213-106">DocumentViewer Parts</span></span>  
 <span data-ttu-id="9b213-107">下表列出了 <xref:System.Windows.Controls.DocumentViewer> 控件的已命名部分。</span><span class="sxs-lookup"><span data-stu-id="9b213-107">The following table lists the named parts for the <xref:System.Windows.Controls.DocumentViewer> control.</span></span>  
  
|<span data-ttu-id="9b213-108">部件</span><span class="sxs-lookup"><span data-stu-id="9b213-108">Part</span></span>|<span data-ttu-id="9b213-109">类型</span><span class="sxs-lookup"><span data-stu-id="9b213-109">Type</span></span>|<span data-ttu-id="9b213-110">说明</span><span class="sxs-lookup"><span data-stu-id="9b213-110">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="9b213-111">PART_ContentHost</span><span class="sxs-lookup"><span data-stu-id="9b213-111">PART_ContentHost</span></span>|<xref:System.Windows.Controls.ScrollViewer>|<span data-ttu-id="9b213-112">内容和滚动区域。</span><span class="sxs-lookup"><span data-stu-id="9b213-112">The content and scrolling area.</span></span>|  
|<span data-ttu-id="9b213-113">PART_FindToolBarHost</span><span class="sxs-lookup"><span data-stu-id="9b213-113">PART_FindToolBarHost</span></span>|<xref:System.Windows.Controls.ContentControl>|<span data-ttu-id="9b213-114">默认情况下的搜索框。</span><span class="sxs-lookup"><span data-stu-id="9b213-114">The search box, at the bottom by default.</span></span>|  
  
## <a name="documentviewer-states"></a><span data-ttu-id="9b213-115">DocumentViewer 状态</span><span class="sxs-lookup"><span data-stu-id="9b213-115">DocumentViewer States</span></span>  
 <span data-ttu-id="9b213-116">下表列出了 <xref:System.Windows.Controls.DocumentViewer> 控件的可视状态。</span><span class="sxs-lookup"><span data-stu-id="9b213-116">The following table lists the visual states for the <xref:System.Windows.Controls.DocumentViewer> control.</span></span>  
  
|<span data-ttu-id="9b213-117">VisualState 名称</span><span class="sxs-lookup"><span data-stu-id="9b213-117">VisualState Name</span></span>|<span data-ttu-id="9b213-118">VisualStateGroup 名称</span><span class="sxs-lookup"><span data-stu-id="9b213-118">VisualStateGroup Name</span></span>|<span data-ttu-id="9b213-119">说明</span><span class="sxs-lookup"><span data-stu-id="9b213-119">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="9b213-120">有效</span><span class="sxs-lookup"><span data-stu-id="9b213-120">Valid</span></span>|<span data-ttu-id="9b213-121">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="9b213-121">ValidationStates</span></span>|<span data-ttu-id="9b213-122">控件使用 <xref:System.Windows.Controls.Validation> 类，并且 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 附加属性是 `false`。</span><span class="sxs-lookup"><span data-stu-id="9b213-122">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="9b213-123">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="9b213-123">InvalidFocused</span></span>|<span data-ttu-id="9b213-124">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="9b213-124">ValidationStates</span></span>|<span data-ttu-id="9b213-125"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 附加属性是控件具有焦点 `true`。</span><span class="sxs-lookup"><span data-stu-id="9b213-125">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="9b213-126">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="9b213-126">InvalidUnfocused</span></span>|<span data-ttu-id="9b213-127">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="9b213-127">ValidationStates</span></span>|<span data-ttu-id="9b213-128"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 附加属性是 `true` 控件没有焦点。</span><span class="sxs-lookup"><span data-stu-id="9b213-128">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="documentviewer-controltemplate-example"></a><span data-ttu-id="9b213-129">DocumentViewer System.windows.controls.controltemplate> 示例</span><span class="sxs-lookup"><span data-stu-id="9b213-129">DocumentViewer ControlTemplate Example</span></span>  
 <span data-ttu-id="9b213-130">下面的示例演示如何为 <xref:System.Windows.Controls.DocumentViewer> 控件定义 <xref:System.Windows.Controls.ControlTemplate>。</span><span class="sxs-lookup"><span data-stu-id="9b213-130">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.DocumentViewer> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#DocumentViewer](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/documentviewer.xaml#documentviewer)]  
  
 <span data-ttu-id="9b213-131">上一示例使用了一个或多个以下资源。</span><span class="sxs-lookup"><span data-stu-id="9b213-131">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="9b213-132">有关完整示例，请参阅[使用 ControlTemplates 设置样式示例](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating)。</span><span class="sxs-lookup"><span data-stu-id="9b213-132">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9b213-133">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9b213-133">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="9b213-134">控件样式和模板</span><span class="sxs-lookup"><span data-stu-id="9b213-134">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="9b213-135">控件自定义</span><span class="sxs-lookup"><span data-stu-id="9b213-135">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="9b213-136">样式设置和模板化</span><span class="sxs-lookup"><span data-stu-id="9b213-136">Styling and Templating</span></span>](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [<span data-ttu-id="9b213-137">为控件创建模板</span><span class="sxs-lookup"><span data-stu-id="9b213-137">Create a template for a control</span></span>](../../../desktop-wpf/themes/how-to-create-apply-template.md)
