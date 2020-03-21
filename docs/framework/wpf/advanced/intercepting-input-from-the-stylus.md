---
title: 截获触笔输入
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- 'architecture [WPF], '
- ', '
- ', '
- ', '
ms.assetid: 791bb2f0-4e5c-4569-ac3c-211996808d44
ms.openlocfilehash: 17cf42a9d6d94d6ea12399561af5647df3b4d8c2
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79181920"
---
# <a name="intercepting-input-from-the-stylus"></a><span data-ttu-id="b2b23-102">截获触笔输入</span><span class="sxs-lookup"><span data-stu-id="b2b23-102">Intercepting Input from the Stylus</span></span>
<span data-ttu-id="b2b23-103">该<xref:System.Windows.Input.StylusPlugIns>体系结构为实现对<xref:System.Windows.Input.Stylus>输入的低级控制和创建数字墨迹<xref:System.Windows.Ink.Stroke>对象提供了一种机制。</span><span class="sxs-lookup"><span data-stu-id="b2b23-103">The <xref:System.Windows.Input.StylusPlugIns> architecture provides a mechanism for implementing low-level control over <xref:System.Windows.Input.Stylus> input and the creation of digital ink <xref:System.Windows.Ink.Stroke> objects.</span></span> <span data-ttu-id="b2b23-104">该<xref:System.Windows.Input.StylusPlugIns.StylusPlugIn>类提供了一种机制，用于实现自定义行为并将其应用于来自手写笔设备的数据流，以实现最佳性能。</span><span class="sxs-lookup"><span data-stu-id="b2b23-104">The <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> class provides a mechanism for you to implement custom behavior and apply it to the stream of data coming from the stylus device for the optimal performance.</span></span>  
  
 <span data-ttu-id="b2b23-105">本主题包含以下小节：</span><span class="sxs-lookup"><span data-stu-id="b2b23-105">This topic contains the following subsections:</span></span>  
  
- [<span data-ttu-id="b2b23-106">建筑</span><span class="sxs-lookup"><span data-stu-id="b2b23-106">Architecture</span></span>](#Architecture)  
  
- [<span data-ttu-id="b2b23-107">实现手写插件</span><span class="sxs-lookup"><span data-stu-id="b2b23-107">Implementing Stylus Plug-ins</span></span>](#ImplementingStylusPlugins)  
  
- [<span data-ttu-id="b2b23-108">将插件添加到 InkCanvas</span><span class="sxs-lookup"><span data-stu-id="b2b23-108">Adding Your Plug-in to an InkCanvas</span></span>](#AddingYourPluginToAnInkCanvas)  
  
- [<span data-ttu-id="b2b23-109">结论</span><span class="sxs-lookup"><span data-stu-id="b2b23-109">Conclusion</span></span>](#Conclusion)  
  
<a name="Architecture"></a>
## <a name="architecture"></a><span data-ttu-id="b2b23-110">体系结构</span><span class="sxs-lookup"><span data-stu-id="b2b23-110">Architecture</span></span>  
 <span data-ttu-id="b2b23-111">是<xref:System.Windows.Input.StylusPlugIns.StylusPlugIn>[手写输入](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms574861(v=vs.90))API 的演变，在[访问和操作笔输入](https://docs.microsoft.com/previous-versions/ms818317(v%3dmsdn.10))中描述。</span><span class="sxs-lookup"><span data-stu-id="b2b23-111">The <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> is the evolution of the [StylusInput](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms574861(v=vs.90)) APIs, described in [Accessing and Manipulating Pen Input](https://docs.microsoft.com/previous-versions/ms818317(v%3dmsdn.10)).</span></span>  
  
 <span data-ttu-id="b2b23-112">每个<xref:System.Windows.UIElement>都有一<xref:System.Windows.UIElement.StylusPlugIns%2A>个属性是<xref:System.Windows.Input.StylusPlugIns.StylusPlugInCollection>。</span><span class="sxs-lookup"><span data-stu-id="b2b23-112">Each <xref:System.Windows.UIElement> has a <xref:System.Windows.UIElement.StylusPlugIns%2A> property that is a <xref:System.Windows.Input.StylusPlugIns.StylusPlugInCollection>.</span></span> <span data-ttu-id="b2b23-113">您可以将 添加到<xref:System.Windows.Input.StylusPlugIns.StylusPlugIn>元素的属性<xref:System.Windows.UIElement.StylusPlugIns%2A>以在生成数据时操作<xref:System.Windows.Input.StylusPoint>数据。</span><span class="sxs-lookup"><span data-stu-id="b2b23-113">You can add a <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> to an element's <xref:System.Windows.UIElement.StylusPlugIns%2A> property to manipulate <xref:System.Windows.Input.StylusPoint> data as it is generated.</span></span> <span data-ttu-id="b2b23-114"><xref:System.Windows.Input.StylusPoint>数据由系统数字化器支持的所有属性组成，包括<xref:System.Windows.Input.StylusPoint.X%2A>和<xref:System.Windows.Input.StylusPoint.Y%2A>点数据以及<xref:System.Windows.Input.StylusPoint.PressureFactor%2A>数据。</span><span class="sxs-lookup"><span data-stu-id="b2b23-114"><xref:System.Windows.Input.StylusPoint> data consists of all the properties supported by the system digitizer, including the <xref:System.Windows.Input.StylusPoint.X%2A> and <xref:System.Windows.Input.StylusPoint.Y%2A> point data, as well as <xref:System.Windows.Input.StylusPoint.PressureFactor%2A> data.</span></span>  
  
 <span data-ttu-id="b2b23-115">将<xref:System.Windows.Input.StylusPlugIns.StylusPlugIn>的对象直接插入到设备<xref:System.Windows.Input.Stylus>的数据流中，当您将 添加到<xref:System.Windows.Input.StylusPlugIns.StylusPlugIn>属性时。 <xref:System.Windows.UIElement.StylusPlugIns%2A></span><span class="sxs-lookup"><span data-stu-id="b2b23-115">Your <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> objects are inserted directly into the stream of data coming from the <xref:System.Windows.Input.Stylus> device when you add the <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> to the <xref:System.Windows.UIElement.StylusPlugIns%2A> property.</span></span> <span data-ttu-id="b2b23-116">插件添加到<xref:System.Windows.UIElement.StylusPlugIns%2A>集合的顺序决定了它们接收<xref:System.Windows.Input.StylusPoint>数据的顺序。</span><span class="sxs-lookup"><span data-stu-id="b2b23-116">The order in which plug-ins are added to the <xref:System.Windows.UIElement.StylusPlugIns%2A> collection dictates the order in which they will receive <xref:System.Windows.Input.StylusPoint> data.</span></span> <span data-ttu-id="b2b23-117">例如，如果添加筛选器插件，将输入限制到特定区域，然后添加一个插件，在编写手势时识别手势，则识别手势的插件将收到筛选<xref:System.Windows.Input.StylusPoint>的数据。</span><span class="sxs-lookup"><span data-stu-id="b2b23-117">For example, if you add a filter plug-in that restricts input to a particular region, and then add a plug-in that recognizes gestures as they are written, the plug-in that recognizes gestures will receive filtered <xref:System.Windows.Input.StylusPoint> data.</span></span>  
  
<a name="ImplementingStylusPlugins"></a>
## <a name="implementing-stylus-plug-ins"></a><span data-ttu-id="b2b23-118">实现手写插件</span><span class="sxs-lookup"><span data-stu-id="b2b23-118">Implementing Stylus Plug-ins</span></span>  
 <span data-ttu-id="b2b23-119">要实现插件，请从<xref:System.Windows.Input.StylusPlugIns.StylusPlugIn>派生类。</span><span class="sxs-lookup"><span data-stu-id="b2b23-119">To implement a plug-in, derive a class from <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn>.</span></span> <span data-ttu-id="b2b23-120">类应用 o 数据流，因为它来自 。 <xref:System.Windows.Input.Stylus></span><span class="sxs-lookup"><span data-stu-id="b2b23-120">This class is applied o the stream of data as it comes in from the <xref:System.Windows.Input.Stylus>.</span></span> <span data-ttu-id="b2b23-121">在此类中，您可以修改<xref:System.Windows.Input.StylusPoint>数据的值。</span><span class="sxs-lookup"><span data-stu-id="b2b23-121">In this class you can modify the values of the <xref:System.Windows.Input.StylusPoint> data.</span></span>  
  
> [!CAUTION]
> <span data-ttu-id="b2b23-122">如果<xref:System.Windows.Input.StylusPlugIns.StylusPlugIn>引发或导致异常，应用程序将关闭。</span><span class="sxs-lookup"><span data-stu-id="b2b23-122">If a <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> throws or causes an exception, the application will close.</span></span> <span data-ttu-id="b2b23-123">应彻底测试使用 和<xref:System.Windows.Input.StylusPlugIns.StylusPlugIn>仅在您确定 不会引发异常时才使用控件<xref:System.Windows.Input.StylusPlugIns.StylusPlugIn>的控件。</span><span class="sxs-lookup"><span data-stu-id="b2b23-123">You should thoroughly test controls that consume a <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> and only use a control if you are certain the <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> will not throw an exception.</span></span>  
  
 <span data-ttu-id="b2b23-124">下面的示例演示了一个插件，该<xref:System.Windows.Input.StylusPoint.X%2A>插件通过修改<xref:System.Windows.Input.StylusPoint.Y%2A><xref:System.Windows.Input.StylusPoint>数据中的 和 值来限制手写笔输入。<xref:System.Windows.Input.Stylus>因为数据来自设备。</span><span class="sxs-lookup"><span data-stu-id="b2b23-124">The following example demonstrates a plug-in that restricts the stylus input by modifying the <xref:System.Windows.Input.StylusPoint.X%2A> and <xref:System.Windows.Input.StylusPoint.Y%2A> values in the <xref:System.Windows.Input.StylusPoint> data as it comes in from the <xref:System.Windows.Input.Stylus> device.</span></span>  
  
 [!code-csharp[AdvancedInkTopicsSamples#19](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/DynamicRenderer.cs#19)]
 [!code-vb[AdvancedInkTopicsSamples#19](~/samples/snippets/visualbasic/VS_Snippets_Wpf/AdvancedInkTopicsSamples/VisualBasic/DynamicRenderer.vb#19)]  
[!code-csharp[AdvancedInkTopicsSamples#3](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/DynamicRenderer.cs#3)]
[!code-vb[AdvancedInkTopicsSamples#3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/AdvancedInkTopicsSamples/VisualBasic/DynamicRenderer.vb#3)]  
  
<a name="AddingYourPluginToAnInkCanvas"></a>
## <a name="adding-your-plug-in-to-an-inkcanvas"></a><span data-ttu-id="b2b23-125">将插件添加到 InkCanvas</span><span class="sxs-lookup"><span data-stu-id="b2b23-125">Adding Your Plug-in to an InkCanvas</span></span>  
 <span data-ttu-id="b2b23-126">使用自定义插件的最简单方法是实现从 InkCanvas 派生的类并将其添加到<xref:System.Windows.UIElement.StylusPlugIns%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="b2b23-126">The easiest way to use your custom plug-in is to implement a class that derives from InkCanvas and add it to the <xref:System.Windows.UIElement.StylusPlugIns%2A> property.</span></span>  
  
 <span data-ttu-id="b2b23-127">下面的示例演示了筛选墨<xref:System.Windows.Controls.InkCanvas>迹的自定义。</span><span class="sxs-lookup"><span data-stu-id="b2b23-127">The following example demonstrates a custom <xref:System.Windows.Controls.InkCanvas> that filters the ink.</span></span>  
  
 [!code-csharp[AdvancedInkTopicsSamples#4](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/Window1.xaml.cs#4)]  
  
 <span data-ttu-id="b2b23-128">如果向应用程序添加`FilterInkCanvas`并运行它，您会注意到，在用户完成笔画之前，墨迹不会局限于区域。</span><span class="sxs-lookup"><span data-stu-id="b2b23-128">If you add a `FilterInkCanvas` to your application and run it, you will notice that the ink isn't restricted to a region until after the user completes a stroke.</span></span> <span data-ttu-id="b2b23-129">这是因为<xref:System.Windows.Controls.InkCanvas>具有 属性<xref:System.Windows.Controls.InkCanvas.DynamicRenderer%2A>，该属性是<xref:System.Windows.Input.StylusPlugIns.StylusPlugIn>，并且已经是<xref:System.Windows.UIElement.StylusPlugIns%2A>集合的成员。</span><span class="sxs-lookup"><span data-stu-id="b2b23-129">This is because the <xref:System.Windows.Controls.InkCanvas> has a <xref:System.Windows.Controls.InkCanvas.DynamicRenderer%2A> property, which is a <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> and is already a member of the <xref:System.Windows.UIElement.StylusPlugIns%2A> collection.</span></span> <span data-ttu-id="b2b23-130">添加到集合<xref:System.Windows.Input.StylusPlugIns.StylusPlugIn>中的<xref:System.Windows.UIElement.StylusPlugIns%2A>自定义在接收数据后<xref:System.Windows.Input.StylusPoint><xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>接收数据。</span><span class="sxs-lookup"><span data-stu-id="b2b23-130">The custom <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> you added to the <xref:System.Windows.UIElement.StylusPlugIns%2A> collection receives the <xref:System.Windows.Input.StylusPoint> data after <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> receives data.</span></span> <span data-ttu-id="b2b23-131">因此，<xref:System.Windows.Input.StylusPoint>在用户抬起笔以结束笔画之前，数据才会被筛选。</span><span class="sxs-lookup"><span data-stu-id="b2b23-131">As a result, the <xref:System.Windows.Input.StylusPoint> data will not be filtered until after the user lifts the pen to end a stroke.</span></span> <span data-ttu-id="b2b23-132">若要在用户绘制墨迹时筛选墨迹，必须在 之前`FilterPlugin`<xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>插入 。</span><span class="sxs-lookup"><span data-stu-id="b2b23-132">To filter the ink as the user draws it, you must insert the `FilterPlugin` before the <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>.</span></span>  
  
 <span data-ttu-id="b2b23-133">以下 C# 代码演示了<xref:System.Windows.Controls.InkCanvas>在绘制墨迹时筛选墨迹的自定义。</span><span class="sxs-lookup"><span data-stu-id="b2b23-133">The following C# code demonstrates a custom <xref:System.Windows.Controls.InkCanvas> that filters the ink as it is drawn.</span></span>  
  
 [!code-csharp[AdvancedInkTopicsSamples#5](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/Window1.xaml.cs#5)]  
  
<a name="Conclusion"></a>
## <a name="conclusion"></a><span data-ttu-id="b2b23-134">结束语</span><span class="sxs-lookup"><span data-stu-id="b2b23-134">Conclusion</span></span>  
 <span data-ttu-id="b2b23-135">通过派生自己的<xref:System.Windows.Input.StylusPlugIns.StylusPlugIn>类并将其插入到集合中<xref:System.Windows.Input.StylusPlugIns.StylusPlugInCollection>，可以极大地增强数字墨迹的行为。</span><span class="sxs-lookup"><span data-stu-id="b2b23-135">By deriving your own <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> classes and inserting them into <xref:System.Windows.Input.StylusPlugIns.StylusPlugInCollection> collections, you can greatly enhance the behavior of your digital ink.</span></span> <span data-ttu-id="b2b23-136">您可以在生成<xref:System.Windows.Input.StylusPoint>数据时访问数据，从而有机会自定义<xref:System.Windows.Input.Stylus>输入。</span><span class="sxs-lookup"><span data-stu-id="b2b23-136">You have access to the <xref:System.Windows.Input.StylusPoint> data as it is generated, giving you the opportunity to customize the <xref:System.Windows.Input.Stylus> input.</span></span> <span data-ttu-id="b2b23-137">由于您对<xref:System.Windows.Input.StylusPoint>数据具有如此低级别的访问，因此可以实现墨迹收集和呈现，从而为您的应用程序提供最佳性能。</span><span class="sxs-lookup"><span data-stu-id="b2b23-137">Because you have such low-level access to the <xref:System.Windows.Input.StylusPoint> data, you can implement ink collection and rendering with optimal performance for your application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b2b23-138">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b2b23-138">See also</span></span>

- [<span data-ttu-id="b2b23-139">高级墨迹处理</span><span class="sxs-lookup"><span data-stu-id="b2b23-139">Advanced Ink Handling</span></span>](advanced-ink-handling.md)
- <span data-ttu-id="b2b23-140">[访问和操作笔输入](https://docs.microsoft.com/previous-versions/ms818317(v%3dmsdn.10))</span><span class="sxs-lookup"><span data-stu-id="b2b23-140">[Accessing and Manipulating Pen Input](https://docs.microsoft.com/previous-versions/ms818317(v%3dmsdn.10))</span></span>
