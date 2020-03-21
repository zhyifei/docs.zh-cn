---
title: 装饰器概述
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- adorners [WPF], about adorners
ms.assetid: 33d4c5c2-2daf-4e45-ba9a-5b673e2b8280
ms.openlocfilehash: b41c1f10f7e1b7c1799fd27270a3eeb9899ceeb6
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/21/2020
ms.locfileid: "80111174"
---
# <a name="adorners-overview"></a><span data-ttu-id="11525-102">装饰器概述</span><span class="sxs-lookup"><span data-stu-id="11525-102">Adorners Overview</span></span>

<span data-ttu-id="11525-103">装饰器是一种特殊的类型<xref:System.Windows.FrameworkElement>，用于向用户提供视觉提示。</span><span class="sxs-lookup"><span data-stu-id="11525-103">Adorners are a special type of <xref:System.Windows.FrameworkElement>, used to provide visual cues to a user.</span></span> <span data-ttu-id="11525-104">装饰器有很多用途，可用来向元素添加功能句柄，或者提供有关某个控件的状态信息。</span><span class="sxs-lookup"><span data-stu-id="11525-104">Among other uses, Adorners can be used to add functional handles to elements or provide state information about a control.</span></span>

## <a name="about-adorners"></a><span data-ttu-id="11525-105">关于装饰器</span><span class="sxs-lookup"><span data-stu-id="11525-105">About Adorners</span></span>

<span data-ttu-id="11525-106">是<xref:System.Windows.Documents.Adorner>绑定到<xref:System.Windows.FrameworkElement>的<xref:System.Windows.UIElement>自定义项。</span><span class="sxs-lookup"><span data-stu-id="11525-106">An <xref:System.Windows.Documents.Adorner> is a custom <xref:System.Windows.FrameworkElement> that is bound to a <xref:System.Windows.UIElement>.</span></span> <span data-ttu-id="11525-107">装饰器以 中呈现<xref:System.Windows.Documents.AdornerLayer>，这是始终位于修饰元素或修饰元素集合之上的呈现曲面。</span><span class="sxs-lookup"><span data-stu-id="11525-107">Adorners are rendered in an <xref:System.Windows.Documents.AdornerLayer>, which is a rendering surface that is always on top of the adorned element or a collection of adorned elements.</span></span> <span data-ttu-id="11525-108">修饰器的渲染独立于修饰器绑定到的<xref:System.Windows.UIElement>渲染。</span><span class="sxs-lookup"><span data-stu-id="11525-108">Rendering of an adorner is independent from rendering of the <xref:System.Windows.UIElement> that the adorner is bound to.</span></span> <span data-ttu-id="11525-109">装饰器通常相对于绑定的元素进行定位，使用位于修饰元素左上角的标准 2D 坐标原点。</span><span class="sxs-lookup"><span data-stu-id="11525-109">An adorner is typically positioned relative to the element to which it is bound, using the standard 2D coordinate origin located at the upper-left of the adorned element.</span></span>

<span data-ttu-id="11525-110">装饰器的常见应用包括：</span><span class="sxs-lookup"><span data-stu-id="11525-110">Common applications for adorners include:</span></span>

- <span data-ttu-id="11525-111">将功能句柄添加到<xref:System.Windows.UIElement>，使用户能够以某种方式操作元素（调整大小、旋转、重新定位等）。</span><span class="sxs-lookup"><span data-stu-id="11525-111">Adding functional handles to a <xref:System.Windows.UIElement> that enable a user to manipulate the element in some way (resize, rotate, reposition, etc.).</span></span>
- <span data-ttu-id="11525-112">提供视觉反馈以指示各种状态，或者响应各种事件。</span><span class="sxs-lookup"><span data-stu-id="11525-112">Provide visual feedback to indicate various states, or in response to various events.</span></span>
- <span data-ttu-id="11525-113">在 上叠加视觉装饰<xref:System.Windows.UIElement>。</span><span class="sxs-lookup"><span data-stu-id="11525-113">Overlay visual decorations on a <xref:System.Windows.UIElement>.</span></span>
- <span data-ttu-id="11525-114">直观地屏蔽或覆盖 部分或 全部<xref:System.Windows.UIElement>。</span><span class="sxs-lookup"><span data-stu-id="11525-114">Visually mask or override part or all of a <xref:System.Windows.UIElement>.</span></span>

[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] <span data-ttu-id="11525-115">提供用于装饰视觉元素的基本框架。</span><span class="sxs-lookup"><span data-stu-id="11525-115">provides a basic framework for adorning visual elements.</span></span> <span data-ttu-id="11525-116">下表列出了装饰对象时使用的主要类型及其用途。</span><span class="sxs-lookup"><span data-stu-id="11525-116">The following table lists the primary types used when adorning objects, and their purpose.</span></span> <span data-ttu-id="11525-117">以下几个使用示例如下：</span><span class="sxs-lookup"><span data-stu-id="11525-117">Several usage examples follow:</span></span>

|||
|-|-|
|<xref:System.Windows.Documents.Adorner>|<span data-ttu-id="11525-118">一个抽象基类，从中继承所有的具体装饰器实现。</span><span class="sxs-lookup"><span data-stu-id="11525-118">An abstract base class from which all concrete adorner implementations inherit.</span></span>|
|<xref:System.Windows.Documents.AdornerLayer>|<span data-ttu-id="11525-119">一个类，表示一个或多个装饰元素的装饰器的呈现层。</span><span class="sxs-lookup"><span data-stu-id="11525-119">A class representing a rendering layer for the adorner(s) of one or more adorned elements.</span></span>|
|<xref:System.Windows.Documents.AdornerDecorator>|<span data-ttu-id="11525-120">一个类，使装饰器层与元素集合相关联。</span><span class="sxs-lookup"><span data-stu-id="11525-120">A class that enables an adorner layer to be associated with a collection of elements.</span></span>|

## <a name="implementing-a-custom-adorner"></a><span data-ttu-id="11525-121">实现自定义装饰器</span><span class="sxs-lookup"><span data-stu-id="11525-121">Implementing a Custom Adorner</span></span>

<span data-ttu-id="11525-122">[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 提供的装饰器框架的主要用于支持创建自定义装饰器。</span><span class="sxs-lookup"><span data-stu-id="11525-122">The adorners framework provided by [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] is intended primarily to support the creation of custom adorners.</span></span> <span data-ttu-id="11525-123">自定义修饰器是通过实现从抽象<xref:System.Windows.Documents.Adorner>类继承的类创建的。</span><span class="sxs-lookup"><span data-stu-id="11525-123">A custom adorner is created by implementing a class that inherits from the abstract <xref:System.Windows.Documents.Adorner> class.</span></span>

> [!NOTE]
> <span data-ttu-id="11525-124">的父<xref:System.Windows.Documents.Adorner>级是<xref:System.Windows.Documents.AdornerLayer>呈现 的<xref:System.Windows.Documents.Adorner>， 而不是正在修饰的元素。</span><span class="sxs-lookup"><span data-stu-id="11525-124">The parent of an <xref:System.Windows.Documents.Adorner> is the <xref:System.Windows.Documents.AdornerLayer> that renders the <xref:System.Windows.Documents.Adorner>, not the element being adorned.</span></span>

<span data-ttu-id="11525-125">下面的示例展示了实现简单装饰器的类。</span><span class="sxs-lookup"><span data-stu-id="11525-125">The following example shows a class that implements a simple adorner.</span></span> <span data-ttu-id="11525-126">示例修饰器只是修饰带有圆圈的角<xref:System.Windows.UIElement>。</span><span class="sxs-lookup"><span data-stu-id="11525-126">The example adorner simply adorns the corners of a <xref:System.Windows.UIElement> with circles.</span></span>

[!code-csharp[Adorners_SimpleCircleAdorner#_SimpleCircleAdornerBody](~/samples/snippets/csharp/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/CSharp/Window1.xaml.cs#_simplecircleadornerbody)]
[!code-vb[Adorners_SimpleCircleAdorner#_SimpleCircleAdornerBody](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/VisualBasic/Window1.xaml.vb#_simplecircleadornerbody)]
  
<span data-ttu-id="11525-127">下图显示了应用于 的<xref:System.Windows.Controls.TextBox>SimpleCircleAdorner：</span><span class="sxs-lookup"><span data-stu-id="11525-127">The following image shows the SimpleCircleAdorner applied to a <xref:System.Windows.Controls.TextBox>:</span></span>

![显示修饰文本框的屏幕截图。](./media/adorners-overview/simplecircleadorner-textbox.png)

## <a name="rendering-behavior-for-adorners"></a><span data-ttu-id="11525-129">装饰器的呈现行为</span><span class="sxs-lookup"><span data-stu-id="11525-129">Rendering Behavior for Adorners</span></span>

<span data-ttu-id="11525-130">请务必注意，装饰器不包括任何继承呈现行为，确保装饰器呈现是装饰器实施者的责任。</span><span class="sxs-lookup"><span data-stu-id="11525-130">It is important to note that adorners do not include any inherent rendering behavior; ensuring that an adorner renders is the responsibility of the adorner implementer.</span></span> <span data-ttu-id="11525-131">实现呈现行为的常见方法是重写<xref:System.Windows.UIElement.OnRender%2A>该方法，并使用一个或多个<xref:System.Windows.Media.DrawingContext>对象根据需要呈现修饰器的视觉效果（如上例所示）。</span><span class="sxs-lookup"><span data-stu-id="11525-131">A common way of implementing rendering behavior is to override the <xref:System.Windows.UIElement.OnRender%2A> method and use one or more <xref:System.Windows.Media.DrawingContext> objects to render the adorner's visuals as needed (as shown in the example above).</span></span>

> [!NOTE]
> <span data-ttu-id="11525-132">放置在装饰器层中的任何内容将呈现在设置的其他任何样式的顶部。</span><span class="sxs-lookup"><span data-stu-id="11525-132">Anything placed in the adorner layer is rendered on top of the rest of any styles you have set.</span></span> <span data-ttu-id="11525-133">换言之，装饰器始终以可见的方式位于顶部，无法使用 z 顺序重写。</span><span class="sxs-lookup"><span data-stu-id="11525-133">In other words, adorners are always visually on top and cannot be overridden using z-order.</span></span>

## <a name="events-and-hit-testing"></a><span data-ttu-id="11525-134">事件和命中测试</span><span class="sxs-lookup"><span data-stu-id="11525-134">Events and Hit Testing</span></span>

<span data-ttu-id="11525-135">修饰器接收输入事件就像任何其他<xref:System.Windows.FrameworkElement>一样。</span><span class="sxs-lookup"><span data-stu-id="11525-135">Adorners receive input events just like any other <xref:System.Windows.FrameworkElement>.</span></span>  <span data-ttu-id="11525-136">由于修饰器的 z 顺序始终高于其修饰的元素，因此修饰器接收可能用于基础修饰元素的输入事件（如<xref:System.Windows.UIElement.Drop><xref:System.Windows.UIElement.MouseMove>或 ）。</span><span class="sxs-lookup"><span data-stu-id="11525-136">Because an adorner always has a higher z-order than the element it adorns, the adorner receives input events (such as <xref:System.Windows.UIElement.Drop> or <xref:System.Windows.UIElement.MouseMove>) that may be intended for the underlying adorned element.</span></span>  <span data-ttu-id="11525-137">装饰器可以侦听某些输入事件，并通过重新引发这些事件将它们传递到基础装饰元素。</span><span class="sxs-lookup"><span data-stu-id="11525-137">An adorner can listen for certain input events and pass these on to the underlying adorned element by re-raising the event.</span></span>

<span data-ttu-id="11525-138">要启用修饰器下元素的直通命中测试，将命中测试<xref:System.Windows.UIElement.IsHitTestVisible%2A>属性设置为修饰器上的**false。**</span><span class="sxs-lookup"><span data-stu-id="11525-138">To enable pass-through hit testing of elements under an adorner, set the hit test <xref:System.Windows.UIElement.IsHitTestVisible%2A> property to **false** on the adorner.</span></span>  <span data-ttu-id="11525-139">有关命中测试的详细信息，请参阅[可视化图层中的命中测试](../graphics-multimedia/hit-testing-in-the-visual-layer.md)。</span><span class="sxs-lookup"><span data-stu-id="11525-139">For more information about hit testing, see [Hit Testing in the Visual Layer](../graphics-multimedia/hit-testing-in-the-visual-layer.md).</span></span>

## <a name="adorning-a-single-uielement"></a><span data-ttu-id="11525-140">装饰单个 UIElement</span><span class="sxs-lookup"><span data-stu-id="11525-140">Adorning a Single UIElement</span></span>

<span data-ttu-id="11525-141">要将装饰器绑定到特定<xref:System.Windows.UIElement>，请按照以下步骤操作：</span><span class="sxs-lookup"><span data-stu-id="11525-141">To bind an adorner to a particular <xref:System.Windows.UIElement>, follow these steps:</span></span>

1. <span data-ttu-id="11525-142">调用静态方法<xref:System.Windows.Documents.AdornerLayer.GetAdornerLayer%2A>获取<xref:System.Windows.Documents.AdornerLayer><xref:System.Windows.UIElement>要修饰的对象。</span><span class="sxs-lookup"><span data-stu-id="11525-142">Call the static method <xref:System.Windows.Documents.AdornerLayer.GetAdornerLayer%2A> to get an <xref:System.Windows.Documents.AdornerLayer> object for the <xref:System.Windows.UIElement> to be adorned.</span></span> <span data-ttu-id="11525-143"><xref:System.Windows.Documents.AdornerLayer.GetAdornerLayer%2A>向上走，从指定的<xref:System.Windows.UIElement>开始，然后返回它找到的第一个修饰器图层。</span><span class="sxs-lookup"><span data-stu-id="11525-143"><xref:System.Windows.Documents.AdornerLayer.GetAdornerLayer%2A> walks up the visual tree, starting at the specified <xref:System.Windows.UIElement>, and returns the first adorner layer it finds.</span></span> <span data-ttu-id="11525-144">（如果未发现装饰器层，该方法将返回 null。）</span><span class="sxs-lookup"><span data-stu-id="11525-144">(If no adorner layers are found, the method returns null.)</span></span>

2. <span data-ttu-id="11525-145">调用<xref:System.Windows.Documents.AdornerLayer.Add%2A>方法将修饰器绑定到目标<xref:System.Windows.UIElement>。</span><span class="sxs-lookup"><span data-stu-id="11525-145">Call the <xref:System.Windows.Documents.AdornerLayer.Add%2A> method to bind the adorner to the target <xref:System.Windows.UIElement>.</span></span>

 <span data-ttu-id="11525-146">下面的示例将 SimpleCircleAdorner（如上图所示）绑定到<xref:System.Windows.Controls.TextBox>名为*myTextBox ：*</span><span class="sxs-lookup"><span data-stu-id="11525-146">The following example binds a SimpleCircleAdorner (shown above) to a <xref:System.Windows.Controls.TextBox> named *myTextBox*:</span></span>

 [!code-csharp[Adorners_SimpleCircleAdorner#_AdornSingleElement](~/samples/snippets/csharp/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/CSharp/Window1.xaml.cs#_adornsingleelement)]
 [!code-vb[Adorners_SimpleCircleAdorner#_AdornSingleElement](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/VisualBasic/Window1.xaml.vb#_adornsingleelement)]

> [!NOTE]
> <span data-ttu-id="11525-147">目前不支持使用 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 将装饰器绑定到另一个元素。</span><span class="sxs-lookup"><span data-stu-id="11525-147">Using [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] to bind an adorner to another element is currently not supported.</span></span>

## <a name="adorning-the-children-of-a-panel"></a><span data-ttu-id="11525-148">装饰面板的子级</span><span class="sxs-lookup"><span data-stu-id="11525-148">Adorning the Children of a Panel</span></span>

<span data-ttu-id="11525-149">要将装饰器绑定到 子级<xref:System.Windows.Controls.Panel>，请按照以下步骤操作：</span><span class="sxs-lookup"><span data-stu-id="11525-149">To bind an adorner to the children of a <xref:System.Windows.Controls.Panel>, follow these steps:</span></span>

1. <span data-ttu-id="11525-150">调用`static`方法<xref:System.Windows.Documents.AdornerLayer.GetAdornerLayer%2A>查找要修饰其子元素的元素的修饰器图层。</span><span class="sxs-lookup"><span data-stu-id="11525-150">Call the `static` method <xref:System.Windows.Documents.AdornerLayer.GetAdornerLayer%2A> to find an adorner layer for the element whose children are to be adorned.</span></span>

2. <span data-ttu-id="11525-151">通过父元素的子元素枚举，<xref:System.Windows.Documents.AdornerLayer.Add%2A>并调用 方法将修饰器绑定到每个子元素。</span><span class="sxs-lookup"><span data-stu-id="11525-151">Enumerate through the children of the parent element and call the <xref:System.Windows.Documents.AdornerLayer.Add%2A> method to bind an adorner to each child element.</span></span>

<span data-ttu-id="11525-152">下面的示例将 SimpleCircleAdorner（如上图所示）绑定到<xref:System.Windows.Controls.StackPanel>名为*myStackPanel*的子级：</span><span class="sxs-lookup"><span data-stu-id="11525-152">The following example binds a SimpleCircleAdorner (shown above) to the children of a <xref:System.Windows.Controls.StackPanel> named *myStackPanel*:</span></span>

[!code-csharp[Adorners_SimpleCircleAdorner#_AdornChildren](~/samples/snippets/csharp/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/CSharp/Window1.xaml.cs#_adornchildren)]
[!code-vb[Adorners_SimpleCircleAdorner#_AdornChildren](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Adorners_SimpleCircleAdorner/VisualBasic/Window1.xaml.vb#_adornchildren)]

## <a name="see-also"></a><span data-ttu-id="11525-153">另请参阅</span><span class="sxs-lookup"><span data-stu-id="11525-153">See also</span></span>

- <xref:System.Windows.Media.AdornerHitTestResult>
- [<span data-ttu-id="11525-154">WPF 中的形状和基本绘图概述</span><span class="sxs-lookup"><span data-stu-id="11525-154">Shapes and Basic Drawing in WPF Overview</span></span>](../graphics-multimedia/shapes-and-basic-drawing-in-wpf-overview.md)
- [<span data-ttu-id="11525-155">使用图像、绘图和视觉对象进行绘制</span><span class="sxs-lookup"><span data-stu-id="11525-155">Painting with Images, Drawings, and Visuals</span></span>](../graphics-multimedia/painting-with-images-drawings-and-visuals.md)
- [<span data-ttu-id="11525-156">Drawing 对象概述</span><span class="sxs-lookup"><span data-stu-id="11525-156">Drawing Objects Overview</span></span>](../graphics-multimedia/drawing-objects-overview.md)
- [<span data-ttu-id="11525-157">如何使用主题</span><span class="sxs-lookup"><span data-stu-id="11525-157">How-to Topics</span></span>](adorners-how-to-topics.md)
