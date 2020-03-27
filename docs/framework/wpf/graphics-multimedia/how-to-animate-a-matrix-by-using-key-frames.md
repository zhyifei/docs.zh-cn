---
title: 如何：使用关键帧对 Matrix 进行动画处理
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], Matrix properties with key frames
- Matrix properties [WPF], animating with key frames
- key frames [WPF], animating Matrix properties with
ms.assetid: b851a4c7-ecb1-420e-9203-83e7afd037fd
ms.openlocfilehash: eb596cf728f8a7cc1964963b8509f42bdd7a392a
ms.sourcegitcommit: 59e36e65ac81cdd094a5a84617625b2a0ff3506e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2020
ms.locfileid: "80344919"
---
# <a name="how-to-animate-a-matrix-by-using-key-frames"></a>如何：使用关键帧对 Matrix 进行动画处理
此示例演示如何使用关键帧对<xref:System.Windows.Media.MatrixTransform.Matrix%2A>属性<xref:System.Windows.Media.MatrixTransform>进行动画处理。  
  
## <a name="example"></a>示例  
 下面的示例使用 类<xref:System.Windows.Media.Animation.MatrixAnimationUsingKeyFrames>为 属性<xref:System.Windows.Media.MatrixTransform>设置<xref:System.Windows.Media.MatrixTransform.Matrix%2A>动画。 该示例使用<xref:System.Windows.Media.MatrixTransform>对象转换 的外观<xref:System.Windows.Controls.Button>和位置。  
  
 此动画使用<xref:System.Windows.Media.Animation.DiscreteMatrixKeyFrame>类创建两个关键帧，并对其进行以下操作：  
  
1. 在前 0.2 秒内为第一个<xref:System.Windows.Media.Matrix>进行动画处理。 该示例更改<xref:System.Windows.Media.Matrix.M11%2A>的<xref:System.Windows.Media.Matrix.M12%2A>和<xref:System.Windows.Media.Matrix>属性。 此更改会导致按钮拉伸并变得倾斜。 该示例还更改<xref:System.Windows.Media.Matrix.OffsetX%2A>和<xref:System.Windows.Media.Matrix.OffsetY%2A>属性，以便按钮更改位置。  
  
2. 在 1.0 秒内为第二个<xref:System.Windows.Media.Matrix>设置动画。 当按钮不再倾斜或拉伸时，按钮将移动到其他位置。  
  
3. 无限期重复动画。  
  
> [!NOTE]
> 从<xref:System.Windows.Media.Animation.DiscreteMatrixKeyFrame>对象派生的关键帧在值之间创建突然跳转，也就是说，动画的移动是抖动的。  
  
 [!code-xaml[keyframes_snip#MatrixAnimationUsingKeyFramesWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/MatrixAnimationUsingKeyFramesExample.xaml#matrixanimationusingkeyframeswholepage)]  
  
 有关完整示例，请参阅[关键帧动画示例](https://github.com/microsoft/WPF-Samples/tree/master/Animation/KeyFrameAnimation)。  
  
## <a name="see-also"></a>请参阅

- <xref:System.Windows.Media.MatrixTransform.Matrix%2A>
- <xref:System.Windows.Media.MatrixTransform>
- [关键帧动画概述](key-frame-animations-overview.md)
- [关键帧操作说明主题](key-frame-animation-how-to-topics.md)
