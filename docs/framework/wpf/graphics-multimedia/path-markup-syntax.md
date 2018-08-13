---
title: 路径标记语法
ms.date: 03/30/2017
helpviewer_keywords:
- attribute usage in XAML [WPF]
- XAML [WPF], attribute usage
- graphics [WPF], PathGeometry class
- XAML [WPF], object element usage
ms.assetid: b8586241-a02d-486e-9223-e1e98e047f41
ms.openlocfilehash: 86901f357c43dc7c0c1402bf313e674603eaccbe
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33566764"
---
# <a name="path-markup-syntax"></a><span data-ttu-id="bb3c3-102">路径标记语法</span><span class="sxs-lookup"><span data-stu-id="bb3c3-102">Path Markup Syntax</span></span>
<span data-ttu-id="bb3c3-103">路径中讨论了[形状和 WPF 概述中的基本绘图](../../../../docs/framework/wpf/graphics-multimedia/shapes-and-basic-drawing-in-wpf-overview.md)和[几何图形概述](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md)，但是，本主题详细地介绍了功能强大且复杂的最小化语言，可用于指定路径几何图形更简洁使用[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="bb3c3-103">Paths are discussed in [Shapes and Basic Drawing in WPF Overview](../../../../docs/framework/wpf/graphics-multimedia/shapes-and-basic-drawing-in-wpf-overview.md) and the [Geometry Overview](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md), however, this topic describes in detail the powerful and complex mini-language you can use to specify path geometries more compactly using [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].</span></span>  
  
<a name="prerequisites"></a>   
## <a name="prerequisites"></a><span data-ttu-id="bb3c3-104">系统必备</span><span class="sxs-lookup"><span data-stu-id="bb3c3-104">Prerequisites</span></span>  
 <span data-ttu-id="bb3c3-105">若要了解本主题，你应该熟悉的基本功能<xref:System.Windows.Media.Geometry>对象。</span><span class="sxs-lookup"><span data-stu-id="bb3c3-105">To understand this topic, you should be familiar with the basic features of <xref:System.Windows.Media.Geometry> objects.</span></span> <span data-ttu-id="bb3c3-106">有关详细信息，请参阅[几何图形概述](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="bb3c3-106">For more information, see the [Geometry Overview](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md).</span></span>  
  
<a name="abouthisdocument"></a>   
## <a name="streamgeometry-and-pathfigurecollection-mini-languages"></a><span data-ttu-id="bb3c3-107">StreamGeometry and PathFigureCollection Mini-Languages</span><span class="sxs-lookup"><span data-stu-id="bb3c3-107">StreamGeometry and PathFigureCollection Mini-Languages</span></span>  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<span data-ttu-id="bb3c3-108"> 提供用于描述几何路径提供迷你语言的两个类：<xref:System.Windows.Media.StreamGeometry>和<xref:System.Windows.Media.PathFigureCollection>。</span><span class="sxs-lookup"><span data-stu-id="bb3c3-108"> provides two classes that provide mini-languages for describing geometric paths: <xref:System.Windows.Media.StreamGeometry> and <xref:System.Windows.Media.PathFigureCollection>.</span></span>  
  
-   <span data-ttu-id="bb3c3-109">你使用<xref:System.Windows.Media.StreamGeometry>设置类型的属性时的最小化语言<xref:System.Windows.Media.Geometry>，如<xref:System.Windows.UIElement.Clip%2A>属性<xref:System.Windows.UIElement>或<xref:System.Windows.Shapes.Path.Data%2A>属性<xref:System.Windows.Shapes.Path>元素。</span><span class="sxs-lookup"><span data-stu-id="bb3c3-109">You use the <xref:System.Windows.Media.StreamGeometry> mini-language when setting a property of type <xref:System.Windows.Media.Geometry>, such as the <xref:System.Windows.UIElement.Clip%2A> property of a <xref:System.Windows.UIElement> or the <xref:System.Windows.Shapes.Path.Data%2A> property of a <xref:System.Windows.Shapes.Path> element.</span></span> <span data-ttu-id="bb3c3-110">下面的示例使用的特性语法创建<xref:System.Windows.Media.StreamGeometry>。</span><span class="sxs-lookup"><span data-stu-id="bb3c3-110">The following example uses attribute syntax to create a <xref:System.Windows.Media.StreamGeometry>.</span></span>  
  
     [!code-xaml[GeometrySample_snip_XAML#GraphicsMMStreamGeometryAttributeSyntaxInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample_snip_XAML/CS/MiniLanguageExample.xaml#graphicsmmstreamgeometryattributesyntaxinline)]  
  
-   <span data-ttu-id="bb3c3-111">你使用<xref:System.Windows.Media.PathFigureCollection>最小化语言设置时<xref:System.Windows.Media.PathGeometry.Figures%2A>属性<xref:System.Windows.Media.PathGeometry>。</span><span class="sxs-lookup"><span data-stu-id="bb3c3-111">You use the <xref:System.Windows.Media.PathFigureCollection> mini-language when setting the <xref:System.Windows.Media.PathGeometry.Figures%2A> property of a <xref:System.Windows.Media.PathGeometry>.</span></span> <span data-ttu-id="bb3c3-112">下面的示例使用的特性语法创建<xref:System.Windows.Media.PathFigureCollection>为<xref:System.Windows.Media.PathGeometry>。</span><span class="sxs-lookup"><span data-stu-id="bb3c3-112">The following example uses a attribute syntax to create a <xref:System.Windows.Media.PathFigureCollection> for a <xref:System.Windows.Media.PathGeometry>.</span></span>  
  
     [!code-xaml[GeometrySample_snip_XAML#GraphicsMMPathFigureCollectionAttributeSyntaxInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample_snip_XAML/CS/MiniLanguageExample.xaml#graphicsmmpathfigurecollectionattributesyntaxinline)]  
  
 <span data-ttu-id="bb3c3-113">从前面的示例中可以看出，两种微型语言非常相似。</span><span class="sxs-lookup"><span data-stu-id="bb3c3-113">As you can see from the preceding examples, the two mini-languages are very similar.</span></span> <span data-ttu-id="bb3c3-114">它始终是可以使用<xref:System.Windows.Media.PathGeometry>在其中你可以使用任何情况下<xref:System.Windows.Media.StreamGeometry>; 因此您应使用哪一个？</span><span class="sxs-lookup"><span data-stu-id="bb3c3-114">It's always possible to use a <xref:System.Windows.Media.PathGeometry> in any situation where you could use a <xref:System.Windows.Media.StreamGeometry>; so which one should you use?</span></span> <span data-ttu-id="bb3c3-115">使用<xref:System.Windows.Media.StreamGeometry>当不需要在创建它; 后修改路径使用<xref:System.Windows.Media.PathGeometry>如果需要修改路径。</span><span class="sxs-lookup"><span data-stu-id="bb3c3-115">Use a <xref:System.Windows.Media.StreamGeometry> when you don't need to modify the path after creating it; use a <xref:System.Windows.Media.PathGeometry> if you do need to modify the path.</span></span>  
  
 <span data-ttu-id="bb3c3-116">有关详细信息之间的差异<xref:System.Windows.Media.PathGeometry>和<xref:System.Windows.Media.StreamGeometry>对象，请参阅[几何图形概述](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="bb3c3-116">For more information about the differences between <xref:System.Windows.Media.PathGeometry> and <xref:System.Windows.Media.StreamGeometry> objects, see the [Geometry Overview](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md).</span></span>  
  
### <a name="a-note-about-white-space"></a><span data-ttu-id="bb3c3-117">有关空格的注意事项</span><span class="sxs-lookup"><span data-stu-id="bb3c3-117">A Note about White Space</span></span>  
 <span data-ttu-id="bb3c3-118">为简洁起见，随后的语法部分中显示一个空格，但在显示一个空格的地方，多个空格也可以接受。</span><span class="sxs-lookup"><span data-stu-id="bb3c3-118">For brevity, a single space is shown in the syntax sections that follow, but multiple spaces are also acceptable wherever a single space is shown.</span></span>  
  
 <span data-ttu-id="bb3c3-119">两个数字之间不必用逗号或空格分隔，但仅适用于生成的字符串明确时。</span><span class="sxs-lookup"><span data-stu-id="bb3c3-119">Two numbers don’t actually have to be separated by a comma or whitespace, but this can only be done when the resulting string is unambiguous.</span></span> <span data-ttu-id="bb3c3-120">例如，`2..3`实际两个数字:"2"。</span><span class="sxs-lookup"><span data-stu-id="bb3c3-120">For instance, `2..3` is actually two numbers: "2."</span></span> <span data-ttu-id="bb3c3-121">和“.3”。</span><span class="sxs-lookup"><span data-stu-id="bb3c3-121">And ".3".</span></span> <span data-ttu-id="bb3c3-122">同样，`2-3`是"2"和"-3"。</span><span class="sxs-lookup"><span data-stu-id="bb3c3-122">Similarly, `2-3` is "2" and "-3".</span></span> <span data-ttu-id="bb3c3-123">命令前面或后面也无需加空格。</span><span class="sxs-lookup"><span data-stu-id="bb3c3-123">Spaces are not required before or after commands, either.</span></span>  
  
### <a name="syntax"></a><span data-ttu-id="bb3c3-124">语法</span><span class="sxs-lookup"><span data-stu-id="bb3c3-124">Syntax</span></span>  
 <span data-ttu-id="bb3c3-125">[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]属性使用情况语法<xref:System.Windows.Media.StreamGeometry>由组成一个可选<xref:System.Windows.Media.FillRule>值和一个或多个图说明。</span><span class="sxs-lookup"><span data-stu-id="bb3c3-125">The [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] attribute usage syntax for a <xref:System.Windows.Media.StreamGeometry> is composed of an optional <xref:System.Windows.Media.FillRule> value and one or more figure descriptions.</span></span>  
  
|<span data-ttu-id="bb3c3-126">StreamGeometry XAML 属性用法</span><span class="sxs-lookup"><span data-stu-id="bb3c3-126">StreamGeometry XAML Attribute Usage</span></span>|  
|-----------------------------------------|  
|<span data-ttu-id="bb3c3-127">`<` *对象\*\*属性* `="`[ `fillRule`] `figureDescription`[ `figureDescription`] \* `" ... />`</span><span class="sxs-lookup"><span data-stu-id="bb3c3-127">`<` *object* *property* `="`[ `fillRule`] `figureDescription`[ `figureDescription`]\* `" ... />`</span></span>|  
  
 <span data-ttu-id="bb3c3-128">[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]属性使用情况语法<xref:System.Windows.Media.PathFigureCollection>由组成一个或多个图说明。</span><span class="sxs-lookup"><span data-stu-id="bb3c3-128">The [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] attribute usage syntax for a <xref:System.Windows.Media.PathFigureCollection> is composed of one or more figure descriptions.</span></span>  
  
|<span data-ttu-id="bb3c3-129">PathFigureCollection XAML Attribute Usage</span><span class="sxs-lookup"><span data-stu-id="bb3c3-129">PathFigureCollection XAML Attribute Usage</span></span>|  
|-----------------------------------------------|  
|<span data-ttu-id="bb3c3-130">`<` *对象\*\*属性* `="` `figureDescription`[ `figureDescription`] \* `" ... />`</span><span class="sxs-lookup"><span data-stu-id="bb3c3-130">`<` *object* *property* `="` `figureDescription`[ `figureDescription`]\* `" ... />`</span></span>|  
  
|<span data-ttu-id="bb3c3-131">术语</span><span class="sxs-lookup"><span data-stu-id="bb3c3-131">Term</span></span>|<span data-ttu-id="bb3c3-132">描述</span><span class="sxs-lookup"><span data-stu-id="bb3c3-132">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="bb3c3-133">*fillRule*</span><span class="sxs-lookup"><span data-stu-id="bb3c3-133">*fillRule*</span></span>|<xref:System.Windows.Media.FillRule?displayProperty=nameWithType><br /><br /> <span data-ttu-id="bb3c3-134">指定是否<xref:System.Windows.Media.StreamGeometry>使用<xref:System.Windows.Media.FillRule.EvenOdd>或<xref:System.Windows.Media.FillRule.Nonzero> <xref:System.Windows.Media.PathGeometry.FillRule%2A>。</span><span class="sxs-lookup"><span data-stu-id="bb3c3-134">Specifies whether the <xref:System.Windows.Media.StreamGeometry> uses the <xref:System.Windows.Media.FillRule.EvenOdd> or <xref:System.Windows.Media.FillRule.Nonzero><xref:System.Windows.Media.PathGeometry.FillRule%2A>.</span></span><br /><br /> <span data-ttu-id="bb3c3-135">-   `F0` 指定<xref:System.Windows.Media.FillRule.EvenOdd>填充规则。</span><span class="sxs-lookup"><span data-stu-id="bb3c3-135">-   `F0` specifies the <xref:System.Windows.Media.FillRule.EvenOdd> fill rule.</span></span><br /><span data-ttu-id="bb3c3-136">-   `F1` 指定<xref:System.Windows.Media.FillRule.Nonzero>填充规则。</span><span class="sxs-lookup"><span data-stu-id="bb3c3-136">-   `F1` specifies the <xref:System.Windows.Media.FillRule.Nonzero> fill rule.</span></span><br /><br /> <span data-ttu-id="bb3c3-137">如果省略此命令，则子路径使用默认行为，即<xref:System.Windows.Media.FillRule.EvenOdd>。</span><span class="sxs-lookup"><span data-stu-id="bb3c3-137">If you omit this command, the subpath uses the default behavior, which is <xref:System.Windows.Media.FillRule.EvenOdd>.</span></span> <span data-ttu-id="bb3c3-138">如果指定该命令，须先设置命令。</span><span class="sxs-lookup"><span data-stu-id="bb3c3-138">If you specify this command, you must place it first.</span></span>|  
|<span data-ttu-id="bb3c3-139">*figureDescription*</span><span class="sxs-lookup"><span data-stu-id="bb3c3-139">*figureDescription*</span></span>|<span data-ttu-id="bb3c3-140">图形由一个移动命令，绘制命令和一个可选的关闭命令组成。</span><span class="sxs-lookup"><span data-stu-id="bb3c3-140">A figure composed of a move command, draw commands, and an optional close command.</span></span><br /><br /> <span data-ttu-id="bb3c3-141">`moveCommand` `drawCommands`  `[` `closeCommand` `]`</span><span class="sxs-lookup"><span data-stu-id="bb3c3-141">`moveCommand` `drawCommands`  `[` `closeCommand` `]`</span></span>|  
|<span data-ttu-id="bb3c3-142">*moveCommand*</span><span class="sxs-lookup"><span data-stu-id="bb3c3-142">*moveCommand*</span></span>|<span data-ttu-id="bb3c3-143">用于指定图形起点的移动命令。</span><span class="sxs-lookup"><span data-stu-id="bb3c3-143">A move command that specifies the start point of the figure.</span></span> <span data-ttu-id="bb3c3-144">请参阅[移动命令](#themovecommand)部分。</span><span class="sxs-lookup"><span data-stu-id="bb3c3-144">See the [Move Command](#themovecommand) section.</span></span>|  
|<span data-ttu-id="bb3c3-145">*drawCommands*</span><span class="sxs-lookup"><span data-stu-id="bb3c3-145">*drawCommands*</span></span>|<span data-ttu-id="bb3c3-146">用于描述图形内容的一个或多个绘图命令。</span><span class="sxs-lookup"><span data-stu-id="bb3c3-146">One or more drawing commands that describe the figure's contents.</span></span> <span data-ttu-id="bb3c3-147">请参阅[绘制命令](#drawcommands)部分。</span><span class="sxs-lookup"><span data-stu-id="bb3c3-147">See the [Draw Commands](#drawcommands) section.</span></span>|  
|<span data-ttu-id="bb3c3-148">*closeCommand*</span><span class="sxs-lookup"><span data-stu-id="bb3c3-148">*closeCommand*</span></span>|<span data-ttu-id="bb3c3-149">用于关闭图形的可选关闭命令。</span><span class="sxs-lookup"><span data-stu-id="bb3c3-149">An optional close command that closes figure.</span></span> <span data-ttu-id="bb3c3-150">请参阅[关闭命令](#closecommand)部分。</span><span class="sxs-lookup"><span data-stu-id="bb3c3-150">See the [Close Command](#closecommand) section.</span></span>|  
  
<a name="themovecommand"></a>   
## <a name="move-command"></a><span data-ttu-id="bb3c3-151">移动命令</span><span class="sxs-lookup"><span data-stu-id="bb3c3-151">Move Command</span></span>  
 <span data-ttu-id="bb3c3-152">指定新图形的起点。</span><span class="sxs-lookup"><span data-stu-id="bb3c3-152">Specifies the start point of a new figure.</span></span>  
  
|<span data-ttu-id="bb3c3-153">语法</span><span class="sxs-lookup"><span data-stu-id="bb3c3-153">Syntax</span></span>|  
|------------|  
|<span data-ttu-id="bb3c3-154">`M` *startPoint*</span><span class="sxs-lookup"><span data-stu-id="bb3c3-154">`M` *startPoint*</span></span><br /><br /> <span data-ttu-id="bb3c3-155">- 或 -</span><span class="sxs-lookup"><span data-stu-id="bb3c3-155">- or -</span></span><br /><br /> <span data-ttu-id="bb3c3-156">`m` *startPoint*</span><span class="sxs-lookup"><span data-stu-id="bb3c3-156">`m` *startPoint*</span></span>|  
  
|<span data-ttu-id="bb3c3-157">术语</span><span class="sxs-lookup"><span data-stu-id="bb3c3-157">Term</span></span>|<span data-ttu-id="bb3c3-158">描述</span><span class="sxs-lookup"><span data-stu-id="bb3c3-158">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="bb3c3-159">*startPoint*</span><span class="sxs-lookup"><span data-stu-id="bb3c3-159">*startPoint*</span></span>|<xref:System.Windows.Point?displayProperty=nameWithType><br /><br /> <span data-ttu-id="bb3c3-160">新图形的起点。</span><span class="sxs-lookup"><span data-stu-id="bb3c3-160">The start point of a new figure.</span></span>|  
  
 <span data-ttu-id="bb3c3-161">大写`M`指示`startPoint`绝对值; 小写`m`指示`startPoint`是到以前的点的偏移量或 (0，0) 如果不存在。</span><span class="sxs-lookup"><span data-stu-id="bb3c3-161">An uppercase `M` indicates that `startPoint` is an absolute value; a lowercase `m` indicates that `startPoint` is an offset to the previous point, or (0,0) if none exists.</span></span> <span data-ttu-id="bb3c3-162">如果在移动命令之后列出多个点，可以绘制一条连接到这些点的直线，尽管已指定了直线命令。</span><span class="sxs-lookup"><span data-stu-id="bb3c3-162">If you list multiple points after the move command, a line is drawn to those points though you specified the line command.</span></span>  
  
<a name="drawcommands"></a>   
## <a name="draw-commands"></a><span data-ttu-id="bb3c3-163">绘制命令</span><span class="sxs-lookup"><span data-stu-id="bb3c3-163">Draw Commands</span></span>  
 <span data-ttu-id="bb3c3-164">绘制命令可以由几个形状命令组成。</span><span class="sxs-lookup"><span data-stu-id="bb3c3-164">A draw command can consist of several shape commands.</span></span> <span data-ttu-id="bb3c3-165">以下形状命令可用：直线、水平线、竖线、三次贝塞尔曲线、二次贝塞尔曲线、平滑三次贝塞尔曲线、平滑二次贝塞尔曲线和椭圆弧。</span><span class="sxs-lookup"><span data-stu-id="bb3c3-165">The following shape commands are available: line, horizontal line, vertical line, cubic Bezier curve, quadratic Bezier curve, smooth cubic Bezier curve, smooth quadratic Bezier curve, and elliptical arc.</span></span>  
  
 <span data-ttu-id="bb3c3-166">可以使用大写或小写字母输入每个命令：大写字母表示绝对值，小写字母表示相对值：该线段的控制点相对于前面示例的终点。</span><span class="sxs-lookup"><span data-stu-id="bb3c3-166">You enter each command by using either an uppercase or a lowercase letter: uppercase letters denote absolute values and lowercase letters denote relative values: the control points for that segment are relative to the end point of the preceding example.</span></span> <span data-ttu-id="bb3c3-167">在按顺序输入多个相同类型的命令，则可以省略重复命令项中;例如，`L 100,200 300,400`等效于`L 100,200 L 300,400`。</span><span class="sxs-lookup"><span data-stu-id="bb3c3-167">When sequentially entering more than one command of the same type, you can omit the duplicate command entry; for example, `L 100,200 300,400` is equivalent to `L 100,200 L 300,400`.</span></span> <span data-ttu-id="bb3c3-168">下表描述了**移动**和**绘制**命令。</span><span class="sxs-lookup"><span data-stu-id="bb3c3-168">The following table describes the **move** and **draw** commands.</span></span>  
  
### <a name="line-command"></a><span data-ttu-id="bb3c3-169">直线命令</span><span class="sxs-lookup"><span data-stu-id="bb3c3-169">Line Command</span></span>  
 <span data-ttu-id="bb3c3-170">在当前点和指定的终点之间创建一条直线。</span><span class="sxs-lookup"><span data-stu-id="bb3c3-170">Creates a straight line between the current point and the specified end point.</span></span> <span data-ttu-id="bb3c3-171">`l 20 30` 和`L 20,30`是有效的示例**行**命令。</span><span class="sxs-lookup"><span data-stu-id="bb3c3-171">`l 20 30` and `L 20,30` are examples of valid **line** commands.</span></span>  
  
|<span data-ttu-id="bb3c3-172">语法</span><span class="sxs-lookup"><span data-stu-id="bb3c3-172">Syntax</span></span>|  
|------------|  
|<span data-ttu-id="bb3c3-173">`L` *endPoint*</span><span class="sxs-lookup"><span data-stu-id="bb3c3-173">`L` *endPoint*</span></span><br /><br /> <span data-ttu-id="bb3c3-174">- 或 -</span><span class="sxs-lookup"><span data-stu-id="bb3c3-174">- or -</span></span><br /><br /> <span data-ttu-id="bb3c3-175">`l` *endPoint*</span><span class="sxs-lookup"><span data-stu-id="bb3c3-175">`l` *endPoint*</span></span>|  
  
|<span data-ttu-id="bb3c3-176">术语</span><span class="sxs-lookup"><span data-stu-id="bb3c3-176">Term</span></span>|<span data-ttu-id="bb3c3-177">描述</span><span class="sxs-lookup"><span data-stu-id="bb3c3-177">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="bb3c3-178">*endPoint*</span><span class="sxs-lookup"><span data-stu-id="bb3c3-178">*endPoint*</span></span>|<xref:System.Windows.Point?displayProperty=nameWithType><br /><br /> <span data-ttu-id="bb3c3-179">线条的终点。</span><span class="sxs-lookup"><span data-stu-id="bb3c3-179">The end point of the line.</span></span>|  

<span data-ttu-id="bb3c3-180">大写`L`指示`endPoint`绝对值; 小写`l`指示`endPoint`是到以前的点的偏移量或 (0，0) 如果不存在。</span><span class="sxs-lookup"><span data-stu-id="bb3c3-180">An uppercase `L` indicates that `endPoint` is an absolute value; a lowercase `l` indicates that `endPoint` is an offset to the previous point, or (0,0) if none exists.</span></span>

### <a name="horizontal-line-command"></a><span data-ttu-id="bb3c3-181">水平线命令</span><span class="sxs-lookup"><span data-stu-id="bb3c3-181">Horizontal Line Command</span></span>  
 <span data-ttu-id="bb3c3-182">在当前点和指定的 x 坐标之间创建一条水平线。</span><span class="sxs-lookup"><span data-stu-id="bb3c3-182">Creates a horizontal line between the current point and the specified x-coordinate.</span></span> <span data-ttu-id="bb3c3-183">`H 90` 是有效水平线命令的示例。</span><span class="sxs-lookup"><span data-stu-id="bb3c3-183">`H 90` is an example of a valid horizontal line command.</span></span>

  
|<span data-ttu-id="bb3c3-184">语法</span><span class="sxs-lookup"><span data-stu-id="bb3c3-184">Syntax</span></span>|  
|------------|  
|<span data-ttu-id="bb3c3-185">`H`  *x*</span><span class="sxs-lookup"><span data-stu-id="bb3c3-185">`H`  *x*</span></span><br /><br /> <span data-ttu-id="bb3c3-186">- 或 -</span><span class="sxs-lookup"><span data-stu-id="bb3c3-186">- or -</span></span><br /><br /> <span data-ttu-id="bb3c3-187">`h`  *x*</span><span class="sxs-lookup"><span data-stu-id="bb3c3-187">`h`  *x*</span></span>|  
  
|<span data-ttu-id="bb3c3-188">术语</span><span class="sxs-lookup"><span data-stu-id="bb3c3-188">Term</span></span>|<span data-ttu-id="bb3c3-189">描述</span><span class="sxs-lookup"><span data-stu-id="bb3c3-189">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="bb3c3-190">*x*</span><span class="sxs-lookup"><span data-stu-id="bb3c3-190">*x*</span></span>|<xref:System.Double?displayProperty=nameWithType><br /><br /> <span data-ttu-id="bb3c3-191">线条终点的 x 坐标。</span><span class="sxs-lookup"><span data-stu-id="bb3c3-191">The x-coordinate of the end point of the line.</span></span>|  
  
<span data-ttu-id="bb3c3-192">大写`H`指示`x`绝对值; 小写`h`指示`x`是到以前的点的偏移量或 (0，0) 如果不存在。</span><span class="sxs-lookup"><span data-stu-id="bb3c3-192">An uppercase `H` indicates that `x` is an absolute value; a lowercase `h` indicates that `x` is an offset to the previous point, or (0,0) if none exists.</span></span>
  
### <a name="vertical-line-command"></a><span data-ttu-id="bb3c3-193">竖线命令</span><span class="sxs-lookup"><span data-stu-id="bb3c3-193">Vertical Line Command</span></span>  
 <span data-ttu-id="bb3c3-194">在当前点和指定的 y 坐标之间创建一条竖线。</span><span class="sxs-lookup"><span data-stu-id="bb3c3-194">Creates a vertical line between the current point and the specified y-coordinate.</span></span> <span data-ttu-id="bb3c3-195">`v 90` 是有效竖线命令的示例。</span><span class="sxs-lookup"><span data-stu-id="bb3c3-195">`v 90` is an example of a valid vertical line command.</span></span>

  
|<span data-ttu-id="bb3c3-196">语法</span><span class="sxs-lookup"><span data-stu-id="bb3c3-196">Syntax</span></span>|  
|------------|  
|<span data-ttu-id="bb3c3-197">`V`  *y*</span><span class="sxs-lookup"><span data-stu-id="bb3c3-197">`V`  *y*</span></span><br /><br /> <span data-ttu-id="bb3c3-198">- 或 -</span><span class="sxs-lookup"><span data-stu-id="bb3c3-198">- or -</span></span><br /><br /> <span data-ttu-id="bb3c3-199">`v`  *y*</span><span class="sxs-lookup"><span data-stu-id="bb3c3-199">`v`  *y*</span></span>|  
  
|<span data-ttu-id="bb3c3-200">术语</span><span class="sxs-lookup"><span data-stu-id="bb3c3-200">Term</span></span>|<span data-ttu-id="bb3c3-201">描述</span><span class="sxs-lookup"><span data-stu-id="bb3c3-201">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="bb3c3-202">*y*</span><span class="sxs-lookup"><span data-stu-id="bb3c3-202">*y*</span></span>|<xref:System.Double?displayProperty=nameWithType><br /><br /> <span data-ttu-id="bb3c3-203">直线终点的 y 坐标。</span><span class="sxs-lookup"><span data-stu-id="bb3c3-203">The y-coordinate of the end point of the line.</span></span>|  

<span data-ttu-id="bb3c3-204">大写`V`指示`y`绝对值; 小写`v`指示`y`是到以前的点的偏移量或 (0，0) 如果不存在。</span><span class="sxs-lookup"><span data-stu-id="bb3c3-204">An uppercase `V` indicates that `y` is an absolute value; a lowercase `v` indicates that `y` is an offset to the previous point, or (0,0) if none exists.</span></span>  
    
### <a name="cubic-bezier-curve-command"></a><span data-ttu-id="bb3c3-205">三次贝塞尔曲线命令</span><span class="sxs-lookup"><span data-stu-id="bb3c3-205">Cubic Bezier Curve Command</span></span>  
 <span data-ttu-id="bb3c3-206">通过使用两个指定的控制点创建当前点和指定的终结点之间的三次方贝塞尔曲线 (`controlPoint`1 和`controlPoint`2)。</span><span class="sxs-lookup"><span data-stu-id="bb3c3-206">Creates a cubic Bezier curve between the current point and the specified end point by using the two specified control points (`controlPoint`1 and `controlPoint`2).</span></span> <span data-ttu-id="bb3c3-207">`C 100,200 200,400 300,200` 是有效曲线命令的示例。</span><span class="sxs-lookup"><span data-stu-id="bb3c3-207">`C 100,200 200,400 300,200` is an example of a valid curve command.</span></span>  
  
|<span data-ttu-id="bb3c3-208">语法</span><span class="sxs-lookup"><span data-stu-id="bb3c3-208">Syntax</span></span>|  
|------------|  
|<span data-ttu-id="bb3c3-209">`C` `controlPoint`1`controlPoint`2`endPoint`</span><span class="sxs-lookup"><span data-stu-id="bb3c3-209">`C` `controlPoint`1`controlPoint`2`endPoint`</span></span><br /><br /> <span data-ttu-id="bb3c3-210">- 或 -</span><span class="sxs-lookup"><span data-stu-id="bb3c3-210">- or -</span></span><br /><br /> <span data-ttu-id="bb3c3-211">`c` `controlPoint`1`controlPoint`2`endPoint`</span><span class="sxs-lookup"><span data-stu-id="bb3c3-211">`c` `controlPoint`1`controlPoint`2`endPoint`</span></span>|  
  
|<span data-ttu-id="bb3c3-212">术语</span><span class="sxs-lookup"><span data-stu-id="bb3c3-212">Term</span></span>|<span data-ttu-id="bb3c3-213">描述</span><span class="sxs-lookup"><span data-stu-id="bb3c3-213">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="bb3c3-214">`controlPoint`1</span><span class="sxs-lookup"><span data-stu-id="bb3c3-214">`controlPoint`1</span></span>|<xref:System.Windows.Point?displayProperty=nameWithType><br /><br /> <span data-ttu-id="bb3c3-215">曲线的第一个控制点，它决定曲线的起始切线。</span><span class="sxs-lookup"><span data-stu-id="bb3c3-215">The first control point of the curve, which determines the starting tangent of the curve.</span></span>|  
|<span data-ttu-id="bb3c3-216">`controlPoint`2</span><span class="sxs-lookup"><span data-stu-id="bb3c3-216">`controlPoint`2</span></span>|<xref:System.Windows.Point?displayProperty=nameWithType><br /><br /> <span data-ttu-id="bb3c3-217">曲线的第二个控制点，它决定曲线的结束切线。</span><span class="sxs-lookup"><span data-stu-id="bb3c3-217">The second control point of the curve, which determines the ending tangent of the curve.</span></span>|  
|`endPoint`|<xref:System.Windows.Point?displayProperty=nameWithType><br /><br /> <span data-ttu-id="bb3c3-218">绘制曲线将通过的点。</span><span class="sxs-lookup"><span data-stu-id="bb3c3-218">The point to which the curve is drawn.</span></span>|  
  
### <a name="quadratic-bezier-curve-command"></a><span data-ttu-id="bb3c3-219">二次贝塞尔曲线命令</span><span class="sxs-lookup"><span data-stu-id="bb3c3-219">Quadratic Bezier Curve Command</span></span>  
 <span data-ttu-id="bb3c3-220">通过使用指定的控制点创建二次贝塞尔曲线的当前点和指定的终结点之间 (`controlPoint`)。</span><span class="sxs-lookup"><span data-stu-id="bb3c3-220">Creates a quadratic Bezier curve between the current point and the specified end point by using the specified control point (`controlPoint`).</span></span> <span data-ttu-id="bb3c3-221">`q 100,200 300,200` 为有效二次贝塞尔曲线命令的示例。</span><span class="sxs-lookup"><span data-stu-id="bb3c3-221">`q 100,200 300,200` is an example of a valid quadratic Bezier curve command.</span></span>  
  
|<span data-ttu-id="bb3c3-222">语法</span><span class="sxs-lookup"><span data-stu-id="bb3c3-222">Syntax</span></span>|  
|------------|  
|<span data-ttu-id="bb3c3-223">`Q` `controlPoint` `endPoint`</span><span class="sxs-lookup"><span data-stu-id="bb3c3-223">`Q` `controlPoint` `endPoint`</span></span><br /><br /> <span data-ttu-id="bb3c3-224">- 或 -</span><span class="sxs-lookup"><span data-stu-id="bb3c3-224">- or -</span></span><br /><br /> <span data-ttu-id="bb3c3-225">`q` `controlPoint` `endPoint`</span><span class="sxs-lookup"><span data-stu-id="bb3c3-225">`q` `controlPoint` `endPoint`</span></span>|  
  
|<span data-ttu-id="bb3c3-226">术语</span><span class="sxs-lookup"><span data-stu-id="bb3c3-226">Term</span></span>|<span data-ttu-id="bb3c3-227">描述</span><span class="sxs-lookup"><span data-stu-id="bb3c3-227">Description</span></span>|  
|----------|-----------------|  
|`controlPoint`|<xref:System.Windows.Point?displayProperty=nameWithType><br /><br /> <span data-ttu-id="bb3c3-228">曲线的控制点，它决定曲线的开始和结束切线。</span><span class="sxs-lookup"><span data-stu-id="bb3c3-228">The control point of the curve, which determines the starting and ending tangents of the curve.</span></span>|  
|`endPoint`|<xref:System.Windows.Point?displayProperty=nameWithType><br /><br /> <span data-ttu-id="bb3c3-229">绘制曲线将通过的点。</span><span class="sxs-lookup"><span data-stu-id="bb3c3-229">The point to which the curve is drawn.</span></span>|  
  
### <a name="smooth-cubic-bezier-curve-command"></a><span data-ttu-id="bb3c3-230">平滑三次贝塞尔曲线命令</span><span class="sxs-lookup"><span data-stu-id="bb3c3-230">Smooth cubic Bezier curve Command</span></span>  
 <span data-ttu-id="bb3c3-231">在当前点和指定的终点之间创建三次贝塞尔曲线。</span><span class="sxs-lookup"><span data-stu-id="bb3c3-231">Creates a cubic Bezier curve between the current point and the specified end point.</span></span> <span data-ttu-id="bb3c3-232">假设第一控制点为相对当前点前一命令的第二控制点的反射。</span><span class="sxs-lookup"><span data-stu-id="bb3c3-232">The first control point is assumed to be the reflection of the second control point of the previous command relative to the current point.</span></span> <span data-ttu-id="bb3c3-233">如果没有前一命令或如果前一命令不是三次贝塞尔曲线命令或平滑三次贝塞尔曲线命令，则假设第一个控制点与当前点重合。</span><span class="sxs-lookup"><span data-stu-id="bb3c3-233">If there is no previous command or if the previous command was not a cubic Bezier curve command or a smooth cubic Bezier curve command, assume the first control point is coincident with the current point.</span></span> <span data-ttu-id="bb3c3-234">第二个控制点，由指定的曲线，最终的控制点`controlPoint`2。</span><span class="sxs-lookup"><span data-stu-id="bb3c3-234">The second control point, the control point for the end of the curve, is specified by `controlPoint`2.</span></span> <span data-ttu-id="bb3c3-235">例如，`S 100,200 200,300`是一个有效的平滑三次方贝塞尔曲线命令。</span><span class="sxs-lookup"><span data-stu-id="bb3c3-235">For example, `S 100,200 200,300` is a valid smooth cubic Bezier curve command.</span></span>  
  
|<span data-ttu-id="bb3c3-236">语法</span><span class="sxs-lookup"><span data-stu-id="bb3c3-236">Syntax</span></span>|  
|------------|  
|<span data-ttu-id="bb3c3-237">`S` `controlPoint`2`endPoint`</span><span class="sxs-lookup"><span data-stu-id="bb3c3-237">`S` `controlPoint`2`endPoint`</span></span><br /><br /> <span data-ttu-id="bb3c3-238">- 或 -</span><span class="sxs-lookup"><span data-stu-id="bb3c3-238">- or -</span></span><br /><br /> <span data-ttu-id="bb3c3-239">`s` `controlPoint`2`endPoint`</span><span class="sxs-lookup"><span data-stu-id="bb3c3-239">`s` `controlPoint`2`endPoint`</span></span>|  
  
|<span data-ttu-id="bb3c3-240">术语</span><span class="sxs-lookup"><span data-stu-id="bb3c3-240">Term</span></span>|<span data-ttu-id="bb3c3-241">描述</span><span class="sxs-lookup"><span data-stu-id="bb3c3-241">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="bb3c3-242">`controlPoint`2</span><span class="sxs-lookup"><span data-stu-id="bb3c3-242">`controlPoint`2</span></span>|<xref:System.Windows.Point?displayProperty=nameWithType><br /><br /> <span data-ttu-id="bb3c3-243">曲线的控制点，它决定曲线的结束切线。</span><span class="sxs-lookup"><span data-stu-id="bb3c3-243">The control point of the curve, which determines the ending tangent of the curve.</span></span>|  
|`endPoint`|<xref:System.Windows.Point?displayProperty=nameWithType><br /><br /> <span data-ttu-id="bb3c3-244">绘制曲线将通过的点。</span><span class="sxs-lookup"><span data-stu-id="bb3c3-244">The point to which the curve is drawn.</span></span>|  
  
### <a name="smooth-quadratic-bezier-curve-command"></a><span data-ttu-id="bb3c3-245">平滑二次贝塞尔曲线命令</span><span class="sxs-lookup"><span data-stu-id="bb3c3-245">Smooth quadratic Bezier curve Command</span></span>  
 <span data-ttu-id="bb3c3-246">在当前点和指定的终点之间创建二次贝塞尔曲线。</span><span class="sxs-lookup"><span data-stu-id="bb3c3-246">Creates a quadratic Bezier curve between the current point and the specified end point.</span></span> <span data-ttu-id="bb3c3-247">假设控制点为相对于当前点前一命令的控制点的反射。</span><span class="sxs-lookup"><span data-stu-id="bb3c3-247">The control point is assumed to be the reflection of the control point of the previous command relative to the current point.</span></span> <span data-ttu-id="bb3c3-248">如果没有前一命令或如果前一命令不是二次贝塞尔曲线命令或平滑二次贝塞尔曲线命令，则控制点与当前点重合。</span><span class="sxs-lookup"><span data-stu-id="bb3c3-248">If there is no previous command or if the previous command was not a quadratic Bezier curve command or a smooth quadratic Bezier curve command, the control point is coincident with the current point.</span></span>  
  
|<span data-ttu-id="bb3c3-249">语法</span><span class="sxs-lookup"><span data-stu-id="bb3c3-249">Syntax</span></span>|  
|------------|  
|<span data-ttu-id="bb3c3-250">`T` `controlPoint` `endPoint`</span><span class="sxs-lookup"><span data-stu-id="bb3c3-250">`T` `controlPoint` `endPoint`</span></span><br /><br /> <span data-ttu-id="bb3c3-251">- 或 -</span><span class="sxs-lookup"><span data-stu-id="bb3c3-251">- or -</span></span><br /><br /> <span data-ttu-id="bb3c3-252">`t` `controlPoint` `endPoint`</span><span class="sxs-lookup"><span data-stu-id="bb3c3-252">`t` `controlPoint` `endPoint`</span></span>|  
  
|<span data-ttu-id="bb3c3-253">术语</span><span class="sxs-lookup"><span data-stu-id="bb3c3-253">Term</span></span>|<span data-ttu-id="bb3c3-254">描述</span><span class="sxs-lookup"><span data-stu-id="bb3c3-254">Description</span></span>|  
|----------|-----------------|  
|`controlPoint`|<xref:System.Windows.Point?displayProperty=nameWithType><br /><br /> <span data-ttu-id="bb3c3-255">曲线的控制点，决定曲线的起点和曲线的切线。</span><span class="sxs-lookup"><span data-stu-id="bb3c3-255">The control point of the curve, which determines the starting and tangent of the curve.</span></span>|  
|`endPoint`|<xref:System.Windows.Point?displayProperty=nameWithType><br /><br /> <span data-ttu-id="bb3c3-256">绘制曲线将通过的点。</span><span class="sxs-lookup"><span data-stu-id="bb3c3-256">The point to which the curve is drawn.</span></span>|  
  
### <a name="elliptical-arc-command"></a><span data-ttu-id="bb3c3-257">椭圆弧命令</span><span class="sxs-lookup"><span data-stu-id="bb3c3-257">Elliptical Arc Command</span></span>  
 <span data-ttu-id="bb3c3-258">在当前点和指定的终点之间创建一个椭圆弧。</span><span class="sxs-lookup"><span data-stu-id="bb3c3-258">Creates an elliptical arc between the current point and the specified end point.</span></span>  
  
|<span data-ttu-id="bb3c3-259">语法</span><span class="sxs-lookup"><span data-stu-id="bb3c3-259">Syntax</span></span>|  
|------------|  
|<span data-ttu-id="bb3c3-260">`A` `size` `rotationAngle` `isLargeArcFlag` `sweepDirectionFlag` `endPoint`</span><span class="sxs-lookup"><span data-stu-id="bb3c3-260">`A` `size` `rotationAngle` `isLargeArcFlag` `sweepDirectionFlag` `endPoint`</span></span><br /><br /> <span data-ttu-id="bb3c3-261">- 或 -</span><span class="sxs-lookup"><span data-stu-id="bb3c3-261">- or -</span></span><br /><br /> <span data-ttu-id="bb3c3-262">`a` `size` `rotationAngle` `isLargeArcFlag` `sweepDirectionFlag` `endPoint`</span><span class="sxs-lookup"><span data-stu-id="bb3c3-262">`a` `size` `rotationAngle` `isLargeArcFlag` `sweepDirectionFlag` `endPoint`</span></span>|  
  
|<span data-ttu-id="bb3c3-263">术语</span><span class="sxs-lookup"><span data-stu-id="bb3c3-263">Term</span></span>|<span data-ttu-id="bb3c3-264">描述</span><span class="sxs-lookup"><span data-stu-id="bb3c3-264">Description</span></span>|  
|----------|-----------------|  
|`size`|<xref:System.Windows.Size?displayProperty=nameWithType><br /><br /> <span data-ttu-id="bb3c3-265">圆弧的 x 轴和 y 轴半径。</span><span class="sxs-lookup"><span data-stu-id="bb3c3-265">The x- and y-radius of the arc.</span></span>|  
|`rotationAngle`|<xref:System.Double?displayProperty=nameWithType><br /><br /> <span data-ttu-id="bb3c3-266">椭圆的旋转，以度为单位。</span><span class="sxs-lookup"><span data-stu-id="bb3c3-266">The rotation of the ellipse, in degrees.</span></span>|  
|`isLargeArcFlag`|<span data-ttu-id="bb3c3-267">如果圆弧角度应为 180 度或更大，请设置为 1，否则设置为 0。</span><span class="sxs-lookup"><span data-stu-id="bb3c3-267">Set to 1 if the angle of the arc should be 180 degrees or greater; otherwise, set to 0.</span></span>|  
|`sweepDirectionFlag`|<span data-ttu-id="bb3c3-268">如果以正角方向绘制圆弧，请设置为 1；否则设置为 0。</span><span class="sxs-lookup"><span data-stu-id="bb3c3-268">Set to 1 if the arc is drawn in a positive-angle direction; otherwise, set to 0.</span></span>|  
|`endPoint`|<xref:System.Windows.Point?displayProperty=nameWithType><br /><br /> <span data-ttu-id="bb3c3-269">绘制弧将通过的点。</span><span class="sxs-lookup"><span data-stu-id="bb3c3-269">The point to which the arc is drawn.</span></span>|  
  
<a name="closecommand"></a>   
## <a name="the-close-command"></a><span data-ttu-id="bb3c3-270">关闭命令</span><span class="sxs-lookup"><span data-stu-id="bb3c3-270">The Close Command</span></span>  
 <span data-ttu-id="bb3c3-271">结束当前图形，并创建一条将当前点连接到图形起点的直线。</span><span class="sxs-lookup"><span data-stu-id="bb3c3-271">Ends the current figure and creates a line that connects the current point to the starting point of the figure.</span></span> <span data-ttu-id="bb3c3-272">此命令可以在图形最后一段与第一段之间创建一条连接线（角）。</span><span class="sxs-lookup"><span data-stu-id="bb3c3-272">This command creates a line-join (corner) between the last segment and the first segment of the figure.</span></span>  
  
|<span data-ttu-id="bb3c3-273">语法</span><span class="sxs-lookup"><span data-stu-id="bb3c3-273">Syntax</span></span>|  
|------------|  
|`Z`<br /><br /> <span data-ttu-id="bb3c3-274">- 或 -</span><span class="sxs-lookup"><span data-stu-id="bb3c3-274">- or -</span></span><br /><br /> `z`|  

<a name="pointsyntax"></a>   
## <a name="point-syntax"></a><span data-ttu-id="bb3c3-275">点语法</span><span class="sxs-lookup"><span data-stu-id="bb3c3-275">Point Syntax</span></span>  
 <span data-ttu-id="bb3c3-276">描述一个点 x 和 y 坐标位置 (0，0) 是左上的角。</span><span class="sxs-lookup"><span data-stu-id="bb3c3-276">Describes the x- and y-coordinates of a point where (0,0) is the top left corner.</span></span>
  
|<span data-ttu-id="bb3c3-277">语法</span><span class="sxs-lookup"><span data-stu-id="bb3c3-277">Syntax</span></span>|  
|------------|  
|<span data-ttu-id="bb3c3-278">`x` `,` `y`</span><span class="sxs-lookup"><span data-stu-id="bb3c3-278">`x` `,` `y`</span></span><br /><br /> <span data-ttu-id="bb3c3-279">- 或 -</span><span class="sxs-lookup"><span data-stu-id="bb3c3-279">- or -</span></span><br /><br /> <span data-ttu-id="bb3c3-280">`x` `y`</span><span class="sxs-lookup"><span data-stu-id="bb3c3-280">`x` `y`</span></span>|  
  
|<span data-ttu-id="bb3c3-281">术语</span><span class="sxs-lookup"><span data-stu-id="bb3c3-281">Term</span></span>|<span data-ttu-id="bb3c3-282">描述</span><span class="sxs-lookup"><span data-stu-id="bb3c3-282">Description</span></span>|  
|----------|-----------------|  
|`x`|<xref:System.Double?displayProperty=nameWithType><br /><br /> <span data-ttu-id="bb3c3-283">该点的 x 坐标。</span><span class="sxs-lookup"><span data-stu-id="bb3c3-283">The x-coordinate of the point.</span></span>|  
|`y`|<xref:System.Double?displayProperty=nameWithType><br /><br /> <span data-ttu-id="bb3c3-284">该点的 y 坐标。</span><span class="sxs-lookup"><span data-stu-id="bb3c3-284">The y-coordinate of the point.</span></span>|  
  
<a name="specialvalues"></a>   
## <a name="special-values"></a><span data-ttu-id="bb3c3-285">特殊值</span><span class="sxs-lookup"><span data-stu-id="bb3c3-285">Special Values</span></span>  
 <span data-ttu-id="bb3c3-286">除了标准数值外，还可使用以下特殊值。</span><span class="sxs-lookup"><span data-stu-id="bb3c3-286">Instead of a standard numerical value, you can also use the following special values.</span></span> <span data-ttu-id="bb3c3-287">这些数值区分大小写。</span><span class="sxs-lookup"><span data-stu-id="bb3c3-287">These values are case-sensitive.</span></span>  
  
 <span data-ttu-id="bb3c3-288">无限</span><span class="sxs-lookup"><span data-stu-id="bb3c3-288">Infinity</span></span>  
 <span data-ttu-id="bb3c3-289">表示<xref:System.Double.PositiveInfinity?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="bb3c3-289">Represents <xref:System.Double.PositiveInfinity?displayProperty=nameWithType>.</span></span>  
  
 <span data-ttu-id="bb3c3-290">-Infinity</span><span class="sxs-lookup"><span data-stu-id="bb3c3-290">-Infinity</span></span>  
 <span data-ttu-id="bb3c3-291">表示<xref:System.Double.NegativeInfinity?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="bb3c3-291">Represents <xref:System.Double.NegativeInfinity?displayProperty=nameWithType>.</span></span>  
  
 <span data-ttu-id="bb3c3-292">NaN</span><span class="sxs-lookup"><span data-stu-id="bb3c3-292">NaN</span></span>  
 <span data-ttu-id="bb3c3-293">表示<xref:System.Double.NaN?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="bb3c3-293">Represents <xref:System.Double.NaN?displayProperty=nameWithType>.</span></span>  
  
 <span data-ttu-id="bb3c3-294">也可使用科学计数法。</span><span class="sxs-lookup"><span data-stu-id="bb3c3-294">You may also use scientific notation.</span></span> <span data-ttu-id="bb3c3-295">例如，`+1.e17`是有效的值。</span><span class="sxs-lookup"><span data-stu-id="bb3c3-295">For example, `+1.e17` is a valid value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bb3c3-296">请参阅</span><span class="sxs-lookup"><span data-stu-id="bb3c3-296">See Also</span></span>  
 <xref:System.Windows.Shapes.Path>  
 <xref:System.Windows.Media.StreamGeometry>  
 <xref:System.Windows.Media.PathGeometry>  
 <xref:System.Windows.Media.PathFigureCollection>  
 [<span data-ttu-id="bb3c3-297">WPF 中的形状和基本绘图概述</span><span class="sxs-lookup"><span data-stu-id="bb3c3-297">Shapes and Basic Drawing in WPF Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/shapes-and-basic-drawing-in-wpf-overview.md)  
 [<span data-ttu-id="bb3c3-298">Geometry 概述</span><span class="sxs-lookup"><span data-stu-id="bb3c3-298">Geometry Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md)  
 [<span data-ttu-id="bb3c3-299">帮助主题</span><span class="sxs-lookup"><span data-stu-id="bb3c3-299">How-to Topics</span></span>](../../../../docs/framework/wpf/graphics-multimedia/geometries-how-to-topics.md)
