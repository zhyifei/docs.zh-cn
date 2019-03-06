---
title: WPF 应用程序中收集墨迹
ms.date: 08/15/2018
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ink [WPF], collecting
- InkCanvas element [WPF]
- properties [WPF], DrawingAttributes
- collecting digital ink [WPF]
- digital ink [WPF], collecting
- properties [WPF], DefaultDrawingAttributes
- DefaultDrawingAttributes property [WPF]
ms.assetid: 66a3129d-9577-43eb-acbd-56c147282016
ms.openlocfilehash: 0d0796eae469f8a40e01e3de02c00149eb3f00c7
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/05/2019
ms.locfileid: "57374669"
---
# <a name="collect-ink"></a><span data-ttu-id="98d47-102">收集墨迹</span><span class="sxs-lookup"><span data-stu-id="98d47-102">Collect Ink</span></span>

<span data-ttu-id="98d47-103">[Windows Presentation Foundation](../index.md) 平台会收集数字墨迹，这是其功能中的核心部分之一。</span><span class="sxs-lookup"><span data-stu-id="98d47-103">The [Windows Presentation Foundation](../index.md) platform collects digital ink as a core part of its functionality.</span></span> <span data-ttu-id="98d47-104">本主题讨论用于收集墨迹 Windows Presentation Foundation (WPF) 中的方法。</span><span class="sxs-lookup"><span data-stu-id="98d47-104">This topic discusses methods for collection of ink in Windows Presentation Foundation (WPF).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="98d47-105">系统必备</span><span class="sxs-lookup"><span data-stu-id="98d47-105">Prerequisites</span></span>

<span data-ttu-id="98d47-106">若要使用下面的示例，必须首先安装 Visual Studio 和[!INCLUDE[TLA2#tla_winfxsdk](../../../../includes/tla2sharptla-winfxsdk-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="98d47-106">To use the following examples, you must first install Visual Studio and the [!INCLUDE[TLA2#tla_winfxsdk](../../../../includes/tla2sharptla-winfxsdk-md.md)].</span></span> <span data-ttu-id="98d47-107">您还应了解如何编写 WPF 应用程序。</span><span class="sxs-lookup"><span data-stu-id="98d47-107">You should also understand how to write applications for the WPF.</span></span> <span data-ttu-id="98d47-108">有关如何开始使用 WPF 的详细信息，请参阅[演练：我第一个 WPF 桌面应用程序](../getting-started/walkthrough-my-first-wpf-desktop-application.md)。</span><span class="sxs-lookup"><span data-stu-id="98d47-108">For more information about getting started with WPF, see [Walkthrough: My first WPF desktop application](../getting-started/walkthrough-my-first-wpf-desktop-application.md).</span></span>

## <a name="use-the-inkcanvas-element"></a><span data-ttu-id="98d47-109">使用 InkCanvas 元素</span><span class="sxs-lookup"><span data-stu-id="98d47-109">Use the InkCanvas Element</span></span>

<span data-ttu-id="98d47-110"><xref:System.Windows.Controls.InkCanvas?displayProperty=fullName>元素提供 WPF 中收集墨迹的最简单方法。</span><span class="sxs-lookup"><span data-stu-id="98d47-110">The <xref:System.Windows.Controls.InkCanvas?displayProperty=fullName> element provides the easiest way to collect ink in WPF.</span></span> <span data-ttu-id="98d47-111">使用<xref:System.Windows.Controls.InkCanvas>元素可接收和显示墨迹输入。</span><span class="sxs-lookup"><span data-stu-id="98d47-111">Use an <xref:System.Windows.Controls.InkCanvas> element to receive and display ink input.</span></span> <span data-ttu-id="98d47-112">通常使用触笔（与数字化仪交互产生墨迹笔画）输入墨迹。</span><span class="sxs-lookup"><span data-stu-id="98d47-112">You commonly input ink through the use of a stylus, which interacts with a digitizer to produce ink strokes.</span></span> <span data-ttu-id="98d47-113">此外，还可以使用鼠标代替触笔。</span><span class="sxs-lookup"><span data-stu-id="98d47-113">In addition, a mouse can be used in place of a stylus.</span></span> <span data-ttu-id="98d47-114">创建的笔画表示为<xref:System.Windows.Ink.Stroke>对象，并且它们可以操作以编程方式和用户输入。</span><span class="sxs-lookup"><span data-stu-id="98d47-114">The created strokes are represented as <xref:System.Windows.Ink.Stroke> objects, and they can be manipulated both programmatically and by user input.</span></span> <span data-ttu-id="98d47-115"><xref:System.Windows.Controls.InkCanvas>使用户能够选择、 修改或删除现有<xref:System.Windows.Ink.Stroke>。</span><span class="sxs-lookup"><span data-stu-id="98d47-115">The <xref:System.Windows.Controls.InkCanvas> enables users to select, modify, or delete an existing <xref:System.Windows.Ink.Stroke>.</span></span>

<span data-ttu-id="98d47-116">通过使用 XAML，您可以设置墨迹收集与添加轻松**InkCanvas**到树的元素。</span><span class="sxs-lookup"><span data-stu-id="98d47-116">By using XAML, you can set up ink collection as easily as adding an **InkCanvas** element to your tree.</span></span> <span data-ttu-id="98d47-117">下面的示例添加<xref:System.Windows.Controls.InkCanvas>到 Visual Studio 中创建一个默认 WPF 项目：</span><span class="sxs-lookup"><span data-stu-id="98d47-117">The following example adds an <xref:System.Windows.Controls.InkCanvas> to a default WPF project created in Visual Studio:</span></span>

[!code-xaml[DigitalInkTopics#6](~/samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window2.xaml#6)]

<span data-ttu-id="98d47-118">**InkCanvas**元素还可以包含子元素，这样便可以将墨迹批注功能添加到几乎任何类型的 XAML 元素。</span><span class="sxs-lookup"><span data-stu-id="98d47-118">The **InkCanvas** element can also contain child elements, making it possible to add ink annotation capabilities to almost any type of XAML element.</span></span> <span data-ttu-id="98d47-119">例如，若要将墨迹功能添加到文本元素，只需使其成为子的<xref:System.Windows.Controls.InkCanvas>:</span><span class="sxs-lookup"><span data-stu-id="98d47-119">For example, to add inking capabilities to a text element, simply make it a child of an <xref:System.Windows.Controls.InkCanvas>:</span></span>

[!code-xaml[DigitalInkTopics#5](~/samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window2.xaml#5)]

<span data-ttu-id="98d47-120">添加图像墨迹标记支持操作同样非常简单：</span><span class="sxs-lookup"><span data-stu-id="98d47-120">Adding support for marking up an image with ink is just as easy:</span></span>

[!code-xaml[DigitalInkTopics#7](~/samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window2.xaml#7)]

### <a name="inkcollection-modes"></a><span data-ttu-id="98d47-121">InkCollection 模式</span><span class="sxs-lookup"><span data-stu-id="98d47-121">InkCollection Modes</span></span>

<span data-ttu-id="98d47-122"><xref:System.Windows.Controls.InkCanvas>提供支持，对各种输入模式通过其<xref:System.Windows.Controls.InkCanvas.EditingMode%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="98d47-122">The <xref:System.Windows.Controls.InkCanvas> provides support for various input modes through its <xref:System.Windows.Controls.InkCanvas.EditingMode%2A> property.</span></span>

### <a name="manipulate-ink"></a><span data-ttu-id="98d47-123">操作墨迹</span><span class="sxs-lookup"><span data-stu-id="98d47-123">Manipulate Ink</span></span>

<span data-ttu-id="98d47-124"><xref:System.Windows.Controls.InkCanvas>对多种墨迹编辑操作提供支持。</span><span class="sxs-lookup"><span data-stu-id="98d47-124">The <xref:System.Windows.Controls.InkCanvas> provides support for many ink editing operations.</span></span> <span data-ttu-id="98d47-125">例如，<xref:System.Windows.Controls.InkCanvas>支持笔后清除图像以及任何其他代码需要将该功能添加到元素。</span><span class="sxs-lookup"><span data-stu-id="98d47-125">For example, <xref:System.Windows.Controls.InkCanvas> supports back-of-pen erase, and no additional code is needed to add the functionality to the element.</span></span>

#### <a name="selection"></a><span data-ttu-id="98d47-126">选择</span><span class="sxs-lookup"><span data-stu-id="98d47-126">Selection</span></span>

<span data-ttu-id="98d47-127">设置选择模式非常简单，只设置<xref:System.Windows.Controls.InkCanvasEditingMode>属性设置为**选择**。</span><span class="sxs-lookup"><span data-stu-id="98d47-127">Setting selection mode is as simple as setting the <xref:System.Windows.Controls.InkCanvasEditingMode> property to **Select**.</span></span>

<span data-ttu-id="98d47-128">下面的代码设置值的基础的编辑模式<xref:System.Windows.Forms.CheckBox>:</span><span class="sxs-lookup"><span data-stu-id="98d47-128">The following code sets the editing mode based on the value of a <xref:System.Windows.Forms.CheckBox>:</span></span>

[!code-csharp[DigitalInkTopics#8](~/samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window1.xaml.cs#8)]
[!code-vb[DigitalInkTopics#8](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DigitalInkTopics/VisualBasic/Window1.xaml.vb#8)]

#### <a name="drawingattributes"></a><span data-ttu-id="98d47-129">DrawingAttributes</span><span class="sxs-lookup"><span data-stu-id="98d47-129">DrawingAttributes</span></span>

<span data-ttu-id="98d47-130">使用<xref:System.Windows.Ink.Stroke.DrawingAttributes%2A>要更改墨迹笔画的外观属性。</span><span class="sxs-lookup"><span data-stu-id="98d47-130">Use the <xref:System.Windows.Ink.Stroke.DrawingAttributes%2A> property to change the appearance of ink strokes.</span></span> <span data-ttu-id="98d47-131">例如，<xref:System.Windows.Ink.DrawingAttributes.Color%2A>的成员<xref:System.Windows.Ink.DrawingAttributes>设置的颜色呈现的<xref:System.Windows.Ink.Stroke>。</span><span class="sxs-lookup"><span data-stu-id="98d47-131">For instance, the <xref:System.Windows.Ink.DrawingAttributes.Color%2A> member of <xref:System.Windows.Ink.DrawingAttributes> sets the color of the rendered <xref:System.Windows.Ink.Stroke>.</span></span>

<span data-ttu-id="98d47-132">下面的示例更改选定笔画的颜色为红色：</span><span class="sxs-lookup"><span data-stu-id="98d47-132">The following example changes the color of the selected strokes to red:</span></span>

[!code-csharp[DigitalInkTopics#9](~/samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window1.xaml.cs#9)]
[!code-vb[DigitalInkTopics#9](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DigitalInkTopics/VisualBasic/Window1.xaml.vb#9)]

### <a name="defaultdrawingattributes"></a><span data-ttu-id="98d47-133">DefaultDrawingAttributes</span><span class="sxs-lookup"><span data-stu-id="98d47-133">DefaultDrawingAttributes</span></span>

<span data-ttu-id="98d47-134"><xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A>属性提供访问权限属性，例如高度、 宽度和要在其中创建的笔画的颜色<xref:System.Windows.Controls.InkCanvas>。</span><span class="sxs-lookup"><span data-stu-id="98d47-134">The <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A> property provides access to properties such as the height, width, and color of the strokes to be created in an <xref:System.Windows.Controls.InkCanvas>.</span></span> <span data-ttu-id="98d47-135">一旦更改<xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A>，所有将来的笔画输入到<xref:System.Windows.Controls.InkCanvas>呈现使用新的属性值。</span><span class="sxs-lookup"><span data-stu-id="98d47-135">Once you change the <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A>, all future strokes entered into the <xref:System.Windows.Controls.InkCanvas> are rendered with the new property values.</span></span>

<span data-ttu-id="98d47-136">还可以修改<xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A>在代码隐藏文件中，可用于 XAML 语法指定<xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="98d47-136">In addition to modifying the <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A> in the code-behind file, you can use XAML syntax for specifying <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A> properties.</span></span>

<span data-ttu-id="98d47-137">下面的示例演示如何设置<xref:System.Windows.Ink.DrawingAttributes.Color%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="98d47-137">The next example demonstrates how to set the <xref:System.Windows.Ink.DrawingAttributes.Color%2A> property.</span></span> <span data-ttu-id="98d47-138">若要使用此代码，创建新的 WPF 项目在 Visual Studio 中名为"HelloInkCanvas"。</span><span class="sxs-lookup"><span data-stu-id="98d47-138">To use this code, create a new WPF project called "HelloInkCanvas" in Visual Studio.</span></span> <span data-ttu-id="98d47-139">中的代码替换*MainWindow.xaml*文件使用以下代码：</span><span class="sxs-lookup"><span data-stu-id="98d47-139">Replace the code in the *MainWindow.xaml* file with the following code:</span></span>

[!code-xaml[HelloInkCanvas#1](~/samples/snippets/csharp/VS_Snippets_Wpf/HelloInkCanvas/CSharp/Window1.xaml#1)]

<span data-ttu-id="98d47-140">接下来，将以下按钮事件处理程序添加到代码隐藏文件，在 MainWindow 类中：</span><span class="sxs-lookup"><span data-stu-id="98d47-140">Next, add the following button event handlers to the code behind file, inside the MainWindow class:</span></span>

[!code-csharp[HelloInkCanvas#2](~/samples/snippets/csharp/VS_Snippets_Wpf/HelloInkCanvas/CSharp/Window1.xaml.cs#2)]

<span data-ttu-id="98d47-141">复制此代码后, 按**F5** Visual Studio 调试器中运行程序中。</span><span class="sxs-lookup"><span data-stu-id="98d47-141">After copying this code, press **F5** in Visual Studio to run the program in the debugger.</span></span>

<span data-ttu-id="98d47-142">请注意如何<xref:System.Windows.Controls.StackPanel>的顶部将按钮置于<xref:System.Windows.Controls.InkCanvas>。</span><span class="sxs-lookup"><span data-stu-id="98d47-142">Notice how the <xref:System.Windows.Controls.StackPanel> places the buttons on top of the <xref:System.Windows.Controls.InkCanvas>.</span></span> <span data-ttu-id="98d47-143">如果您尝试对墨迹上方的按钮，<xref:System.Windows.Controls.InkCanvas>收集和按钮后面呈现墨迹。</span><span class="sxs-lookup"><span data-stu-id="98d47-143">If you try to ink over the top of the buttons, the <xref:System.Windows.Controls.InkCanvas> collects and renders the ink behind the buttons.</span></span> <span data-ttu-id="98d47-144">这是因为这些按钮是同级的<xref:System.Windows.Controls.InkCanvas>而不是子级。</span><span class="sxs-lookup"><span data-stu-id="98d47-144">This is because the buttons are siblings of the <xref:System.Windows.Controls.InkCanvas> as opposed to children.</span></span> <span data-ttu-id="98d47-145">此外，这些按钮的 Z 顺序较高，所以墨迹呈现在其后面。</span><span class="sxs-lookup"><span data-stu-id="98d47-145">Also, the buttons are higher in the z-order, so the ink is rendered behind them.</span></span>

## <a name="see-also"></a><span data-ttu-id="98d47-146">请参阅</span><span class="sxs-lookup"><span data-stu-id="98d47-146">See also</span></span>

- <xref:System.Windows.Ink.DrawingAttributes>
- <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A>
- <xref:System.Windows.Ink>