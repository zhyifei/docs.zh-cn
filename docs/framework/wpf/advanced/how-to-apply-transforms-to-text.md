---
title: 如何：向文本应用变换
ms.date: 03/30/2017
helpviewer_keywords:
- typography [WPF], rotated text
- typography [WPF], scaled text
- skewed text [WPF]
- typography [WPF], translated text
- typography [WPF], shadowed text
- rotated text [WPF]
- translated text [WPF]
- shadowed text [WPF]
- transforms in text [WPF]
- typography [WPF], transforms
- scaled text [WPF]
- typography [WPF], skewed text
ms.assetid: 0d61678a-4185-4f2a-85c6-c1d020f96fa0
ms.openlocfilehash: 531537013ab3bbfba278ca63e14155341eefc826
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33544917"
---
# <a name="how-to-apply-transforms-to-text"></a>如何：向文本应用变换
应用变换可以改变应用程序中文本的显示。 下面的示例使用不同类型的呈现转换来影响中的文本显示<xref:System.Windows.Controls.TextBlock>控件。  
  
## <a name="example"></a>示例  
 下面的示例演示了在 x-y 二维平面中文本围绕一个特定点进行旋转。  
  
 ![使用 rotatetransform 旋转的文本](../../../../docs/framework/wpf/advanced/media/transformedtext01.jpg "TransformedText01")  
文本旋转 90 度的示例  
  
 下面的代码示例使用<xref:System.Windows.Media.RotateTransform>旋转文本。 <xref:System.Windows.Media.RotateTransform.Angle%2A>值为 90 旋转元素顺时针旋转 90 度。  
  
 [!code-xaml[TextTransformSample#TextTransformSample1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextTransformSample/CS/Window1.xaml#texttransformsample1)]  
  
 下面的示例演示沿 X 轴放大 150% 得到第二行文本，沿 Y 轴放大 150% 得到第三行文本。  
  
 ![使用 scaletransform 缩放的文本](../../../../docs/framework/wpf/advanced/media/transformedtext02.jpg "TransformedText02")  
缩放文本的示例  
  
 下面的代码示例使用<xref:System.Windows.Media.ScaleTransform>对从其原始大小的文本进行缩放。  
  
 [!code-xaml[TextTransformSample#TextTransformSample2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextTransformSample/CS/Window1.xaml#texttransformsample2)]  
  
> [!NOTE]
>  放大文本不同于增大文本字号。 字号的计算相互独立，以便针对不同字号提供最佳分辨率。 而缩放后的文本将按比例保持原始的文本大小。  
  
 以下示例演示沿 X 轴倾斜的文本。  
  
 ![使用 SkewTransform 扭曲的文本](../../../../docs/framework/wpf/advanced/media/transformedtext03.jpg "TransformedText03")  
扭曲文本的示例  
  
 下面的代码示例使用<xref:System.Windows.Media.SkewTransform>，以扭曲的文本。 扭曲（也称为倾斜）是一种以非均匀方式拉伸坐标空间的变换。 在本示例中，两个文本字符串沿 x 坐标扭曲了 -30° 和 30°。  
  
 [!code-xaml[TextTransformSample#TextTransformSample3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextTransformSample/CS/Window1.xaml#texttransformsample3)]  
  
 下面的示例演示沿 x 轴和 y 轴平移或移动的文本。  
  
 ![使用 TranslateTransform 偏移的文本](../../../../docs/framework/wpf/advanced/media/transformedtext04.jpg "TransformedText04")  
平移文本的示例  
  
 下面的代码示例使用<xref:System.Windows.Media.TranslateTransform>来偏移文本。 在本示例中，主要文本下方略微偏移的文本副本营造出了阴影效果。  
  
 [!code-xaml[TextTransformSample#TextTransformSample4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextTransformSample/CS/Window1.xaml#texttransformsample4)]  
  
> [!NOTE]
>  <xref:System.Windows.Media.Effects.DropShadowBitmapEffect>提供阴影效果提供一组丰富的功能。 有关详细信息，请参阅[创建带阴影的文本](../../../../docs/framework/wpf/advanced/how-to-create-text-with-a-shadow.md)。  
  
## <a name="see-also"></a>请参阅  
 [向文本应用动画](../../../../docs/framework/wpf/advanced/how-to-apply-animations-to-text.md)
