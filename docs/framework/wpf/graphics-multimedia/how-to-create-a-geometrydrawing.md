---
title: 如何：创建 GeometryDrawing
ms.date: 03/30/2017
helpviewer_keywords:
- shapes [WPF], renderable
- renderable shapes [WPF]
- graphics [WPF], GeometryDrawing class
- classes [WPF], GeometryDrawing
ms.assetid: 11d3c096-91ba-4d41-9bba-aeac0db70f97
ms.openlocfilehash: f5cdcfdb68ad8030bcbd6c689f45a8baddd000e1
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61904951"
---
# <a name="how-to-create-a-geometrydrawing"></a><span data-ttu-id="d8ac8-102">如何：创建 GeometryDrawing</span><span class="sxs-lookup"><span data-stu-id="d8ac8-102">How to: Create a GeometryDrawing</span></span>
<span data-ttu-id="d8ac8-103">此示例演示如何创建和显示<xref:System.Windows.Media.GeometryDrawing>。</span><span class="sxs-lookup"><span data-stu-id="d8ac8-103">This example shows how to create and display a <xref:System.Windows.Media.GeometryDrawing>.</span></span> <span data-ttu-id="d8ac8-104">一个<xref:System.Windows.Media.GeometryDrawing>使您能够通过关联来创建具有填充和边框的形状<xref:System.Windows.Media.Pen>和一个<xref:System.Windows.Media.Brush>与<xref:System.Windows.Media.Geometry>。</span><span class="sxs-lookup"><span data-stu-id="d8ac8-104">A <xref:System.Windows.Media.GeometryDrawing> enables you to create shape with a fill and an outline by associating a <xref:System.Windows.Media.Pen> and a <xref:System.Windows.Media.Brush> with a <xref:System.Windows.Media.Geometry>.</span></span> <span data-ttu-id="d8ac8-105"><xref:System.Windows.Media.GeometryDrawing.Geometry%2A>描述形状的结构<xref:System.Windows.Media.GeometryDrawing.Brush%2A>描述形状的填充和<xref:System.Windows.Media.GeometryDrawing.Pen%2A>描述形状的轮廓。</span><span class="sxs-lookup"><span data-stu-id="d8ac8-105">The <xref:System.Windows.Media.GeometryDrawing.Geometry%2A> describes the shape's structure, the <xref:System.Windows.Media.GeometryDrawing.Brush%2A> describes the shape's fill, and the <xref:System.Windows.Media.GeometryDrawing.Pen%2A> describes the shape's outline.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d8ac8-106">示例</span><span class="sxs-lookup"><span data-stu-id="d8ac8-106">Example</span></span>  
 <span data-ttu-id="d8ac8-107">下面的示例使用<xref:System.Windows.Media.GeometryDrawing>来呈现形状。</span><span class="sxs-lookup"><span data-stu-id="d8ac8-107">The following example uses a <xref:System.Windows.Media.GeometryDrawing> to render a shape.</span></span> <span data-ttu-id="d8ac8-108">由描述形状<xref:System.Windows.Media.GeometryGroup>和两个<xref:System.Windows.Media.EllipseGeometry>对象。</span><span class="sxs-lookup"><span data-stu-id="d8ac8-108">The shape is described by a <xref:System.Windows.Media.GeometryGroup> and two <xref:System.Windows.Media.EllipseGeometry> objects.</span></span> <span data-ttu-id="d8ac8-109">用来绘制形状内部<xref:System.Windows.Media.LinearGradientBrush>并使用绘制其轮廓<xref:System.Windows.Media.Brushes.Black%2A> <xref:System.Windows.Media.Pen>。</span><span class="sxs-lookup"><span data-stu-id="d8ac8-109">The shape's interior is painted with a <xref:System.Windows.Media.LinearGradientBrush> and its outline is drawn with a <xref:System.Windows.Media.Brushes.Black%2A> <xref:System.Windows.Media.Pen>.</span></span> <span data-ttu-id="d8ac8-110"><xref:System.Windows.Media.GeometryDrawing>使用显示<xref:System.Windows.Media.ImageDrawing>和<xref:System.Windows.Controls.Image>元素。</span><span class="sxs-lookup"><span data-stu-id="d8ac8-110">The <xref:System.Windows.Media.GeometryDrawing> is displayed using an <xref:System.Windows.Media.ImageDrawing> and an <xref:System.Windows.Controls.Image> element.</span></span>  
  
 [!code-csharp[DrawingMiscSnippets_snip#GeometryDrawingExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/GeometryDrawingExample.cs#geometrydrawingexamplewholepage)]
 [!code-xaml[DrawingMiscSnippets_snip#GeometryDrawingExampleWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/GeometryDrawingExample.xaml#geometrydrawingexamplewholepage)]  
  
 <span data-ttu-id="d8ac8-111">下图显示了生成<xref:System.Windows.Media.GeometryDrawing>。</span><span class="sxs-lookup"><span data-stu-id="d8ac8-111">The following illustration shows the resulting <xref:System.Windows.Media.GeometryDrawing>.</span></span>  
  
 <span data-ttu-id="d8ac8-112">![两个椭圆的 GeometryDrawing](./media/graphicsmm-geodraw.jpg "graphicsmm_geodraw")</span><span class="sxs-lookup"><span data-stu-id="d8ac8-112">![A GeometryDrawing of two ellipses](./media/graphicsmm-geodraw.jpg "graphicsmm_geodraw")</span></span>  
  
 <span data-ttu-id="d8ac8-113">若要创建更复杂的图形，可以将多个图形对象组合到一个单个复合图形使用<xref:System.Windows.Media.DrawingGroup>。</span><span class="sxs-lookup"><span data-stu-id="d8ac8-113">To create more complex drawings, you can combine multiple drawing objects into a single composite drawing using a <xref:System.Windows.Media.DrawingGroup>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d8ac8-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="d8ac8-114">See also</span></span>

- <xref:System.Windows.Media.DrawingGroup>
- [<span data-ttu-id="d8ac8-115">Drawing 对象概述</span><span class="sxs-lookup"><span data-stu-id="d8ac8-115">Drawing Objects Overview</span></span>](drawing-objects-overview.md)
- [<span data-ttu-id="d8ac8-116">Geometry 概述</span><span class="sxs-lookup"><span data-stu-id="d8ac8-116">Geometry Overview</span></span>](geometry-overview.md)
- [<span data-ttu-id="d8ac8-117">创建复合绘图</span><span class="sxs-lookup"><span data-stu-id="d8ac8-117">Create a Composite Drawing</span></span>](how-to-create-a-composite-drawing.md)
