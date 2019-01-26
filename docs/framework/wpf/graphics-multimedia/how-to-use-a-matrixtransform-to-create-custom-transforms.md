---
title: 如何：使用 MatrixTransform 创建自定义变换
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [WPF], custom Transforms
ms.assetid: 919381ca-989f-47cf-86b4-1094060236e4
ms.openlocfilehash: 3b5a6fbedd30c859dffadad00c8faab74fc0773b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54628794"
---
# <a name="how-to-use-a-matrixtransform-to-create-custom-transforms"></a>如何：使用 MatrixTransform 创建自定义变换
此示例演示如何使用<xref:System.Windows.Media.MatrixTransform>平移 （移动） 位置，拉伸和扭曲的<xref:System.Windows.Controls.Button>。  
  
> [!NOTE]
>  使用<xref:System.Windows.Media.MatrixTransform>类，以创建不由提供的自定义转换<xref:System.Windows.Media.RotateTransform>， <xref:System.Windows.Media.SkewTransform>， <xref:System.Windows.Media.ScaleTransform>，或<xref:System.Windows.Media.TranslateTransform>类。  
  
## <a name="example"></a>示例  
 [!code-xaml[Transforms_snip#MatrixTransform](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/MatrixTransformExample.xaml#matrixtransform)]  
  
## <a name="see-also"></a>请参阅
- <xref:System.Windows.Media.MatrixTransform>
- <xref:System.Windows.Media.Transform>
- [转换概述](../../../../docs/framework/wpf/graphics-multimedia/transforms-overview.md)
- [帮助主题](../../../../docs/framework/wpf/graphics-multimedia/transformations-how-to-topics.md)
- [WPF 中的形状和基本绘图概述](../../../../docs/framework/wpf/graphics-multimedia/shapes-and-basic-drawing-in-wpf-overview.md)
