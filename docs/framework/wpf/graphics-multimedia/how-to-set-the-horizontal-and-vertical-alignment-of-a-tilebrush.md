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
ms.workload: dotnet
ms.openlocfilehash: 3dcbf4715c80f72178295c0b6abdc1272a055a8a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-set-the-horizontal-and-vertical-alignment-of-a-tilebrush"></a>如何：设置 TileBrush 的水平对齐方式和垂直对齐方式
本示例演示如何控制平铺内容的水平对齐方式和垂直对齐方式。 若要控制的水平和垂直对齐方式<xref:System.Windows.Media.TileBrush>，使用其<xref:System.Windows.Media.TileBrush.AlignmentX%2A>和<xref:System.Windows.Media.TileBrush.AlignmentY%2A>属性。  
  
 <xref:System.Windows.Media.TileBrush.AlignmentX%2A>和<xref:System.Windows.Media.TileBrush.AlignmentY%2A>属性<xref:System.Windows.Media.TileBrush>使用满足以下条件之一时：  
  
-   <xref:System.Windows.Media.TileBrush.Stretch%2A>属性是<xref:System.Windows.Media.Stretch.Uniform>或<xref:System.Windows.Media.Stretch.UniformToFill>和<xref:System.Windows.Media.TileBrush.Viewbox%2A>和<xref:System.Windows.Media.TileBrush.Viewport%2A>具有不同的纵横比。  
  
-   <xref:System.Windows.Media.TileBrush.Stretch%2A>属性是<xref:System.Windows.Media.Stretch.None>和<xref:System.Windows.Media.TileBrush.Viewbox%2A>和<xref:System.Windows.Media.TileBrush.Viewport%2A>具有不同大小。  
  
## <a name="example"></a>示例  
 下面的示例将对齐的内容<xref:System.Windows.Media.DrawingBrush>，这是一种<xref:System.Windows.Media.TileBrush>，到其磁贴的左上角。 若要对齐的内容，该示例设置<xref:System.Windows.Media.TileBrush.AlignmentX%2A>属性<xref:System.Windows.Media.DrawingBrush>到<xref:System.Windows.Media.AlignmentX.Left>和<xref:System.Windows.Media.TileBrush.AlignmentY%2A>属性<xref:System.Windows.Media.AlignmentY.Top>。 本示例生成以下输出。  
  
 ![TileBrush 顶部 &#45; 左的对齐](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-tilebrushalignmentexampletopleft.png "graphicsmm_TileBrushAlignmentExampleTopLeft")  
内容与左上角对齐的 TileBrush  
  
 [!code-csharp[brushoverviewexamples_snip#TileBrushTopLeftAlignmentInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BrushOverviewExamples_snip/CSharp/TileBrushAlignmentExample.cs#tilebrushtopleftalignmentinline)]
 [!code-vb[brushoverviewexamples_snip#TileBrushTopLeftAlignmentInline](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BrushOverviewExamples_snip/visualbasic/tilebrushalignmentexample.vb#tilebrushtopleftalignmentinline)]
 [!code-xaml[brushoverviewexamples_snip#TileBrushTopLeftAlignmentInline](../../../../samples/snippets/xaml/VS_Snippets_Wpf/BrushOverviewExamples_snip/XAML/TileBrushAlignmentExample.xaml#tilebrushtopleftalignmentinline)]  
  
## <a name="example"></a>示例  
 下一步的示例将对齐的内容<xref:System.Windows.Media.DrawingBrush>到通过设置其磁贴右下角<xref:System.Windows.Media.TileBrush.AlignmentX%2A>属性<xref:System.Windows.Media.AlignmentX.Right>和<xref:System.Windows.Media.TileBrush.AlignmentY%2A>属性<xref:System.Windows.Media.AlignmentY.Bottom>。 该示例生成以下输出。  
  
 ![TileBrush 底部 &#45; 右对齐](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-tilebrushalignmentexamplebottomright.png "graphicsmm_TileBrushAlignmentExampleBottomRight")  
内容与右下角对齐的 TileBrush  
  
 [!code-csharp[brushoverviewexamples_snip#TileBrushBottomRightAlignmentInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BrushOverviewExamples_snip/CSharp/TileBrushAlignmentExample.cs#tilebrushbottomrightalignmentinline)]
 [!code-vb[brushoverviewexamples_snip#TileBrushBottomRightAlignmentInline](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BrushOverviewExamples_snip/visualbasic/tilebrushalignmentexample.vb#tilebrushbottomrightalignmentinline)]
 [!code-xaml[brushoverviewexamples_snip#TileBrushBottomRightAlignmentInline](../../../../samples/snippets/xaml/VS_Snippets_Wpf/BrushOverviewExamples_snip/XAML/TileBrushAlignmentExample.xaml#tilebrushbottomrightalignmentinline)]  
  
## <a name="example"></a>示例  
 下一步的示例将对齐的内容<xref:System.Windows.Media.DrawingBrush>到通过设置其磁贴的左上角<xref:System.Windows.Media.TileBrush.AlignmentX%2A>属性<xref:System.Windows.Media.AlignmentX.Left>和<xref:System.Windows.Media.TileBrush.AlignmentY%2A>属性<xref:System.Windows.Media.AlignmentY.Top>。 它还将设置<xref:System.Windows.Media.TileBrush.Viewport%2A>和<xref:System.Windows.Media.TileBrush.TileMode%2A>的<xref:System.Windows.Media.DrawingBrush>生成平铺模式。 该示例生成以下输出。  
  
 ![平铺的 TileBrush 顶部 &#45; 左的对齐](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-tilebrushalignmentexampletoplefttiled.png "graphicsmm_TileBrushAlignmentExampleTopLeftTiled")  
内容与基本平铺图案的左上角对齐的平铺图案  
  
 上图突出显示了基本平铺图案，以便显示其内容的对齐方式。 请注意，<xref:System.Windows.Media.TileBrush.AlignmentX%2A>设置无任何影响，因为内容<xref:System.Windows.Media.DrawingBrush>完全水平填充基本磁贴。  
  
 [!code-csharp[brushoverviewexamples_snip#TileBrushTopLeftAlignmentTiledInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BrushOverviewExamples_snip/CSharp/TileBrushAlignmentExample.cs#tilebrushtopleftalignmenttiledinline)]
 [!code-vb[brushoverviewexamples_snip#TileBrushTopLeftAlignmentTiledInline](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BrushOverviewExamples_snip/visualbasic/tilebrushalignmentexample.vb#tilebrushtopleftalignmenttiledinline)]
 [!code-xaml[brushoverviewexamples_snip#TileBrushTopLeftAlignmentTiledInline](../../../../samples/snippets/xaml/VS_Snippets_Wpf/BrushOverviewExamples_snip/XAML/TileBrushAlignmentExample.xaml#tilebrushtopleftalignmenttiledinline)]  
  
## <a name="example"></a>示例  
 最后一个示例将对齐的平铺内容<xref:System.Windows.Media.DrawingBrush>到通过设置其基本磁贴右下角<xref:System.Windows.Media.TileBrush.AlignmentX%2A>属性<xref:System.Windows.Media.AlignmentX.Right>和<xref:System.Windows.Media.TileBrush.AlignmentY%2A>属性<xref:System.Windows.Media.AlignmentY.Bottom>。 该示例生成以下输出。  
  
 ![一个平铺 TileBrush 底部 &#45; 右对齐](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-tilebrushalignmentexamplebottomrighttiled.png "graphicsmm_TileBrushAlignmentExampleBottomRightTiled")  
内容与基本平铺图案的右下角对齐的平铺图案  
  
 同样，<xref:System.Windows.Media.TileBrush.AlignmentX%2A>设置无任何影响，因为内容<xref:System.Windows.Media.DrawingBrush>完全水平填充基本磁贴。  
  
 [!code-csharp[brushoverviewexamples_snip#TileBrushBottomRightAlignmentInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BrushOverviewExamples_snip/CSharp/TileBrushAlignmentExample.cs#tilebrushbottomrightalignmentinline)]
 [!code-vb[brushoverviewexamples_snip#TileBrushBottomRightAlignmentInline](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BrushOverviewExamples_snip/visualbasic/tilebrushalignmentexample.vb#tilebrushbottomrightalignmentinline)]
 [!code-xaml[brushoverviewexamples_snip#TileBrushBottomRightAlignmentInline](../../../../samples/snippets/xaml/VS_Snippets_Wpf/BrushOverviewExamples_snip/XAML/TileBrushAlignmentExample.xaml#tilebrushbottomrightalignmentinline)]  
  
 示例使用<xref:System.Windows.Media.DrawingBrush>对象来演示如何<xref:System.Windows.Media.TileBrush.AlignmentX%2A>和<xref:System.Windows.Media.TileBrush.AlignmentY%2A>使用属性。 这些属性具有相同行为对于所有磁贴画笔： <xref:System.Windows.Media.DrawingBrush>， <xref:System.Windows.Media.ImageBrush>，和<xref:System.Windows.Media.VisualBrush>。 有关平铺画笔的详细信息，请参阅[使用图像、绘图和视觉对象进行绘制](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md)。  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Windows.Media.DrawingBrush>  
 <xref:System.Windows.Media.ImageBrush>  
 <xref:System.Windows.Media.VisualBrush>  
 [使用图像、绘图和视觉对象进行绘制](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md)
