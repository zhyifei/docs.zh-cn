---
title: 如何：使用关键帧对字符串进行动画处理
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], strings with key frames
- strings [WPF], animating with key frames
- key frames [WPF], animating strings with
ms.assetid: c62bc9fd-c09a-4227-bce0-0a1ab82049dd
ms.openlocfilehash: c954806ca901bbfc3ab6d4bbcc237cd0e404f154
ms.sourcegitcommit: 59e36e65ac81cdd094a5a84617625b2a0ff3506e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2020
ms.locfileid: "80344673"
---
# <a name="how-to-animate-a-string-by-using-key-frames"></a>如何：使用关键帧对字符串进行动画处理
此示例演示如何使用关键帧为字符串设置动画，在此示例中，该字符串是<xref:System.Windows.Controls.ContentControl.Content%2A><xref:System.Windows.Controls.Button>控件的属性。  
  
## <a name="example"></a>示例  
 下面的示例使用 类<xref:System.Windows.Media.Animation.StringAnimationUsingKeyFrames>为 属性<xref:System.Windows.Controls.Button>设置<xref:System.Windows.Controls.ContentControl.Content%2A>动画。  
  
 此示例中的所有关键帧都使用类的实例，<xref:System.Windows.Media.Animation.DiscreteStringKeyFrame>因为使用关键帧创建的字符串动画只能使用离散关键帧。 离散的关键帧（<xref:System.Windows.Media.Animation.DiscreteStringKeyFrame>如在值之间创建突然跳转），即动画更改发生得很快，并且不是微妙的。  
  
 [!code-xaml[keyframes_snip#StringAnimationUsingKeyFramesWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/StringAnimationUsingKeyFramesExample.xaml#stringanimationusingkeyframeswholepage)]  
  
 有关完整示例，请参阅[关键帧动画示例](https://github.com/microsoft/WPF-Samples/tree/master/Animation/KeyFrameAnimation)。  
  
## <a name="see-also"></a>请参阅

- <xref:System.Windows.Media.Animation.StringAnimationUsingKeyFrames>
- <xref:System.Windows.Controls.ContentControl.Content%2A>
- <xref:System.Windows.Controls.Button>
- <xref:System.Windows.Media.Animation.DiscreteStringKeyFrame>
- [关键帧动画概述](key-frame-animations-overview.md)
- [关键帧操作说明主题](key-frame-animation-how-to-topics.md)
