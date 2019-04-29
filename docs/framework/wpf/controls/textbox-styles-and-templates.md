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
ms.openlocfilehash: ccc89e0e0c8977398ed162b246ff6cdede3b8351
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61790866"
---
# <a name="textbox-styles-and-templates"></a><span data-ttu-id="3bf5b-102">TextBox 样式和模板</span><span class="sxs-lookup"><span data-stu-id="3bf5b-102">TextBox Styles and Templates</span></span>
<span data-ttu-id="3bf5b-103">本主题介绍的样式和模板的<xref:System.Windows.Controls.TextBox>控件。</span><span class="sxs-lookup"><span data-stu-id="3bf5b-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.TextBox> control.</span></span> <span data-ttu-id="3bf5b-104">可以修改默认<xref:System.Windows.Controls.ControlTemplate>为控件提供唯一外观。</span><span class="sxs-lookup"><span data-stu-id="3bf5b-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="3bf5b-105">有关详细信息，请参阅[通过创建 ControlTemplate 自定义现有控件的外观](customizing-the-appearance-of-an-existing-control.md)。</span><span class="sxs-lookup"><span data-stu-id="3bf5b-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="textbox-parts"></a><span data-ttu-id="3bf5b-106">文本框部件</span><span class="sxs-lookup"><span data-stu-id="3bf5b-106">TextBox Parts</span></span>  
 <span data-ttu-id="3bf5b-107">下表列出了用于命名的部件<xref:System.Windows.Controls.TextBox>控件。</span><span class="sxs-lookup"><span data-stu-id="3bf5b-107">The following table lists the named parts for the <xref:System.Windows.Controls.TextBox> control.</span></span>  
  
|<span data-ttu-id="3bf5b-108">部件</span><span class="sxs-lookup"><span data-stu-id="3bf5b-108">Part</span></span>|<span data-ttu-id="3bf5b-109">类型</span><span class="sxs-lookup"><span data-stu-id="3bf5b-109">Type</span></span>|<span data-ttu-id="3bf5b-110">描述</span><span class="sxs-lookup"><span data-stu-id="3bf5b-110">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="3bf5b-111">PART_ContentHost</span><span class="sxs-lookup"><span data-stu-id="3bf5b-111">PART_ContentHost</span></span>|<xref:System.Windows.FrameworkElement>|<span data-ttu-id="3bf5b-112">可以包含一个可见元素<xref:System.Windows.FrameworkElement>。</span><span class="sxs-lookup"><span data-stu-id="3bf5b-112">A visual element that can contain a <xref:System.Windows.FrameworkElement>.</span></span> <span data-ttu-id="3bf5b-113">文本<xref:System.Windows.Controls.TextBox>显示在此元素。</span><span class="sxs-lookup"><span data-stu-id="3bf5b-113">The text of the <xref:System.Windows.Controls.TextBox> is displayed in this element.</span></span>|  
  
## <a name="textbox-states"></a><span data-ttu-id="3bf5b-114">文本框状态</span><span class="sxs-lookup"><span data-stu-id="3bf5b-114">TextBox States</span></span>  
 <span data-ttu-id="3bf5b-115">下表列出了的可视状态<xref:System.Windows.Controls.TextBox>控件。</span><span class="sxs-lookup"><span data-stu-id="3bf5b-115">The following table lists the visual states for the <xref:System.Windows.Controls.TextBox> control.</span></span>  
  
|<span data-ttu-id="3bf5b-116">VisualState 名称</span><span class="sxs-lookup"><span data-stu-id="3bf5b-116">VisualState Name</span></span>|<span data-ttu-id="3bf5b-117">VisualStateGroup 名称</span><span class="sxs-lookup"><span data-stu-id="3bf5b-117">VisualStateGroup Name</span></span>|<span data-ttu-id="3bf5b-118">描述</span><span class="sxs-lookup"><span data-stu-id="3bf5b-118">Description</span></span>|  
|----------------------|---------------------------|-----------------|  
|<span data-ttu-id="3bf5b-119">普通</span><span class="sxs-lookup"><span data-stu-id="3bf5b-119">Normal</span></span>|<span data-ttu-id="3bf5b-120">CommonStates</span><span class="sxs-lookup"><span data-stu-id="3bf5b-120">CommonStates</span></span>|<span data-ttu-id="3bf5b-121">默认状态。</span><span class="sxs-lookup"><span data-stu-id="3bf5b-121">The default state.</span></span>|  
|<span data-ttu-id="3bf5b-122">MouseOver</span><span class="sxs-lookup"><span data-stu-id="3bf5b-122">MouseOver</span></span>|<span data-ttu-id="3bf5b-123">CommonStates</span><span class="sxs-lookup"><span data-stu-id="3bf5b-123">CommonStates</span></span>|<span data-ttu-id="3bf5b-124">鼠标指针悬停在控件上。</span><span class="sxs-lookup"><span data-stu-id="3bf5b-124">The mouse pointer is positioned over the control.</span></span>|  
|<span data-ttu-id="3bf5b-125">已禁用</span><span class="sxs-lookup"><span data-stu-id="3bf5b-125">Disabled</span></span>|<span data-ttu-id="3bf5b-126">CommonStates</span><span class="sxs-lookup"><span data-stu-id="3bf5b-126">CommonStates</span></span>|<span data-ttu-id="3bf5b-127">已禁用控件。</span><span class="sxs-lookup"><span data-stu-id="3bf5b-127">The control is disabled.</span></span>|  
|<span data-ttu-id="3bf5b-128">ReadOnly</span><span class="sxs-lookup"><span data-stu-id="3bf5b-128">ReadOnly</span></span>|<span data-ttu-id="3bf5b-129">CommonStates</span><span class="sxs-lookup"><span data-stu-id="3bf5b-129">CommonStates</span></span>|<span data-ttu-id="3bf5b-130">用户不能更改中的文本<xref:System.Windows.Controls.TextBox>。</span><span class="sxs-lookup"><span data-stu-id="3bf5b-130">The user cannot change the text in the <xref:System.Windows.Controls.TextBox>.</span></span>|  
|<span data-ttu-id="3bf5b-131">已设定焦点</span><span class="sxs-lookup"><span data-stu-id="3bf5b-131">Focused</span></span>|<span data-ttu-id="3bf5b-132">FocusStates</span><span class="sxs-lookup"><span data-stu-id="3bf5b-132">FocusStates</span></span>|<span data-ttu-id="3bf5b-133">控件有焦点。</span><span class="sxs-lookup"><span data-stu-id="3bf5b-133">The control has focus.</span></span>|  
|<span data-ttu-id="3bf5b-134">失去焦点</span><span class="sxs-lookup"><span data-stu-id="3bf5b-134">Unfocused</span></span>|<span data-ttu-id="3bf5b-135">FocusStates</span><span class="sxs-lookup"><span data-stu-id="3bf5b-135">FocusStates</span></span>|<span data-ttu-id="3bf5b-136">控件没有焦点。</span><span class="sxs-lookup"><span data-stu-id="3bf5b-136">The control does not have focus.</span></span>|  
|<span data-ttu-id="3bf5b-137">有效</span><span class="sxs-lookup"><span data-stu-id="3bf5b-137">Valid</span></span>|<span data-ttu-id="3bf5b-138">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="3bf5b-138">ValidationStates</span></span>|<span data-ttu-id="3bf5b-139">该控件使用<xref:System.Windows.Controls.Validation>类和<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>附加的属性是`false`。</span><span class="sxs-lookup"><span data-stu-id="3bf5b-139">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="3bf5b-140">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="3bf5b-140">InvalidFocused</span></span>|<span data-ttu-id="3bf5b-141">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="3bf5b-141">ValidationStates</span></span>|<span data-ttu-id="3bf5b-142"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>附加的属性是`true`已在控件有焦点。</span><span class="sxs-lookup"><span data-stu-id="3bf5b-142">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="3bf5b-143">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="3bf5b-143">InvalidUnfocused</span></span>|<span data-ttu-id="3bf5b-144">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="3bf5b-144">ValidationStates</span></span>|<span data-ttu-id="3bf5b-145"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType>附加的属性是`true`具有该控件没有焦点。</span><span class="sxs-lookup"><span data-stu-id="3bf5b-145">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="textbox-controltemplate-example"></a><span data-ttu-id="3bf5b-146">文本框 ControlTemplate 示例</span><span class="sxs-lookup"><span data-stu-id="3bf5b-146">TextBox ControlTemplate Example</span></span>  
 <span data-ttu-id="3bf5b-147">下面的示例演示如何定义<xref:System.Windows.Controls.ControlTemplate>为<xref:System.Windows.Controls.TextBox>控件。</span><span class="sxs-lookup"><span data-stu-id="3bf5b-147">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.TextBox> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#TextBox](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/textbox.xaml#textbox)]  
  
 <span data-ttu-id="3bf5b-148">上一示例使用了一个或多个以下资源。</span><span class="sxs-lookup"><span data-stu-id="3bf5b-148">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="3bf5b-149">有关完整示例，请参阅[使用 ControlTemplates 设置样式示例](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating)。</span><span class="sxs-lookup"><span data-stu-id="3bf5b-149">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3bf5b-150">请参阅</span><span class="sxs-lookup"><span data-stu-id="3bf5b-150">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="3bf5b-151">控件样式和模板</span><span class="sxs-lookup"><span data-stu-id="3bf5b-151">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="3bf5b-152">控件自定义</span><span class="sxs-lookup"><span data-stu-id="3bf5b-152">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="3bf5b-153">样式设置和模板化</span><span class="sxs-lookup"><span data-stu-id="3bf5b-153">Styling and Templating</span></span>](styling-and-templating.md)
- [<span data-ttu-id="3bf5b-154">通过创建 ControlTemplate 自定义现有控件的外观</span><span class="sxs-lookup"><span data-stu-id="3bf5b-154">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](customizing-the-appearance-of-an-existing-control.md)
