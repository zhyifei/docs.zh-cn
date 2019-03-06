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
ms.openlocfilehash: b120359e63c2916e82b79b2f7b7f1aa5426be99c
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/05/2019
ms.locfileid: "57369638"
---
# <a name="documentviewer-styles-and-templates"></a><span data-ttu-id="60e0d-102">DocumentViewer 样式和模板</span><span class="sxs-lookup"><span data-stu-id="60e0d-102">DocumentViewer Styles and Templates</span></span>
<span data-ttu-id="60e0d-103">本主题介绍的样式和模板的<xref:System.Windows.Controls.DocumentViewer>控件。</span><span class="sxs-lookup"><span data-stu-id="60e0d-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.DocumentViewer> control.</span></span> <span data-ttu-id="60e0d-104">可以修改默认<xref:System.Windows.Controls.ControlTemplate>为控件提供唯一外观。</span><span class="sxs-lookup"><span data-stu-id="60e0d-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="60e0d-105">有关详细信息，请参阅[通过创建 ControlTemplate 自定义现有控件的外观](customizing-the-appearance-of-an-existing-control.md)。</span><span class="sxs-lookup"><span data-stu-id="60e0d-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="documentviewer-parts"></a><span data-ttu-id="60e0d-106">DocumentViewer 部件</span><span class="sxs-lookup"><span data-stu-id="60e0d-106">DocumentViewer Parts</span></span>  
 <span data-ttu-id="60e0d-107">下表列出了用于命名的部件<xref:System.Windows.Controls.DocumentViewer>控件。</span><span class="sxs-lookup"><span data-stu-id="60e0d-107">The following table lists the named parts for the <xref:System.Windows.Controls.DocumentViewer> control.</span></span>  
  
|<span data-ttu-id="60e0d-108">部件</span><span class="sxs-lookup"><span data-stu-id="60e0d-108">Part</span></span>|<span data-ttu-id="60e0d-109">类型</span><span class="sxs-lookup"><span data-stu-id="60e0d-109">Type</span></span>|<span data-ttu-id="60e0d-110">描述</span><span class="sxs-lookup"><span data-stu-id="60e0d-110">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="60e0d-111">PART_ContentHost</span><span class="sxs-lookup"><span data-stu-id="60e0d-111">PART_ContentHost</span></span>|<xref:System.Windows.Controls.ScrollViewer>|<span data-ttu-id="60e0d-112">内容和滚动区域。</span><span class="sxs-lookup"><span data-stu-id="60e0d-112">The content and scrolling area.</span></span>|  
|<span data-ttu-id="60e0d-113">PART_FindToolBarHost</span><span class="sxs-lookup"><span data-stu-id="60e0d-113">PART_FindToolBarHost</span></span>|<xref:System.Windows.Controls.ContentControl>|<span data-ttu-id="60e0d-114">搜索框中，在默认情况下的底部。</span><span class="sxs-lookup"><span data-stu-id="60e0d-114">The search box, at the bottom by default.</span></span>|  
  
## <a name="documentviewer-states"></a><span data-ttu-id="60e0d-115">DocumentViewer 状态</span><span class="sxs-lookup"><span data-stu-id="60e0d-115">DocumentViewer States</span></span>  
 <span data-ttu-id="60e0d-116">下表列出了的可视状态<xref:System.Windows.Controls.DocumentViewer>控件。</span><span class="sxs-lookup"><span data-stu-id="60e0d-116">The following table lists the visual states for the <xref:System.Windows.Controls.DocumentViewer> control.</span></span>  
  
|<span data-ttu-id="60e0d-117">VisualState 名称</span><span class="sxs-lookup"><span data-stu-id="60e0d-117">VisualState Name</span></span>|<span data-ttu-id="60e0d-118">VisualStateGroup 名称</span><span class="sxs-lookup"><span data-stu-id="60e0d-118">VisualStateGroup Name</span></span>|<span data-ttu-id="60e0d-119">描述</span><span class="sxs-lookup"><span data-stu-id="60e0d-119">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="60e0d-120">有效</span><span class="sxs-lookup"><span data-stu-id="60e0d-120">Valid</span></span>|<span data-ttu-id="60e0d-121">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="60e0d-121">ValidationStates</span></span>|<span data-ttu-id="60e0d-122">该控件使用<xref:System.Windows.Controls.Validation>类和<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>附加的属性是`false`。</span><span class="sxs-lookup"><span data-stu-id="60e0d-122">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="60e0d-123">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="60e0d-123">InvalidFocused</span></span>|<span data-ttu-id="60e0d-124">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="60e0d-124">ValidationStates</span></span>|<span data-ttu-id="60e0d-125"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>附加的属性是`true`已在控件有焦点。</span><span class="sxs-lookup"><span data-stu-id="60e0d-125">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="60e0d-126">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="60e0d-126">InvalidUnfocused</span></span>|<span data-ttu-id="60e0d-127">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="60e0d-127">ValidationStates</span></span>|<span data-ttu-id="60e0d-128"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>附加的属性是`true`具有该控件没有焦点。</span><span class="sxs-lookup"><span data-stu-id="60e0d-128">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="documentviewer-controltemplate-example"></a><span data-ttu-id="60e0d-129">DocumentViewer ControlTemplate 示例</span><span class="sxs-lookup"><span data-stu-id="60e0d-129">DocumentViewer ControlTemplate Example</span></span>  
 <span data-ttu-id="60e0d-130">下面的示例演示如何定义<xref:System.Windows.Controls.ControlTemplate>为<xref:System.Windows.Controls.DocumentViewer>控件。</span><span class="sxs-lookup"><span data-stu-id="60e0d-130">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.DocumentViewer> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#DocumentViewer](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/documentviewer.xaml#documentviewer)]  
  
 <span data-ttu-id="60e0d-131">上一示例使用了一个或多个以下资源。</span><span class="sxs-lookup"><span data-stu-id="60e0d-131">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="60e0d-132">有关完整示例，请参阅[使用 ControlTemplates 设置样式示例](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating)。</span><span class="sxs-lookup"><span data-stu-id="60e0d-132">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="60e0d-133">请参阅</span><span class="sxs-lookup"><span data-stu-id="60e0d-133">See also</span></span>
- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="60e0d-134">控件样式和模板</span><span class="sxs-lookup"><span data-stu-id="60e0d-134">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="60e0d-135">控件自定义</span><span class="sxs-lookup"><span data-stu-id="60e0d-135">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="60e0d-136">样式设置和模板化</span><span class="sxs-lookup"><span data-stu-id="60e0d-136">Styling and Templating</span></span>](styling-and-templating.md)
- [<span data-ttu-id="60e0d-137">通过创建 ControlTemplate 自定义现有控件的外观</span><span class="sxs-lookup"><span data-stu-id="60e0d-137">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](customizing-the-appearance-of-an-existing-control.md)
