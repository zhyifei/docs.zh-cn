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
ms.openlocfilehash: 48fe5887ebad86efad1b1aae39ba03a26fda3bd8
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2019
ms.locfileid: "73460015"
---
# <a name="window-styles-and-templates"></a><span data-ttu-id="17865-102">Window 样式和模板</span><span class="sxs-lookup"><span data-stu-id="17865-102">Window Styles and Templates</span></span>
<span data-ttu-id="17865-103">本主题介绍 <xref:System.Windows.Window> 控件的样式和模板。</span><span class="sxs-lookup"><span data-stu-id="17865-103">This topic describes the styles and templates for the <xref:System.Windows.Window> control.</span></span> <span data-ttu-id="17865-104">您可以修改默认 <xref:System.Windows.Controls.ControlTemplate> 以使控件具有独特的外观。</span><span class="sxs-lookup"><span data-stu-id="17865-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="17865-105">有关详细信息，请参阅[通过创建 ControlTemplate 自定义现有控件的外观](customizing-the-appearance-of-an-existing-control.md)。</span><span class="sxs-lookup"><span data-stu-id="17865-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="window-parts"></a><span data-ttu-id="17865-106">窗口部件</span><span class="sxs-lookup"><span data-stu-id="17865-106">Window Parts</span></span>  
 <span data-ttu-id="17865-107"><xref:System.Windows.Window> 控件没有任何命名部分。</span><span class="sxs-lookup"><span data-stu-id="17865-107">The <xref:System.Windows.Window> control does not have any named parts.</span></span>  
  
## <a name="window-states"></a><span data-ttu-id="17865-108">窗口状态</span><span class="sxs-lookup"><span data-stu-id="17865-108">Window States</span></span>  
 <span data-ttu-id="17865-109">下表列出了 <xref:System.Windows.Window> 控件的可视状态。</span><span class="sxs-lookup"><span data-stu-id="17865-109">The following table lists the visual states for the <xref:System.Windows.Window> control.</span></span>  
  
|<span data-ttu-id="17865-110">VisualState 名称</span><span class="sxs-lookup"><span data-stu-id="17865-110">VisualState Name</span></span>|<span data-ttu-id="17865-111">VisualStateGroup 名称</span><span class="sxs-lookup"><span data-stu-id="17865-111">VisualStateGroup Name</span></span>|<span data-ttu-id="17865-112">描述</span><span class="sxs-lookup"><span data-stu-id="17865-112">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="17865-113">有效</span><span class="sxs-lookup"><span data-stu-id="17865-113">Valid</span></span>|<span data-ttu-id="17865-114">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="17865-114">ValidationStates</span></span>|<span data-ttu-id="17865-115">控件使用 <xref:System.Windows.Controls.Validation> 类，并且 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 附加属性是 `false`。</span><span class="sxs-lookup"><span data-stu-id="17865-115">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="17865-116">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="17865-116">InvalidFocused</span></span>|<span data-ttu-id="17865-117">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="17865-117">ValidationStates</span></span>|<span data-ttu-id="17865-118"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 附加属性是控件具有焦点 `true`。</span><span class="sxs-lookup"><span data-stu-id="17865-118">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="17865-119">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="17865-119">InvalidUnfocused</span></span>|<span data-ttu-id="17865-120">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="17865-120">ValidationStates</span></span>|<span data-ttu-id="17865-121"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 附加属性是 `true` 控件没有焦点。</span><span class="sxs-lookup"><span data-stu-id="17865-121">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="window-controltemplate-example"></a><span data-ttu-id="17865-122">Window System.windows.controls.controltemplate> 示例</span><span class="sxs-lookup"><span data-stu-id="17865-122">Window ControlTemplate Example</span></span>  
 <span data-ttu-id="17865-123">下面的示例演示如何为 <xref:System.Windows.Window> 控件定义 <xref:System.Windows.Controls.ControlTemplate>。</span><span class="sxs-lookup"><span data-stu-id="17865-123">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Window> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Window](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/window.xaml#window)]  
  
 <span data-ttu-id="17865-124"><xref:System.Windows.Controls.ControlTemplate> 使用以下一个或多个资源。</span><span class="sxs-lookup"><span data-stu-id="17865-124">The <xref:System.Windows.Controls.ControlTemplate> uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#ResizeGrip](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/resizegrip.xaml#resizegrip)]  
[!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="17865-125">有关完整示例，请参阅[使用 ControlTemplates 设置样式示例](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating)。</span><span class="sxs-lookup"><span data-stu-id="17865-125">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="17865-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="17865-126">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="17865-127">控件样式和模板</span><span class="sxs-lookup"><span data-stu-id="17865-127">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="17865-128">控件自定义</span><span class="sxs-lookup"><span data-stu-id="17865-128">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="17865-129">样式设置和模板化</span><span class="sxs-lookup"><span data-stu-id="17865-129">Styling and Templating</span></span>](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [<span data-ttu-id="17865-130">通过创建 ControlTemplate 自定义现有控件的外观</span><span class="sxs-lookup"><span data-stu-id="17865-130">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](customizing-the-appearance-of-an-existing-control.md)
