---
title: "如何：设置 TileBrush 的水平对齐方式和垂直对齐方式"
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
- TileBrush [WPF], alignment of
- vertical alignment of TileBrushes [WPF]
- aligning [WPF], TileBrushes
- horizontal alignment of Tilebrushes [WPF]
ms.assetid: 65ae89bd-9246-4c9e-bde4-2fb991d4060d
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 3c581bb167c020e9e4f0de26b0e17e7a1d70704e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-set-the-horizontal-and-vertical-alignment-of-a-tilebrush"></a><span data-ttu-id="3f153-102">如何：设置 TileBrush 的水平对齐方式和垂直对齐方式</span><span class="sxs-lookup"><span data-stu-id="3f153-102">How to: Set the Horizontal and Vertical Alignment of a TileBrush</span></span>
<span data-ttu-id="3f153-103">本示例演示如何控制平铺内容的水平对齐方式和垂直对齐方式。</span><span class="sxs-lookup"><span data-stu-id="3f153-103">This example shows how to control the horizontal and vertical alignment of content in a tile.</span></span> <span data-ttu-id="3f153-104">若要控制的水平和垂直对齐方式<xref:System.Windows.Media.TileBrush>，使用其<xref:System.Windows.Media.TileBrush.AlignmentX%2A>和<xref:System.Windows.Media.TileBrush.AlignmentY%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="3f153-104">To control the horizontal and vertical alignment of a <xref:System.Windows.Media.TileBrush>, use its <xref:System.Windows.Media.TileBrush.AlignmentX%2A> and <xref:System.Windows.Media.TileBrush.AlignmentY%2A> properties.</span></span>  
  
 <span data-ttu-id="3f153-105"><xref:System.Windows.Media.TileBrush.AlignmentX%2A>和<xref:System.Windows.Media.TileBrush.AlignmentY%2A>属性<xref:System.Windows.Media.TileBrush>使用满足以下条件之一时：</span><span class="sxs-lookup"><span data-stu-id="3f153-105">The <xref:System.Windows.Media.TileBrush.AlignmentX%2A> and <xref:System.Windows.Media.TileBrush.AlignmentY%2A> properties of a <xref:System.Windows.Media.TileBrush> are used when either of the following conditions is true:</span></span>  
  
-   <span data-ttu-id="3f153-106"><xref:System.Windows.Media.TileBrush.Stretch%2A>属性是<xref:System.Windows.Media.Stretch.Uniform>或<xref:System.Windows.Media.Stretch.UniformToFill>和<xref:System.Windows.Media.TileBrush.Viewbox%2A>和<xref:System.Windows.Media.TileBrush.Viewport%2A>具有不同的纵横比。</span><span class="sxs-lookup"><span data-stu-id="3f153-106">The <xref:System.Windows.Media.TileBrush.Stretch%2A> property is <xref:System.Windows.Media.Stretch.Uniform> or <xref:System.Windows.Media.Stretch.UniformToFill> and the <xref:System.Windows.Media.TileBrush.Viewbox%2A> and <xref:System.Windows.Media.TileBrush.Viewport%2A> have different aspect ratios.</span></span>  
  
-   <span data-ttu-id="3f153-107"><xref:System.Windows.Media.TileBrush.Stretch%2A>属性是<xref:System.Windows.Media.Stretch.None>和<xref:System.Windows.Media.TileBrush.Viewbox%2A>和<xref:System.Windows.Media.TileBrush.Viewport%2A>具有不同大小。</span><span class="sxs-lookup"><span data-stu-id="3f153-107">The <xref:System.Windows.Media.TileBrush.Stretch%2A> property is <xref:System.Windows.Media.Stretch.None> and the <xref:System.Windows.Media.TileBrush.Viewbox%2A> and <xref:System.Windows.Media.TileBrush.Viewport%2A> are different sizes.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3f153-108">示例</span><span class="sxs-lookup"><span data-stu-id="3f153-108">Example</span></span>  
 <span data-ttu-id="3f153-109">下面的示例将对齐的内容<xref:System.Windows.Media.DrawingBrush>，这是一种<xref:System.Windows.Media.TileBrush>，到其磁贴的左上角。</span><span class="sxs-lookup"><span data-stu-id="3f153-109">The following example aligns the content of a <xref:System.Windows.Media.DrawingBrush>, which is a type of <xref:System.Windows.Media.TileBrush>, to the upper-left corner of its tile.</span></span> <span data-ttu-id="3f153-110">若要对齐的内容，该示例设置<xref:System.Windows.Media.TileBrush.AlignmentX%2A>属性<xref:System.Windows.Media.DrawingBrush>到<xref:System.Windows.Media.AlignmentX.Left>和<xref:System.Windows.Media.TileBrush.AlignmentY%2A>属性<xref:System.Windows.Media.AlignmentY.Top>。</span><span class="sxs-lookup"><span data-stu-id="3f153-110">To align the content, the example sets the <xref:System.Windows.Media.TileBrush.AlignmentX%2A> property of the <xref:System.Windows.Media.DrawingBrush> to <xref:System.Windows.Media.AlignmentX.Left> and the <xref:System.Windows.Media.TileBrush.AlignmentY%2A> property to <xref:System.Windows.Media.AlignmentY.Top>.</span></span> <span data-ttu-id="3f153-111">本示例生成以下输出。</span><span class="sxs-lookup"><span data-stu-id="3f153-111">This example produces the following output.</span></span>  
  
 <span data-ttu-id="3f153-112">![TileBrush 顶部 &#45; 左的对齐](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-tilebrushalignmentexampletopleft.png "graphicsmm_TileBrushAlignmentExampleTopLeft")</span><span class="sxs-lookup"><span data-stu-id="3f153-112">![A TileBrush with top&#45;left alignment](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-tilebrushalignmentexampletopleft.png "graphicsmm_TileBrushAlignmentExampleTopLeft")</span></span>  
<span data-ttu-id="3f153-113">内容与左上角对齐的 TileBrush</span><span class="sxs-lookup"><span data-stu-id="3f153-113">TileBrush with content aligned to the upper-left corner</span></span>  
  
 [!code-csharp[brushoverviewexamples_snip#TileBrushTopLeftAlignmentInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BrushOverviewExamples_snip/CSharp/TileBrushAlignmentExample.cs#tilebrushtopleftalignmentinline)]
 [!code-vb[brushoverviewexamples_snip#TileBrushTopLeftAlignmentInline](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BrushOverviewExamples_snip/visualbasic/tilebrushalignmentexample.vb#tilebrushtopleftalignmentinline)]
 [!code-xaml[brushoverviewexamples_snip#TileBrushTopLeftAlignmentInline](../../../../samples/snippets/xaml/VS_Snippets_Wpf/BrushOverviewExamples_snip/XAML/TileBrushAlignmentExample.xaml#tilebrushtopleftalignmentinline)]  
  
## <a name="example"></a><span data-ttu-id="3f153-114">示例</span><span class="sxs-lookup"><span data-stu-id="3f153-114">Example</span></span>  
 <span data-ttu-id="3f153-115">下一步的示例将对齐的内容<xref:System.Windows.Media.DrawingBrush>到通过设置其磁贴右下角<xref:System.Windows.Media.TileBrush.AlignmentX%2A>属性<xref:System.Windows.Media.AlignmentX.Right>和<xref:System.Windows.Media.TileBrush.AlignmentY%2A>属性<xref:System.Windows.Media.AlignmentY.Bottom>。</span><span class="sxs-lookup"><span data-stu-id="3f153-115">The next example aligns the content of a <xref:System.Windows.Media.DrawingBrush> to the lower-right corner of its tile by setting the <xref:System.Windows.Media.TileBrush.AlignmentX%2A> property to <xref:System.Windows.Media.AlignmentX.Right> and the <xref:System.Windows.Media.TileBrush.AlignmentY%2A> property to <xref:System.Windows.Media.AlignmentY.Bottom>.</span></span> <span data-ttu-id="3f153-116">该示例生成以下输出。</span><span class="sxs-lookup"><span data-stu-id="3f153-116">The example produces the following output.</span></span>  
  
 <span data-ttu-id="3f153-117">![TileBrush 底部 &#45; 右对齐](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-tilebrushalignmentexamplebottomright.png "graphicsmm_TileBrushAlignmentExampleBottomRight")</span><span class="sxs-lookup"><span data-stu-id="3f153-117">![A TileBrush with bottom&#45;right alignment](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-tilebrushalignmentexamplebottomright.png "graphicsmm_TileBrushAlignmentExampleBottomRight")</span></span>  
<span data-ttu-id="3f153-118">内容与右下角对齐的 TileBrush</span><span class="sxs-lookup"><span data-stu-id="3f153-118">TileBrush with content aligned to the lower-right corner</span></span>  
  
 [!code-csharp[brushoverviewexamples_snip#TileBrushBottomRightAlignmentInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BrushOverviewExamples_snip/CSharp/TileBrushAlignmentExample.cs#tilebrushbottomrightalignmentinline)]
 [!code-vb[brushoverviewexamples_snip#TileBrushBottomRightAlignmentInline](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BrushOverviewExamples_snip/visualbasic/tilebrushalignmentexample.vb#tilebrushbottomrightalignmentinline)]
 [!code-xaml[brushoverviewexamples_snip#TileBrushBottomRightAlignmentInline](../../../../samples/snippets/xaml/VS_Snippets_Wpf/BrushOverviewExamples_snip/XAML/TileBrushAlignmentExample.xaml#tilebrushbottomrightalignmentinline)]  
  
## <a name="example"></a><span data-ttu-id="3f153-119">示例</span><span class="sxs-lookup"><span data-stu-id="3f153-119">Example</span></span>  
 <span data-ttu-id="3f153-120">下一步的示例将对齐的内容<xref:System.Windows.Media.DrawingBrush>到通过设置其磁贴的左上角<xref:System.Windows.Media.TileBrush.AlignmentX%2A>属性<xref:System.Windows.Media.AlignmentX.Left>和<xref:System.Windows.Media.TileBrush.AlignmentY%2A>属性<xref:System.Windows.Media.AlignmentY.Top>。</span><span class="sxs-lookup"><span data-stu-id="3f153-120">The next example aligns the content of a <xref:System.Windows.Media.DrawingBrush> to the upper-left corner of its tile by setting the <xref:System.Windows.Media.TileBrush.AlignmentX%2A> property to <xref:System.Windows.Media.AlignmentX.Left> and the <xref:System.Windows.Media.TileBrush.AlignmentY%2A> property to <xref:System.Windows.Media.AlignmentY.Top>.</span></span> <span data-ttu-id="3f153-121">它还将设置<xref:System.Windows.Media.TileBrush.Viewport%2A>和<xref:System.Windows.Media.TileBrush.TileMode%2A>的<xref:System.Windows.Media.DrawingBrush>生成平铺模式。</span><span class="sxs-lookup"><span data-stu-id="3f153-121">It also sets the <xref:System.Windows.Media.TileBrush.Viewport%2A> and <xref:System.Windows.Media.TileBrush.TileMode%2A> of the <xref:System.Windows.Media.DrawingBrush> to produce a tile pattern.</span></span> <span data-ttu-id="3f153-122">该示例生成以下输出。</span><span class="sxs-lookup"><span data-stu-id="3f153-122">The example produces the following output.</span></span>  
  
 <span data-ttu-id="3f153-123">![平铺的 TileBrush 顶部 &#45; 左的对齐](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-tilebrushalignmentexampletoplefttiled.png "graphicsmm_TileBrushAlignmentExampleTopLeftTiled")</span><span class="sxs-lookup"><span data-stu-id="3f153-123">![A tiled TileBrush with top&#45;left alignment](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-tilebrushalignmentexampletoplefttiled.png "graphicsmm_TileBrushAlignmentExampleTopLeftTiled")</span></span>  
<span data-ttu-id="3f153-124">内容与基本平铺图案的左上角对齐的平铺图案</span><span class="sxs-lookup"><span data-stu-id="3f153-124">Tile pattern with content aligned to upper-left in base tile</span></span>  
  
 <span data-ttu-id="3f153-125">上图突出显示了基本平铺图案，以便显示其内容的对齐方式。</span><span class="sxs-lookup"><span data-stu-id="3f153-125">The illustration highlights abase tile so that you can see how its content is aligned.</span></span> <span data-ttu-id="3f153-126">请注意，<xref:System.Windows.Media.TileBrush.AlignmentX%2A>设置无任何影响，因为内容<xref:System.Windows.Media.DrawingBrush>完全水平填充基本磁贴。</span><span class="sxs-lookup"><span data-stu-id="3f153-126">Notice that the <xref:System.Windows.Media.TileBrush.AlignmentX%2A> setting has no effect because the content of the <xref:System.Windows.Media.DrawingBrush> completely fills the base tile horizontally.</span></span>  
  
 [!code-csharp[brushoverviewexamples_snip#TileBrushTopLeftAlignmentTiledInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BrushOverviewExamples_snip/CSharp/TileBrushAlignmentExample.cs#tilebrushtopleftalignmenttiledinline)]
 [!code-vb[brushoverviewexamples_snip#TileBrushTopLeftAlignmentTiledInline](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BrushOverviewExamples_snip/visualbasic/tilebrushalignmentexample.vb#tilebrushtopleftalignmenttiledinline)]
 [!code-xaml[brushoverviewexamples_snip#TileBrushTopLeftAlignmentTiledInline](../../../../samples/snippets/xaml/VS_Snippets_Wpf/BrushOverviewExamples_snip/XAML/TileBrushAlignmentExample.xaml#tilebrushtopleftalignmenttiledinline)]  
  
## <a name="example"></a><span data-ttu-id="3f153-127">示例</span><span class="sxs-lookup"><span data-stu-id="3f153-127">Example</span></span>  
 <span data-ttu-id="3f153-128">最后一个示例将对齐的平铺内容<xref:System.Windows.Media.DrawingBrush>到通过设置其基本磁贴右下角<xref:System.Windows.Media.TileBrush.AlignmentX%2A>属性<xref:System.Windows.Media.AlignmentX.Right>和<xref:System.Windows.Media.TileBrush.AlignmentY%2A>属性<xref:System.Windows.Media.AlignmentY.Bottom>。</span><span class="sxs-lookup"><span data-stu-id="3f153-128">The final example aligns the content of a tiled <xref:System.Windows.Media.DrawingBrush> to the lower-right of its base tile by setting the <xref:System.Windows.Media.TileBrush.AlignmentX%2A> property to <xref:System.Windows.Media.AlignmentX.Right> and the <xref:System.Windows.Media.TileBrush.AlignmentY%2A> property to <xref:System.Windows.Media.AlignmentY.Bottom>.</span></span> <span data-ttu-id="3f153-129">该示例生成以下输出。</span><span class="sxs-lookup"><span data-stu-id="3f153-129">The example produces the following output.</span></span>  
  
 <span data-ttu-id="3f153-130">![一个平铺 TileBrush 底部 &#45; 右对齐](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-tilebrushalignmentexamplebottomrighttiled.png "graphicsmm_TileBrushAlignmentExampleBottomRightTiled")</span><span class="sxs-lookup"><span data-stu-id="3f153-130">![A tiled TileBrush with bottom&#45;right alignment](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-tilebrushalignmentexamplebottomrighttiled.png "graphicsmm_TileBrushAlignmentExampleBottomRightTiled")</span></span>  
<span data-ttu-id="3f153-131">内容与基本平铺图案的右下角对齐的平铺图案</span><span class="sxs-lookup"><span data-stu-id="3f153-131">Tile pattern with content aligned to lower-right in base tile</span></span>  
  
 <span data-ttu-id="3f153-132">同样，<xref:System.Windows.Media.TileBrush.AlignmentX%2A>设置无任何影响，因为内容<xref:System.Windows.Media.DrawingBrush>完全水平填充基本磁贴。</span><span class="sxs-lookup"><span data-stu-id="3f153-132">Again, the <xref:System.Windows.Media.TileBrush.AlignmentX%2A> setting has no effect because the content of the <xref:System.Windows.Media.DrawingBrush> completely fills the base tile horizontally.</span></span>  
  
 [!code-csharp[brushoverviewexamples_snip#TileBrushBottomRightAlignmentInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BrushOverviewExamples_snip/CSharp/TileBrushAlignmentExample.cs#tilebrushbottomrightalignmentinline)]
 [!code-vb[brushoverviewexamples_snip#TileBrushBottomRightAlignmentInline](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BrushOverviewExamples_snip/visualbasic/tilebrushalignmentexample.vb#tilebrushbottomrightalignmentinline)]
 [!code-xaml[brushoverviewexamples_snip#TileBrushBottomRightAlignmentInline](../../../../samples/snippets/xaml/VS_Snippets_Wpf/BrushOverviewExamples_snip/XAML/TileBrushAlignmentExample.xaml#tilebrushbottomrightalignmentinline)]  
  
 <span data-ttu-id="3f153-133">示例使用<xref:System.Windows.Media.DrawingBrush>对象来演示如何<xref:System.Windows.Media.TileBrush.AlignmentX%2A>和<xref:System.Windows.Media.TileBrush.AlignmentY%2A>使用属性。</span><span class="sxs-lookup"><span data-stu-id="3f153-133">The examples use <xref:System.Windows.Media.DrawingBrush> objects to demonstrate how the <xref:System.Windows.Media.TileBrush.AlignmentX%2A> and <xref:System.Windows.Media.TileBrush.AlignmentY%2A> properties are used.</span></span> <span data-ttu-id="3f153-134">这些属性具有相同行为对于所有磁贴画笔： <xref:System.Windows.Media.DrawingBrush>， <xref:System.Windows.Media.ImageBrush>，和<xref:System.Windows.Media.VisualBrush>。</span><span class="sxs-lookup"><span data-stu-id="3f153-134">These properties behave identically for all the tile brushes: <xref:System.Windows.Media.DrawingBrush>, <xref:System.Windows.Media.ImageBrush>, and <xref:System.Windows.Media.VisualBrush>.</span></span> <span data-ttu-id="3f153-135">有关平铺画笔的详细信息，请参阅[使用图像、绘图和视觉对象进行绘制](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md)。</span><span class="sxs-lookup"><span data-stu-id="3f153-135">For more information about tile brushes, see [Painting with Images, Drawings, and Visuals](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3f153-136">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3f153-136">See Also</span></span>  
 <xref:System.Windows.Media.DrawingBrush>  
 <xref:System.Windows.Media.ImageBrush>  
 <xref:System.Windows.Media.VisualBrush>  
 [<span data-ttu-id="3f153-137">使用图像、绘图和视觉对象进行绘制</span><span class="sxs-lookup"><span data-stu-id="3f153-137">Painting with Images, Drawings, and Visuals</span></span>](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md)
