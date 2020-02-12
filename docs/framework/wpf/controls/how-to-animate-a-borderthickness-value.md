---
title: 如何：对 BorderThickness 值进行动画处理
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- border thickness [WPF], animating changes to
- animation [WPF], changes to border thickness
ms.assetid: fd021978-f74b-4e7b-a7f7-3987dcad9e0f
ms.openlocfilehash: 4533ce6f2a1fe7243267ee8d638e2ad0a4f9cf3a
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/11/2020
ms.locfileid: "77124658"
---
# <a name="how-to-animate-a-borderthickness-value"></a>如何：对 BorderThickness 值进行动画处理
此示例演示如何使用 <xref:System.Windows.Media.Animation.ThicknessAnimation> 类对边框的粗细进行动画处理。  
  
## <a name="example"></a>示例  
 下面的示例使用 <xref:System.Windows.Media.Animation.ThicknessAnimation>对边框的粗细进行动画处理。 该示例使用 <xref:System.Windows.Controls.Border>的 <xref:System.Windows.Controls.Border.BorderThickness%2A> 属性。  
  
 [!code-csharp[BasicAnimations_snip#ThicknessAnimationWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/BasicAnimations_snip/CSharp/ThicknessAnimationExample.cs#thicknessanimationwholepage)]
 [!code-vb[BasicAnimations_snip#ThicknessAnimationWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BasicAnimations_snip/VisualBasic/ThicknessAnimationExample.vb#thicknessanimationwholepage)]  
  
 有关完整示例，请参阅[动画示例库](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/AnimationExamples)。  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Media.Animation.ThicknessAnimation>
- <xref:System.Windows.Controls.Border.BorderThickness%2A>
- <xref:System.Windows.Controls.Border>
- [动画概述](../graphics-multimedia/animation-overview.md)
- [动画和计时操作指南主题](../graphics-multimedia/animation-and-timing-how-to-topics.md)
- [使用关键帧为边框粗细设置动画效果](../graphics-multimedia/how-to-animate-the-thickness-of-a-border-by-using-key-frames.md)
