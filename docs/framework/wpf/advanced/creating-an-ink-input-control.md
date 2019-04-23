---
title: 创建墨迹输入控件
ms.date: 03/30/2017
helpviewer_keywords:
- ink strokes [WPF], managing
- managing ink strokes [WPF]
- ink input control [WPF]
- input from mouse [WPF], accepting
- mouse input [WPF], accepting
- ink [WPF], rendering
- ink strokes [WPF], collecting
- rendering ink [WPF]
- collecting ink strokes [WPF]
- DynamicRenderer objects [WPF]
- StylusPlugIn objects [WPF]
ms.assetid: c31f3a67-cb3f-4ded-af9e-ed21f6575b26
ms.openlocfilehash: 105a44f90c1c654a21fc8920a149ad63b2dabc99
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59323845"
---
# <a name="creating-an-ink-input-control"></a><span data-ttu-id="f116e-102">创建墨迹输入控件</span><span class="sxs-lookup"><span data-stu-id="f116e-102">Creating an Ink Input Control</span></span>
<span data-ttu-id="f116e-103">您可以创建自定义控件的动态和静态呈现墨迹。</span><span class="sxs-lookup"><span data-stu-id="f116e-103">You can create a custom control that dynamically and statically renders ink.</span></span> <span data-ttu-id="f116e-104">这就是，根据用户绘制笔划，从而导致出现"流"从 tablet 笔，并在其后显示墨迹添加到该控件，通过触笔从剪贴板粘贴数据或从文件加载的手写内容呈现墨迹。</span><span class="sxs-lookup"><span data-stu-id="f116e-104">That is, render ink as a user draws a stroke, causing the ink to appear to "flow" from the tablet pen, and display ink after it is added to the control, either via the tablet pen, pasted from the Clipboard, or loaded from a file.</span></span> <span data-ttu-id="f116e-105">若要动态呈现墨迹，控件必须使用<xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>。</span><span class="sxs-lookup"><span data-stu-id="f116e-105">To dynamically render ink, your control must use a <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>.</span></span> <span data-ttu-id="f116e-106">若要以静态方式呈现墨迹，您必须重写触笔事件方法 (<xref:System.Windows.UIElement.OnStylusDown%2A>， <xref:System.Windows.UIElement.OnStylusMove%2A>，并<xref:System.Windows.UIElement.OnStylusUp%2A>) 来收集<xref:System.Windows.Input.StylusPoint>数据，创建的笔画，并将其添加到<xref:System.Windows.Controls.InkPresenter>（它将呈现在控件上的墨迹）。</span><span class="sxs-lookup"><span data-stu-id="f116e-106">To statically render ink, you must override the stylus event methods (<xref:System.Windows.UIElement.OnStylusDown%2A>, <xref:System.Windows.UIElement.OnStylusMove%2A>, and <xref:System.Windows.UIElement.OnStylusUp%2A>) to collect <xref:System.Windows.Input.StylusPoint> data, create strokes, and add them to an <xref:System.Windows.Controls.InkPresenter> (which renders the ink on the control).</span></span>  
  
 <span data-ttu-id="f116e-107">本主题包含以下小节：</span><span class="sxs-lookup"><span data-stu-id="f116e-107">This topic contains the following subsections:</span></span>  
  
-   [<span data-ttu-id="f116e-108">如何：收集触笔接触点数据并创建墨迹笔画</span><span class="sxs-lookup"><span data-stu-id="f116e-108">How to: Collect Stylus Point Data and Create Ink Strokes</span></span>](#CollectingStylusPointDataAndCreatingInkStrokes)  
  
-   [<span data-ttu-id="f116e-109">如何：使控件能够接受从鼠标输入</span><span class="sxs-lookup"><span data-stu-id="f116e-109">How to: Enable Your Control to Accept Input from the Mouse</span></span>](#EnablingYourControlToAcceptInputTromTheMouse)  
  
-   [<span data-ttu-id="f116e-110">将它放在一起</span><span class="sxs-lookup"><span data-stu-id="f116e-110">Putting it together</span></span>](#PuttingItTogether)  
  
-   [<span data-ttu-id="f116e-111">使用其他插件和 DynamicRenderers</span><span class="sxs-lookup"><span data-stu-id="f116e-111">Using Additional Plug-ins and DynamicRenderers</span></span>](#UsingAdditionalPluginsAndDynamicRenderers)  
  
-   [<span data-ttu-id="f116e-112">结束语</span><span class="sxs-lookup"><span data-stu-id="f116e-112">Conclusion</span></span>](#AdvancedInkHandling_Conclusion)  
  
<a name="CollectingStylusPointDataAndCreatingInkStrokes"></a>   
## <a name="how-to-collect-stylus-point-data-and-create-ink-strokes"></a><span data-ttu-id="f116e-113">如何：收集触笔接触点数据并创建墨迹笔画</span><span class="sxs-lookup"><span data-stu-id="f116e-113">How to: Collect Stylus Point Data and Create Ink Strokes</span></span>  
 <span data-ttu-id="f116e-114">若要创建的控件，可收集和管理墨迹笔画执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="f116e-114">To create a control that collects and manages ink strokes do the following:</span></span>  
  
1. <span data-ttu-id="f116e-115">从派生类<xref:System.Windows.Controls.Control>或其中一个类派生自<xref:System.Windows.Controls.Control>，如<xref:System.Windows.Controls.Label>。</span><span class="sxs-lookup"><span data-stu-id="f116e-115">Derive a class from <xref:System.Windows.Controls.Control> or one of the classes derived from <xref:System.Windows.Controls.Control>, such as <xref:System.Windows.Controls.Label>.</span></span>  
  
     [!code-csharp[AdvancedInkTopicsSamples#20](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControl.cs#20)]  
    [!code-csharp[AdvancedInkTopicsSamples#14](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControlSnippets.cs#14)]  
    [!code-csharp[AdvancedInkTopicsSamples#15](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControlSnippets.cs#15)]  
  
2. <span data-ttu-id="f116e-116">添加<xref:System.Windows.Controls.InkPresenter>向类和组<xref:System.Windows.Controls.ContentControl.Content%2A>属性设置为新<xref:System.Windows.Controls.InkPresenter>。</span><span class="sxs-lookup"><span data-stu-id="f116e-116">Add an <xref:System.Windows.Controls.InkPresenter> to the class and set the <xref:System.Windows.Controls.ContentControl.Content%2A> property to the new <xref:System.Windows.Controls.InkPresenter>.</span></span>  
  
     [!code-csharp[AdvancedInkTopicsSamples#16](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControlSnippets.cs#16)]  
  
3. <span data-ttu-id="f116e-117">附加<xref:System.Windows.Input.StylusPlugIns.DynamicRenderer.RootVisual%2A>的<xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>到<xref:System.Windows.Controls.InkPresenter>通过调用<xref:System.Windows.Controls.InkPresenter.AttachVisuals%2A>方法，并添加<xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>到<xref:System.Windows.UIElement.StylusPlugIns%2A>集合。</span><span class="sxs-lookup"><span data-stu-id="f116e-117">Attach the <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer.RootVisual%2A> of the <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> to the <xref:System.Windows.Controls.InkPresenter> by calling the <xref:System.Windows.Controls.InkPresenter.AttachVisuals%2A> method, and add the <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> to the <xref:System.Windows.UIElement.StylusPlugIns%2A> collection.</span></span> <span data-ttu-id="f116e-118">这允许<xref:System.Windows.Controls.InkPresenter>触笔接触点数据收集由控件显示墨迹。</span><span class="sxs-lookup"><span data-stu-id="f116e-118">This allows the <xref:System.Windows.Controls.InkPresenter> to display the ink as the stylus point data is collected by your control.</span></span>  
  
     [!code-csharp[AdvancedInkTopicsSamples#17](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControlSnippets.cs#17)]  
    [!code-csharp[AdvancedInkTopicsSamples#18](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControlSnippets.cs#18)]  
  
4. <span data-ttu-id="f116e-119">重写 <xref:System.Windows.UIElement.OnStylusDown%2A> 方法。</span><span class="sxs-lookup"><span data-stu-id="f116e-119">Override the <xref:System.Windows.UIElement.OnStylusDown%2A> method.</span></span>  <span data-ttu-id="f116e-120">在此方法，来获取调用触笔<xref:System.Windows.Input.Stylus.Capture%2A>。</span><span class="sxs-lookup"><span data-stu-id="f116e-120">In this method, capture the stylus with a call to <xref:System.Windows.Input.Stylus.Capture%2A>.</span></span> <span data-ttu-id="f116e-121">通过捕获触笔，控件将继续接收<xref:System.Windows.UIElement.StylusMove>和<xref:System.Windows.UIElement.StylusUp>事件，即使在触笔离开控件的边界。</span><span class="sxs-lookup"><span data-stu-id="f116e-121">By capturing the stylus, your control will to continue to receive <xref:System.Windows.UIElement.StylusMove> and <xref:System.Windows.UIElement.StylusUp> events even if the stylus leaves the control's boundaries.</span></span> <span data-ttu-id="f116e-122">这不是严格必需的但几乎总是需要进行很好的用户体验。</span><span class="sxs-lookup"><span data-stu-id="f116e-122">This is not strictly mandatory, but almost always desired for a good user experience.</span></span> <span data-ttu-id="f116e-123">创建一个新<xref:System.Windows.Input.StylusPointCollection>收集<xref:System.Windows.Input.StylusPoint>数据。</span><span class="sxs-lookup"><span data-stu-id="f116e-123">Create a new <xref:System.Windows.Input.StylusPointCollection> to gather <xref:System.Windows.Input.StylusPoint> data.</span></span> <span data-ttu-id="f116e-124">最后，添加一组初始<xref:System.Windows.Input.StylusPoint>数据到<xref:System.Windows.Input.StylusPointCollection>。</span><span class="sxs-lookup"><span data-stu-id="f116e-124">Finally, add the initial set of <xref:System.Windows.Input.StylusPoint> data to the <xref:System.Windows.Input.StylusPointCollection>.</span></span>  
  
     [!code-csharp[AdvancedInkTopicsSamples#7](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControl.cs#7)]  
  
5. <span data-ttu-id="f116e-125">重写<xref:System.Windows.UIElement.OnStylusMove%2A>方法并添加<xref:System.Windows.Input.StylusPoint>数据到<xref:System.Windows.Input.StylusPointCollection>前面创建的对象。</span><span class="sxs-lookup"><span data-stu-id="f116e-125">Override the <xref:System.Windows.UIElement.OnStylusMove%2A> method and add the <xref:System.Windows.Input.StylusPoint> data to the <xref:System.Windows.Input.StylusPointCollection> object that you created earlier.</span></span>  
  
     [!code-csharp[AdvancedInkTopicsSamples#8](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControl.cs#8)]  
  
6. <span data-ttu-id="f116e-126">重写<xref:System.Windows.UIElement.OnStylusUp%2A>方法创建一个新<xref:System.Windows.Ink.Stroke>与<xref:System.Windows.Input.StylusPointCollection>数据。</span><span class="sxs-lookup"><span data-stu-id="f116e-126">Override the <xref:System.Windows.UIElement.OnStylusUp%2A> method and create a new <xref:System.Windows.Ink.Stroke> with the <xref:System.Windows.Input.StylusPointCollection> data.</span></span> <span data-ttu-id="f116e-127">添加新<xref:System.Windows.Ink.Stroke>创建到<xref:System.Windows.Controls.InkPresenter.Strokes%2A>的集合<xref:System.Windows.Controls.InkPresenter>并释放触笔捕获。</span><span class="sxs-lookup"><span data-stu-id="f116e-127">Add the new <xref:System.Windows.Ink.Stroke> you created to the <xref:System.Windows.Controls.InkPresenter.Strokes%2A> collection of the <xref:System.Windows.Controls.InkPresenter> and release stylus capture.</span></span>  
  
     [!code-csharp[AdvancedInkTopicsSamples#10](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControl.cs#10)]  
  
<a name="EnablingYourControlToAcceptInputTromTheMouse"></a>   
## <a name="how-to-enable-your-control-to-accept-input-from-the-mouse"></a><span data-ttu-id="f116e-128">如何：使控件能够接受从鼠标输入</span><span class="sxs-lookup"><span data-stu-id="f116e-128">How to: Enable Your Control to Accept Input from the Mouse</span></span>  
 <span data-ttu-id="f116e-129">如果将前面的控件添加到你的应用程序、 运行它，并使用鼠标输入设备，你会注意到笔画不会保留。</span><span class="sxs-lookup"><span data-stu-id="f116e-129">If you add the preceding control to your application, run it, and use the mouse as an input device, you will notice that the strokes are not persisted.</span></span> <span data-ttu-id="f116e-130">若要持久保存的笔画鼠标用作输入的设备时执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="f116e-130">To persist the strokes when the mouse is used as the input device do the following:</span></span>  
  
1. <span data-ttu-id="f116e-131">重写<xref:System.Windows.UIElement.OnMouseLeftButtonDown%2A>并创建一个新<xref:System.Windows.Input.StylusPointCollection>在事件发生时获取鼠标的位置，并创建<xref:System.Windows.Input.StylusPoint>使用点数据，并添加<xref:System.Windows.Input.StylusPoint>到<xref:System.Windows.Input.StylusPointCollection>。</span><span class="sxs-lookup"><span data-stu-id="f116e-131">Override the <xref:System.Windows.UIElement.OnMouseLeftButtonDown%2A> and create a new <xref:System.Windows.Input.StylusPointCollection> Get the position of the mouse when the event occurred and create a <xref:System.Windows.Input.StylusPoint> using the point data and add the <xref:System.Windows.Input.StylusPoint> to the <xref:System.Windows.Input.StylusPointCollection>.</span></span>  
  
     [!code-csharp[AdvancedInkTopicsSamples#11](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControl.cs#11)]  
  
2. <span data-ttu-id="f116e-132">重写 <xref:System.Windows.UIElement.OnMouseMove%2A> 方法。</span><span class="sxs-lookup"><span data-stu-id="f116e-132">Override the <xref:System.Windows.UIElement.OnMouseMove%2A> method.</span></span> <span data-ttu-id="f116e-133">在事件发生时获取鼠标的位置，并创建<xref:System.Windows.Input.StylusPoint>使用点数据。</span><span class="sxs-lookup"><span data-stu-id="f116e-133">Get the position of the mouse when the event occurred and create a <xref:System.Windows.Input.StylusPoint> using the point data.</span></span>  <span data-ttu-id="f116e-134">添加<xref:System.Windows.Input.StylusPoint>到<xref:System.Windows.Input.StylusPointCollection>前面创建的对象。</span><span class="sxs-lookup"><span data-stu-id="f116e-134">Add the <xref:System.Windows.Input.StylusPoint> to the <xref:System.Windows.Input.StylusPointCollection> object that you created earlier.</span></span>  
  
     [!code-csharp[AdvancedInkTopicsSamples#12](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControl.cs#12)]  
  
3. <span data-ttu-id="f116e-135">重写 <xref:System.Windows.UIElement.OnMouseLeftButtonUp%2A> 方法。</span><span class="sxs-lookup"><span data-stu-id="f116e-135">Override the <xref:System.Windows.UIElement.OnMouseLeftButtonUp%2A> method.</span></span>  <span data-ttu-id="f116e-136">创建一个新<xref:System.Windows.Ink.Stroke>与<xref:System.Windows.Input.StylusPointCollection>数据，并添加新<xref:System.Windows.Ink.Stroke>您创建到<xref:System.Windows.Controls.InkPresenter.Strokes%2A>的集合<xref:System.Windows.Controls.InkPresenter>。</span><span class="sxs-lookup"><span data-stu-id="f116e-136">Create a new <xref:System.Windows.Ink.Stroke> with the <xref:System.Windows.Input.StylusPointCollection> data, and add the new <xref:System.Windows.Ink.Stroke> you created to the <xref:System.Windows.Controls.InkPresenter.Strokes%2A> collection of the <xref:System.Windows.Controls.InkPresenter>.</span></span>  
  
     [!code-csharp[AdvancedInkTopicsSamples#13](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControl.cs#13)]  
  
<a name="PuttingItTogether"></a>   
## <a name="putting-it-together"></a><span data-ttu-id="f116e-137">将它放在一起</span><span class="sxs-lookup"><span data-stu-id="f116e-137">Putting it together</span></span>  
 <span data-ttu-id="f116e-138">下面的示例是当用户使用鼠标或触笔收集墨迹的自定义控件。</span><span class="sxs-lookup"><span data-stu-id="f116e-138">The following example is a custom control that collects ink when the user uses either the mouse or the pen.</span></span>  
  
 [!code-csharp[AdvancedInkTopicsSamples#20](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControl.cs#20)]  
[!code-csharp[AdvancedInkTopicsSamples#6](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/StylusControl.cs#6)]  
  
<a name="UsingAdditionalPluginsAndDynamicRenderers"></a>   
## <a name="using-additional-plug-ins-and-dynamicrenderers"></a><span data-ttu-id="f116e-139">使用其他插件和 DynamicRenderers</span><span class="sxs-lookup"><span data-stu-id="f116e-139">Using Additional Plug-ins and DynamicRenderers</span></span>  
 <span data-ttu-id="f116e-140">在 InkCanvas，如自定义控件可以具有自定义<xref:System.Windows.Input.StylusPlugIns.StylusPlugIn>和其他<xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>对象。</span><span class="sxs-lookup"><span data-stu-id="f116e-140">Like the InkCanvas, your custom control can have custom <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> and additional <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> objects.</span></span> <span data-ttu-id="f116e-141">将它们添加到<xref:System.Windows.UIElement.StylusPlugIns%2A>集合。</span><span class="sxs-lookup"><span data-stu-id="f116e-141">Add these to the <xref:System.Windows.UIElement.StylusPlugIns%2A> collection.</span></span> <span data-ttu-id="f116e-142">顺序<xref:System.Windows.Input.StylusPlugIns.StylusPlugIn>中的对象<xref:System.Windows.Input.StylusPlugIns.StylusPlugInCollection>呈现时，会影响墨迹的外观。</span><span class="sxs-lookup"><span data-stu-id="f116e-142">The order of the <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> objects in the <xref:System.Windows.Input.StylusPlugIns.StylusPlugInCollection> affects the appearance of the ink when it is rendered.</span></span> <span data-ttu-id="f116e-143">假设您有<xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>称为`dynamicRenderer`和自定义<xref:System.Windows.Input.StylusPlugIns.StylusPlugIn>调用`translatePlugin`的偏移量从 tablet 笔墨迹。</span><span class="sxs-lookup"><span data-stu-id="f116e-143">Suppose you have a <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> called `dynamicRenderer` and a custom <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> called `translatePlugin` that offsets the ink from the tablet pen.</span></span> <span data-ttu-id="f116e-144">如果`translatePlugin`是第一个<xref:System.Windows.Input.StylusPlugIns.StylusPlugIn>中<xref:System.Windows.Input.StylusPlugIns.StylusPlugInCollection>，和`dynamicRenderer`是第二，当用户移动笔将偏移"流"的墨迹。</span><span class="sxs-lookup"><span data-stu-id="f116e-144">If `translatePlugin` is the first <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> in the <xref:System.Windows.Input.StylusPlugIns.StylusPlugInCollection>, and `dynamicRenderer` is the second, the ink that "flows" will be offset as the user moves the pen.</span></span> <span data-ttu-id="f116e-145">如果`dynamicRenderer`第一次，和`translatePlugin`是第二个，墨迹将不会在用户提起笔之前偏移。</span><span class="sxs-lookup"><span data-stu-id="f116e-145">If `dynamicRenderer` is first, and `translatePlugin` is second, the ink will not be offset until the user lifts the pen.</span></span>  
  
<a name="AdvancedInkHandling_Conclusion"></a>   
## <a name="conclusion"></a><span data-ttu-id="f116e-146">结束语</span><span class="sxs-lookup"><span data-stu-id="f116e-146">Conclusion</span></span>  
 <span data-ttu-id="f116e-147">可以创建一个控件，可收集和通过重写的触笔事件方法呈现墨迹。</span><span class="sxs-lookup"><span data-stu-id="f116e-147">You can create a control that collects and renders ink by overriding the stylus event methods.</span></span> <span data-ttu-id="f116e-148">通过创建自己的控件，派生您自己<xref:System.Windows.Input.StylusPlugIns.StylusPlugIn>类，并将它们插入到<xref:System.Windows.Input.StylusPlugIns.StylusPlugInCollection>，可以实现与数字墨迹想象几乎任何行为。</span><span class="sxs-lookup"><span data-stu-id="f116e-148">By creating your own control, deriving your own <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn> classes, and inserting them the into <xref:System.Windows.Input.StylusPlugIns.StylusPlugInCollection>, you can implement virtually any behavior imaginable with digital ink.</span></span> <span data-ttu-id="f116e-149">你有权<xref:System.Windows.Input.StylusPoint>生成数据时，您可以自定义<xref:System.Windows.Input.Stylus>输入，并根据你的应用程序在屏幕上呈现它。</span><span class="sxs-lookup"><span data-stu-id="f116e-149">You have access to the <xref:System.Windows.Input.StylusPoint> data as it is generated, giving you the opportunity to  customize <xref:System.Windows.Input.Stylus> input and render it on the screen as appropriate for your application.</span></span> <span data-ttu-id="f116e-150">因为此类低级别访问<xref:System.Windows.Input.StylusPoint>数据，可以实现墨迹收集，并使其具有优化性能的应用程序。</span><span class="sxs-lookup"><span data-stu-id="f116e-150">Because you have such low-level access to the <xref:System.Windows.Input.StylusPoint> data, you can implement ink collection and render it with optimal performance for your application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f116e-151">请参阅</span><span class="sxs-lookup"><span data-stu-id="f116e-151">See also</span></span>

- [<span data-ttu-id="f116e-152">高级墨迹处理</span><span class="sxs-lookup"><span data-stu-id="f116e-152">Advanced Ink Handling</span></span>](advanced-ink-handling.md)
- [<span data-ttu-id="f116e-153">访问和操作笔输入</span><span class="sxs-lookup"><span data-stu-id="f116e-153">Accessing and Manipulating Pen Input</span></span>](https://go.microsoft.com/fwlink/?LinkId=50752&clcid=0x409)
