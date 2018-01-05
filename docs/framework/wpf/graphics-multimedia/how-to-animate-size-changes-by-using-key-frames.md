---
title: "如何：使用关键帧对大小变化进行动画处理"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- key frames [WPF], animating size changes with
- animation [WPF], size changes with key frames
- size changes [WPF], animating with key frames
ms.assetid: 86bd2950-d4c9-4ec4-aa8d-7dc3ccadded4
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 30ee897efd01712bf4313da87e1050c5a16e4523
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-animate-size-changes-by-using-key-frames"></a>如何：使用关键帧对大小变化进行动画处理
此示例演示如何使用关键帧对大小变化进行动画处理。  
  
## <a name="example"></a>示例  
 下面的示例使用<xref:System.Windows.Media.Animation.SizeAnimationUsingKeyFrames>类进行动画处理<xref:System.Windows.Media.ArcSegment.Size%2A>属性<xref:System.Windows.Media.ArcSegment>。 此动画按以下方式使用三个关键帧：  
  
1.  在第一个半秒的动画，使用的是实例<xref:System.Windows.Media.Animation.LinearSizeKeyFrame>类，以逐渐增加弧的大小。之类的线性的关键帧<xref:System.Windows.Media.Animation.LinearSizeKeyFrame>创建平滑的值之间的线性转换。  
  
2.  在下一步的末尾半秒，将使用的实例<xref:System.Windows.Media.Animation.DiscreteSizeKeyFrame>类突然增加弧的大小。之类的离散的关键帧<xref:System.Windows.Media.Animation.DiscreteSizeKeyFrame>突变值，即，大小更改突然发生，并且不是细微。  
  
3.  通过最后两秒内，使用的实例<xref:System.Windows.Media.Animation.SplineSizeKeyFrame>类以增加弧的大小。之类的样条关键帧<xref:System.Windows.Media.Animation.SplineSizeKeyFrame>创建变量的值根据值之间转换<xref:System.Windows.Media.Animation.SplineSizeKeyFrame.KeySpline%2A>属性。 在本例中，弧的大小开始时缓慢增加，然后以指数方式增加，直到时间段结束。  
  
 [!code-xaml[keyframes_snip#SizeAnimationUsingKeyFramesWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/SizeAnimationUsingKeyFramesExample.xaml#sizeanimationusingkeyframeswholepage)]  
  
 有关完整示例，请参阅[关键帧动画示例](http://go.microsoft.com/fwlink/?LinkID=160012)。  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Windows.Media.Animation.SizeAnimationUsingKeyFrames>  
 <xref:System.Windows.Media.ArcSegment.Size%2A>  
 <xref:System.Windows.Media.ArcSegment>  
 <xref:System.Windows.Media.Animation.LinearSizeKeyFrame>  
 <xref:System.Windows.Media.Animation.DiscreteSizeKeyFrame>  
 <xref:System.Windows.Media.Animation.SplineSizeKeyFrame>  
 [关键帧动画概述](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)  
 [关键帧操作说明主题](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animation-how-to-topics.md)
