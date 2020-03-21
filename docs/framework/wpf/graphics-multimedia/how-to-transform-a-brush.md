---
title: 如何：变换画笔
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- brushes [WPF], rotating contents
- brushes [WPF], Transform property
- rotating contents of brushes [WPF]
ms.assetid: ebada2f9-f01f-4863-9ea2-c2e4e51610f1
ms.openlocfilehash: b4484e2fc1ae3e969b02b1d8f3ae4ab2a035558e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79187341"
---
# <a name="how-to-transform-a-brush"></a>如何：变换画笔
此示例演示如何使用对象的两个<xref:System.Windows.Media.Brush>转换属性：<xref:System.Windows.Media.Brush.RelativeTransform%2A>和<xref:System.Windows.Media.Brush.Transform%2A>转换来转换对象。  
  
 以下示例使用<xref:System.Windows.Media.RotateTransform>将 内容<xref:System.Windows.Media.ImageBrush>旋转 45 度。  
  
 下图显示了<xref:System.Windows.Media.ImageBrush>无<xref:System.Windows.Media.RotateTransform>的 ，其中<xref:System.Windows.Media.RotateTransform>应用于<xref:System.Windows.Media.Brush.RelativeTransform%2A>属性，并<xref:System.Windows.Media.RotateTransform>应用于 属性。 <xref:System.Windows.Media.Brush.Transform%2A>  
  
 ![画笔的 RelativeTransform 和 Transform 设置](./media/wcpsdk-graphicsmm-transformandrelativetransform.png "wcpsdk_graphicsmm_transformandrelativetransform")  
  
## <a name="example"></a>示例  
 第一个示例将<xref:System.Windows.Media.RotateTransform>应用于<xref:System.Windows.Media.Brush.RelativeTransform%2A>的属性<xref:System.Windows.Media.ImageBrush>。 对象的 和<xref:System.Windows.Media.RotateTransform.CenterX%2A><xref:System.Windows.Media.RotateTransform.CenterY%2A>属性都设置为 0.5，这是此内容的中心点的相对坐标。 <xref:System.Windows.Media.RotateTransform> 因此，<xref:System.Windows.Media.ImageBrush>内容围绕其中心旋转。  
  
 [!code-csharp[BrushesIntroduction_snip#ImageBrushRelativeTransformExample](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/BrushTransformExample.cs#imagebrushrelativetransformexample)]
 [!code-vb[BrushesIntroduction_snip#ImageBrushRelativeTransformExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/brushtransformexample.vb#imagebrushrelativetransformexample)]
 [!code-xaml[BrushesIntroduction_snip#ImageBrushRelativeTransformExample](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/BrushTransformExample.xaml#imagebrushrelativetransformexample)]  
  
 第二个<xref:System.Windows.Media.RotateTransform><xref:System.Windows.Media.ImageBrush>示例还应用于但是，此示例使用 属性<xref:System.Windows.Media.Brush.Transform%2A>而不是 属性<xref:System.Windows.Media.Brush.RelativeTransform%2A>。  
  
 要围绕其中心旋转画笔，该示例将<xref:System.Windows.Media.RotateTransform.CenterX%2A><xref:System.Windows.Media.RotateTransform.CenterY%2A><xref:System.Windows.Media.RotateTransform>对象的 和 属性设置为绝对坐标。 因为画笔绘制了一个 175x90 像素的矩形，所以该矩形的中心点为 (87.5, 45)。  
  
 [!code-csharp[BrushesIntroduction_snip#ImageBrushTransformExample](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/BrushTransformExample.cs#imagebrushtransformexample)]
 [!code-vb[BrushesIntroduction_snip#ImageBrushTransformExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/brushtransformexample.vb#imagebrushtransformexample)]
 [!code-xaml[BrushesIntroduction_snip#ImageBrushTransformExample](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/BrushTransformExample.xaml#imagebrushtransformexample)]  
  
 有关<xref:System.Windows.Media.Brush.RelativeTransform%2A>和<xref:System.Windows.Media.Brush.Transform%2A>属性工作方式的说明，请参阅[画笔转换概述](brush-transformation-overview.md)。  
  
 有关完整示例，请参阅[画笔示例](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Brushes)。 有关画笔的详细信息，请参阅[使用纯色和渐变进行绘制概述](painting-with-solid-colors-and-gradients-overview.md)。  
  
## <a name="see-also"></a>另请参阅

- [Brush 转换概述](brush-transformation-overview.md)
- [使用纯色和渐变进行绘制概述](painting-with-solid-colors-and-gradients-overview.md)
- [转换概述](transforms-overview.md)
