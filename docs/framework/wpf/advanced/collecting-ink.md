---
title: "收集墨迹"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: cbf55b5d84420a6aa7af06e94497a85a2b54a0c0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="collecting-ink"></a><span data-ttu-id="f07af-102">收集墨迹</span><span class="sxs-lookup"><span data-stu-id="f07af-102">Collecting Ink</span></span>
<span data-ttu-id="f07af-103">[Windows Presentation Foundation](../../../../docs/framework/wpf/index.md) 平台会收集数字墨迹，这是其功能中的核心部分之一。</span><span class="sxs-lookup"><span data-stu-id="f07af-103">The [Windows Presentation Foundation](../../../../docs/framework/wpf/index.md) platform collects digital ink as a core part of its functionality.</span></span> <span data-ttu-id="f07af-104">本主题讨论在 [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)] 中收集墨迹的方法。</span><span class="sxs-lookup"><span data-stu-id="f07af-104">This topic discusses methods for collection of ink in [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)].</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="f07af-105">系统必备</span><span class="sxs-lookup"><span data-stu-id="f07af-105">Prerequisites</span></span>  
 <span data-ttu-id="f07af-106">要使用以下示例，首先必须安装 [!INCLUDE[TLA#tla_visualstu2005](../../../../includes/tlasharptla-visualstu2005-md.md)] 和 [!INCLUDE[TLA2#tla_winfxsdk](../../../../includes/tla2sharptla-winfxsdk-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="f07af-106">To use the following examples, you must first install [!INCLUDE[TLA#tla_visualstu2005](../../../../includes/tlasharptla-visualstu2005-md.md)] and the [!INCLUDE[TLA2#tla_winfxsdk](../../../../includes/tla2sharptla-winfxsdk-md.md)].</span></span> <span data-ttu-id="f07af-107">还必须了解如何编写 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 的应用程序。</span><span class="sxs-lookup"><span data-stu-id="f07af-107">You should also understand how to write applications for the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].</span></span> <span data-ttu-id="f07af-108">有关详细信息，有关如何开始使用[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]，请参阅[演练： 我第一个 WPF 桌面应用程序](../../../../docs/framework/wpf/getting-started/walkthrough-my-first-wpf-desktop-application.md)。</span><span class="sxs-lookup"><span data-stu-id="f07af-108">For more information about getting started with [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], see [Walkthrough: My first WPF desktop application](../../../../docs/framework/wpf/getting-started/walkthrough-my-first-wpf-desktop-application.md).</span></span>  
  
## <a name="using-the-inkcanvas-element"></a><span data-ttu-id="f07af-109">使用 InkCanvas 元素</span><span class="sxs-lookup"><span data-stu-id="f07af-109">Using the InkCanvas Element</span></span>  
 <span data-ttu-id="f07af-110"><xref:System.Windows.Controls.InkCanvas>元素提供的最简单的方法中收集墨迹[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="f07af-110">The <xref:System.Windows.Controls.InkCanvas> element provides the easiest way to collect ink in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].</span></span> <span data-ttu-id="f07af-111"><xref:System.Windows.Controls.InkCanvas>元素是类似于[Microsoft.Ink.InkOverlay](https://msdn.microsoft.com/library/microsoft.ink.inkoverlay\(v=vs.90\).aspx)对象[!INCLUDE[TLA2#tla_tpclssdk](../../../../includes/tla2sharptla-tpclssdk-md.md)]及更早版本。</span><span class="sxs-lookup"><span data-stu-id="f07af-111">The <xref:System.Windows.Controls.InkCanvas> element is similar to the [Microsoft.Ink.InkOverlay](https://msdn.microsoft.com/library/microsoft.ink.inkoverlay\(v=vs.90\).aspx) object from the [!INCLUDE[TLA2#tla_tpclssdk](../../../../includes/tla2sharptla-tpclssdk-md.md)] and earlier versions.</span></span>  
  
 <span data-ttu-id="f07af-112">使用<xref:System.Windows.Controls.InkCanvas>要接收和显示墨迹输入元素。</span><span class="sxs-lookup"><span data-stu-id="f07af-112">Use an <xref:System.Windows.Controls.InkCanvas> element to receive and display ink input.</span></span> <span data-ttu-id="f07af-113">通常使用触笔（与数字化仪交互产生墨迹笔画）输入墨迹。</span><span class="sxs-lookup"><span data-stu-id="f07af-113">You commonly input ink through the use of a stylus, which interacts with a digitizer to produce ink strokes.</span></span> <span data-ttu-id="f07af-114">此外，还可以使用鼠标代替触笔。</span><span class="sxs-lookup"><span data-stu-id="f07af-114">In addition, a mouse can be used in place of a stylus.</span></span> <span data-ttu-id="f07af-115">创建的笔画表示为<xref:System.Windows.Ink.Stroke>对象，并且它们可以操作以编程方式和由用户输入。</span><span class="sxs-lookup"><span data-stu-id="f07af-115">The created strokes are represented as <xref:System.Windows.Ink.Stroke> objects, and they can be manipulated both programmatically and by user input.</span></span> <span data-ttu-id="f07af-116"><xref:System.Windows.Controls.InkCanvas>使用户能够选择、 修改或删除现有<xref:System.Windows.Ink.Stroke>。</span><span class="sxs-lookup"><span data-stu-id="f07af-116">The <xref:System.Windows.Controls.InkCanvas> enables users to select, modify, or delete an existing <xref:System.Windows.Ink.Stroke>.</span></span>  
  
 <span data-ttu-id="f07af-117">通过使用 XAML，可以轻松设置墨迹收集，就像将 `InkCanvas` 元素添加到树中一样轻松。</span><span class="sxs-lookup"><span data-stu-id="f07af-117">By using XAML, you can set up ink collection as easily as adding an `InkCanvas` element to your tree.</span></span> <span data-ttu-id="f07af-118">下面的示例添加<xref:System.Windows.Controls.InkCanvas>为默认值[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]中创建项目[!INCLUDE[TLA#tla_visualstu2005](../../../../includes/tlasharptla-visualstu2005-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="f07af-118">The following example adds an <xref:System.Windows.Controls.InkCanvas> to a default [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] project created in [!INCLUDE[TLA#tla_visualstu2005](../../../../includes/tlasharptla-visualstu2005-md.md)].</span></span>  
  
 [!code-xaml[DigitalInkTopics#6](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window2.xaml#6)]  
  
 <span data-ttu-id="f07af-119">`InkCanvas` 元素也可以包含子元素，这样便可以将墨迹批注功能添加到几乎所有类型的 XAML 元素。</span><span class="sxs-lookup"><span data-stu-id="f07af-119">The `InkCanvas` element can also contain child elements, making it possible to add ink annotation capabilities to almost any type of XAML element.</span></span> <span data-ttu-id="f07af-120">例如，若要将墨迹功能添加到文本元素中时，只需使其成为子的<xref:System.Windows.Controls.InkCanvas>。</span><span class="sxs-lookup"><span data-stu-id="f07af-120">For example, to add inking capabilities to a text element, simply make it a child of an <xref:System.Windows.Controls.InkCanvas>.</span></span>  
  
 [!code-xaml[DigitalInkTopics#5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window2.xaml#5)]  
  
 <span data-ttu-id="f07af-121">同样，可轻松添加图像墨迹标记支持。</span><span class="sxs-lookup"><span data-stu-id="f07af-121">Adding support for marking up an image with ink is just as easy.</span></span>  
  
 [!code-xaml[DigitalInkTopics#7](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window2.xaml#7)]  
  
### <a name="inkcollection-modes"></a><span data-ttu-id="f07af-122">InkCollection 模式</span><span class="sxs-lookup"><span data-stu-id="f07af-122">InkCollection Modes</span></span>  
 <span data-ttu-id="f07af-123"><xref:System.Windows.Controls.InkCanvas>提供支持，对各种输入模式通过其<xref:System.Windows.Controls.InkCanvas.EditingMode%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="f07af-123">The <xref:System.Windows.Controls.InkCanvas> provides support for various input modes through its <xref:System.Windows.Controls.InkCanvas.EditingMode%2A> property.</span></span>  
  
### <a name="manipulating-ink"></a><span data-ttu-id="f07af-124">操作墨迹</span><span class="sxs-lookup"><span data-stu-id="f07af-124">Manipulating Ink</span></span>  
 <span data-ttu-id="f07af-125"><xref:System.Windows.Controls.InkCanvas>的多种墨迹编辑操作提供支持。</span><span class="sxs-lookup"><span data-stu-id="f07af-125">The <xref:System.Windows.Controls.InkCanvas> provides support for many ink editing operations.</span></span> <span data-ttu-id="f07af-126">例如，<xref:System.Windows.Controls.InkCanvas>支持笔后擦除时需要将该功能添加到元素没有其他代码使用。</span><span class="sxs-lookup"><span data-stu-id="f07af-126">For example, <xref:System.Windows.Controls.InkCanvas> supports back-of-pen erase with no additional code needed to add the functionality to the element.</span></span>  
  
#### <a name="selection"></a><span data-ttu-id="f07af-127">选择</span><span class="sxs-lookup"><span data-stu-id="f07af-127">Selection</span></span>  
 <span data-ttu-id="f07af-128">设置选择模式非常简单，只设置<xref:System.Windows.Controls.InkCanvasEditingMode>属性**选择**。</span><span class="sxs-lookup"><span data-stu-id="f07af-128">Setting selection mode is as simple as setting the <xref:System.Windows.Controls.InkCanvasEditingMode> property to **Select**.</span></span> <span data-ttu-id="f07af-129">下面的代码设置的值的编辑模式<xref:System.Windows.Forms.CheckBox>:</span><span class="sxs-lookup"><span data-stu-id="f07af-129">The following code sets the editing mode based on the value of a <xref:System.Windows.Forms.CheckBox>:</span></span>  
  
 [!code-csharp[DigitalInkTopics#8](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window1.xaml.cs#8)]
 [!code-vb[DigitalInkTopics#8](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DigitalInkTopics/VisualBasic/Window1.xaml.vb#8)]  
  
#### <a name="drawingattributes"></a><span data-ttu-id="f07af-130">DrawingAttributes</span><span class="sxs-lookup"><span data-stu-id="f07af-130">DrawingAttributes</span></span>  
 <span data-ttu-id="f07af-131">使用<xref:System.Windows.Ink.Stroke.DrawingAttributes%2A>属性可以更改墨迹笔画的外观。</span><span class="sxs-lookup"><span data-stu-id="f07af-131">Use the <xref:System.Windows.Ink.Stroke.DrawingAttributes%2A> property to change the appearance of ink strokes.</span></span> <span data-ttu-id="f07af-132">例如，<xref:System.Windows.Ink.DrawingAttributes.Color%2A>的成员<xref:System.Windows.Ink.DrawingAttributes>设置呈现的颜色<xref:System.Windows.Ink.Stroke>。</span><span class="sxs-lookup"><span data-stu-id="f07af-132">For instance, the <xref:System.Windows.Ink.DrawingAttributes.Color%2A> member of <xref:System.Windows.Ink.DrawingAttributes> sets the color of the rendered <xref:System.Windows.Ink.Stroke>.</span></span> <span data-ttu-id="f07af-133">下面的示例将所选笔画的颜色更改为红色。</span><span class="sxs-lookup"><span data-stu-id="f07af-133">The following example changes the color of the selected strokes to red.</span></span>  
  
 [!code-csharp[DigitalInkTopics#9](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window1.xaml.cs#9)]
 [!code-vb[DigitalInkTopics#9](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DigitalInkTopics/VisualBasic/Window1.xaml.vb#9)]  
  
### <a name="defaultdrawingattributes"></a><span data-ttu-id="f07af-134">DefaultDrawingAttributes</span><span class="sxs-lookup"><span data-stu-id="f07af-134">DefaultDrawingAttributes</span></span>  
 <span data-ttu-id="f07af-135"><xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A>属性提供访问权限属性，例如高度、 宽度和颜色在中创建的笔画<xref:System.Windows.Controls.InkCanvas>。</span><span class="sxs-lookup"><span data-stu-id="f07af-135">The <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A> property provides access to properties such as the height, width, and color of the strokes to be created in an <xref:System.Windows.Controls.InkCanvas>.</span></span> <span data-ttu-id="f07af-136">一旦你更改<xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A>，所有将来的描边输入到<xref:System.Windows.Controls.InkCanvas>呈现所使用的新属性值。</span><span class="sxs-lookup"><span data-stu-id="f07af-136">Once you change the <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A>, all future strokes entered into the <xref:System.Windows.Controls.InkCanvas> are rendered with the new property values.</span></span>  
  
 <span data-ttu-id="f07af-137">除了修改<xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A>在代码隐藏文件中中,，你可以使用 XAML 语法来指定<xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="f07af-137">In addition to modifying the <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A> in the code-behind file, you can use XAML syntax for specifying <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A> properties.</span></span> <span data-ttu-id="f07af-138">下面的 XAML 代码演示如何设置<xref:System.Windows.Ink.DrawingAttributes.Color%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="f07af-138">The following XAML code demonstrates how to set the <xref:System.Windows.Ink.DrawingAttributes.Color%2A> property.</span></span> <span data-ttu-id="f07af-139">若要使用此代码，请在 Visual Studio 2005 中创建名为“HelloInkCanvas”的新 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 项目。</span><span class="sxs-lookup"><span data-stu-id="f07af-139">To use this code, create a new [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] project called "HelloInkCanvas" in Visual Studio 2005.</span></span> <span data-ttu-id="f07af-140">使用以下代码替换 Window1.xaml 文件中的代码。</span><span class="sxs-lookup"><span data-stu-id="f07af-140">Replace the code in the Window1.xaml file with the following code.</span></span>  
  
 [!code-xaml[HelloInkCanvas#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HelloInkCanvas/CSharp/Window1.xaml#1)]  
  
 <span data-ttu-id="f07af-141">然后，将以下按钮事件处理程序添加到 Window1 类中的代码隐藏文件。</span><span class="sxs-lookup"><span data-stu-id="f07af-141">Next, add the following button event handlers to the code behind file, inside the Window1 class.</span></span>  
  
 [!code-csharp[HelloInkCanvas#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HelloInkCanvas/CSharp/Window1.xaml.cs#2)]  
  
 <span data-ttu-id="f07af-142">复制此代码后，在 Microsoft Visual Studio 2005 中按“F5”，以在调试器中运行该程序。</span><span class="sxs-lookup"><span data-stu-id="f07af-142">After copying this code, press **F5** in Microsoft Visual Studio 2005 to run the program in the debugger.</span></span>  
  
 <span data-ttu-id="f07af-143">请注意如何<xref:System.Windows.Controls.StackPanel>放置的顶部的按钮<xref:System.Windows.Controls.InkCanvas>。</span><span class="sxs-lookup"><span data-stu-id="f07af-143">Notice how the <xref:System.Windows.Controls.StackPanel> places the buttons on top of the <xref:System.Windows.Controls.InkCanvas>.</span></span> <span data-ttu-id="f07af-144">如果您尝试对墨迹上方的按钮、<xref:System.Windows.Controls.InkCanvas>收集和呈现在按钮后的墨迹。</span><span class="sxs-lookup"><span data-stu-id="f07af-144">If you try to ink over the top of the buttons, the <xref:System.Windows.Controls.InkCanvas> collects and renders the ink behind the buttons.</span></span> <span data-ttu-id="f07af-145">这是因为这些按钮是同级的<xref:System.Windows.Controls.InkCanvas>而不是子级。</span><span class="sxs-lookup"><span data-stu-id="f07af-145">This is because the buttons are siblings of the <xref:System.Windows.Controls.InkCanvas> as opposed to children.</span></span> <span data-ttu-id="f07af-146">此外，这些按钮的 Z 顺序较高，所以墨迹呈现在其后面。</span><span class="sxs-lookup"><span data-stu-id="f07af-146">Also, the buttons are higher in the z-order, so the ink is rendered behind them.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f07af-147">请参阅</span><span class="sxs-lookup"><span data-stu-id="f07af-147">See Also</span></span>  
 <xref:System.Windows.Ink.DrawingAttributes>  
 <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A>  
 <xref:System.Windows.Ink>
