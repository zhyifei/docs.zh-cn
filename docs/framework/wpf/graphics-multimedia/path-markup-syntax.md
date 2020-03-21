---
title: 路径标记语法
ms.date: 03/30/2017
helpviewer_keywords:
- attribute usage in XAML [WPF]
- XAML [WPF], attribute usage
- graphics [WPF], PathGeometry class
- XAML [WPF], object element usage
ms.assetid: b8586241-a02d-486e-9223-e1e98e047f41
ms.openlocfilehash: adcedcea6c8d6d988021cbbccf87bd25a042fd16
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79181852"
---
# <a name="path-markup-syntax"></a><span data-ttu-id="0c5d5-102">路径标记语法</span><span class="sxs-lookup"><span data-stu-id="0c5d5-102">Path Markup Syntax</span></span>
<span data-ttu-id="0c5d5-103">路径在[WPF 概述和几何概述中讨论形状和基本图形](shapes-and-basic-drawing-in-wpf-overview.md)，但是，本主题详细介绍了可以使用 更紧凑地指定路径几何体的强大而复杂的微型语言。 [Geometry Overview](geometry-overview.md) [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0c5d5-103">Paths are discussed in [Shapes and Basic Drawing in WPF Overview](shapes-and-basic-drawing-in-wpf-overview.md) and the [Geometry Overview](geometry-overview.md), however, this topic describes in detail the powerful and complex mini-language you can use to specify path geometries more compactly using [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].</span></span>  
  
<a name="prerequisites"></a>
## <a name="prerequisites"></a><span data-ttu-id="0c5d5-104">系统必备</span><span class="sxs-lookup"><span data-stu-id="0c5d5-104">Prerequisites</span></span>  
 <span data-ttu-id="0c5d5-105">要理解本主题，应熟悉<xref:System.Windows.Media.Geometry>对象的基本特征。</span><span class="sxs-lookup"><span data-stu-id="0c5d5-105">To understand this topic, you should be familiar with the basic features of <xref:System.Windows.Media.Geometry> objects.</span></span> <span data-ttu-id="0c5d5-106">有关详细信息，请参阅[几何概述](geometry-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="0c5d5-106">For more information, see the [Geometry Overview](geometry-overview.md).</span></span>  
  
<a name="abouthisdocument"></a>
## <a name="streamgeometry-and-pathfigurecollection-mini-languages"></a><span data-ttu-id="0c5d5-107">StreamGeometry and PathFigureCollection Mini-Languages</span><span class="sxs-lookup"><span data-stu-id="0c5d5-107">StreamGeometry and PathFigureCollection Mini-Languages</span></span>  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<span data-ttu-id="0c5d5-108">提供了两个类，提供用于描述几何路径的微型语言<xref:System.Windows.Media.StreamGeometry>：<xref:System.Windows.Media.PathFigureCollection>和 。</span><span class="sxs-lookup"><span data-stu-id="0c5d5-108">provides two classes that provide mini-languages for describing geometric paths: <xref:System.Windows.Media.StreamGeometry> and <xref:System.Windows.Media.PathFigureCollection>.</span></span>  
  
- <span data-ttu-id="0c5d5-109">设置类型属性<xref:System.Windows.Media.StreamGeometry><xref:System.Windows.Media.Geometry>（如<xref:System.Windows.UIElement.Clip%2A><xref:System.Windows.UIElement><xref:System.Windows.Shapes.Path.Data%2A><xref:System.Windows.Shapes.Path>元素的属性或元素的属性）时，可以使用 mini 语言。</span><span class="sxs-lookup"><span data-stu-id="0c5d5-109">You use the <xref:System.Windows.Media.StreamGeometry> mini-language when setting a property of type <xref:System.Windows.Media.Geometry>, such as the <xref:System.Windows.UIElement.Clip%2A> property of a <xref:System.Windows.UIElement> or the <xref:System.Windows.Shapes.Path.Data%2A> property of a <xref:System.Windows.Shapes.Path> element.</span></span> <span data-ttu-id="0c5d5-110">下面的示例使用属性语法创建 。 <xref:System.Windows.Media.StreamGeometry></span><span class="sxs-lookup"><span data-stu-id="0c5d5-110">The following example uses attribute syntax to create a <xref:System.Windows.Media.StreamGeometry>.</span></span>  
  
     [!code-xaml[GeometrySample_snip_XAML#GraphicsMMStreamGeometryAttributeSyntaxInline](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample_snip_XAML/CS/MiniLanguageExample.xaml#graphicsmmstreamgeometryattributesyntaxinline)]  
  
- <span data-ttu-id="0c5d5-111">设置<xref:System.Windows.Media.PathFigureCollection><xref:System.Windows.Media.PathGeometry.Figures%2A>的属性时，可以使用 迷你语言<xref:System.Windows.Media.PathGeometry>。</span><span class="sxs-lookup"><span data-stu-id="0c5d5-111">You use the <xref:System.Windows.Media.PathFigureCollection> mini-language when setting the <xref:System.Windows.Media.PathGeometry.Figures%2A> property of a <xref:System.Windows.Media.PathGeometry>.</span></span> <span data-ttu-id="0c5d5-112">下面的示例使用属性语法为 创建 。 <xref:System.Windows.Media.PathFigureCollection> <xref:System.Windows.Media.PathGeometry></span><span class="sxs-lookup"><span data-stu-id="0c5d5-112">The following example uses a attribute syntax to create a <xref:System.Windows.Media.PathFigureCollection> for a <xref:System.Windows.Media.PathGeometry>.</span></span>  
  
     [!code-xaml[GeometrySample_snip_XAML#GraphicsMMPathFigureCollectionAttributeSyntaxInline](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample_snip_XAML/CS/MiniLanguageExample.xaml#graphicsmmpathfigurecollectionattributesyntaxinline)]  
  
 <span data-ttu-id="0c5d5-113">从前面的示例中可以看出，两种微型语言非常相似。</span><span class="sxs-lookup"><span data-stu-id="0c5d5-113">As you can see from the preceding examples, the two mini-languages are very similar.</span></span> <span data-ttu-id="0c5d5-114"><xref:System.Windows.Media.PathGeometry>在可以使用<xref:System.Windows.Media.StreamGeometry>的 和那你应该用哪一个？</span><span class="sxs-lookup"><span data-stu-id="0c5d5-114">It's always possible to use a <xref:System.Windows.Media.PathGeometry> in any situation where you could use a <xref:System.Windows.Media.StreamGeometry>; so which one should you use?</span></span> <span data-ttu-id="0c5d5-115"><xref:System.Windows.Media.StreamGeometry>创建路径后不需要修改路径时，请使用如果需要修改<xref:System.Windows.Media.PathGeometry>路径，请使用 。</span><span class="sxs-lookup"><span data-stu-id="0c5d5-115">Use a <xref:System.Windows.Media.StreamGeometry> when you don't need to modify the path after creating it; use a <xref:System.Windows.Media.PathGeometry> if you do need to modify the path.</span></span>  
  
 <span data-ttu-id="0c5d5-116">有关和<xref:System.Windows.Media.PathGeometry><xref:System.Windows.Media.StreamGeometry>对象之间的差异的详细信息，请参阅[几何概述](geometry-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="0c5d5-116">For more information about the differences between <xref:System.Windows.Media.PathGeometry> and <xref:System.Windows.Media.StreamGeometry> objects, see the [Geometry Overview](geometry-overview.md).</span></span>  
  
### <a name="a-note-about-white-space"></a><span data-ttu-id="0c5d5-117">有关空格的注意事项</span><span class="sxs-lookup"><span data-stu-id="0c5d5-117">A Note about White Space</span></span>  
 <span data-ttu-id="0c5d5-118">为简洁起见，随后的语法部分中显示一个空格，但在显示一个空格的地方，多个空格也可以接受。</span><span class="sxs-lookup"><span data-stu-id="0c5d5-118">For brevity, a single space is shown in the syntax sections that follow, but multiple spaces are also acceptable wherever a single space is shown.</span></span>  
  
 <span data-ttu-id="0c5d5-119">两个数字实际上不必用逗号或空格分隔，但只有在生成的字符串是明确的时才能这样做。</span><span class="sxs-lookup"><span data-stu-id="0c5d5-119">Two numbers don’t actually have to be separated by a comma or white space, but this can only be done when the resulting string is unambiguous.</span></span> <span data-ttu-id="0c5d5-120">例如，`2..3`实际上是两个数字："2"。</span><span class="sxs-lookup"><span data-stu-id="0c5d5-120">For instance, `2..3` is actually two numbers: "2."</span></span> <span data-ttu-id="0c5d5-121">和“.3”。</span><span class="sxs-lookup"><span data-stu-id="0c5d5-121">And ".3".</span></span> <span data-ttu-id="0c5d5-122">同样，`2-3`是"2"和"-3"。</span><span class="sxs-lookup"><span data-stu-id="0c5d5-122">Similarly, `2-3` is "2" and "-3".</span></span> <span data-ttu-id="0c5d5-123">命令前面或后面也无需加空格。</span><span class="sxs-lookup"><span data-stu-id="0c5d5-123">Spaces are not required before or after commands, either.</span></span>  
  
### <a name="syntax"></a><span data-ttu-id="0c5d5-124">语法</span><span class="sxs-lookup"><span data-stu-id="0c5d5-124">Syntax</span></span>  
 <span data-ttu-id="0c5d5-125">属性[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]使用语法<xref:System.Windows.Media.StreamGeometry>由可选<xref:System.Windows.Media.FillRule>值和一个或多个图形描述组成。</span><span class="sxs-lookup"><span data-stu-id="0c5d5-125">The [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] attribute usage syntax for a <xref:System.Windows.Media.StreamGeometry> is composed of an optional <xref:System.Windows.Media.FillRule> value and one or more figure descriptions.</span></span>  
  
|<span data-ttu-id="0c5d5-126">StreamGeometry XAML 属性用法</span><span class="sxs-lookup"><span data-stu-id="0c5d5-126">StreamGeometry XAML Attribute Usage</span></span>|  
|-----------------------------------------|  
|<span data-ttu-id="0c5d5-127">`<`*对象\*\*属性*`="` `fillRule`[ `figureDescription` `figureDescription`] |`" ... />`</span><span class="sxs-lookup"><span data-stu-id="0c5d5-127">`<` *object* *property* `="`[ `fillRule`] `figureDescription`[ `figureDescription`]\* `" ... />`</span></span>|  
  
 <span data-ttu-id="0c5d5-128">属性[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]使用语法<xref:System.Windows.Media.PathFigureCollection>由一个或多个图形描述组成。</span><span class="sxs-lookup"><span data-stu-id="0c5d5-128">The [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] attribute usage syntax for a <xref:System.Windows.Media.PathFigureCollection> is composed of one or more figure descriptions.</span></span>  
  
|<span data-ttu-id="0c5d5-129">PathFigureCollection XAML Attribute Usage</span><span class="sxs-lookup"><span data-stu-id="0c5d5-129">PathFigureCollection XAML Attribute Usage</span></span>|  
|-----------------------------------------------|  
|<span data-ttu-id="0c5d5-130">`<`*对象\*\*property*`="`属性`figureDescription` `figureDescription`[ ]`" ... />`</span><span class="sxs-lookup"><span data-stu-id="0c5d5-130">`<` *object* *property* `="` `figureDescription`[ `figureDescription`]\* `" ... />`</span></span>|  
  
|<span data-ttu-id="0c5d5-131">术语</span><span class="sxs-lookup"><span data-stu-id="0c5d5-131">Term</span></span>|<span data-ttu-id="0c5d5-132">说明</span><span class="sxs-lookup"><span data-stu-id="0c5d5-132">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="0c5d5-133">*fillRule*</span><span class="sxs-lookup"><span data-stu-id="0c5d5-133">*fillRule*</span></span>|<xref:System.Windows.Media.FillRule?displayProperty=nameWithType><br /><br /> <span data-ttu-id="0c5d5-134">指定 是否<xref:System.Windows.Media.StreamGeometry>使用<xref:System.Windows.Media.FillRule.EvenOdd>。 <xref:System.Windows.Media.FillRule.Nonzero> <xref:System.Windows.Media.PathGeometry.FillRule%2A></span><span class="sxs-lookup"><span data-stu-id="0c5d5-134">Specifies whether the <xref:System.Windows.Media.StreamGeometry> uses the <xref:System.Windows.Media.FillRule.EvenOdd> or <xref:System.Windows.Media.FillRule.Nonzero><xref:System.Windows.Media.PathGeometry.FillRule%2A>.</span></span><br /><br /> <span data-ttu-id="0c5d5-135">-   `F0`指定<xref:System.Windows.Media.FillRule.EvenOdd>填充规则。</span><span class="sxs-lookup"><span data-stu-id="0c5d5-135">-   `F0` specifies the <xref:System.Windows.Media.FillRule.EvenOdd> fill rule.</span></span><br /><span data-ttu-id="0c5d5-136">-   `F1`指定<xref:System.Windows.Media.FillRule.Nonzero>填充规则。</span><span class="sxs-lookup"><span data-stu-id="0c5d5-136">-   `F1` specifies the <xref:System.Windows.Media.FillRule.Nonzero> fill rule.</span></span><br /><br /> <span data-ttu-id="0c5d5-137">如果省略此命令，子路径将使用默认行为，即<xref:System.Windows.Media.FillRule.EvenOdd>。</span><span class="sxs-lookup"><span data-stu-id="0c5d5-137">If you omit this command, the subpath uses the default behavior, which is <xref:System.Windows.Media.FillRule.EvenOdd>.</span></span> <span data-ttu-id="0c5d5-138">如果指定该命令，须先设置命令。</span><span class="sxs-lookup"><span data-stu-id="0c5d5-138">If you specify this command, you must place it first.</span></span>|  
|<span data-ttu-id="0c5d5-139">*figureDescription*</span><span class="sxs-lookup"><span data-stu-id="0c5d5-139">*figureDescription*</span></span>|<span data-ttu-id="0c5d5-140">图形由一个移动命令，绘制命令和一个可选的关闭命令组成。</span><span class="sxs-lookup"><span data-stu-id="0c5d5-140">A figure composed of a move command, draw commands, and an optional close command.</span></span><br /><br /> <span data-ttu-id="0c5d5-141">`moveCommand` `drawCommands`  `[` `closeCommand` `]`</span><span class="sxs-lookup"><span data-stu-id="0c5d5-141">`moveCommand` `drawCommands`  `[` `closeCommand` `]`</span></span>|  
|<span data-ttu-id="0c5d5-142">*moveCommand*</span><span class="sxs-lookup"><span data-stu-id="0c5d5-142">*moveCommand*</span></span>|<span data-ttu-id="0c5d5-143">用于指定图形起点的移动命令。</span><span class="sxs-lookup"><span data-stu-id="0c5d5-143">A move command that specifies the start point of the figure.</span></span> <span data-ttu-id="0c5d5-144">请参阅[移动命令](#themovecommand)部分。</span><span class="sxs-lookup"><span data-stu-id="0c5d5-144">See the [Move Command](#themovecommand) section.</span></span>|  
|<span data-ttu-id="0c5d5-145">*drawCommands*</span><span class="sxs-lookup"><span data-stu-id="0c5d5-145">*drawCommands*</span></span>|<span data-ttu-id="0c5d5-146">用于描述图形内容的一个或多个绘图命令。</span><span class="sxs-lookup"><span data-stu-id="0c5d5-146">One or more drawing commands that describe the figure's contents.</span></span> <span data-ttu-id="0c5d5-147">请参阅["绘制命令"](#drawcommands)部分。</span><span class="sxs-lookup"><span data-stu-id="0c5d5-147">See the [Draw Commands](#drawcommands) section.</span></span>|  
|<span data-ttu-id="0c5d5-148">*closeCommand*</span><span class="sxs-lookup"><span data-stu-id="0c5d5-148">*closeCommand*</span></span>|<span data-ttu-id="0c5d5-149">用于关闭图形的可选关闭命令。</span><span class="sxs-lookup"><span data-stu-id="0c5d5-149">An optional close command that closes figure.</span></span> <span data-ttu-id="0c5d5-150">请参阅[关闭命令](#closecommand)部分。</span><span class="sxs-lookup"><span data-stu-id="0c5d5-150">See the [Close Command](#closecommand) section.</span></span>|  
  
<a name="themovecommand"></a>
## <a name="move-command"></a><span data-ttu-id="0c5d5-151">移动命令</span><span class="sxs-lookup"><span data-stu-id="0c5d5-151">Move Command</span></span>  
 <span data-ttu-id="0c5d5-152">指定新图形的起点。</span><span class="sxs-lookup"><span data-stu-id="0c5d5-152">Specifies the start point of a new figure.</span></span>  
  
|<span data-ttu-id="0c5d5-153">语法</span><span class="sxs-lookup"><span data-stu-id="0c5d5-153">Syntax</span></span>|  
|------------|  
|<span data-ttu-id="0c5d5-154">`M` *startPoint*</span><span class="sxs-lookup"><span data-stu-id="0c5d5-154">`M` *startPoint*</span></span><br /><br /> <span data-ttu-id="0c5d5-155">- 或 -</span><span class="sxs-lookup"><span data-stu-id="0c5d5-155">- or -</span></span><br /><br /> <span data-ttu-id="0c5d5-156">`m` *startPoint*</span><span class="sxs-lookup"><span data-stu-id="0c5d5-156">`m` *startPoint*</span></span>|  
  
|<span data-ttu-id="0c5d5-157">术语</span><span class="sxs-lookup"><span data-stu-id="0c5d5-157">Term</span></span>|<span data-ttu-id="0c5d5-158">说明</span><span class="sxs-lookup"><span data-stu-id="0c5d5-158">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="0c5d5-159">*startPoint*</span><span class="sxs-lookup"><span data-stu-id="0c5d5-159">*startPoint*</span></span>|<xref:System.Windows.Point?displayProperty=nameWithType><br /><br /> <span data-ttu-id="0c5d5-160">新图形的起点。</span><span class="sxs-lookup"><span data-stu-id="0c5d5-160">The start point of a new figure.</span></span>|  
  
 <span data-ttu-id="0c5d5-161">大写表示`M``startPoint`为绝对值;大写大写表示为绝对值。小写表示`m`该`startPoint`小写是与前一个点的偏移量，如果不存在，则 （0，0）。</span><span class="sxs-lookup"><span data-stu-id="0c5d5-161">An uppercase `M` indicates that `startPoint` is an absolute value; a lowercase `m` indicates that `startPoint` is an offset to the previous point, or (0,0) if none exists.</span></span> <span data-ttu-id="0c5d5-162">如果在移动命令之后列出多个点，可以绘制一条连接到这些点的直线，尽管已指定了直线命令。</span><span class="sxs-lookup"><span data-stu-id="0c5d5-162">If you list multiple points after the move command, a line is drawn to those points though you specified the line command.</span></span>  
  
<a name="drawcommands"></a>
## <a name="draw-commands"></a><span data-ttu-id="0c5d5-163">绘制命令</span><span class="sxs-lookup"><span data-stu-id="0c5d5-163">Draw Commands</span></span>  
 <span data-ttu-id="0c5d5-164">绘制命令可以由几个形状命令组成。</span><span class="sxs-lookup"><span data-stu-id="0c5d5-164">A draw command can consist of several shape commands.</span></span> <span data-ttu-id="0c5d5-165">以下形状命令可用：直线、水平线、竖线、三次贝塞尔曲线、二次贝塞尔曲线、平滑三次贝塞尔曲线、平滑二次贝塞尔曲线和椭圆弧。</span><span class="sxs-lookup"><span data-stu-id="0c5d5-165">The following shape commands are available: line, horizontal line, vertical line, cubic Bezier curve, quadratic Bezier curve, smooth cubic Bezier curve, smooth quadratic Bezier curve, and elliptical arc.</span></span>  
  
 <span data-ttu-id="0c5d5-166">可以使用大写或小写字母输入每个命令：大写字母表示绝对值，小写字母表示相对值：该线段的控制点相对于前面示例的终点。</span><span class="sxs-lookup"><span data-stu-id="0c5d5-166">You enter each command by using either an uppercase or a lowercase letter: uppercase letters denote absolute values and lowercase letters denote relative values: the control points for that segment are relative to the end point of the preceding example.</span></span> <span data-ttu-id="0c5d5-167">当按顺序输入同一类型的多个命令时，可以省略重复的命令条目;例如，可以省略重复的命令条目。例如，`L 100,200 300,400`等效于`L 100,200 L 300,400`。</span><span class="sxs-lookup"><span data-stu-id="0c5d5-167">When sequentially entering more than one command of the same type, you can omit the duplicate command entry; for example, `L 100,200 300,400` is equivalent to `L 100,200 L 300,400`.</span></span> <span data-ttu-id="0c5d5-168">下表描述了**移动**和**绘制**命令。</span><span class="sxs-lookup"><span data-stu-id="0c5d5-168">The following table describes the **move** and **draw** commands.</span></span>  
  
### <a name="line-command"></a><span data-ttu-id="0c5d5-169">直线命令</span><span class="sxs-lookup"><span data-stu-id="0c5d5-169">Line Command</span></span>  
 <span data-ttu-id="0c5d5-170">在当前点和指定的终点之间创建一条直线。</span><span class="sxs-lookup"><span data-stu-id="0c5d5-170">Creates a straight line between the current point and the specified end point.</span></span> <span data-ttu-id="0c5d5-171">`l 20 30`是`L 20,30`有效**行**命令的示例。</span><span class="sxs-lookup"><span data-stu-id="0c5d5-171">`l 20 30` and `L 20,30` are examples of valid **line** commands.</span></span>  
  
|<span data-ttu-id="0c5d5-172">语法</span><span class="sxs-lookup"><span data-stu-id="0c5d5-172">Syntax</span></span>|  
|------------|  
|<span data-ttu-id="0c5d5-173">`L`*端点*</span><span class="sxs-lookup"><span data-stu-id="0c5d5-173">`L` *endPoint*</span></span><br /><br /> <span data-ttu-id="0c5d5-174">- 或 -</span><span class="sxs-lookup"><span data-stu-id="0c5d5-174">- or -</span></span><br /><br /> <span data-ttu-id="0c5d5-175">`l`*端点*</span><span class="sxs-lookup"><span data-stu-id="0c5d5-175">`l` *endPoint*</span></span>|  
  
|<span data-ttu-id="0c5d5-176">术语</span><span class="sxs-lookup"><span data-stu-id="0c5d5-176">Term</span></span>|<span data-ttu-id="0c5d5-177">说明</span><span class="sxs-lookup"><span data-stu-id="0c5d5-177">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="0c5d5-178">*端点*</span><span class="sxs-lookup"><span data-stu-id="0c5d5-178">*endPoint*</span></span>|<xref:System.Windows.Point?displayProperty=nameWithType><br /><br /> <span data-ttu-id="0c5d5-179">线条的终点。</span><span class="sxs-lookup"><span data-stu-id="0c5d5-179">The end point of the line.</span></span>|  

<span data-ttu-id="0c5d5-180">大写表示`L``endPoint`为绝对值;大写大写表示为绝对值。小写表示`l`该`endPoint`小写是与前一个点的偏移量，如果不存在，则 （0，0）。</span><span class="sxs-lookup"><span data-stu-id="0c5d5-180">An uppercase `L` indicates that `endPoint` is an absolute value; a lowercase `l` indicates that `endPoint` is an offset to the previous point, or (0,0) if none exists.</span></span>

### <a name="horizontal-line-command"></a><span data-ttu-id="0c5d5-181">水平线命令</span><span class="sxs-lookup"><span data-stu-id="0c5d5-181">Horizontal Line Command</span></span>  
 <span data-ttu-id="0c5d5-182">在当前点和指定的 x 坐标之间创建一条水平线。</span><span class="sxs-lookup"><span data-stu-id="0c5d5-182">Creates a horizontal line between the current point and the specified x-coordinate.</span></span> <span data-ttu-id="0c5d5-183">`H 90` 是有效水平线命令的示例。</span><span class="sxs-lookup"><span data-stu-id="0c5d5-183">`H 90` is an example of a valid horizontal line command.</span></span>

|<span data-ttu-id="0c5d5-184">语法</span><span class="sxs-lookup"><span data-stu-id="0c5d5-184">Syntax</span></span>|  
|------------|  
|<span data-ttu-id="0c5d5-185">`H`  *Ⅹ*</span><span class="sxs-lookup"><span data-stu-id="0c5d5-185">`H`  *x*</span></span><br /><br /> <span data-ttu-id="0c5d5-186">- 或 -</span><span class="sxs-lookup"><span data-stu-id="0c5d5-186">- or -</span></span><br /><br /> <span data-ttu-id="0c5d5-187">`h`  *Ⅹ*</span><span class="sxs-lookup"><span data-stu-id="0c5d5-187">`h`  *x*</span></span>|  
  
|<span data-ttu-id="0c5d5-188">术语</span><span class="sxs-lookup"><span data-stu-id="0c5d5-188">Term</span></span>|<span data-ttu-id="0c5d5-189">说明</span><span class="sxs-lookup"><span data-stu-id="0c5d5-189">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="0c5d5-190">*Ⅹ*</span><span class="sxs-lookup"><span data-stu-id="0c5d5-190">*x*</span></span>|<xref:System.Double?displayProperty=nameWithType><br /><br /> <span data-ttu-id="0c5d5-191">线条终点的 x 坐标。</span><span class="sxs-lookup"><span data-stu-id="0c5d5-191">The x-coordinate of the end point of the line.</span></span>|  
  
<span data-ttu-id="0c5d5-192">大写表示`H``x`为绝对值;大写大写表示为绝对值。小写表示`h`该`x`小写是与前一个点的偏移量，如果不存在，则 （0，0）。</span><span class="sxs-lookup"><span data-stu-id="0c5d5-192">An uppercase `H` indicates that `x` is an absolute value; a lowercase `h` indicates that `x` is an offset to the previous point, or (0,0) if none exists.</span></span>
  
### <a name="vertical-line-command"></a><span data-ttu-id="0c5d5-193">竖线命令</span><span class="sxs-lookup"><span data-stu-id="0c5d5-193">Vertical Line Command</span></span>  
 <span data-ttu-id="0c5d5-194">在当前点和指定的 y 坐标之间创建一条竖线。</span><span class="sxs-lookup"><span data-stu-id="0c5d5-194">Creates a vertical line between the current point and the specified y-coordinate.</span></span> <span data-ttu-id="0c5d5-195">`v 90` 是有效竖线命令的示例。</span><span class="sxs-lookup"><span data-stu-id="0c5d5-195">`v 90` is an example of a valid vertical line command.</span></span>

|<span data-ttu-id="0c5d5-196">语法</span><span class="sxs-lookup"><span data-stu-id="0c5d5-196">Syntax</span></span>|  
|------------|  
|<span data-ttu-id="0c5d5-197">`V`  *Y*</span><span class="sxs-lookup"><span data-stu-id="0c5d5-197">`V`  *y*</span></span><br /><br /> <span data-ttu-id="0c5d5-198">- 或 -</span><span class="sxs-lookup"><span data-stu-id="0c5d5-198">- or -</span></span><br /><br /> <span data-ttu-id="0c5d5-199">`v`  *Y*</span><span class="sxs-lookup"><span data-stu-id="0c5d5-199">`v`  *y*</span></span>|  
  
|<span data-ttu-id="0c5d5-200">术语</span><span class="sxs-lookup"><span data-stu-id="0c5d5-200">Term</span></span>|<span data-ttu-id="0c5d5-201">说明</span><span class="sxs-lookup"><span data-stu-id="0c5d5-201">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="0c5d5-202">*Y*</span><span class="sxs-lookup"><span data-stu-id="0c5d5-202">*y*</span></span>|<xref:System.Double?displayProperty=nameWithType><br /><br /> <span data-ttu-id="0c5d5-203">直线终点的 y 坐标。</span><span class="sxs-lookup"><span data-stu-id="0c5d5-203">The y-coordinate of the end point of the line.</span></span>|  

<span data-ttu-id="0c5d5-204">大写表示`V``y`为绝对值;大写大写表示为绝对值。小写表示`v`该`y`小写是与前一个点的偏移量，如果不存在，则 （0，0）。</span><span class="sxs-lookup"><span data-stu-id="0c5d5-204">An uppercase `V` indicates that `y` is an absolute value; a lowercase `v` indicates that `y` is an offset to the previous point, or (0,0) if none exists.</span></span>  

### <a name="cubic-bezier-curve-command"></a><span data-ttu-id="0c5d5-205">三次贝塞尔曲线命令</span><span class="sxs-lookup"><span data-stu-id="0c5d5-205">Cubic Bezier Curve Command</span></span>  
 <span data-ttu-id="0c5d5-206">使用两个指定的控制点（1`controlPoint`和`controlPoint`2）在当前点和指定端点之间创建立方贝塞尔曲线。</span><span class="sxs-lookup"><span data-stu-id="0c5d5-206">Creates a cubic Bezier curve between the current point and the specified end point by using the two specified control points (`controlPoint`1 and `controlPoint`2).</span></span> <span data-ttu-id="0c5d5-207">`C 100,200 200,400 300,200` 是有效曲线命令的示例。</span><span class="sxs-lookup"><span data-stu-id="0c5d5-207">`C 100,200 200,400 300,200` is an example of a valid curve command.</span></span>  
  
|<span data-ttu-id="0c5d5-208">语法</span><span class="sxs-lookup"><span data-stu-id="0c5d5-208">Syntax</span></span>|  
|------------|  
|<span data-ttu-id="0c5d5-209">`C``controlPoint`1`controlPoint`2`endPoint`</span><span class="sxs-lookup"><span data-stu-id="0c5d5-209">`C` `controlPoint`1`controlPoint`2`endPoint`</span></span><br /><br /> <span data-ttu-id="0c5d5-210">- 或 -</span><span class="sxs-lookup"><span data-stu-id="0c5d5-210">- or -</span></span><br /><br /> <span data-ttu-id="0c5d5-211">`c``controlPoint`1`controlPoint`2`endPoint`</span><span class="sxs-lookup"><span data-stu-id="0c5d5-211">`c` `controlPoint`1`controlPoint`2`endPoint`</span></span>|  
  
|<span data-ttu-id="0c5d5-212">术语</span><span class="sxs-lookup"><span data-stu-id="0c5d5-212">Term</span></span>|<span data-ttu-id="0c5d5-213">说明</span><span class="sxs-lookup"><span data-stu-id="0c5d5-213">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="0c5d5-214">`controlPoint`1</span><span class="sxs-lookup"><span data-stu-id="0c5d5-214">`controlPoint`1</span></span>|<xref:System.Windows.Point?displayProperty=nameWithType><br /><br /> <span data-ttu-id="0c5d5-215">曲线的第一个控制点，它决定曲线的起始切线。</span><span class="sxs-lookup"><span data-stu-id="0c5d5-215">The first control point of the curve, which determines the starting tangent of the curve.</span></span>|  
|<span data-ttu-id="0c5d5-216">`controlPoint`2</span><span class="sxs-lookup"><span data-stu-id="0c5d5-216">`controlPoint`2</span></span>|<xref:System.Windows.Point?displayProperty=nameWithType><br /><br /> <span data-ttu-id="0c5d5-217">曲线的第二个控制点，它决定曲线的结束切线。</span><span class="sxs-lookup"><span data-stu-id="0c5d5-217">The second control point of the curve, which determines the ending tangent of the curve.</span></span>|  
|`endPoint`|<xref:System.Windows.Point?displayProperty=nameWithType><br /><br /> <span data-ttu-id="0c5d5-218">绘制曲线将通过的点。</span><span class="sxs-lookup"><span data-stu-id="0c5d5-218">The point to which the curve is drawn.</span></span>|  
  
### <a name="quadratic-bezier-curve-command"></a><span data-ttu-id="0c5d5-219">二次贝塞尔曲线命令</span><span class="sxs-lookup"><span data-stu-id="0c5d5-219">Quadratic Bezier Curve Command</span></span>  
 <span data-ttu-id="0c5d5-220">使用指定的控制点 （）`controlPoint`在当前点和指定端点之间创建二次贝塞尔曲线。</span><span class="sxs-lookup"><span data-stu-id="0c5d5-220">Creates a quadratic Bezier curve between the current point and the specified end point by using the specified control point (`controlPoint`).</span></span> <span data-ttu-id="0c5d5-221">`q 100,200 300,200` 为有效二次贝塞尔曲线命令的示例。</span><span class="sxs-lookup"><span data-stu-id="0c5d5-221">`q 100,200 300,200` is an example of a valid quadratic Bezier curve command.</span></span>  
  
|<span data-ttu-id="0c5d5-222">语法</span><span class="sxs-lookup"><span data-stu-id="0c5d5-222">Syntax</span></span>|  
|------------|  
|<span data-ttu-id="0c5d5-223">`Q` `controlPoint` `endPoint`</span><span class="sxs-lookup"><span data-stu-id="0c5d5-223">`Q` `controlPoint` `endPoint`</span></span><br /><br /> <span data-ttu-id="0c5d5-224">- 或 -</span><span class="sxs-lookup"><span data-stu-id="0c5d5-224">- or -</span></span><br /><br /> <span data-ttu-id="0c5d5-225">`q` `controlPoint` `endPoint`</span><span class="sxs-lookup"><span data-stu-id="0c5d5-225">`q` `controlPoint` `endPoint`</span></span>|  
  
|<span data-ttu-id="0c5d5-226">术语</span><span class="sxs-lookup"><span data-stu-id="0c5d5-226">Term</span></span>|<span data-ttu-id="0c5d5-227">说明</span><span class="sxs-lookup"><span data-stu-id="0c5d5-227">Description</span></span>|  
|----------|-----------------|  
|`controlPoint`|<xref:System.Windows.Point?displayProperty=nameWithType><br /><br /> <span data-ttu-id="0c5d5-228">曲线的控制点，它决定曲线的开始和结束切线。</span><span class="sxs-lookup"><span data-stu-id="0c5d5-228">The control point of the curve, which determines the starting and ending tangents of the curve.</span></span>|  
|`endPoint`|<xref:System.Windows.Point?displayProperty=nameWithType><br /><br /> <span data-ttu-id="0c5d5-229">绘制曲线将通过的点。</span><span class="sxs-lookup"><span data-stu-id="0c5d5-229">The point to which the curve is drawn.</span></span>|  
  
### <a name="smooth-cubic-bezier-curve-command"></a><span data-ttu-id="0c5d5-230">平滑三次贝塞尔曲线命令</span><span class="sxs-lookup"><span data-stu-id="0c5d5-230">Smooth cubic Bezier curve Command</span></span>  
 <span data-ttu-id="0c5d5-231">在当前点和指定的终点之间创建三次贝塞尔曲线。</span><span class="sxs-lookup"><span data-stu-id="0c5d5-231">Creates a cubic Bezier curve between the current point and the specified end point.</span></span> <span data-ttu-id="0c5d5-232">假设第一控制点为相对当前点前一命令的第二控制点的反射。</span><span class="sxs-lookup"><span data-stu-id="0c5d5-232">The first control point is assumed to be the reflection of the second control point of the previous command relative to the current point.</span></span> <span data-ttu-id="0c5d5-233">如果没有前一命令或如果前一命令不是三次贝塞尔曲线命令或平滑三次贝塞尔曲线命令，则假设第一个控制点与当前点重合。</span><span class="sxs-lookup"><span data-stu-id="0c5d5-233">If there is no previous command or if the previous command was not a cubic Bezier curve command or a smooth cubic Bezier curve command, assume the first control point is coincident with the current point.</span></span> <span data-ttu-id="0c5d5-234">第二个控制点（曲线末端的控制点）由`controlPoint`2 指定。</span><span class="sxs-lookup"><span data-stu-id="0c5d5-234">The second control point, the control point for the end of the curve, is specified by `controlPoint`2.</span></span> <span data-ttu-id="0c5d5-235">例如，`S 100,200 200,300`是一个有效的平滑立方贝塞尔曲线命令。</span><span class="sxs-lookup"><span data-stu-id="0c5d5-235">For example, `S 100,200 200,300` is a valid smooth cubic Bezier curve command.</span></span>  
  
|<span data-ttu-id="0c5d5-236">语法</span><span class="sxs-lookup"><span data-stu-id="0c5d5-236">Syntax</span></span>|  
|------------|  
|<span data-ttu-id="0c5d5-237">`S` `controlPoint`2`endPoint`</span><span class="sxs-lookup"><span data-stu-id="0c5d5-237">`S` `controlPoint`2`endPoint`</span></span><br /><br /> <span data-ttu-id="0c5d5-238">- 或 -</span><span class="sxs-lookup"><span data-stu-id="0c5d5-238">- or -</span></span><br /><br /> <span data-ttu-id="0c5d5-239">`s` `controlPoint`2`endPoint`</span><span class="sxs-lookup"><span data-stu-id="0c5d5-239">`s` `controlPoint`2`endPoint`</span></span>|  
  
|<span data-ttu-id="0c5d5-240">术语</span><span class="sxs-lookup"><span data-stu-id="0c5d5-240">Term</span></span>|<span data-ttu-id="0c5d5-241">说明</span><span class="sxs-lookup"><span data-stu-id="0c5d5-241">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="0c5d5-242">`controlPoint`2</span><span class="sxs-lookup"><span data-stu-id="0c5d5-242">`controlPoint`2</span></span>|<xref:System.Windows.Point?displayProperty=nameWithType><br /><br /> <span data-ttu-id="0c5d5-243">曲线的控制点，它决定曲线的结束切线。</span><span class="sxs-lookup"><span data-stu-id="0c5d5-243">The control point of the curve, which determines the ending tangent of the curve.</span></span>|  
|`endPoint`|<xref:System.Windows.Point?displayProperty=nameWithType><br /><br /> <span data-ttu-id="0c5d5-244">绘制曲线将通过的点。</span><span class="sxs-lookup"><span data-stu-id="0c5d5-244">The point to which the curve is drawn.</span></span>|  
  
### <a name="smooth-quadratic-bezier-curve-command"></a><span data-ttu-id="0c5d5-245">平滑二次贝塞尔曲线命令</span><span class="sxs-lookup"><span data-stu-id="0c5d5-245">Smooth quadratic Bezier curve Command</span></span>  
 <span data-ttu-id="0c5d5-246">在当前点和指定的终点之间创建二次贝塞尔曲线。</span><span class="sxs-lookup"><span data-stu-id="0c5d5-246">Creates a quadratic Bezier curve between the current point and the specified end point.</span></span> <span data-ttu-id="0c5d5-247">假设控制点为相对于当前点前一命令的控制点的反射。</span><span class="sxs-lookup"><span data-stu-id="0c5d5-247">The control point is assumed to be the reflection of the control point of the previous command relative to the current point.</span></span> <span data-ttu-id="0c5d5-248">如果没有前一命令或如果前一命令不是二次贝塞尔曲线命令或平滑二次贝塞尔曲线命令，则控制点与当前点重合。</span><span class="sxs-lookup"><span data-stu-id="0c5d5-248">If there is no previous command or if the previous command was not a quadratic Bezier curve command or a smooth quadratic Bezier curve command, the control point is coincident with the current point.</span></span>  
  
|<span data-ttu-id="0c5d5-249">语法</span><span class="sxs-lookup"><span data-stu-id="0c5d5-249">Syntax</span></span>|  
|------------|  
|<span data-ttu-id="0c5d5-250">`T` `controlPoint` `endPoint`</span><span class="sxs-lookup"><span data-stu-id="0c5d5-250">`T` `controlPoint` `endPoint`</span></span><br /><br /> <span data-ttu-id="0c5d5-251">- 或 -</span><span class="sxs-lookup"><span data-stu-id="0c5d5-251">- or -</span></span><br /><br /> <span data-ttu-id="0c5d5-252">`t` `controlPoint` `endPoint`</span><span class="sxs-lookup"><span data-stu-id="0c5d5-252">`t` `controlPoint` `endPoint`</span></span>|  
  
|<span data-ttu-id="0c5d5-253">术语</span><span class="sxs-lookup"><span data-stu-id="0c5d5-253">Term</span></span>|<span data-ttu-id="0c5d5-254">说明</span><span class="sxs-lookup"><span data-stu-id="0c5d5-254">Description</span></span>|  
|----------|-----------------|  
|`controlPoint`|<xref:System.Windows.Point?displayProperty=nameWithType><br /><br /> <span data-ttu-id="0c5d5-255">曲线的控制点，决定曲线的起点和曲线的切线。</span><span class="sxs-lookup"><span data-stu-id="0c5d5-255">The control point of the curve, which determines the starting and tangent of the curve.</span></span>|  
|`endPoint`|<xref:System.Windows.Point?displayProperty=nameWithType><br /><br /> <span data-ttu-id="0c5d5-256">绘制曲线将通过的点。</span><span class="sxs-lookup"><span data-stu-id="0c5d5-256">The point to which the curve is drawn.</span></span>|  
  
### <a name="elliptical-arc-command"></a><span data-ttu-id="0c5d5-257">椭圆弧命令</span><span class="sxs-lookup"><span data-stu-id="0c5d5-257">Elliptical Arc Command</span></span>  
 <span data-ttu-id="0c5d5-258">在当前点和指定的终点之间创建一个椭圆弧。</span><span class="sxs-lookup"><span data-stu-id="0c5d5-258">Creates an elliptical arc between the current point and the specified end point.</span></span>  
  
|<span data-ttu-id="0c5d5-259">语法</span><span class="sxs-lookup"><span data-stu-id="0c5d5-259">Syntax</span></span>|  
|------------|  
|<span data-ttu-id="0c5d5-260">`A` `size` `rotationAngle` `isLargeArcFlag` `sweepDirectionFlag` `endPoint`</span><span class="sxs-lookup"><span data-stu-id="0c5d5-260">`A` `size` `rotationAngle` `isLargeArcFlag` `sweepDirectionFlag` `endPoint`</span></span><br /><br /> <span data-ttu-id="0c5d5-261">- 或 -</span><span class="sxs-lookup"><span data-stu-id="0c5d5-261">- or -</span></span><br /><br /> <span data-ttu-id="0c5d5-262">`a` `size` `rotationAngle` `isLargeArcFlag` `sweepDirectionFlag` `endPoint`</span><span class="sxs-lookup"><span data-stu-id="0c5d5-262">`a` `size` `rotationAngle` `isLargeArcFlag` `sweepDirectionFlag` `endPoint`</span></span>|  
  
|<span data-ttu-id="0c5d5-263">术语</span><span class="sxs-lookup"><span data-stu-id="0c5d5-263">Term</span></span>|<span data-ttu-id="0c5d5-264">说明</span><span class="sxs-lookup"><span data-stu-id="0c5d5-264">Description</span></span>|  
|----------|-----------------|  
|`size`|<xref:System.Windows.Size?displayProperty=nameWithType><br /><br /> <span data-ttu-id="0c5d5-265">圆弧的 x 轴和 y 轴半径。</span><span class="sxs-lookup"><span data-stu-id="0c5d5-265">The x- and y-radius of the arc.</span></span>|  
|`rotationAngle`|<xref:System.Double?displayProperty=nameWithType><br /><br /> <span data-ttu-id="0c5d5-266">椭圆的旋转，以度为单位。</span><span class="sxs-lookup"><span data-stu-id="0c5d5-266">The rotation of the ellipse, in degrees.</span></span>|  
|`isLargeArcFlag`|<span data-ttu-id="0c5d5-267">如果圆弧角度应为 180 度或更大，请设置为 1，否则设置为 0。</span><span class="sxs-lookup"><span data-stu-id="0c5d5-267">Set to 1 if the angle of the arc should be 180 degrees or greater; otherwise, set to 0.</span></span>|  
|`sweepDirectionFlag`|<span data-ttu-id="0c5d5-268">如果以正角方向绘制圆弧，请设置为 1；否则设置为 0。</span><span class="sxs-lookup"><span data-stu-id="0c5d5-268">Set to 1 if the arc is drawn in a positive-angle direction; otherwise, set to 0.</span></span>|  
|`endPoint`|<xref:System.Windows.Point?displayProperty=nameWithType><br /><br /> <span data-ttu-id="0c5d5-269">绘制弧将通过的点。</span><span class="sxs-lookup"><span data-stu-id="0c5d5-269">The point to which the arc is drawn.</span></span>|  
  
<a name="closecommand"></a>
## <a name="the-close-command"></a><span data-ttu-id="0c5d5-270">关闭命令</span><span class="sxs-lookup"><span data-stu-id="0c5d5-270">The Close Command</span></span>  
 <span data-ttu-id="0c5d5-271">结束当前图形，并创建一条将当前点连接到图形起点的直线。</span><span class="sxs-lookup"><span data-stu-id="0c5d5-271">Ends the current figure and creates a line that connects the current point to the starting point of the figure.</span></span> <span data-ttu-id="0c5d5-272">此命令可以在图形最后一段与第一段之间创建一条连接线（角）。</span><span class="sxs-lookup"><span data-stu-id="0c5d5-272">This command creates a line-join (corner) between the last segment and the first segment of the figure.</span></span>  
  
|<span data-ttu-id="0c5d5-273">语法</span><span class="sxs-lookup"><span data-stu-id="0c5d5-273">Syntax</span></span>|  
|------------|  
|`Z`<br /><br /> <span data-ttu-id="0c5d5-274">- 或 -</span><span class="sxs-lookup"><span data-stu-id="0c5d5-274">- or -</span></span><br /><br /> `z`|  

<a name="pointsyntax"></a>
## <a name="point-syntax"></a><span data-ttu-id="0c5d5-275">点语法</span><span class="sxs-lookup"><span data-stu-id="0c5d5-275">Point Syntax</span></span>  
 <span data-ttu-id="0c5d5-276">描述 （0，0） 是左上角的点的 x 和 y 坐标。</span><span class="sxs-lookup"><span data-stu-id="0c5d5-276">Describes the x- and y-coordinates of a point where (0,0) is the top left corner.</span></span>
  
|<span data-ttu-id="0c5d5-277">语法</span><span class="sxs-lookup"><span data-stu-id="0c5d5-277">Syntax</span></span>|  
|------------|  
|<span data-ttu-id="0c5d5-278">`x` `,` `y`</span><span class="sxs-lookup"><span data-stu-id="0c5d5-278">`x` `,` `y`</span></span><br /><br /> <span data-ttu-id="0c5d5-279">- 或 -</span><span class="sxs-lookup"><span data-stu-id="0c5d5-279">- or -</span></span><br /><br /> <span data-ttu-id="0c5d5-280">`x` `y`</span><span class="sxs-lookup"><span data-stu-id="0c5d5-280">`x` `y`</span></span>|  
  
|<span data-ttu-id="0c5d5-281">术语</span><span class="sxs-lookup"><span data-stu-id="0c5d5-281">Term</span></span>|<span data-ttu-id="0c5d5-282">说明</span><span class="sxs-lookup"><span data-stu-id="0c5d5-282">Description</span></span>|  
|----------|-----------------|  
|`x`|<xref:System.Double?displayProperty=nameWithType><br /><br /> <span data-ttu-id="0c5d5-283">该点的 x 坐标。</span><span class="sxs-lookup"><span data-stu-id="0c5d5-283">The x-coordinate of the point.</span></span>|  
|`y`|<xref:System.Double?displayProperty=nameWithType><br /><br /> <span data-ttu-id="0c5d5-284">该点的 y 坐标。</span><span class="sxs-lookup"><span data-stu-id="0c5d5-284">The y-coordinate of the point.</span></span>|  
  
<a name="specialvalues"></a>
## <a name="special-values"></a><span data-ttu-id="0c5d5-285">特殊值</span><span class="sxs-lookup"><span data-stu-id="0c5d5-285">Special Values</span></span>  
 <span data-ttu-id="0c5d5-286">除了标准数值外，还可使用以下特殊值。</span><span class="sxs-lookup"><span data-stu-id="0c5d5-286">Instead of a standard numerical value, you can also use the following special values.</span></span> <span data-ttu-id="0c5d5-287">这些数值区分大小写。</span><span class="sxs-lookup"><span data-stu-id="0c5d5-287">These values are case-sensitive.</span></span>  
  
 <span data-ttu-id="0c5d5-288">Infinity</span><span class="sxs-lookup"><span data-stu-id="0c5d5-288">Infinity</span></span>  
 <span data-ttu-id="0c5d5-289">表示<xref:System.Double.PositiveInfinity?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="0c5d5-289">Represents <xref:System.Double.PositiveInfinity?displayProperty=nameWithType>.</span></span>  
  
 <span data-ttu-id="0c5d5-290">-Infinity</span><span class="sxs-lookup"><span data-stu-id="0c5d5-290">-Infinity</span></span>  
 <span data-ttu-id="0c5d5-291">表示<xref:System.Double.NegativeInfinity?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="0c5d5-291">Represents <xref:System.Double.NegativeInfinity?displayProperty=nameWithType>.</span></span>  
  
 <span data-ttu-id="0c5d5-292">NaN</span><span class="sxs-lookup"><span data-stu-id="0c5d5-292">NaN</span></span>  
 <span data-ttu-id="0c5d5-293">表示<xref:System.Double.NaN?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="0c5d5-293">Represents <xref:System.Double.NaN?displayProperty=nameWithType>.</span></span>  
  
 <span data-ttu-id="0c5d5-294">也可使用科学计数法。</span><span class="sxs-lookup"><span data-stu-id="0c5d5-294">You may also use scientific notation.</span></span> <span data-ttu-id="0c5d5-295">例如，`+1.e17` 是有效值。</span><span class="sxs-lookup"><span data-stu-id="0c5d5-295">For example, `+1.e17` is a valid value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0c5d5-296">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0c5d5-296">See also</span></span>

- <xref:System.Windows.Shapes.Path>
- <xref:System.Windows.Media.StreamGeometry>
- <xref:System.Windows.Media.PathGeometry>
- <xref:System.Windows.Media.PathFigureCollection>
- [<span data-ttu-id="0c5d5-297">WPF 中的形状和基本绘图概述</span><span class="sxs-lookup"><span data-stu-id="0c5d5-297">Shapes and Basic Drawing in WPF Overview</span></span>](shapes-and-basic-drawing-in-wpf-overview.md)
- [<span data-ttu-id="0c5d5-298">Geometry 概述</span><span class="sxs-lookup"><span data-stu-id="0c5d5-298">Geometry Overview</span></span>](geometry-overview.md)
- [<span data-ttu-id="0c5d5-299">如何使用主题</span><span class="sxs-lookup"><span data-stu-id="0c5d5-299">How-to Topics</span></span>](geometries-how-to-topics.md)
