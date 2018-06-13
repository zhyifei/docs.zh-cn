---
title: 如何：旋转对象
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- graphics [WPF], rotating objects [WPF]
- rotating objects [WPF]
ms.assetid: ee3466cd-e66f-4e8f-8a5a-71d77bc1e390
ms.openlocfilehash: 7eb562d81bdd8c9187672b31ed08ed6ac27da41c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33561936"
---
# <a name="how-to-rotate-an-object"></a>如何：旋转对象
此示例演示如何旋转对象。 此示例首先创建<xref:System.Windows.Media.RotateTransform>，然后指定其<xref:System.Windows.Media.RotateTransform.Angle%2A>以度为单位。  
  
 下面的示例将<xref:System.Windows.Shapes.Polyline>对象有关其左上角的 45 度。  
  
## <a name="example"></a>示例  
 [!code-xaml[Transforms_snip#RotatePolylineAboutTopLeft](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/RotateTransformExample.xaml#rotatepolylineabouttopleft)]  
  
 [!code-csharp[Transforms_Procedural_snip#RotatePolylineAboutTopLeft](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Transforms_Procedural_snip/CSharp/RotateTransformExample.cs#rotatepolylineabouttopleft)]
 [!code-vb[Transforms_Procedural_snip#RotatePolylineAboutTopLeft](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Transforms_Procedural_snip/VisualBasic/RotateTransformExample.vb#rotatepolylineabouttopleft)]  
  
 <xref:System.Windows.Media.RotateTransform.CenterX%2A>和<xref:System.Windows.Media.RotateTransform.CenterY%2A>属性<xref:System.Windows.Media.RotateTransform>指定哪些对象的旋转的点。 此中心点以要转换的元素的坐标空间表示。 默认情况下，将围绕着要转换的对象的左上角 (0,0) 进行旋转。  
  
 下一个示例旋转<xref:System.Windows.Shapes.Polyline>对象有关的点 (25，50) 的顺时针旋转 45 度。  
  
 [!code-xaml[Transforms_snip#RotatePolylineAboutCenter](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/RotateTransformExample.xaml#rotatepolylineaboutcenter)]  
  
 [!code-csharp[Transforms_Procedural_snip#RotatePolylineAboutCenter](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Transforms_Procedural_snip/CSharp/RotateTransformExample.cs#rotatepolylineaboutcenter)]
 [!code-vb[Transforms_Procedural_snip#RotatePolylineAboutCenter](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Transforms_Procedural_snip/VisualBasic/RotateTransformExample.vb#rotatepolylineaboutcenter)]  
  
 下图显示应用的结果<xref:System.Windows.Media.Transform>到两个对象。  
  
 ![围绕不同中心点旋转 45 度](../../../../docs/framework/wpf/graphics-multimedia/media/wcpsdk-graphicsmm-rotatetransform45degrees.gif "wcpsdk_graphicsmm_rotatetransform45degrees")  
两个对象以不同的旋转中心旋转 45 度  
  
 <xref:System.Windows.Shapes.Polyline>在前面的示例是<xref:System.Windows.UIElement>。 当你将<xref:System.Windows.Media.Transform>到<xref:System.Windows.UIElement.RenderTransform%2A>属性<xref:System.Windows.UIElement>，你可以使用<xref:System.Windows.UIElement.RenderTransformOrigin%2A>属性指定的 origin 每个<xref:System.Windows.Media.Transform>适用于元素。 因为<xref:System.Windows.UIElement.RenderTransformOrigin%2A>属性使用相对坐标，你可以将转换应用到元素的中心，即使你不知道其大小。 有关详细信息和示例，请参阅[，指定的一种通过使用相对值的转换原点](../../../../docs/framework/wpf/graphics-multimedia/how-to-specify-the-origin-of-a-transform-by-using-relative-values.md)。  
  
 有关完整示例，请参阅 [2D 转换示例](http://go.microsoft.com/fwlink/?LinkID=158252)。  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Windows.Media.Transform>  
 [转换概述](../../../../docs/framework/wpf/graphics-multimedia/transforms-overview.md)  
 [帮助主题](../../../../docs/framework/wpf/graphics-multimedia/transformations-how-to-topics.md)
