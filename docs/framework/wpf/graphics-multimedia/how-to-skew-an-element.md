---
title: 如何：使元素扭曲
ms.date: 03/30/2017
helpviewer_keywords:
- skewing elements [WPF]
- graphics [WPF], skewing elements
- classes [WPF], SkewTransform
ms.assetid: 56b65f2f-dc6e-4238-923f-ca44ec53c52f
ms.openlocfilehash: 10b00044c1c518641281e2e72cdb5a68474b5170
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/21/2020
ms.locfileid: "80112019"
---
# <a name="how-to-skew-an-element"></a>如何：使元素扭曲
此示例演示如何使用<xref:System.Windows.Media.SkewTransform>倾斜元素。 扭曲（也称为修剪）是一种以非均匀方式拉伸坐标空间的转换。 一<xref:System.Windows.Media.SkewTransform>个典型的用途是模拟 2D 对象中的 3D 深度。  
  
 使用<xref:System.Windows.Media.SkewTransform.CenterX%2A>和<xref:System.Windows.Media.SkewTransform.CenterY%2A>属性指定 的中心<xref:System.Windows.Media.SkewTransform>点。  
  
 使用<xref:System.Windows.Media.SkewTransform.AngleX%2A>和<xref:System.Windows.Media.SkewTransform.AngleY%2A>属性指定 x 轴和 y 轴的倾斜角度，并沿这些轴倾斜当前坐标系。  
  
 要预测偏斜变换的效果，请考虑倾斜<xref:System.Windows.Media.SkewTransform.AngleX%2A>x 轴值相对于原始坐标系。 因此，对于<xref:System.Windows.Media.SkewTransform.AngleX%2A>30，y 轴通过原点旋转 30 度，并将该原点以 x- 30 度表示值。 同样，30 的 y<xref:System.Windows.Media.SkewTransform.AngleY%2A>值从原点偏斜 30 度。 请注意，在 x 或 y 轴中将坐标系统转换（移动）30 度的效果并不相同。  
  
 下面的示例将 45 度的水平偏斜从中心<xref:System.Windows.Shapes.Rectangle>点 （0，0） 应用于 a。  
  
## <a name="example"></a>示例  
 [!code-xaml[transformsSample#41](~/samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/SkewTransformExample.xaml#41)]  
  
 下面的示例将 45 度的水平偏斜从中心<xref:System.Windows.Shapes.Rectangle>点 （25，25） 应用于 a。  
  
 [!code-xaml[transformsSample#42](~/samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/SkewTransformExample.xaml#42)]  
  
 下面的示例将 45 度的垂直倾斜从中心点<xref:System.Windows.Shapes.Rectangle>（25，25） 应用于 a。  
  
 [!code-xaml[transformsSample#43](~/samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/SkewTransformExample.xaml#43)]  
  
 下图演示了此示例中使用的不同扭曲。  
  
 ![SkewTransform 示例](./media/img-wcpsdk-graphicsmm-skewtransformexample.gif "img_wcpsdk_graphicsmm_skewtransformexample")  
三个 SkewTransform 示例的图示  
  
 有关完整示例，请参阅[2D 变换示例](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/2DTransforms)。  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Media.Transform>
- <xref:System.Windows.Media.SkewTransform>
- [转换概述](transforms-overview.md)
- [如何使用主题](transformations-how-to-topics.md)
