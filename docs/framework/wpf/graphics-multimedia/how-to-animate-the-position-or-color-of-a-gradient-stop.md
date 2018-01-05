---
title: "如何：对渐变停止点的位置或颜色进行动画处理"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- position [WPF], animating
- animation [WPF], position of GradientStop objects
- GradientStop objects [WPF], animating color of
- colors [WPF], animating
- animation [WPF], color of GradientStop objects
- GradientStop objects [WPF], animating position of
ms.assetid: 6f5b8b47-6c32-4b8e-98ee-fdf6515ec843
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 9c5a72d5df9d7ff9cdd90d6e09a7dab574e2caaf
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-animate-the-position-or-color-of-a-gradient-stop"></a>如何：对渐变停止点的位置或颜色进行动画处理
此示例演示如何进行动画处理<xref:System.Windows.Media.GradientStop.Color%2A>和<xref:System.Windows.Media.GradientStop.Offset%2A>的<xref:System.Windows.Media.GradientStop>对象。  
  
## <a name="example"></a>示例  
 下面的示例进行动画处理内的三个梯度停止点<xref:System.Windows.Media.LinearGradientBrush>。 该示例使用三个动画，其中每个进行动画处理不同的渐变停止点：  
  
-   第一个动画， <xref:System.Windows.Media.Animation.DoubleAnimation>，进行动画处理对第一个渐变停止点的<xref:System.Windows.Media.GradientStop.Offset%2A>从 0.0 到 1.0，然后再为 0.0。 因此，第一个中，渐变将在从左边算矩形的右侧颜色，然后再返回到左侧。  
  
-   第二个动画， <xref:System.Windows.Media.Animation.ColorAnimation>，进行动画处理对第二个渐变停止点的<xref:System.Windows.Media.GradientStop.Color%2A>从<xref:System.Windows.Media.Colors.Purple%2A>到<xref:System.Windows.Media.Colors.Yellow%2A>和再转回<xref:System.Windows.Media.Colors.Purple%2A>。 因此，为黄色，并返回到紫色，从紫色将更改渐变中的中间颜色。  
  
-   第三个动画，另一个<xref:System.Windows.Media.Animation.ColorAnimation>，进行动画处理的第三个渐变停止点的不透明度<xref:System.Windows.Media.GradientStop.Color%2A>乘以-1，然后再设置。 因此，渐变中的第三个颜色淡出，然后再次变得不透明。  
  
 [!code-csharp[BrushesIntroduction_snip#GraphicsMMGradientAnimationExamplesWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/GradientStopAnimationExample.cs#graphicsmmgradientanimationexampleswholepage)]
 [!code-vb[BrushesIntroduction_snip#GraphicsMMGradientAnimationExamplesWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/gradientstopanimationexample.vb#graphicsmmgradientanimationexampleswholepage)]
 [!code-xaml[BrushesIntroduction_snip#GraphicsMMGradientAnimationExamplesWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/GradientStopAnimationExample.xaml#graphicsmmgradientanimationexampleswholepage)]  
  
 虽然此示例使用<xref:System.Windows.Media.LinearGradientBrush>，过程是相同进行动画处理<xref:System.Windows.Media.GradientStop>对象内<xref:System.Windows.Media.RadialGradientBrush>。  
  
 有关其他示例，请参阅[画笔示例](http://go.microsoft.com/fwlink/?LinkID=159973)。  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Windows.Media.GradientStop>  
 [动画概述](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [演示图板概述](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md)
