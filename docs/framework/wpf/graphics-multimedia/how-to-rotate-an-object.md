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
ms.openlocfilehash: e17d3b7b9986b477df198480129edaf4c139c6bc
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/21/2020
ms.locfileid: "80112058"
---
# <a name="how-to-rotate-an-object"></a>如何：旋转对象
此示例演示如何旋转对象。 该示例首先创建<xref:System.Windows.Media.RotateTransform>a，然后指定<xref:System.Windows.Media.RotateTransform.Angle%2A>其以度表示。  
  
 下面的示例围绕<xref:System.Windows.Shapes.Polyline>其左上角旋转对象 45 度。  
  
## <a name="example"></a>示例  
 [!code-xaml[Transforms_snip#RotatePolylineAboutTopLeft](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/RotateTransformExample.xaml#rotatepolylineabouttopleft)]  
  
 [!code-csharp[Transforms_Procedural_snip#RotatePolylineAboutTopLeft](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_Procedural_snip/CSharp/RotateTransformExample.cs#rotatepolylineabouttopleft)]
 [!code-vb[Transforms_Procedural_snip#RotatePolylineAboutTopLeft](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Transforms_Procedural_snip/VisualBasic/RotateTransformExample.vb#rotatepolylineabouttopleft)]  
  
 的<xref:System.Windows.Media.RotateTransform.CenterX%2A><xref:System.Windows.Media.RotateTransform.CenterY%2A>和 属性<xref:System.Windows.Media.RotateTransform>指定对象旋转的点。 此中心点以要转换的元素的坐标空间表示。 默认情况下，将围绕着要转换的对象的左上角 (0,0) 进行旋转。  
  
 下一<xref:System.Windows.Shapes.Polyline>个示例沿点 （25，50） 顺时针旋转对象 45 度。  
  
 [!code-xaml[Transforms_snip#RotatePolylineAboutCenter](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/RotateTransformExample.xaml#rotatepolylineaboutcenter)]  
  
 [!code-csharp[Transforms_Procedural_snip#RotatePolylineAboutCenter](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_Procedural_snip/CSharp/RotateTransformExample.cs#rotatepolylineaboutcenter)]
 [!code-vb[Transforms_Procedural_snip#RotatePolylineAboutCenter](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Transforms_Procedural_snip/VisualBasic/RotateTransformExample.vb#rotatepolylineaboutcenter)]  
  
 下图显示了对两个对象应用 的结果<xref:System.Windows.Media.Transform>。  
  
 ![以不同中心点进行的 45 度旋转](./media/wcpsdk-graphicsmm-rotatetransform45degrees.gif "wcpsdk_graphicsmm_rotatetransform45degrees")  
两个对象以不同的旋转中心旋转 45 度  
  
 前面的<xref:System.Windows.Shapes.Polyline>示例中是 。 <xref:System.Windows.UIElement> 将 应用<xref:System.Windows.Media.Transform>到<xref:System.Windows.UIElement.RenderTransform%2A>的属性时<xref:System.Windows.UIElement>，可以使用 属性<xref:System.Windows.UIElement.RenderTransformOrigin%2A>为应用于元素的每个<xref:System.Windows.Media.Transform>属性指定原点。 由于属性<xref:System.Windows.UIElement.RenderTransformOrigin%2A>使用相对坐标，因此即使不知道元素的大小，也可以对元素的中心应用变换。 有关详细信息，请参阅[使用相对值指定变换的原点](how-to-specify-the-origin-of-a-transform-by-using-relative-values.md)。  
  
 有关完整示例，请参阅[2D 变换示例](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/2DTransforms)。  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Media.Transform>
- [转换概述](transforms-overview.md)
- [如何使用主题](transformations-how-to-topics.md)
