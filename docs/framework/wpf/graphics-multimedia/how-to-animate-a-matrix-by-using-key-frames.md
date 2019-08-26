---
title: 如何：使用关键帧对矩阵进行动画处理
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], Matrix properties with key frames
- Matrix properties [WPF], animating with key frames
- key frames [WPF], animating Matrix properties with
ms.assetid: b851a4c7-ecb1-420e-9203-83e7afd037fd
ms.openlocfilehash: 6aa3e27cdfda7597c9b6acbf2980a2774f2b667b
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69963027"
---
# <a name="how-to-animate-a-matrix-by-using-key-frames"></a>如何：使用关键帧对矩阵进行动画处理
此示例演示如何使用关键帧<xref:System.Windows.Media.MatrixTransform.Matrix%2A>对的属性<xref:System.Windows.Media.MatrixTransform>进行动画处理。  
  
## <a name="example"></a>示例  
 下面的示例使用<xref:System.Windows.Media.Animation.MatrixAnimationUsingKeyFrames>类对的<xref:System.Windows.Media.MatrixTransform.Matrix%2A>属性<xref:System.Windows.Media.MatrixTransform>进行动画处理。 该示例使用<xref:System.Windows.Media.MatrixTransform>对象来转换的外观和位置<xref:System.Windows.Controls.Button>。  
  
 此动画使用<xref:System.Windows.Media.Animation.DiscreteMatrixKeyFrame>类创建两个关键帧, 并对其执行以下操作:  
  
1. 在前 0.2 <xref:System.Windows.Media.Matrix>秒内对第一个进行动画处理。 此示例更改<xref:System.Windows.Media.Matrix.M11%2A>的和<xref:System.Windows.Media.Matrix.M12%2A>属性。 <xref:System.Windows.Media.Matrix> 此更改会导致按钮拉伸并变得扭曲。 该示例还更改了<xref:System.Windows.Media.Matrix.OffsetX%2A>和<xref:System.Windows.Media.Matrix.OffsetY%2A>属性, 以使按钮更改位置。  
  
2. <xref:System.Windows.Media.Matrix>每秒在1.0 秒进行动画处理。 按钮移至另一个位置, 而按钮不再歪斜或拉伸。  
  
3. 无限期地重复动画。  
  
> [!NOTE]
> 从<xref:System.Windows.Media.Animation.DiscreteMatrixKeyFrame>对象派生的关键帧会在值之间创建突然跳转, 也就是说, 动画的移动是不平稳的。  
  
 [!code-xaml[keyframes_snip#MatrixAnimationUsingKeyFramesWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/MatrixAnimationUsingKeyFramesExample.xaml#matrixanimationusingkeyframeswholepage)]  
  
 有关完整示例，请参阅[关键帧动画示例](https://go.microsoft.com/fwlink/?LinkID=160012)。  
  
## <a name="see-also"></a>请参阅

- <xref:System.Windows.Media.MatrixTransform.Matrix%2A>
- <xref:System.Windows.Media.MatrixTransform>
- [关键帧动画概述](key-frame-animations-overview.md)
- [关键帧操作说明主题](key-frame-animation-how-to-topics.md)
