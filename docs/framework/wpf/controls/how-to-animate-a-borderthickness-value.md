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
ms.openlocfilehash: 10e177d1f6d6add4638ce14af900e75d7e363890
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59150730"
---
# <a name="how-to-animate-a-borderthickness-value"></a>如何：对 BorderThickness 值进行动画处理
此示例演示如何使用更改对边框的粗细进行动画处理<xref:System.Windows.Media.Animation.ThicknessAnimation>类。  
  
## <a name="example"></a>示例  
 下面的示例通过使用进行动画处理对边框的粗细<xref:System.Windows.Media.Animation.ThicknessAnimation>。 该示例使用<xref:System.Windows.Controls.Border.BorderThickness%2A>属性的<xref:System.Windows.Controls.Border>。  
  
 [!code-csharp[BasicAnimations_snip#ThicknessAnimationWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/BasicAnimations_snip/CSharp/ThicknessAnimationExample.cs#thicknessanimationwholepage)]
 [!code-vb[BasicAnimations_snip#ThicknessAnimationWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BasicAnimations_snip/VisualBasic/ThicknessAnimationExample.vb#thicknessanimationwholepage)]  
  
 有关完整示例，请参阅[动画示例库](https://go.microsoft.com/fwlink/?LinkID=159969)。  
  
## <a name="see-also"></a>请参阅

- <xref:System.Windows.Media.Animation.ThicknessAnimation>
- <xref:System.Windows.Controls.Border.BorderThickness%2A>
- <xref:System.Windows.Controls.Border>
- [动画概述](../graphics-multimedia/animation-overview.md)
- [动画和计时操作指南主题](../graphics-multimedia/animation-and-timing-how-to-topics.md)
- [使用关键帧为边框粗细设置动画效果](../graphics-multimedia/how-to-animate-the-thickness-of-a-border-by-using-key-frames.md)
