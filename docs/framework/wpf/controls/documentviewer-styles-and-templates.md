---
title: "DocumentViewer 样式和模板"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- templates [WPF], DocumentViewer
- DocumentViewer [WPF], styles and templates
- states [WPF], DocumentViewer
- ControlTemplate [WPF], DocumentViewer
- parts [WPF], DocumentViewer
- styles [WPF], DocumentViewer
ms.assetid: 6bd4ff8f-ea6a-4084-ac58-e7a67446ce1c
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 33631b0a63b69f848cb3f09b4dcb617fb328b06c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="documentviewer-styles-and-templates"></a><span data-ttu-id="33e78-102">DocumentViewer 样式和模板</span><span class="sxs-lookup"><span data-stu-id="33e78-102">DocumentViewer Styles and Templates</span></span>
<span data-ttu-id="33e78-103">本主题介绍的样式和模板的<xref:System.Windows.Controls.DocumentViewer>控件。</span><span class="sxs-lookup"><span data-stu-id="33e78-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.DocumentViewer> control.</span></span> <span data-ttu-id="33e78-104">你可以修改默认<xref:System.Windows.Controls.ControlTemplate>提供独特外观的控件。</span><span class="sxs-lookup"><span data-stu-id="33e78-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="33e78-105">有关详细信息，请参阅[通过创建 ControlTemplate 自定义现有控件的外观](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)。</span><span class="sxs-lookup"><span data-stu-id="33e78-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="documentviewer-parts"></a><span data-ttu-id="33e78-106">DocumentViewer 部件</span><span class="sxs-lookup"><span data-stu-id="33e78-106">DocumentViewer Parts</span></span>  
 <span data-ttu-id="33e78-107">下表列出的命名的部件<xref:System.Windows.Controls.DocumentViewer>控件。</span><span class="sxs-lookup"><span data-stu-id="33e78-107">The following table lists the named parts for the <xref:System.Windows.Controls.DocumentViewer> control.</span></span>  
  
|<span data-ttu-id="33e78-108">部件</span><span class="sxs-lookup"><span data-stu-id="33e78-108">Part</span></span>|<span data-ttu-id="33e78-109">类型</span><span class="sxs-lookup"><span data-stu-id="33e78-109">Type</span></span>|<span data-ttu-id="33e78-110">描述</span><span class="sxs-lookup"><span data-stu-id="33e78-110">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="33e78-111">PART_ContentHost</span><span class="sxs-lookup"><span data-stu-id="33e78-111">PART_ContentHost</span></span>|<xref:System.Windows.Controls.ScrollViewer>|<span data-ttu-id="33e78-112">内容和滚动区域。</span><span class="sxs-lookup"><span data-stu-id="33e78-112">The content and scrolling area.</span></span>|  
|<span data-ttu-id="33e78-113">PART_FindToolBarHost</span><span class="sxs-lookup"><span data-stu-id="33e78-113">PART_FindToolBarHost</span></span>|<xref:System.Windows.Controls.ContentControl>|<span data-ttu-id="33e78-114">搜索框中，在默认情况下的底部。</span><span class="sxs-lookup"><span data-stu-id="33e78-114">The search box, at the bottom by default.</span></span>|  
  
## <a name="documentviewer-states"></a><span data-ttu-id="33e78-115">DocumentViewer 状态</span><span class="sxs-lookup"><span data-stu-id="33e78-115">DocumentViewer States</span></span>  
 <span data-ttu-id="33e78-116">下表列出的可视状态<xref:System.Windows.Controls.DocumentViewer>控件。</span><span class="sxs-lookup"><span data-stu-id="33e78-116">The following table lists the visual states for the <xref:System.Windows.Controls.DocumentViewer> control.</span></span>  
  
|<span data-ttu-id="33e78-117">VisualState 名称</span><span class="sxs-lookup"><span data-stu-id="33e78-117">VisualState Name</span></span>|<span data-ttu-id="33e78-118">VisualStateGroup 名称</span><span class="sxs-lookup"><span data-stu-id="33e78-118">VisualStateGroup Name</span></span>|<span data-ttu-id="33e78-119">描述</span><span class="sxs-lookup"><span data-stu-id="33e78-119">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="33e78-120">有效</span><span class="sxs-lookup"><span data-stu-id="33e78-120">Valid</span></span>|<span data-ttu-id="33e78-121">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="33e78-121">ValidationStates</span></span>|<span data-ttu-id="33e78-122">该控件使用<xref:System.Windows.Controls.Validation>类和<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>附加的属性`false`。</span><span class="sxs-lookup"><span data-stu-id="33e78-122">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="33e78-123">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="33e78-123">InvalidFocused</span></span>|<span data-ttu-id="33e78-124">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="33e78-124">ValidationStates</span></span>|<span data-ttu-id="33e78-125"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>附加的属性`true`已在控件有焦点。</span><span class="sxs-lookup"><span data-stu-id="33e78-125">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="33e78-126">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="33e78-126">InvalidUnfocused</span></span>|<span data-ttu-id="33e78-127">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="33e78-127">ValidationStates</span></span>|<span data-ttu-id="33e78-128"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>附加的属性`true`具有该控件没有焦点。</span><span class="sxs-lookup"><span data-stu-id="33e78-128">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="documentviewer-controltemplate-example"></a><span data-ttu-id="33e78-129">DocumentViewer ControlTemplate 示例</span><span class="sxs-lookup"><span data-stu-id="33e78-129">DocumentViewer ControlTemplate Example</span></span>  
 <span data-ttu-id="33e78-130">下面的示例演示如何定义<xref:System.Windows.Controls.ControlTemplate>为<xref:System.Windows.Controls.DocumentViewer>控件。</span><span class="sxs-lookup"><span data-stu-id="33e78-130">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.DocumentViewer> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#DocumentViewer](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/documentviewer.xaml#documentviewer)]  
  
 <span data-ttu-id="33e78-131">上一示例使用了一个或多个以下资源。</span><span class="sxs-lookup"><span data-stu-id="33e78-131">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="33e78-132">有关完整示例，请参阅[使用 ControlTemplates 设置样式示例](http://go.microsoft.com/fwlink/?LinkID=160041)。</span><span class="sxs-lookup"><span data-stu-id="33e78-132">For the complete sample, see [Styling with ControlTemplates Sample](http://go.microsoft.com/fwlink/?LinkID=160041).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="33e78-133">请参阅</span><span class="sxs-lookup"><span data-stu-id="33e78-133">See Also</span></span>  
 <xref:System.Windows.FrameworkElement.Style%2A>  
 <xref:System.Windows.Controls.ControlTemplate>  
 [<span data-ttu-id="33e78-134">控件样式和模板</span><span class="sxs-lookup"><span data-stu-id="33e78-134">Control Styles and Templates</span></span>](../../../../docs/framework/wpf/controls/control-styles-and-templates.md)  
 [<span data-ttu-id="33e78-135">控件自定义</span><span class="sxs-lookup"><span data-stu-id="33e78-135">Control Customization</span></span>](../../../../docs/framework/wpf/controls/control-customization.md)  
 [<span data-ttu-id="33e78-136">样式设置和模板化</span><span class="sxs-lookup"><span data-stu-id="33e78-136">Styling and Templating</span></span>](../../../../docs/framework/wpf/controls/styling-and-templating.md)  
 [<span data-ttu-id="33e78-137">通过创建 ControlTemplate 自定义现有控件的外观</span><span class="sxs-lookup"><span data-stu-id="33e78-137">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)
