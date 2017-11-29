---
title: "Window 样式和模板"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- parts [WPF], Window
- templates [WPF], Window
- styles [WPF], Window
- ControlTemplate [WPF], Window
- Window [WPF], styles and templates
- states [WPF], Window
ms.assetid: 2dfdf025-347b-4342-bf28-95206c273f35
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 0415bfae8e1065759efaac1a779655444451fa24
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="window-styles-and-templates"></a><span data-ttu-id="aa3c3-102">Window 样式和模板</span><span class="sxs-lookup"><span data-stu-id="aa3c3-102">Window Styles and Templates</span></span>
<span data-ttu-id="aa3c3-103">本主题介绍的样式和模板的<xref:System.Windows.Window>控件。</span><span class="sxs-lookup"><span data-stu-id="aa3c3-103">This topic describes the styles and templates for the <xref:System.Windows.Window> control.</span></span> <span data-ttu-id="aa3c3-104">你可以修改默认<xref:System.Windows.Controls.ControlTemplate>提供独特外观的控件。</span><span class="sxs-lookup"><span data-stu-id="aa3c3-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="aa3c3-105">有关详细信息，请参阅[通过创建 ControlTemplate 自定义现有控件的外观](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)。</span><span class="sxs-lookup"><span data-stu-id="aa3c3-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="window-parts"></a><span data-ttu-id="aa3c3-106">窗口部分</span><span class="sxs-lookup"><span data-stu-id="aa3c3-106">Window Parts</span></span>  
 <span data-ttu-id="aa3c3-107"><xref:System.Windows.Window>控件不具有任何已命名的部件。</span><span class="sxs-lookup"><span data-stu-id="aa3c3-107">The <xref:System.Windows.Window> control does not have any named parts.</span></span>  
  
## <a name="window-states"></a><span data-ttu-id="aa3c3-108">窗口状态</span><span class="sxs-lookup"><span data-stu-id="aa3c3-108">Window States</span></span>  
 <span data-ttu-id="aa3c3-109">下表列出的可视状态<xref:System.Windows.Window>控件。</span><span class="sxs-lookup"><span data-stu-id="aa3c3-109">The following table lists the visual states for the <xref:System.Windows.Window> control.</span></span>  
  
|<span data-ttu-id="aa3c3-110">VisualState 名称</span><span class="sxs-lookup"><span data-stu-id="aa3c3-110">VisualState Name</span></span>|<span data-ttu-id="aa3c3-111">VisualStateGroup 名称</span><span class="sxs-lookup"><span data-stu-id="aa3c3-111">VisualStateGroup Name</span></span>|<span data-ttu-id="aa3c3-112">描述</span><span class="sxs-lookup"><span data-stu-id="aa3c3-112">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="aa3c3-113">有效</span><span class="sxs-lookup"><span data-stu-id="aa3c3-113">Valid</span></span>|<span data-ttu-id="aa3c3-114">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="aa3c3-114">ValidationStates</span></span>|<span data-ttu-id="aa3c3-115">该控件使用<xref:System.Windows.Controls.Validation>类和<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>附加的属性`false`。</span><span class="sxs-lookup"><span data-stu-id="aa3c3-115">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="aa3c3-116">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="aa3c3-116">InvalidFocused</span></span>|<span data-ttu-id="aa3c3-117">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="aa3c3-117">ValidationStates</span></span>|<span data-ttu-id="aa3c3-118"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>附加的属性`true`已在控件有焦点。</span><span class="sxs-lookup"><span data-stu-id="aa3c3-118">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="aa3c3-119">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="aa3c3-119">InvalidUnfocused</span></span>|<span data-ttu-id="aa3c3-120">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="aa3c3-120">ValidationStates</span></span>|<span data-ttu-id="aa3c3-121"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>附加的属性`true`具有该控件没有焦点。</span><span class="sxs-lookup"><span data-stu-id="aa3c3-121">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="window-controltemplate-example"></a><span data-ttu-id="aa3c3-122">窗口 ControlTemplate 示例</span><span class="sxs-lookup"><span data-stu-id="aa3c3-122">Window ControlTemplate Example</span></span>  
 <span data-ttu-id="aa3c3-123">下面的示例演示如何定义<xref:System.Windows.Controls.ControlTemplate>为<xref:System.Windows.Window>控件。</span><span class="sxs-lookup"><span data-stu-id="aa3c3-123">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Window> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Window](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/window.xaml#window)]  
  
 <span data-ttu-id="aa3c3-124"><xref:System.Windows.Controls.ControlTemplate>使用一个或多个以下资源。</span><span class="sxs-lookup"><span data-stu-id="aa3c3-124">The <xref:System.Windows.Controls.ControlTemplate> uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#ResizeGrip](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/resizegrip.xaml#resizegrip)]  
[!code-xaml[ControlTemplateExamples#Resources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="aa3c3-125">有关完整示例，请参阅[使用 ControlTemplates 设置样式示例](http://go.microsoft.com/fwlink/?LinkID=160041)。</span><span class="sxs-lookup"><span data-stu-id="aa3c3-125">For the complete sample, see [Styling with ControlTemplates Sample](http://go.microsoft.com/fwlink/?LinkID=160041).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aa3c3-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="aa3c3-126">See Also</span></span>  
 <xref:System.Windows.FrameworkElement.Style%2A>  
 <xref:System.Windows.Controls.ControlTemplate>  
 [<span data-ttu-id="aa3c3-127">控件样式和模板</span><span class="sxs-lookup"><span data-stu-id="aa3c3-127">Control Styles and Templates</span></span>](../../../../docs/framework/wpf/controls/control-styles-and-templates.md)  
 [<span data-ttu-id="aa3c3-128">控件自定义</span><span class="sxs-lookup"><span data-stu-id="aa3c3-128">Control Customization</span></span>](../../../../docs/framework/wpf/controls/control-customization.md)  
 [<span data-ttu-id="aa3c3-129">样式设置和模板化</span><span class="sxs-lookup"><span data-stu-id="aa3c3-129">Styling and Templating</span></span>](../../../../docs/framework/wpf/controls/styling-and-templating.md)  
 [<span data-ttu-id="aa3c3-130">通过创建 ControlTemplate 自定义现有控件的外观</span><span class="sxs-lookup"><span data-stu-id="aa3c3-130">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)
