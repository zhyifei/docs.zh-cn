---
title: 如何：使元素扭曲
ms.date: 03/30/2017
helpviewer_keywords:
- skewing elements [WPF]
- graphics [WPF], skewing elements
- classes [WPF], SkewTransform
ms.assetid: 56b65f2f-dc6e-4238-923f-ca44ec53c52f
ms.openlocfilehash: 8bd860a71253a55cb3148426dbb61cbd3477e95e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-skew-an-element"></a>如何：使元素扭曲
此示例演示如何使用<xref:System.Windows.Media.SkewTransform>扭曲元素。 扭曲（也称为修剪）是一种以非均匀方式拉伸坐标空间的转换。 一个典型用法<xref:System.Windows.Media.SkewTransform>是用于模拟[!INCLUDE[TLA#tla_3d](../../../../includes/tlasharptla-3d-md.md)]中的深度[!INCLUDE[TLA#tla_2d](../../../../includes/tlasharptla-2d-md.md)]对象。  
  
 使用<xref:System.Windows.Media.SkewTransform.CenterX%2A>和<xref:System.Windows.Media.SkewTransform.CenterY%2A>属性以指定中心点的<xref:System.Windows.Media.SkewTransform>。  
  
 使用<xref:System.Windows.Media.SkewTransform.AngleX%2A>和<xref:System.Windows.Media.SkewTransform.AngleY%2A>属性以指定的 x 轴和 y 轴的倾斜角度和倾斜沿这些轴当前坐标系统。  
  
 若要预测的倾斜转换的影响，请考虑，<xref:System.Windows.Media.SkewTransform.AngleX%2A>偏差相对于原始的坐标系统的 x 轴值。 因此，对于<xref:System.Windows.Media.SkewTransform.AngleX%2A>为 30，y 轴旋转通过原点 30 度和倾斜 x 轴旋转从该原点 30 度的值。 同样， <xref:System.Windows.Media.SkewTransform.AngleY%2A> 30 的偏差的形状的 y 值从原点 30 度。 请注意，在 x 或 y 轴中将坐标系统转换（移动）30 度的效果并不相同。  
  
 下面的示例应用到的 45 度的水平扭曲<xref:System.Windows.Shapes.Rectangle>要从中心点的 (0，0)。  
  
## <a name="example"></a>示例  
 [!code-xaml[transformsSample#41](../../../../samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/SkewTransformExample.xaml#41)]  
  
 下面的示例应用到的 45 度的水平扭曲<xref:System.Windows.Shapes.Rectangle>要从中心点 (25，25)。  
  
 [!code-xaml[transformsSample#42](../../../../samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/SkewTransformExample.xaml#42)]  
  
 下面的示例应用到的 45 度的垂直扭曲<xref:System.Windows.Shapes.Rectangle>要从中心点 (25，25)。  
  
 [!code-xaml[transformsSample#43](../../../../samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/SkewTransformExample.xaml#43)]  
  
 下图演示了此示例中使用的不同扭曲。  
  
 ![SkewTransform 示例](../../../../docs/framework/wpf/graphics-multimedia/media/img-wcpsdk-graphicsmm-skewtransformexample.gif "img_wcpsdk_graphicsmm_skewtransformexample")  
三个 SkewTransform 示例的图示  
  
 有关完整示例，请参阅 [2D 转换示例](http://go.microsoft.com/fwlink/?LinkID=158252)。  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Windows.Media.Transform>  
 <xref:System.Windows.Media.SkewTransform>  
 [转换概述](../../../../docs/framework/wpf/graphics-multimedia/transforms-overview.md)  
 [帮助主题](../../../../docs/framework/wpf/graphics-multimedia/transformations-how-to-topics.md)
