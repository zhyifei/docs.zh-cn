---
title: Window 样式和模板
ms.date: 03/30/2017
helpviewer_keywords:
- parts [WPF], Window
- templates [WPF], Window
- styles [WPF], Window
- ControlTemplate [WPF], Window
- Window [WPF], styles and templates
- states [WPF], Window
ms.assetid: 2dfdf025-347b-4342-bf28-95206c273f35
ms.openlocfilehash: 9095405c47d4e113a2f0e7d572ba1209718f4b37
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54640077"
---
# <a name="window-styles-and-templates"></a><span data-ttu-id="d7360-102">Window 样式和模板</span><span class="sxs-lookup"><span data-stu-id="d7360-102">Window Styles and Templates</span></span>
<span data-ttu-id="d7360-103">本主题介绍的样式和模板的<xref:System.Windows.Window>控件。</span><span class="sxs-lookup"><span data-stu-id="d7360-103">This topic describes the styles and templates for the <xref:System.Windows.Window> control.</span></span> <span data-ttu-id="d7360-104">可以修改默认<xref:System.Windows.Controls.ControlTemplate>为控件提供唯一外观。</span><span class="sxs-lookup"><span data-stu-id="d7360-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="d7360-105">有关详细信息，请参阅[通过创建 ControlTemplate 自定义现有控件的外观](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)。</span><span class="sxs-lookup"><span data-stu-id="d7360-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="window-parts"></a><span data-ttu-id="d7360-106">窗口部分</span><span class="sxs-lookup"><span data-stu-id="d7360-106">Window Parts</span></span>  
 <span data-ttu-id="d7360-107"><xref:System.Windows.Window>控件没有任何命名的部件。</span><span class="sxs-lookup"><span data-stu-id="d7360-107">The <xref:System.Windows.Window> control does not have any named parts.</span></span>  
  
## <a name="window-states"></a><span data-ttu-id="d7360-108">窗口状态</span><span class="sxs-lookup"><span data-stu-id="d7360-108">Window States</span></span>  
 <span data-ttu-id="d7360-109">下表列出了的可视状态<xref:System.Windows.Window>控件。</span><span class="sxs-lookup"><span data-stu-id="d7360-109">The following table lists the visual states for the <xref:System.Windows.Window> control.</span></span>  
  
|<span data-ttu-id="d7360-110">VisualState 名称</span><span class="sxs-lookup"><span data-stu-id="d7360-110">VisualState Name</span></span>|<span data-ttu-id="d7360-111">VisualStateGroup 名称</span><span class="sxs-lookup"><span data-stu-id="d7360-111">VisualStateGroup Name</span></span>|<span data-ttu-id="d7360-112">描述</span><span class="sxs-lookup"><span data-stu-id="d7360-112">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="d7360-113">有效</span><span class="sxs-lookup"><span data-stu-id="d7360-113">Valid</span></span>|<span data-ttu-id="d7360-114">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="d7360-114">ValidationStates</span></span>|<span data-ttu-id="d7360-115">该控件使用<xref:System.Windows.Controls.Validation>类和<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>附加的属性是`false`。</span><span class="sxs-lookup"><span data-stu-id="d7360-115">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="d7360-116">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="d7360-116">InvalidFocused</span></span>|<span data-ttu-id="d7360-117">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="d7360-117">ValidationStates</span></span>|<span data-ttu-id="d7360-118"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>附加的属性是`true`已在控件有焦点。</span><span class="sxs-lookup"><span data-stu-id="d7360-118">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="d7360-119">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="d7360-119">InvalidUnfocused</span></span>|<span data-ttu-id="d7360-120">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="d7360-120">ValidationStates</span></span>|<span data-ttu-id="d7360-121"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>附加的属性是`true`具有该控件没有焦点。</span><span class="sxs-lookup"><span data-stu-id="d7360-121">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="window-controltemplate-example"></a><span data-ttu-id="d7360-122">窗口 ControlTemplate 示例</span><span class="sxs-lookup"><span data-stu-id="d7360-122">Window ControlTemplate Example</span></span>  
 <span data-ttu-id="d7360-123">下面的示例演示如何定义<xref:System.Windows.Controls.ControlTemplate>为<xref:System.Windows.Window>控件。</span><span class="sxs-lookup"><span data-stu-id="d7360-123">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Window> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Window](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/window.xaml#window)]  
  
 <span data-ttu-id="d7360-124"><xref:System.Windows.Controls.ControlTemplate>使用一个或多个以下资源。</span><span class="sxs-lookup"><span data-stu-id="d7360-124">The <xref:System.Windows.Controls.ControlTemplate> uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#ResizeGrip](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/resizegrip.xaml#resizegrip)]  
[!code-xaml[ControlTemplateExamples#Resources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="d7360-125">有关完整示例，请参阅[使用 ControlTemplates 设置样式示例](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating)。</span><span class="sxs-lookup"><span data-stu-id="d7360-125">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d7360-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="d7360-126">See also</span></span>
- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="d7360-127">控件样式和模板</span><span class="sxs-lookup"><span data-stu-id="d7360-127">Control Styles and Templates</span></span>](../../../../docs/framework/wpf/controls/control-styles-and-templates.md)
- [<span data-ttu-id="d7360-128">控件自定义</span><span class="sxs-lookup"><span data-stu-id="d7360-128">Control Customization</span></span>](../../../../docs/framework/wpf/controls/control-customization.md)
- [<span data-ttu-id="d7360-129">样式设置和模板化</span><span class="sxs-lookup"><span data-stu-id="d7360-129">Styling and Templating</span></span>](../../../../docs/framework/wpf/controls/styling-and-templating.md)
- [<span data-ttu-id="d7360-130">通过创建 ControlTemplate 自定义现有控件的外观</span><span class="sxs-lookup"><span data-stu-id="d7360-130">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)
