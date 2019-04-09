---
title: 使用 DrawingVisual 对象
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- visual layer [WPF], DrawingVisual objects
- DrawingVisual objects in visual layer [WPF]
ms.assetid: 0b4e711d-e640-40cb-81c3-8f5c59909b7d
ms.openlocfilehash: 01e10a4b0f0bf4959850caf3951ad4ea915edb4e
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59121714"
---
# <a name="using-drawingvisual-objects"></a><span data-ttu-id="4818e-102">使用 DrawingVisual 对象</span><span class="sxs-lookup"><span data-stu-id="4818e-102">Using DrawingVisual Objects</span></span>
<span data-ttu-id="4818e-103">本主题概述了如何使用<xref:System.Windows.Media.DrawingVisual>中的对象[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]可视化层。</span><span class="sxs-lookup"><span data-stu-id="4818e-103">This topic provides an overview of how to use <xref:System.Windows.Media.DrawingVisual> objects in the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] visual layer.</span></span>  
  
<a name="drawingvisual_object"></a>   
## <a name="drawingvisual-object"></a><span data-ttu-id="4818e-104">DrawingVisual 对象</span><span class="sxs-lookup"><span data-stu-id="4818e-104">DrawingVisual Object</span></span>  
 <span data-ttu-id="4818e-105"><xref:System.Windows.Media.DrawingVisual>是一个轻量绘图类，用于呈现形状、 图像或文本。</span><span class="sxs-lookup"><span data-stu-id="4818e-105">The <xref:System.Windows.Media.DrawingVisual> is a lightweight drawing class that is used to render shapes, images, or text.</span></span> <span data-ttu-id="4818e-106">此类之所以为轻量类是因为它不提供布局或事件处理，从而性能得以提升。</span><span class="sxs-lookup"><span data-stu-id="4818e-106">This class is considered lightweight because it does not provide layout or event handling, which improves its performance.</span></span> <span data-ttu-id="4818e-107">因此，绘图非常适用于背景和剪贴画。</span><span class="sxs-lookup"><span data-stu-id="4818e-107">For this reason, drawings are ideal for backgrounds and clip art.</span></span>  
  
<a name="drawingvisual_host_container"></a>   
## <a name="drawingvisual-host-container"></a><span data-ttu-id="4818e-108">DrawingVisual 宿主容器</span><span class="sxs-lookup"><span data-stu-id="4818e-108">DrawingVisual Host Container</span></span>  
 <span data-ttu-id="4818e-109">若要使用<xref:System.Windows.Media.DrawingVisual>对象，您需要创建宿主容器对象。</span><span class="sxs-lookup"><span data-stu-id="4818e-109">In order to use <xref:System.Windows.Media.DrawingVisual> objects, you need to create a host container for the objects.</span></span> <span data-ttu-id="4818e-110">宿主容器对象必须派生自<xref:System.Windows.FrameworkElement>类，该类提供的布局和事件处理支持<xref:System.Windows.Media.DrawingVisual>类缺少。</span><span class="sxs-lookup"><span data-stu-id="4818e-110">The host container object must derive from the <xref:System.Windows.FrameworkElement> class, which provides the layout and event handling support that the <xref:System.Windows.Media.DrawingVisual> class lacks.</span></span> <span data-ttu-id="4818e-111">宿主容器对象不显示任何可视属性，因为它的主要用途是包含子对象。</span><span class="sxs-lookup"><span data-stu-id="4818e-111">The host container object does not display any visible properties, since its main purpose is to contain child objects.</span></span> <span data-ttu-id="4818e-112">但是，<xref:System.Windows.UIElement.Visibility%2A>宿主容器的属性必须设置为<xref:System.Windows.Visibility.Visible>; 否则为 none 及其子元素将可见。</span><span class="sxs-lookup"><span data-stu-id="4818e-112">However, the <xref:System.Windows.UIElement.Visibility%2A> property of the host container must be set to <xref:System.Windows.Visibility.Visible>; otherwise, none of its child elements will be visible.</span></span>  
  
 <span data-ttu-id="4818e-113">在创建视觉对象宿主容器对象时，您必须将存储中的视觉对象引用<xref:System.Windows.Media.VisualCollection>。</span><span class="sxs-lookup"><span data-stu-id="4818e-113">When you create a host container object for visual objects, you need to store the visual object references in a <xref:System.Windows.Media.VisualCollection>.</span></span> <span data-ttu-id="4818e-114">使用<xref:System.Windows.Media.VisualCollection.Add%2A>方法将视觉对象添加到宿主容器。</span><span class="sxs-lookup"><span data-stu-id="4818e-114">Use the <xref:System.Windows.Media.VisualCollection.Add%2A> method to add a visual object to the host container.</span></span> <span data-ttu-id="4818e-115">以下示例中，在创建宿主容器对象，并且三个视觉对象添加到其<xref:System.Windows.Media.VisualCollection>。</span><span class="sxs-lookup"><span data-stu-id="4818e-115">In the following example, a host container object is created, and three visual objects are added to its <xref:System.Windows.Media.VisualCollection>.</span></span>  
  
 [!code-csharp[DrawingVisualSample#100](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingVisualSample/CSharp/Window1.xaml.cs#100)]
 [!code-vb[DrawingVisualSample#100](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DrawingVisualSample/visualbasic/window1.xaml.vb#100)]  
  
> [!NOTE]
>  <span data-ttu-id="4818e-116">有关从中提取上述代码示例的完整代码示例，请参阅[使用 DrawingVisual 的命中测试示例](https://go.microsoft.com/fwlink/?LinkID=159994)。</span><span class="sxs-lookup"><span data-stu-id="4818e-116">For the complete code sample from which the preceding code example was extracted, see [Hit Test Using DrawingVisuals Sample](https://go.microsoft.com/fwlink/?LinkID=159994).</span></span>  
  
<a name="creating_drawingvisual_objects"></a>   
## <a name="creating-drawingvisual-objects"></a><span data-ttu-id="4818e-117">创建 DrawingVisual 对象</span><span class="sxs-lookup"><span data-stu-id="4818e-117">Creating DrawingVisual Objects</span></span>  
 <span data-ttu-id="4818e-118">当你创建<xref:System.Windows.Media.DrawingVisual>对象，它不包含任何绘图内容。</span><span class="sxs-lookup"><span data-stu-id="4818e-118">When you create a <xref:System.Windows.Media.DrawingVisual> object, it has no drawing content.</span></span> <span data-ttu-id="4818e-119">可以通过检索对象的添加文本、 图形或图像内容<xref:System.Windows.Media.DrawingContext>和在其中进行绘制。</span><span class="sxs-lookup"><span data-stu-id="4818e-119">You can add text, graphics, or image content by retrieving the object's <xref:System.Windows.Media.DrawingContext> and drawing into it.</span></span> <span data-ttu-id="4818e-120">一个<xref:System.Windows.Media.DrawingContext>返回通过调用<xref:System.Windows.Media.DrawingVisual.RenderOpen%2A>方法的<xref:System.Windows.Media.DrawingVisual>对象。</span><span class="sxs-lookup"><span data-stu-id="4818e-120">A <xref:System.Windows.Media.DrawingContext> is returned by calling the <xref:System.Windows.Media.DrawingVisual.RenderOpen%2A> method of a <xref:System.Windows.Media.DrawingVisual> object.</span></span>  
  
 <span data-ttu-id="4818e-121">若要绘制到一个矩形<xref:System.Windows.Media.DrawingContext>，使用<xref:System.Windows.Media.DrawingContext.DrawRectangle%2A>方法的<xref:System.Windows.Media.DrawingContext>对象。</span><span class="sxs-lookup"><span data-stu-id="4818e-121">To draw a rectangle into the <xref:System.Windows.Media.DrawingContext>, use the <xref:System.Windows.Media.DrawingContext.DrawRectangle%2A> method of the <xref:System.Windows.Media.DrawingContext> object.</span></span> <span data-ttu-id="4818e-122">对于绘制其他类型的内容，存在类似的方法。</span><span class="sxs-lookup"><span data-stu-id="4818e-122">Similar methods exist for drawing other types of content.</span></span> <span data-ttu-id="4818e-123">完成内容绘制到时<xref:System.Windows.Media.DrawingContext>，调用<xref:System.Windows.Media.DrawingContext.Close%2A>方法关闭<xref:System.Windows.Media.DrawingContext>并保存内容。</span><span class="sxs-lookup"><span data-stu-id="4818e-123">When you are finished drawing content into the <xref:System.Windows.Media.DrawingContext>, call the <xref:System.Windows.Media.DrawingContext.Close%2A> method to close the <xref:System.Windows.Media.DrawingContext> and persist the content.</span></span>  
  
 <span data-ttu-id="4818e-124">在以下示例中，<xref:System.Windows.Media.DrawingVisual>创建对象，和一个矩形绘制到其<xref:System.Windows.Media.DrawingContext>。</span><span class="sxs-lookup"><span data-stu-id="4818e-124">In the following example, a <xref:System.Windows.Media.DrawingVisual> object is created, and a rectangle is drawn into its <xref:System.Windows.Media.DrawingContext>.</span></span>  
  
 [!code-csharp[DrawingVisualSample#101](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingVisualSample/CSharp/Window1.xaml.cs#101)]
 [!code-vb[DrawingVisualSample#101](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DrawingVisualSample/visualbasic/window1.xaml.vb#101)]  
  
<a name="creating_overrides"></a>   
## <a name="creating-overrides-for-frameworkelement-members"></a><span data-ttu-id="4818e-125">为 FrameworkElement 成员创建重写</span><span class="sxs-lookup"><span data-stu-id="4818e-125">Creating Overrides for FrameworkElement Members</span></span>  
 <span data-ttu-id="4818e-126">宿主容器对象负责管理其视觉对象的集合。</span><span class="sxs-lookup"><span data-stu-id="4818e-126">The host container object is responsible for managing its collection of visual objects.</span></span> <span data-ttu-id="4818e-127">这要求宿主容器实现为派生的成员重写<xref:System.Windows.FrameworkElement>类。</span><span class="sxs-lookup"><span data-stu-id="4818e-127">This requires that the host container implement member overrides for the derived <xref:System.Windows.FrameworkElement> class.</span></span>  
  
 <span data-ttu-id="4818e-128">下表介绍了必须重写的两个成员：</span><span class="sxs-lookup"><span data-stu-id="4818e-128">The following list describes the two members you must override:</span></span>  
  
-   <xref:System.Windows.FrameworkElement.GetVisualChild%2A><span data-ttu-id="4818e-129">:返回子元素的集合中的指定索引处的子级。</span><span class="sxs-lookup"><span data-stu-id="4818e-129">: Returns a child at the specified index from the collection of child elements.</span></span>  
  
-   <xref:System.Windows.FrameworkElement.VisualChildrenCount%2A><span data-ttu-id="4818e-130">:获取此元素内可视子元素的数目。</span><span class="sxs-lookup"><span data-stu-id="4818e-130">: Gets the number of visual child elements within this element.</span></span>  
  
 <span data-ttu-id="4818e-131">在以下示例中，重写为两个<xref:System.Windows.FrameworkElement>成员实现。</span><span class="sxs-lookup"><span data-stu-id="4818e-131">In the following example, overrides for the two <xref:System.Windows.FrameworkElement> members are implemented.</span></span>  
  
 [!code-csharp[DrawingVisualSample#102](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingVisualSample/CSharp/Window1.xaml.cs#102)]
 [!code-vb[DrawingVisualSample#102](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DrawingVisualSample/visualbasic/window1.xaml.vb#102)]  
  
<a name="providing_hit_testing_support"></a>   
## <a name="providing-hit-testing-support"></a><span data-ttu-id="4818e-132">提供命中测试支持</span><span class="sxs-lookup"><span data-stu-id="4818e-132">Providing Hit Testing Support</span></span>  
 <span data-ttu-id="4818e-133">宿主容器对象可以提供事件处理，即使它不显示任何可视属性，但是，其<xref:System.Windows.UIElement.Visibility%2A>属性必须设置为<xref:System.Windows.Visibility.Visible>。</span><span class="sxs-lookup"><span data-stu-id="4818e-133">The host container object can provide event handling even if it does not display any visible properties—however, its <xref:System.Windows.UIElement.Visibility%2A> property must be set to <xref:System.Windows.Visibility.Visible>.</span></span> <span data-ttu-id="4818e-134">这样便可以为宿主容器创建事件处理例程，此例程可以捕获鼠标事件，如松开鼠标左键。</span><span class="sxs-lookup"><span data-stu-id="4818e-134">This allows you to create an event handling routine for the host container that can trap mouse events, such as the release of the left mouse button.</span></span> <span data-ttu-id="4818e-135">然后，事件处理例程可以实现命中测试通过调用<xref:System.Windows.Media.VisualTreeHelper.HitTest%2A>方法。</span><span class="sxs-lookup"><span data-stu-id="4818e-135">The event handling routine can then implement hit testing by invoking the <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A> method.</span></span> <span data-ttu-id="4818e-136">该方法的<xref:System.Windows.Media.HitTestResultCallback>参数是指可用于确定生成的命中测试操作的用户定义的过程。</span><span class="sxs-lookup"><span data-stu-id="4818e-136">The method's <xref:System.Windows.Media.HitTestResultCallback> parameter refers to a user-defined procedure that you can use to determine the resulting action of a hit test.</span></span>  
  
 <span data-ttu-id="4818e-137">在下面的示例中，为宿主容器对象及其子级实现命中测试支持。</span><span class="sxs-lookup"><span data-stu-id="4818e-137">In the following example, hit testing support is implemented for the host container object and its children.</span></span>  
  
 [!code-csharp[DrawingVisualSample#103](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingVisualSample/CSharp/Window1.xaml.cs#103)]
 [!code-vb[DrawingVisualSample#103](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DrawingVisualSample/visualbasic/window1.xaml.vb#103)]  
  
## <a name="see-also"></a><span data-ttu-id="4818e-138">请参阅</span><span class="sxs-lookup"><span data-stu-id="4818e-138">See also</span></span>

- <xref:System.Windows.Media.DrawingVisual>
- <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A>
- [<span data-ttu-id="4818e-139">WPF 图形呈现疑难解答</span><span class="sxs-lookup"><span data-stu-id="4818e-139">WPF Graphics Rendering Overview</span></span>](wpf-graphics-rendering-overview.md)
- [<span data-ttu-id="4818e-140">可视化层中的命中测试</span><span class="sxs-lookup"><span data-stu-id="4818e-140">Hit Testing in the Visual Layer</span></span>](hit-testing-in-the-visual-layer.md)
