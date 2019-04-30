---
title: 如何：使用关键帧对矩阵进行动画处理
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], Matrix properties with key frames
- Matrix properties [WPF], animating with key frames
- key frames [WPF], animating Matrix properties with
ms.assetid: b851a4c7-ecb1-420e-9203-83e7afd037fd
ms.openlocfilehash: ff5320fa5b4441ae3e0f414b274ab9118b77ec50
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "62020239"
---
# <a name="how-to-animate-a-matrix-by-using-key-frames"></a>如何：使用关键帧对矩阵进行动画处理
此示例演示如何进行动画处理<xref:System.Windows.Media.MatrixTransform.Matrix%2A>属性的<xref:System.Windows.Media.MatrixTransform>使用关键帧。  
  
## <a name="example"></a>示例  
 下面的示例使用<xref:System.Windows.Media.Animation.MatrixAnimationUsingKeyFrames>类进行动画处理<xref:System.Windows.Media.MatrixTransform.Matrix%2A>属性的<xref:System.Windows.Media.MatrixTransform>。 该示例使用<xref:System.Windows.Media.MatrixTransform>要转换的外观和位置对象<xref:System.Windows.Controls.Button>。  
  
 此动画使用<xref:System.Windows.Media.Animation.DiscreteMatrixKeyFrame>类来创建两个关键帧，然后执行以下与它们：  
  
1. 进行动画处理的第一个<xref:System.Windows.Media.Matrix>0.2 的第一个秒数内。 此示例更改<xref:System.Windows.Media.Matrix.M11%2A>并<xref:System.Windows.Media.Matrix.M12%2A>的属性<xref:System.Windows.Media.Matrix>。 此更改会导致该按钮拉伸和扭曲。 此示例还更改<xref:System.Windows.Media.Matrix.OffsetX%2A>和<xref:System.Windows.Media.Matrix.OffsetY%2A>属性，以便该按钮将更改位置。  
  
2. 进行动画处理第二个<xref:System.Windows.Media.Matrix>1.0 秒时。 该按钮将会移到另一个位置，而不再倾斜或拉伸按钮。  
  
3. 无限期地重复动画。  
  
> [!NOTE]
>  关键帧派生<xref:System.Windows.Media.Animation.DiscreteMatrixKeyFrame>对象之间创建突然跳跃值，也就是说，移动动画显得很不稳定。  
  
 [!code-xaml[keyframes_snip#MatrixAnimationUsingKeyFramesWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/MatrixAnimationUsingKeyFramesExample.xaml#matrixanimationusingkeyframeswholepage)]  
  
 有关完整示例，请参阅[关键帧动画示例](https://go.microsoft.com/fwlink/?LinkID=160012)。  
  
## <a name="see-also"></a>请参阅

- <xref:System.Windows.Media.MatrixTransform.Matrix%2A>
- <xref:System.Windows.Media.MatrixTransform>
- [关键帧动画概述](key-frame-animations-overview.md)
- [关键帧操作说明主题](key-frame-animation-how-to-topics.md)
