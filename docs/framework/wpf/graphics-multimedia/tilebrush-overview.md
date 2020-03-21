---
title: TileBrush 概述
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- TileBrush [WPF]
- brushes [WPF], TileBrush
ms.assetid: aa4a7b7e-d09d-44c2-8d61-310c50e08d68
ms.openlocfilehash: 99bcc8695206030a381d71df2dda495867d3e9c7
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79187095"
---
# <a name="tilebrush-overview"></a>TileBrush 概述
<xref:System.Windows.Media.TileBrush>对象可对图像或<xref:System.Windows.Media.Drawing>的<xref:System.Windows.Media.Visual>区域如何绘制具有很大的控制。 本主题介绍<xref:System.Windows.Media.TileBrush>如何使用功能来控制<xref:System.Windows.Media.ImageBrush>如何<xref:System.Windows.Media.DrawingBrush><xref:System.Windows.Media.VisualBrush>绘制 区域。  

<a name="prerequisite"></a>
## <a name="prerequisites"></a>系统必备  
 要理解本主题，了解如何使用<xref:System.Windows.Media.ImageBrush>、<xref:System.Windows.Media.DrawingBrush>或<xref:System.Windows.Media.VisualBrush>类的基本功能很有帮助。 有关这些类型的介绍，请参阅[具有图像、绘图和视觉功能的绘画](painting-with-images-drawings-and-visuals.md)。  
  
<a name="tilebrush"></a>
## <a name="painting-an-area-with-tiles"></a>使用图块绘制区域  
 <xref:System.Windows.Media.ImageBrush><xref:System.Windows.Media.DrawingBrush>是<xref:System.Windows.Media.VisualBrush>对象的类型<xref:System.Windows.Media.TileBrush>。 使用平铺画笔，可以非常自如地控制如何使用图像、绘图或视觉对象来绘制区域。 例如，不使用单个拉伸图像绘制区域，而是使用创建图案的一系列平铺图像绘制区域。  
  
 使用平铺画笔绘制区域涉及三个组成部分：内容、基本图块和输出区域。  
  
 ![TileBrush 组成部分](./media/wcpsdk-mmgraphics-defaultcontentprojection2.png "wcpsdk_mmgraphics_defaultcontentprojection2")  
具有单个图块的 TileBrush 的组成部分  
  
 ![已平铺的 TileBrush 组件](./media/graphicsmm-tiledprojection.png "graphicsmm_tiledprojection")  
已指定图块的 TileMode 的 TileBrush 的组成部分  
  
 输出区域是要绘制<xref:System.Windows.Shapes.Shape.Fill%2A>的区域，如 的<xref:System.Windows.Shapes.Ellipse>或<xref:System.Windows.Controls.Control.Background%2A><xref:System.Windows.Controls.Button>。 接下来的部分将介绍 的其他两个<xref:System.Windows.Media.TileBrush>组件。  
  
<a name="brushcontent"></a>
## <a name="brush-content"></a>画笔内容  
 有三种<xref:System.Windows.Media.TileBrush>不同类型的和每种涂料具有不同类型的内容。  
  
- 如果画笔为<xref:System.Windows.Media.ImageBrush>，则此内容是图像 属性<xref:System.Windows.Media.ImageBrush.ImageSource%2A>指定 的内容。 <xref:System.Windows.Media.ImageBrush>  
  
- 如果画笔为 ，<xref:System.Windows.Media.DrawingBrush>则此内容为绘图。 属性<xref:System.Windows.Media.DrawingBrush.Drawing%2A>指定 的内容<xref:System.Windows.Media.DrawingBrush>。  
  
- 如果画笔是 ，<xref:System.Windows.Media.VisualBrush>则此内容是可视内容。 属性<xref:System.Windows.Media.VisualBrush.Visual%2A>指定 的内容<xref:System.Windows.Media.VisualBrush>。  
  
 可以使用<xref:System.Windows.Media.TileBrush><xref:System.Windows.Media.TileBrush.Viewbox%2A>属性指定内容的位置和尺寸，尽管通常将<xref:System.Windows.Media.TileBrush.Viewbox%2A>集保留为其默认值。 默认情况下，<xref:System.Windows.Media.TileBrush.Viewbox%2A>配置为完全包含画笔的内容。 有关配置 的详细信息，<xref:System.Windows.Controls.Viewbox>请参阅<xref:System.Windows.Controls.Viewbox>属性页。  
  
<a name="thebasetile"></a>
## <a name="the-base-tile"></a>基本图块  
 将<xref:System.Windows.Media.TileBrush>其内容投射到基磁贴上。 属性<xref:System.Windows.Media.TileBrush.Stretch%2A>控制如何<xref:System.Windows.Media.TileBrush>拉伸内容以填充基本磁贴。 属性<xref:System.Windows.Media.TileBrush.Stretch%2A>接受以下值，由<xref:System.Windows.Media.Stretch>枚举定义：  
  
- <xref:System.Windows.Media.Stretch.None>：画笔的内容不会拉伸以填充磁贴。  
  
- <xref:System.Windows.Media.Stretch.Fill>： 画笔的内容将缩放以适合磁贴。 由于内容的高度和宽度独立进行缩放，因此内容的原始纵横比可能不会保留。 也就是说，为了完全填充输出图块，画笔的内容可能会弯曲。  
  
- <xref:System.Windows.Media.Stretch.Uniform>： 画笔的内容被缩放，以便完全适合磁贴。 内容的纵横比会保留。  
  
- <xref:System.Windows.Media.Stretch.UniformToFill>：画笔的内容被缩放，以便它完全填充输出区域，同时保持内容的原始纵横比。  
  
 下图说明了不同的<xref:System.Windows.Media.TileBrush.Stretch%2A>设置。  
  
 ![不同的 TileBrush 拉伸设置](./media/img-mmgraphics-stretchenum.jpg "img_mmgraphics_stretchenum")  
  
 在下面的示例中，将设置 的内容<xref:System.Windows.Media.ImageBrush>，以便它不拉伸以填充输出区域。  
  
 [!code-xaml[BrushOverviewExamples_snip#GraphicsMMNoStretchExample](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushOverviewExamples_snip/XAML/StretchExample.xaml#graphicsmmnostretchexample)]  
  
 [!code-csharp[BrushOverviewExamples_procedural_snip#GraphicsMMNoStretchExample](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushOverviewExamples_procedural_snip/CSharp/StretchExample.cs#graphicsmmnostretchexample)]
 [!code-vb[BrushOverviewExamples_procedural_snip#GraphicsMMNoStretchExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushOverviewExamples_procedural_snip/visualbasic/stretchexample.vb#graphicsmmnostretchexample)]  
  
 默认情况下，生成<xref:System.Windows.Media.TileBrush>单个磁贴（基本磁贴）并拉伸该磁贴以完全填充输出区域。 您可以通过设置<xref:System.Windows.Media.TileBrush.Viewport%2A>和 属性来更改基本磁贴的大小和<xref:System.Windows.Media.TileBrush.ViewportUnits%2A>位置。  
  
<a name="basetilesize"></a>
### <a name="base-tile-size"></a>基本图块大小  
 属性<xref:System.Windows.Media.TileBrush.Viewport%2A>确定基本磁贴的大小和位置，<xref:System.Windows.Media.TileBrush.ViewportUnits%2A>该属性确定是使用绝对坐标还是相对坐标<xref:System.Windows.Media.TileBrush.Viewport%2A>指定 。 如果坐标是相对坐标，则它们相对于输出区域的大小。 点 (0,0) 表示输出区域的左上角，(1,1) 表示输出区域的右下角。 要指定<xref:System.Windows.Media.TileBrush.Viewport%2A>属性使用绝对坐标，请将<xref:System.Windows.Media.TileBrush.ViewportUnits%2A>属性设置为<xref:System.Windows.Media.BrushMappingMode.Absolute>。  
  
 下图显示了<xref:System.Windows.Media.TileBrush>相对与绝对<xref:System.Windows.Media.TileBrush.ViewportUnits%2A>之间的输出差异。 请注意每个图都显示了一种图块图案；下一节介绍如何指定图块图案。  
  
 ![绝对和相对视区单位](./media/absolute-and-relative-viewports.png "absolute_and_relative_viewports")  
  
 在下面的示例中，使用一幅图像来创建一个宽度和高度均为 50% 的图块。 基本图块位于输出区域的 (0,0) 处。  
  
 [!code-xaml[BrushOverviewExamples_snip#GraphicsMMRelativeViewportUnitsExample1](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushOverviewExamples_snip/XAML/TileSizeExample.xaml#graphicsmmrelativeviewportunitsexample1)]  
  
 [!code-csharp[BrushOverviewExamples_procedural_snip#GraphicsMMRelativeViewportUnitsExample1](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushOverviewExamples_procedural_snip/CSharp/TileSizeExample.cs#graphicsmmrelativeviewportunitsexample1)]
 [!code-vb[BrushOverviewExamples_procedural_snip#GraphicsMMRelativeViewportUnitsExample1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushOverviewExamples_procedural_snip/visualbasic/tilesizeexample.vb#graphicsmmrelativeviewportunitsexample1)]  
  
 下一个示例将 a<xref:System.Windows.Media.ImageBrush>的切片设置为 25 x 25 个独立于设备的像素。 由于<xref:System.Windows.Media.TileBrush.ViewportUnits%2A>是绝对的，因此<xref:System.Windows.Media.ImageBrush>无论所绘制的区域大小如何，切片始终为 25 x 25 像素。  
  
 [!code-xaml[BrushOverviewExamples_snip#GraphicsMMAbsoluteViewportUnitsExample1](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushOverviewExamples_snip/XAML/TileSizeExample.xaml#graphicsmmabsoluteviewportunitsexample1)]  
  
 [!code-csharp[BrushOverviewExamples_procedural_snip#GraphicsMMAbsoluteViewportUnitsExample1](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushOverviewExamples_procedural_snip/CSharp/TileSizeExample.cs#graphicsmmabsoluteviewportunitsexample1)]
 [!code-vb[BrushOverviewExamples_procedural_snip#GraphicsMMAbsoluteViewportUnitsExample1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushOverviewExamples_procedural_snip/visualbasic/tilesizeexample.vb#graphicsmmabsoluteviewportunitsexample1)]  
  
<a name="tilingbehavior"></a>
### <a name="tiling-behavior"></a>平铺行为  
 当<xref:System.Windows.Media.TileBrush>基铺未完全填充输出区域，并指定其他<xref:System.Windows.Media.TileMode.None>切片模式时，将生成平铺模式。 当磁贴画笔的磁贴未完全填充输出区域时，其<xref:System.Windows.Media.TileBrush.TileMode%2A>属性指定是否应复制基图以填充输出区域，如果是，则指定基图应如何复制。 属性<xref:System.Windows.Media.TileBrush.TileMode%2A>接受以下值，由<xref:System.Windows.Media.TileMode>枚举定义：  
  
- <xref:System.Windows.Media.TileMode.None>：仅绘制基本磁贴。  
  
- <xref:System.Windows.Media.TileMode.Tile>： 绘制基本磁贴，通过重复基磁贴填充剩余区域，以便一个磁贴的右边缘与下一个磁贴的左边缘相邻，与底部和顶部类似。  
  
- <xref:System.Windows.Media.TileMode.FlipX>： 与<xref:System.Windows.Media.TileMode.Tile>相同，但切片的替代列是水平翻转的。  
  
- <xref:System.Windows.Media.TileMode.FlipY>： 与<xref:System.Windows.Media.TileMode.Tile>相同，但其他切片行垂直翻转。  
  
- <xref:System.Windows.Media.TileMode.FlipXY>： 和<xref:System.Windows.Media.TileMode.FlipY><xref:System.Windows.Media.TileMode.FlipX>的组合。  
  
 下图阐释了不同的平铺模式。  
  
 ![不同的 TileBrush TileMode 设置](./media/img-mmgraphics-tilemodes.gif "img_mmgraphics_tilemodes")  
  
 在下面的示例中，使用一个图像来绘制宽度为 100 像素并且高度为 100 像素的矩形。 通过将画笔<xref:System.Windows.Media.TileBrush.Viewport%2A>设置为 0，0，0.25，0.25，使画笔的基磁贴设置为输出区域的 1/4。 画笔<xref:System.Windows.Media.TileBrush.TileMode%2A>设置为<xref:System.Windows.Media.TileMode.FlipXY>。 这样它便可以用图块行来填充矩形。  
  
 [!code-xaml[BrushOverviewExamples_snip#GraphicsMMFlipXYExample](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushOverviewExamples_snip/XAML/TilingExample.xaml#graphicsmmflipxyexample)]  
  
 [!code-csharp[BrushOverviewExamples_procedural_snip#GraphicsMMFlipXYExample](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushOverviewExamples_procedural_snip/CSharp/TilingExample.cs#graphicsmmflipxyexample)]
 [!code-vb[BrushOverviewExamples_procedural_snip#GraphicsMMFlipXYExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushOverviewExamples_procedural_snip/visualbasic/tilingexample.vb#graphicsmmflipxyexample)]  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Media.ImageBrush>
- <xref:System.Windows.Media.DrawingBrush>
- <xref:System.Windows.Media.VisualBrush>
- <xref:System.Windows.Media.TileBrush>
- [使用图像、绘图和视觉对象进行绘制](painting-with-images-drawings-and-visuals.md)
- [如何使用主题](brushes-how-to-topics.md)
- [Freezable 对象概述](../advanced/freezable-objects-overview.md)
- [ImageBrush 示例](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ImageBrush)
- [VisualBrush 示例](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/VisualBrush)
