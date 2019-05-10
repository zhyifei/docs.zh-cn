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
ms.openlocfilehash: 76976f1599ecbbaf7405d7941f66aa2c5f955565
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "64598957"
---
# <a name="intercepting-input-from-the-stylus"></a><span data-ttu-id="279bf-102">截获触笔输入</span><span class="sxs-lookup"><span data-stu-id="279bf-102">Intercepting Input from the Stylus</span></span>
<span data-ttu-id="279bf-103"><xref:System.Windows.Input.StylusPlugIns>体系结构提供了用于通过实现低级别控制的机制<xref:System.Windows.Input.Stylus>输入和数字墨迹创建<xref:System.Windows.Ink.Stroke>对象。</span><span class="sxs-lookup"><span data-stu-id="279bf-103">The <xref:System.Windows.Input.StylusPlugIns> architecture provides a mechanism for implementing low-level control over <xref:System.Windows.Input.Stylus> input and the creation of digital ink <xref:System.Windows.Ink.Stroke> objects.</span></span> <span data-ttu-id="279bf-104"><xref:System.Windows.Input.StylusPlugIns.StylusPlugIn>类提供了一种机制，以实现自定义行为，并将其应用到从触笔设备以获得最佳性能的数据的流。</span><span class="sxs-lookup"><span data-stu-id="279bf-104">The <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> class provides a mechanism for you to implement custom behavior and apply it to the stream of data coming from the stylus device for the optimal performance.</span></span>  
  
 <span data-ttu-id="279bf-105">本主题包含以下小节：</span><span class="sxs-lookup"><span data-stu-id="279bf-105">This topic contains the following subsections:</span></span>  
  
- [<span data-ttu-id="279bf-106">体系结构</span><span class="sxs-lookup"><span data-stu-id="279bf-106">Architecture</span></span>](#Architecture)  
  
- [<span data-ttu-id="279bf-107">实现触笔插件</span><span class="sxs-lookup"><span data-stu-id="279bf-107">Implementing Stylus Plug-ins</span></span>](#ImplementingStylusPlugins)  
  
- [<span data-ttu-id="279bf-108">将插件添加到 InkCanvas</span><span class="sxs-lookup"><span data-stu-id="279bf-108">Adding Your Plug-in to an InkCanvas</span></span>](#AddingYourPluginToAnInkCanvas)  
  
- [<span data-ttu-id="279bf-109">结束语</span><span class="sxs-lookup"><span data-stu-id="279bf-109">Conclusion</span></span>](#Conclusion)  
  
<a name="Architecture"></a>   
## <a name="architecture"></a><span data-ttu-id="279bf-110">体系结构</span><span class="sxs-lookup"><span data-stu-id="279bf-110">Architecture</span></span>  
 <span data-ttu-id="279bf-111"><xref:System.Windows.Input.StylusPlugIns.StylusPlugIn>的演进[StylusInput](https://go.microsoft.com/fwlink/?LinkId=50753&clcid=0x409)中所述的 Api[访问和操作笔输入](https://go.microsoft.com/fwlink/?LinkId=50752&clcid=0x409)中[Microsoft Windows XP Tablet PC Edition 软件Kit 1.7](https://go.microsoft.com/fwlink/?linkid=11782&clcid=0x409)。</span><span class="sxs-lookup"><span data-stu-id="279bf-111">The <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> is the evolution of the [StylusInput](https://go.microsoft.com/fwlink/?LinkId=50753&clcid=0x409) APIs, described in [Accessing and Manipulating Pen Input](https://go.microsoft.com/fwlink/?LinkId=50752&clcid=0x409), in the [Microsoft Windows XP Tablet PC Edition Software Development Kit 1.7](https://go.microsoft.com/fwlink/?linkid=11782&clcid=0x409).</span></span>  
  
 <span data-ttu-id="279bf-112">每个<xref:System.Windows.UIElement>已<xref:System.Windows.UIElement.StylusPlugIns%2A>是属性<xref:System.Windows.Input.StylusPlugIns.StylusPlugInCollection>。</span><span class="sxs-lookup"><span data-stu-id="279bf-112">Each <xref:System.Windows.UIElement> has a <xref:System.Windows.UIElement.StylusPlugIns%2A> property that is a <xref:System.Windows.Input.StylusPlugIns.StylusPlugInCollection>.</span></span> <span data-ttu-id="279bf-113">您可以添加<xref:System.Windows.Input.StylusPlugIns.StylusPlugIn>的元素<xref:System.Windows.UIElement.StylusPlugIns%2A>属性来操作<xref:System.Windows.Input.StylusPoint>生成作为它的数据。</span><span class="sxs-lookup"><span data-stu-id="279bf-113">You can add a <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> to an element's <xref:System.Windows.UIElement.StylusPlugIns%2A> property to manipulate <xref:System.Windows.Input.StylusPoint> data as it is generated.</span></span> <span data-ttu-id="279bf-114"><xref:System.Windows.Input.StylusPoint> 数据包含的所有系统数字化器，包括支持的属性<xref:System.Windows.Input.StylusPoint.X%2A>并<xref:System.Windows.Input.StylusPoint.Y%2A>点数据，以及<xref:System.Windows.Input.StylusPoint.PressureFactor%2A>数据。</span><span class="sxs-lookup"><span data-stu-id="279bf-114"><xref:System.Windows.Input.StylusPoint> data consists of all the properties supported by the system digitizer, including the <xref:System.Windows.Input.StylusPoint.X%2A> and <xref:System.Windows.Input.StylusPoint.Y%2A> point data, as well as <xref:System.Windows.Input.StylusPoint.PressureFactor%2A> data.</span></span>  
  
 <span data-ttu-id="279bf-115">你<xref:System.Windows.Input.StylusPlugIns.StylusPlugIn>对象插入到流中的数据来自直接<xref:System.Windows.Input.Stylus>设备添加时<xref:System.Windows.Input.StylusPlugIns.StylusPlugIn>到<xref:System.Windows.UIElement.StylusPlugIns%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="279bf-115">Your <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> objects are inserted directly into the stream of data coming from the <xref:System.Windows.Input.Stylus> device when you add the <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> to the <xref:System.Windows.UIElement.StylusPlugIns%2A> property.</span></span> <span data-ttu-id="279bf-116">管理单元添加到中的顺序<xref:System.Windows.UIElement.StylusPlugIns%2A>集合的顺序指定将收到<xref:System.Windows.Input.StylusPoint>数据。</span><span class="sxs-lookup"><span data-stu-id="279bf-116">The order in which plug-ins are added to the <xref:System.Windows.UIElement.StylusPlugIns%2A> collection dictates the order in which they will receive <xref:System.Windows.Input.StylusPoint> data.</span></span> <span data-ttu-id="279bf-117">例如，如果您添加筛选器插件，将输入限制为特定的区域，以及如何将写入时识别的笔势的插件，识别的笔势插件将接收已筛选<xref:System.Windows.Input.StylusPoint>数据。</span><span class="sxs-lookup"><span data-stu-id="279bf-117">For example, if you add a filter plug-in that restricts input to a particular region, and then add a plug-in that recognizes gestures as they are written, the plug-in that recognizes gestures will receive filtered <xref:System.Windows.Input.StylusPoint> data.</span></span>  
  
<a name="ImplementingStylusPlugins"></a>   
## <a name="implementing-stylus-plug-ins"></a><span data-ttu-id="279bf-118">实现触笔插件</span><span class="sxs-lookup"><span data-stu-id="279bf-118">Implementing Stylus Plug-ins</span></span>  
 <span data-ttu-id="279bf-119">若要将插件实现，派生的类从<xref:System.Windows.Input.StylusPlugIns.StylusPlugIn>。</span><span class="sxs-lookup"><span data-stu-id="279bf-119">To implement a plug-in, derive a class from <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn>.</span></span> <span data-ttu-id="279bf-120">此类是应用的 o 数据的流，因为它来自<xref:System.Windows.Input.Stylus>。</span><span class="sxs-lookup"><span data-stu-id="279bf-120">This class is applied o the stream of data as it comes in from the <xref:System.Windows.Input.Stylus>.</span></span> <span data-ttu-id="279bf-121">在此类可以通过修改的值<xref:System.Windows.Input.StylusPoint>数据。</span><span class="sxs-lookup"><span data-stu-id="279bf-121">In this class you can modify the values of the <xref:System.Windows.Input.StylusPoint> data.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="279bf-122">如果<xref:System.Windows.Input.StylusPlugIns.StylusPlugIn>引发或导致异常，应用程序将关闭。</span><span class="sxs-lookup"><span data-stu-id="279bf-122">If a <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> throws or causes an exception, the application will close.</span></span> <span data-ttu-id="279bf-123">您应该全面测试使用的控件<xref:System.Windows.Input.StylusPlugIns.StylusPlugIn>并且只使用一个控件，如果您确信<xref:System.Windows.Input.StylusPlugIns.StylusPlugIn>不会引发异常。</span><span class="sxs-lookup"><span data-stu-id="279bf-123">You should thoroughly test controls that consume a <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> and only use a control if you are certain the <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> will not throw an exception.</span></span>  
  
 <span data-ttu-id="279bf-124">下面的示例演示一个插件，通过修改限制触笔输入<xref:System.Windows.Input.StylusPoint.X%2A>并<xref:System.Windows.Input.StylusPoint.Y%2A>中的值<xref:System.Windows.Input.StylusPoint>作为它的数据来自<xref:System.Windows.Input.Stylus>设备。</span><span class="sxs-lookup"><span data-stu-id="279bf-124">The following example demonstrates a plug-in that restricts the stylus input by modifying the <xref:System.Windows.Input.StylusPoint.X%2A> and <xref:System.Windows.Input.StylusPoint.Y%2A> values in the <xref:System.Windows.Input.StylusPoint> data as it comes in from the <xref:System.Windows.Input.Stylus> device.</span></span>  
  
 [!code-csharp[AdvancedInkTopicsSamples#19](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/DynamicRenderer.cs#19)]
 [!code-vb[AdvancedInkTopicsSamples#19](~/samples/snippets/visualbasic/VS_Snippets_Wpf/AdvancedInkTopicsSamples/VisualBasic/DynamicRenderer.vb#19)]  
[!code-csharp[AdvancedInkTopicsSamples#3](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/DynamicRenderer.cs#3)]
[!code-vb[AdvancedInkTopicsSamples#3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/AdvancedInkTopicsSamples/VisualBasic/DynamicRenderer.vb#3)]  
  
<a name="AddingYourPluginToAnInkCanvas"></a>   
## <a name="adding-your-plug-in-to-an-inkcanvas"></a><span data-ttu-id="279bf-125">将插件添加到 InkCanvas</span><span class="sxs-lookup"><span data-stu-id="279bf-125">Adding Your Plug-in to an InkCanvas</span></span>  
 <span data-ttu-id="279bf-126">若要使用自定义插件的最简单方法是实现从 InkCanvas 派生而来的类并将其添加到<xref:System.Windows.UIElement.StylusPlugIns%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="279bf-126">The easiest way to use your custom plug-in is to implement a class that derives from InkCanvas and add it to the <xref:System.Windows.UIElement.StylusPlugIns%2A> property.</span></span>  
  
 <span data-ttu-id="279bf-127">下面的示例演示自定义<xref:System.Windows.Controls.InkCanvas>对墨迹进行筛选。</span><span class="sxs-lookup"><span data-stu-id="279bf-127">The following example demonstrates a custom <xref:System.Windows.Controls.InkCanvas> that filters the ink.</span></span>  
  
 [!code-csharp[AdvancedInkTopicsSamples#4](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/Window1.xaml.cs#4)]  
  
 <span data-ttu-id="279bf-128">如果添加`FilterInkCanvas`到应用程序并运行它，你会注意到在用户完成一个笔画后手写内容并不局限于之前的区域。</span><span class="sxs-lookup"><span data-stu-id="279bf-128">If you add a `FilterInkCanvas` to your application and run it, you will notice that the ink isn't restricted to a region until after the user completes a stroke.</span></span> <span data-ttu-id="279bf-129">这是因为<xref:System.Windows.Controls.InkCanvas>已<xref:System.Windows.Controls.InkCanvas.DynamicRenderer%2A>属性，即<xref:System.Windows.Input.StylusPlugIns.StylusPlugIn>已经是成员的和<xref:System.Windows.UIElement.StylusPlugIns%2A>集合。</span><span class="sxs-lookup"><span data-stu-id="279bf-129">This is because the <xref:System.Windows.Controls.InkCanvas> has a <xref:System.Windows.Controls.InkCanvas.DynamicRenderer%2A> property, which is a <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> and is already a member of the <xref:System.Windows.UIElement.StylusPlugIns%2A> collection.</span></span> <span data-ttu-id="279bf-130">自定义<xref:System.Windows.Input.StylusPlugIns.StylusPlugIn>你添加到<xref:System.Windows.UIElement.StylusPlugIns%2A>集合接收<xref:System.Windows.Input.StylusPoint>之后，数据<xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>接收数据。</span><span class="sxs-lookup"><span data-stu-id="279bf-130">The custom <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> you added to the <xref:System.Windows.UIElement.StylusPlugIns%2A> collection receives the <xref:System.Windows.Input.StylusPoint> data after <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> receives data.</span></span> <span data-ttu-id="279bf-131">因此，<xref:System.Windows.Input.StylusPoint>数据在用户抬起笔结束笔画后不会直到筛选。</span><span class="sxs-lookup"><span data-stu-id="279bf-131">As a result, the <xref:System.Windows.Input.StylusPoint> data will not be filtered until after the user lifts the pen to end a stroke.</span></span> <span data-ttu-id="279bf-132">若要筛选用户将其绘制手写内容，必须插入`FilterPlugin`之前<xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>。</span><span class="sxs-lookup"><span data-stu-id="279bf-132">To filter the ink as the user draws it, you must insert the `FilterPlugin` before the <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>.</span></span>  
  
 <span data-ttu-id="279bf-133">下面的 C# 代码演示一个自定义<xref:System.Windows.Controls.InkCanvas>是绘制筛选手写内容。</span><span class="sxs-lookup"><span data-stu-id="279bf-133">The following C# code demonstrates a custom <xref:System.Windows.Controls.InkCanvas> that filters the ink as it is drawn.</span></span>  
  
 [!code-csharp[AdvancedInkTopicsSamples#5](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/Window1.xaml.cs#5)]  
  
<a name="Conclusion"></a>   
## <a name="conclusion"></a><span data-ttu-id="279bf-134">结束语</span><span class="sxs-lookup"><span data-stu-id="279bf-134">Conclusion</span></span>  
 <span data-ttu-id="279bf-135">通过派生您自己<xref:System.Windows.Input.StylusPlugIns.StylusPlugIn>类并将它们到插入<xref:System.Windows.Input.StylusPlugIns.StylusPlugInCollection>集合，可以极大地提高你数字墨迹的行为。</span><span class="sxs-lookup"><span data-stu-id="279bf-135">By deriving your own <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> classes and inserting them into <xref:System.Windows.Input.StylusPlugIns.StylusPlugInCollection> collections, you can greatly enhance the behavior of your digital ink.</span></span> <span data-ttu-id="279bf-136">你有权<xref:System.Windows.Input.StylusPoint>生成数据时，您可以自定义<xref:System.Windows.Input.Stylus>输入。</span><span class="sxs-lookup"><span data-stu-id="279bf-136">You have access to the <xref:System.Windows.Input.StylusPoint> data as it is generated, giving you the opportunity to customize the <xref:System.Windows.Input.Stylus> input.</span></span> <span data-ttu-id="279bf-137">因为此类低级别访问<xref:System.Windows.Input.StylusPoint>数据，可以为你的应用程序实现墨迹收集和呈现具有优化性能。</span><span class="sxs-lookup"><span data-stu-id="279bf-137">Because you have such low-level access to the <xref:System.Windows.Input.StylusPoint> data, you can implement ink collection and rendering with optimal performance for your application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="279bf-138">请参阅</span><span class="sxs-lookup"><span data-stu-id="279bf-138">See also</span></span>

- [<span data-ttu-id="279bf-139">高级墨迹处理</span><span class="sxs-lookup"><span data-stu-id="279bf-139">Advanced Ink Handling</span></span>](advanced-ink-handling.md)
- [<span data-ttu-id="279bf-140">访问和操作笔输入</span><span class="sxs-lookup"><span data-stu-id="279bf-140">Accessing and Manipulating Pen Input</span></span>](https://go.microsoft.com/fwlink/?LinkId=50752&clcid=0x409)
