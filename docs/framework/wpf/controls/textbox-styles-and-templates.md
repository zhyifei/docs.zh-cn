---
title: TextBox 样式和模板
ms.date: 03/30/2017
helpviewer_keywords:
- ControlTemplate [WPF], TextBox
- parts [WPF], TextBox
- states [WPF], TextBox
- styles [WPF], TextBox
- templates [WPF], TextBox
- TextBox [WPF], styles and templates
ms.assetid: aa99130c-43a1-450f-9b46-c40ae0db0cca
ms.openlocfilehash: 7c4680a3ea9352e94d628e786fc8e4fd71018d00
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2019
ms.locfileid: "73458253"
---
# <a name="textbox-styles-and-templates"></a><span data-ttu-id="4583b-102">TextBox 样式和模板</span><span class="sxs-lookup"><span data-stu-id="4583b-102">TextBox Styles and Templates</span></span>
<span data-ttu-id="4583b-103">本主题介绍 <xref:System.Windows.Controls.TextBox> 控件的样式和模板。</span><span class="sxs-lookup"><span data-stu-id="4583b-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.TextBox> control.</span></span> <span data-ttu-id="4583b-104">您可以修改默认 <xref:System.Windows.Controls.ControlTemplate> 以使控件具有独特的外观。</span><span class="sxs-lookup"><span data-stu-id="4583b-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="4583b-105">有关详细信息，请参阅[通过创建 ControlTemplate 自定义现有控件的外观](customizing-the-appearance-of-an-existing-control.md)。</span><span class="sxs-lookup"><span data-stu-id="4583b-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="textbox-parts"></a><span data-ttu-id="4583b-106">TextBox 部分</span><span class="sxs-lookup"><span data-stu-id="4583b-106">TextBox Parts</span></span>  
 <span data-ttu-id="4583b-107">下表列出了 <xref:System.Windows.Controls.TextBox> 控件的已命名部分。</span><span class="sxs-lookup"><span data-stu-id="4583b-107">The following table lists the named parts for the <xref:System.Windows.Controls.TextBox> control.</span></span>  
  
|<span data-ttu-id="4583b-108">部件</span><span class="sxs-lookup"><span data-stu-id="4583b-108">Part</span></span>|<span data-ttu-id="4583b-109">键入</span><span class="sxs-lookup"><span data-stu-id="4583b-109">Type</span></span>|<span data-ttu-id="4583b-110">描述</span><span class="sxs-lookup"><span data-stu-id="4583b-110">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="4583b-111">PART_ContentHost</span><span class="sxs-lookup"><span data-stu-id="4583b-111">PART_ContentHost</span></span>|<xref:System.Windows.FrameworkElement>|<span data-ttu-id="4583b-112">可包含 <xref:System.Windows.FrameworkElement>的可视元素。</span><span class="sxs-lookup"><span data-stu-id="4583b-112">A visual element that can contain a <xref:System.Windows.FrameworkElement>.</span></span> <span data-ttu-id="4583b-113"><xref:System.Windows.Controls.TextBox> 的文本显示在此元素中。</span><span class="sxs-lookup"><span data-stu-id="4583b-113">The text of the <xref:System.Windows.Controls.TextBox> is displayed in this element.</span></span>|  
  
## <a name="textbox-states"></a><span data-ttu-id="4583b-114">TextBox 状态</span><span class="sxs-lookup"><span data-stu-id="4583b-114">TextBox States</span></span>  
 <span data-ttu-id="4583b-115">下表列出了 <xref:System.Windows.Controls.TextBox> 控件的可视状态。</span><span class="sxs-lookup"><span data-stu-id="4583b-115">The following table lists the visual states for the <xref:System.Windows.Controls.TextBox> control.</span></span>  
  
|<span data-ttu-id="4583b-116">VisualState 名称</span><span class="sxs-lookup"><span data-stu-id="4583b-116">VisualState Name</span></span>|<span data-ttu-id="4583b-117">VisualStateGroup 名称</span><span class="sxs-lookup"><span data-stu-id="4583b-117">VisualStateGroup Name</span></span>|<span data-ttu-id="4583b-118">描述</span><span class="sxs-lookup"><span data-stu-id="4583b-118">Description</span></span>|  
|----------------------|---------------------------|-----------------|  
|<span data-ttu-id="4583b-119">普通</span><span class="sxs-lookup"><span data-stu-id="4583b-119">Normal</span></span>|<span data-ttu-id="4583b-120">CommonStates</span><span class="sxs-lookup"><span data-stu-id="4583b-120">CommonStates</span></span>|<span data-ttu-id="4583b-121">默认状态。</span><span class="sxs-lookup"><span data-stu-id="4583b-121">The default state.</span></span>|  
|<span data-ttu-id="4583b-122">MouseOver</span><span class="sxs-lookup"><span data-stu-id="4583b-122">MouseOver</span></span>|<span data-ttu-id="4583b-123">CommonStates</span><span class="sxs-lookup"><span data-stu-id="4583b-123">CommonStates</span></span>|<span data-ttu-id="4583b-124">鼠标指针悬停在控件上。</span><span class="sxs-lookup"><span data-stu-id="4583b-124">The mouse pointer is positioned over the control.</span></span>|  
|<span data-ttu-id="4583b-125">Disabled</span><span class="sxs-lookup"><span data-stu-id="4583b-125">Disabled</span></span>|<span data-ttu-id="4583b-126">CommonStates</span><span class="sxs-lookup"><span data-stu-id="4583b-126">CommonStates</span></span>|<span data-ttu-id="4583b-127">已禁用控件。</span><span class="sxs-lookup"><span data-stu-id="4583b-127">The control is disabled.</span></span>|  
|<span data-ttu-id="4583b-128">ReadOnly</span><span class="sxs-lookup"><span data-stu-id="4583b-128">ReadOnly</span></span>|<span data-ttu-id="4583b-129">CommonStates</span><span class="sxs-lookup"><span data-stu-id="4583b-129">CommonStates</span></span>|<span data-ttu-id="4583b-130">用户无法更改 <xref:System.Windows.Controls.TextBox>中的文本。</span><span class="sxs-lookup"><span data-stu-id="4583b-130">The user cannot change the text in the <xref:System.Windows.Controls.TextBox>.</span></span>|  
|<span data-ttu-id="4583b-131">已设定焦点</span><span class="sxs-lookup"><span data-stu-id="4583b-131">Focused</span></span>|<span data-ttu-id="4583b-132">FocusStates</span><span class="sxs-lookup"><span data-stu-id="4583b-132">FocusStates</span></span>|<span data-ttu-id="4583b-133">控件有焦点。</span><span class="sxs-lookup"><span data-stu-id="4583b-133">The control has focus.</span></span>|  
|<span data-ttu-id="4583b-134">失去焦点</span><span class="sxs-lookup"><span data-stu-id="4583b-134">Unfocused</span></span>|<span data-ttu-id="4583b-135">FocusStates</span><span class="sxs-lookup"><span data-stu-id="4583b-135">FocusStates</span></span>|<span data-ttu-id="4583b-136">控件没有焦点。</span><span class="sxs-lookup"><span data-stu-id="4583b-136">The control does not have focus.</span></span>|  
|<span data-ttu-id="4583b-137">有效</span><span class="sxs-lookup"><span data-stu-id="4583b-137">Valid</span></span>|<span data-ttu-id="4583b-138">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="4583b-138">ValidationStates</span></span>|<span data-ttu-id="4583b-139">控件使用 <xref:System.Windows.Controls.Validation> 类，并且 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 附加属性是 `false`。</span><span class="sxs-lookup"><span data-stu-id="4583b-139">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="4583b-140">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="4583b-140">InvalidFocused</span></span>|<span data-ttu-id="4583b-141">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="4583b-141">ValidationStates</span></span>|<span data-ttu-id="4583b-142"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 附加属性是控件具有焦点 `true`。</span><span class="sxs-lookup"><span data-stu-id="4583b-142">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="4583b-143">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="4583b-143">InvalidUnfocused</span></span>|<span data-ttu-id="4583b-144">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="4583b-144">ValidationStates</span></span>|<span data-ttu-id="4583b-145"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 附加属性是 `true` 控件没有焦点。</span><span class="sxs-lookup"><span data-stu-id="4583b-145">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="textbox-controltemplate-example"></a><span data-ttu-id="4583b-146">TextBox System.windows.controls.controltemplate> 示例</span><span class="sxs-lookup"><span data-stu-id="4583b-146">TextBox ControlTemplate Example</span></span>  
 <span data-ttu-id="4583b-147">下面的示例演示如何为 <xref:System.Windows.Controls.TextBox> 控件定义 <xref:System.Windows.Controls.ControlTemplate>。</span><span class="sxs-lookup"><span data-stu-id="4583b-147">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.TextBox> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#TextBox](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/textbox.xaml#textbox)]  
  
 <span data-ttu-id="4583b-148">上一示例使用了一个或多个以下资源。</span><span class="sxs-lookup"><span data-stu-id="4583b-148">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="4583b-149">有关完整示例，请参阅[使用 ControlTemplates 设置样式示例](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating)。</span><span class="sxs-lookup"><span data-stu-id="4583b-149">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4583b-150">请参阅</span><span class="sxs-lookup"><span data-stu-id="4583b-150">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="4583b-151">控件样式和模板</span><span class="sxs-lookup"><span data-stu-id="4583b-151">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="4583b-152">控件自定义</span><span class="sxs-lookup"><span data-stu-id="4583b-152">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="4583b-153">样式设置和模板化</span><span class="sxs-lookup"><span data-stu-id="4583b-153">Styling and Templating</span></span>](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [<span data-ttu-id="4583b-154">通过创建 ControlTemplate 自定义现有控件的外观</span><span class="sxs-lookup"><span data-stu-id="4583b-154">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](customizing-the-appearance-of-an-existing-control.md)
