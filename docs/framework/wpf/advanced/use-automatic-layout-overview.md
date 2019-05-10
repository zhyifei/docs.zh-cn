---
title: 使用自动布局概述
ms.date: 03/30/2017
helpviewer_keywords:
- layout [WPF], automatic
- automatic layout [WPF]
ms.assetid: 6fed9264-18bb-4d05-8867-1fe356c6f687
ms.openlocfilehash: a9f04f6da4dc4024f4c9ece19f045eb8e3775e6a
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "64620885"
---
# <a name="use-automatic-layout-overview"></a><span data-ttu-id="5b7e9-102">使用自动布局概述</span><span class="sxs-lookup"><span data-stu-id="5b7e9-102">Use Automatic Layout Overview</span></span>
<span data-ttu-id="5b7e9-103">本主题介绍如何编写上面向开发人员的指导原则[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]具有可本地化的应用程序[!INCLUDE[TLA#tla_ui#plural](../../../../includes/tlasharptla-uisharpplural-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="5b7e9-103">This topic introduces guidelines for developers on how to write [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] applications with localizable [!INCLUDE[TLA#tla_ui#plural](../../../../includes/tlasharptla-uisharpplural-md.md)].</span></span> <span data-ttu-id="5b7e9-104">在过去，UI 的本地化是一个耗时的过程。</span><span class="sxs-lookup"><span data-stu-id="5b7e9-104">In the past, localization of a UI was a time consuming process.</span></span> <span data-ttu-id="5b7e9-105">UI 适用于每种语言需要按像素逐一调整。</span><span class="sxs-lookup"><span data-stu-id="5b7e9-105">Each language that the UI was adapted for required a pixel by pixel adjustment.</span></span> <span data-ttu-id="5b7e9-106">使用适当的设计和编码标准，今天[!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)]可以构建，这样本地化人员较少的调整大小和重新定位的工作量。</span><span class="sxs-lookup"><span data-stu-id="5b7e9-106">Today with the right design and right coding standards, [!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)] can be constructed so that localizers have less resizing and repositioning to do.</span></span> <span data-ttu-id="5b7e9-107">种编写可以更轻松地重设大小和重新定位应用程序的方法称为自动布局，可以通过使用[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]应用程序设计。</span><span class="sxs-lookup"><span data-stu-id="5b7e9-107">The approach to writing applications that can be more easily resized and repositioned is called automatic layout, and can be achieved by using [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] application design.</span></span>  

<a name="advantages_of_autolayout"></a>   
## <a name="advantages-of-using-automatic-layout"></a><span data-ttu-id="5b7e9-108">使用自动布局的优点</span><span class="sxs-lookup"><span data-stu-id="5b7e9-108">Advantages of Using Automatic Layout</span></span>  
 <span data-ttu-id="5b7e9-109">因为[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]的演示系统，是功能强大且灵活，它提供到可以进行调整以适应不同语言的要求的应用程序中的布局元素的功能。</span><span class="sxs-lookup"><span data-stu-id="5b7e9-109">Because the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] presentation system is powerful and flexible, it provides the ability to layout elements in an application that can be adjusted to fit the requirements of different languages.</span></span> <span data-ttu-id="5b7e9-110">下面列出自动布局的部分优点。</span><span class="sxs-lookup"><span data-stu-id="5b7e9-110">The following list points out some of the advantages of automatic layout.</span></span>  

- <span data-ttu-id="5b7e9-111">UI 会显示在任何语言中。</span><span class="sxs-lookup"><span data-stu-id="5b7e9-111">UI displays well  in any language.</span></span>  

- <span data-ttu-id="5b7e9-112">减少了文本转换完后重新调整控件位置和大小的需要。</span><span class="sxs-lookup"><span data-stu-id="5b7e9-112">Reduces the need to readjust position and size of controls after text is translated.</span></span>  
  
- <span data-ttu-id="5b7e9-113">减少了重新调整窗口大小的需要。</span><span class="sxs-lookup"><span data-stu-id="5b7e9-113">Reduces the need to readjust window size.</span></span>  

- <span data-ttu-id="5b7e9-114">UI 布局中的任何语言正确呈现。</span><span class="sxs-lookup"><span data-stu-id="5b7e9-114">UI layout renders properly in any language.</span></span>  

- <span data-ttu-id="5b7e9-115">本地化过程可缩减为与进行字符串转换差不多。</span><span class="sxs-lookup"><span data-stu-id="5b7e9-115">Localization can be reduced to the point that it is little more than string translation.</span></span>  
  
<a name="autolayout_controls"></a>   
## <a name="automatic-layout-and-controls"></a><span data-ttu-id="5b7e9-116">自动布局和控件</span><span class="sxs-lookup"><span data-stu-id="5b7e9-116">Automatic Layout and Controls</span></span>  
 <span data-ttu-id="5b7e9-117">利用自动布局，应用程序可以自动调整控件大小。</span><span class="sxs-lookup"><span data-stu-id="5b7e9-117">Automatic layout enables an application to adjust the size of a control automatically.</span></span> <span data-ttu-id="5b7e9-118">例如，控件可按字符串长度相应改变。</span><span class="sxs-lookup"><span data-stu-id="5b7e9-118">For example, a control can change to accommodate the length of a string.</span></span> <span data-ttu-id="5b7e9-119">利用此功能，本地化人员可转换字符串，而无需再调整控件大小以适应转换后的文本。</span><span class="sxs-lookup"><span data-stu-id="5b7e9-119">This capability enables  localizers to translate the string; they no longer need to resize the control to fit the translated text.</span></span> <span data-ttu-id="5b7e9-120">下面的示例创建一个带有英文内容的按钮。</span><span class="sxs-lookup"><span data-stu-id="5b7e9-120">The following example creates a button with English content.</span></span>  
  
 [!code-xaml[LocalizationBtn_snip#1](~/samples/snippets/csharp/VS_Snippets_Wpf/LocalizationBtn_snip/CS/Pane1.xaml#1)]  
  
 <span data-ttu-id="5b7e9-121">在此示例中，只需更改文本即可生成一个西班牙文按钮。</span><span class="sxs-lookup"><span data-stu-id="5b7e9-121">In the example, all you have to do to make a Spanish button is change the text.</span></span> <span data-ttu-id="5b7e9-122">例如，应用于对象的</span><span class="sxs-lookup"><span data-stu-id="5b7e9-122">For example,</span></span>  
  
 [!code-xaml[LocalizationBtn#1](~/samples/snippets/csharp/VS_Snippets_Wpf/LocalizationBtn/CS/Pane1.xaml#1)]  
  
 <span data-ttu-id="5b7e9-123">下图显示了代码示例的输出：</span><span class="sxs-lookup"><span data-stu-id="5b7e9-123">The following graphic shows the output of the code samples:</span></span>  
  
 ![具有不同语言的文本的同一按钮](./media/use-automatic-layout-overview/auto-resizable-button.png)  
  
<a name="autolayout_coding"></a>   
## <a name="automatic-layout-and-coding-standards"></a><span data-ttu-id="5b7e9-125">自动布局和编码标准</span><span class="sxs-lookup"><span data-stu-id="5b7e9-125">Automatic Layout and Coding Standards</span></span>  
 <span data-ttu-id="5b7e9-126">使用自动布局方法需要一组编码和设计标准和规则以生成可完全本地化的 UI。</span><span class="sxs-lookup"><span data-stu-id="5b7e9-126">Using the automatic layout approach requires a set of coding and design standards and rules to produce a fully localizable UI.</span></span> <span data-ttu-id="5b7e9-127">下列准则可帮助完成自动布局编码。</span><span class="sxs-lookup"><span data-stu-id="5b7e9-127">The following guidelines will aid your automatic layout coding.</span></span>  

<span data-ttu-id="5b7e9-128">**不要使用绝对位置**</span><span class="sxs-lookup"><span data-stu-id="5b7e9-128">**Do not use absolute positions**</span></span>

- <span data-ttu-id="5b7e9-129">不要使用<xref:System.Windows.Controls.Canvas>因为它会以绝对方式定位元素。</span><span class="sxs-lookup"><span data-stu-id="5b7e9-129">Do not use <xref:System.Windows.Controls.Canvas> because it positions elements absolutely.</span></span>

- <span data-ttu-id="5b7e9-130">使用<xref:System.Windows.Controls.DockPanel>， <xref:System.Windows.Controls.StackPanel>，和<xref:System.Windows.Controls.Grid>来定位控件。</span><span class="sxs-lookup"><span data-stu-id="5b7e9-130">Use <xref:System.Windows.Controls.DockPanel>, <xref:System.Windows.Controls.StackPanel>, and <xref:System.Windows.Controls.Grid> to position controls.</span></span>

<span data-ttu-id="5b7e9-131">有关各种面板类型的讨论，请参阅[面板概述](../controls/panels-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="5b7e9-131">For a discussion about various types of panels, see [Panels Overview](../controls/panels-overview.md).</span></span>

<span data-ttu-id="5b7e9-132">**未设置固定的大小的窗口**</span><span class="sxs-lookup"><span data-stu-id="5b7e9-132">**Do not set a fixed size for a window**</span></span>

- <span data-ttu-id="5b7e9-133">请使用 <xref:System.Windows.Window.SizeToContent%2A?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="5b7e9-133">Use <xref:System.Windows.Window.SizeToContent%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="5b7e9-134">例如：</span><span class="sxs-lookup"><span data-stu-id="5b7e9-134">For example:</span></span>

   [!code-xaml[LocalizationGrid#2](~/samples/snippets/csharp/VS_Snippets_Wpf/LocalizationGrid/CS/Pane1.xaml#2)]

<span data-ttu-id="5b7e9-135">**添加 <xref:System.Windows.FrameworkElement.FlowDirection%2A>**</span><span class="sxs-lookup"><span data-stu-id="5b7e9-135">**Add a <xref:System.Windows.FrameworkElement.FlowDirection%2A>**</span></span>

- <span data-ttu-id="5b7e9-136">添加<xref:System.Windows.FrameworkElement.FlowDirection%2A>到你的应用程序的根元素。</span><span class="sxs-lookup"><span data-stu-id="5b7e9-136">Add a <xref:System.Windows.FrameworkElement.FlowDirection%2A> to the root element of your application.</span></span>

   <span data-ttu-id="5b7e9-137">WPF 提供了方便地支持水平、 双向和垂直布局。</span><span class="sxs-lookup"><span data-stu-id="5b7e9-137">WPF provides a convenient way to support horizontal, bidirectional, and vertical layouts.</span></span> <span data-ttu-id="5b7e9-138">在演示框架<xref:System.Windows.FrameworkElement.FlowDirection%2A>属性可以用于定义布局。</span><span class="sxs-lookup"><span data-stu-id="5b7e9-138">In presentation framework, the <xref:System.Windows.FrameworkElement.FlowDirection%2A> property can be used to define layout.</span></span> <span data-ttu-id="5b7e9-139">流方向模式包括：</span><span class="sxs-lookup"><span data-stu-id="5b7e9-139">The flow-direction patterns are:</span></span>
   
     - <span data-ttu-id="5b7e9-140"><xref:System.Windows.FlowDirection.LeftToRight?displayProperty=nameWithType> (LrTb) — 拉丁语、 东亚语言等的水平布局。</span><span class="sxs-lookup"><span data-stu-id="5b7e9-140"><xref:System.Windows.FlowDirection.LeftToRight?displayProperty=nameWithType> (LrTb) — horizontal layout for Latin, East Asian, and so forth.</span></span>
     
     - <span data-ttu-id="5b7e9-141"><xref:System.Windows.FlowDirection.RightToLeft?displayProperty=nameWithType> (RlTb) — 有关阿拉伯语、 希伯来语等双向。</span><span class="sxs-lookup"><span data-stu-id="5b7e9-141"><xref:System.Windows.FlowDirection.RightToLeft?displayProperty=nameWithType> (RlTb) — bidirectional for Arabic, Hebrew, and so forth.</span></span>

<span data-ttu-id="5b7e9-142">**使用复合字体而不是物理字体**</span><span class="sxs-lookup"><span data-stu-id="5b7e9-142">**Use composite fonts instead of physical fonts**</span></span>

- <span data-ttu-id="5b7e9-143">使用复合字体<xref:System.Windows.Controls.Control.FontFamily%2A>属性不需要进行本地化。</span><span class="sxs-lookup"><span data-stu-id="5b7e9-143">With composite fonts, the <xref:System.Windows.Controls.Control.FontFamily%2A> property does not need to be localized.</span></span>

- <span data-ttu-id="5b7e9-144">开发人员可以使用以下字体之一，也可以创建自己的字体。</span><span class="sxs-lookup"><span data-stu-id="5b7e9-144">Developers can use one of the following fonts or create their own.</span></span>

   - <span data-ttu-id="5b7e9-145">Global User Interface</span><span class="sxs-lookup"><span data-stu-id="5b7e9-145">Global User Interface</span></span>
   - <span data-ttu-id="5b7e9-146">Global San Serif</span><span class="sxs-lookup"><span data-stu-id="5b7e9-146">Global San Serif</span></span>
   - <span data-ttu-id="5b7e9-147">Global Serif</span><span class="sxs-lookup"><span data-stu-id="5b7e9-147">Global Serif</span></span>

<span data-ttu-id="5b7e9-148">**添加 xml: lang**</span><span class="sxs-lookup"><span data-stu-id="5b7e9-148">**Add xml:lang**</span></span>

- <span data-ttu-id="5b7e9-149">添加`xml:lang`特性中的根元素的 UI，如`xml:lang="en-US"`英文应用程序。</span><span class="sxs-lookup"><span data-stu-id="5b7e9-149">Add the `xml:lang` attribute in the root element of your UI, such as `xml:lang="en-US"` for an English application.</span></span>

- <span data-ttu-id="5b7e9-150">因为复合字体使用`xml:lang`若要确定要使用的字体，请设置此属性以支持多语言方案。</span><span class="sxs-lookup"><span data-stu-id="5b7e9-150">Because composite fonts use `xml:lang` to determine what font to use, set this property to support multilingual scenarios.</span></span>

<a name="autolay_grids"></a>   
## <a name="automatic-layout-and-grids"></a><span data-ttu-id="5b7e9-151">自动布局和网格</span><span class="sxs-lookup"><span data-stu-id="5b7e9-151">Automatic Layout and Grids</span></span>  
 <span data-ttu-id="5b7e9-152"><xref:System.Windows.Controls.Grid>元素，是对于自动布局很有用，因为它使开发人员来定位元素。</span><span class="sxs-lookup"><span data-stu-id="5b7e9-152">The <xref:System.Windows.Controls.Grid> element, is useful for automatic layout because it enables a developer to position elements.</span></span> <span data-ttu-id="5b7e9-153">一个<xref:System.Windows.Controls.Grid>控件是支持的分发在其子元素，使用列和行排列方式的可用空间。</span><span class="sxs-lookup"><span data-stu-id="5b7e9-153">A <xref:System.Windows.Controls.Grid> control is capable of distributing the available space among its child elements, using a column and row arrangement.</span></span> <span data-ttu-id="5b7e9-154">UI 元素可以跨多个单元格，并且可能具有在网格内的网格。</span><span class="sxs-lookup"><span data-stu-id="5b7e9-154">The UI elements can span multiple cells, and it is possible to have grids within grids.</span></span> <span data-ttu-id="5b7e9-155">网格非常有用，因为它们使您能够创建和定位复杂的 UI。</span><span class="sxs-lookup"><span data-stu-id="5b7e9-155">Grids are useful because they enable you to create and position complex UI.</span></span> <span data-ttu-id="5b7e9-156">下面的示例演示使用网格来定位某些按钮和文本。</span><span class="sxs-lookup"><span data-stu-id="5b7e9-156">The following example demonstrates using a grid to position some buttons and text.</span></span> <span data-ttu-id="5b7e9-157">请注意，高度和宽度的单元格设置为<xref:System.Windows.GridUnitType.Auto>; 因此，包含带图像按钮的单元格调整以适合图像。</span><span class="sxs-lookup"><span data-stu-id="5b7e9-157">Notice that the height and width of the cells are set to <xref:System.Windows.GridUnitType.Auto>; therefore, the cell that contains the button with an image adjusts to fit the image.</span></span>  

 [!code-xaml[LocalizationGrid#1](~/samples/snippets/csharp/VS_Snippets_Wpf/LocalizationGrid/CS/Pane1.xaml#1)]  
  
 <span data-ttu-id="5b7e9-158">下图显示了以上代码生成的网格。</span><span class="sxs-lookup"><span data-stu-id="5b7e9-158">The following graphic shows the grid produced by the previous code.</span></span>  
  
 <span data-ttu-id="5b7e9-159">![网格示例](./media/glob-grid.png "glob_grid")</span><span class="sxs-lookup"><span data-stu-id="5b7e9-159">![Grid example](./media/glob-grid.png "glob_grid")</span></span>  
<span data-ttu-id="5b7e9-160">Grid</span><span class="sxs-lookup"><span data-stu-id="5b7e9-160">Grid</span></span>  
  
<a name="autolay_grids_issharedsizescope"></a>   
## <a name="automatic-layout-and-grids-using-the-issharedsizescope-property"></a><span data-ttu-id="5b7e9-161">使用 IsSharedSizeScope 属性的自动布局和网格</span><span class="sxs-lookup"><span data-stu-id="5b7e9-161">Automatic Layout and Grids Using the IsSharedSizeScope Property</span></span>  
 <span data-ttu-id="5b7e9-162">一个<xref:System.Windows.Controls.Grid>元素是可本地化的应用程序创建进行调整以适应内容的控件中很有用。</span><span class="sxs-lookup"><span data-stu-id="5b7e9-162">A <xref:System.Windows.Controls.Grid> element is useful in localizable applications to create controls that adjust to fit content.</span></span> <span data-ttu-id="5b7e9-163">不过，有时可能希望控件无论包含什么内容都可以保持特定大小。</span><span class="sxs-lookup"><span data-stu-id="5b7e9-163">However, at times you want controls to maintain a particular size regardless of content.</span></span> <span data-ttu-id="5b7e9-164">例如，对于“确定”、“取消”和“浏览”按钮，可能不希望按钮根据内容调整大小。</span><span class="sxs-lookup"><span data-stu-id="5b7e9-164">For example, if you have "OK", "Cancel" and "Browse" buttons you probably do not want the buttons sized to fit the content.</span></span> <span data-ttu-id="5b7e9-165">在这种情况下<xref:System.Windows.Controls.Grid.IsSharedSizeScope%2A?displayProperty=nameWithType>附加的属性可用于共享多个网格元素之间同样的大小。</span><span class="sxs-lookup"><span data-stu-id="5b7e9-165">In this case the <xref:System.Windows.Controls.Grid.IsSharedSizeScope%2A?displayProperty=nameWithType> attached property is useful for sharing the same sizing among multiple grid elements.</span></span> <span data-ttu-id="5b7e9-166">下面的示例演示如何共享列和行的大小之间多个数据<xref:System.Windows.Controls.Grid>元素。</span><span class="sxs-lookup"><span data-stu-id="5b7e9-166">The following example demonstrates how to share column and row sizing data between multiple <xref:System.Windows.Controls.Grid> elements.</span></span>  
  
 [!code-xaml[gridIssharedsizescopeProp#2](~/samples/snippets/csharp/VS_Snippets_Wpf/gridIssharedsizescopeProp/CSharp/Window1.xaml#2)]  
  
 <span data-ttu-id="5b7e9-167">**请注意**完整的代码示例，请参阅[共享大小调整属性网格之间](../controls/how-to-share-sizing-properties-between-grids.md)</span><span class="sxs-lookup"><span data-stu-id="5b7e9-167">**Note** For the complete code sample, see [Share Sizing Properties Between Grids](../controls/how-to-share-sizing-properties-between-grids.md)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5b7e9-168">请参阅</span><span class="sxs-lookup"><span data-stu-id="5b7e9-168">See also</span></span>

- [<span data-ttu-id="5b7e9-169">WPF 全球化</span><span class="sxs-lookup"><span data-stu-id="5b7e9-169">Globalization for WPF</span></span>](globalization-for-wpf.md)
- [<span data-ttu-id="5b7e9-170">使用自动布局创建按钮</span><span class="sxs-lookup"><span data-stu-id="5b7e9-170">Use Automatic Layout to Create a Button</span></span>](how-to-use-automatic-layout-to-create-a-button.md)
- [<span data-ttu-id="5b7e9-171">使用网格进行自动布局</span><span class="sxs-lookup"><span data-stu-id="5b7e9-171">Use a Grid for Automatic Layout</span></span>](how-to-use-a-grid-for-automatic-layout.md)
