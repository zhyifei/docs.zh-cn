---
title: "如何：沿着路径针对对象进行动画处理（点动画）"
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
- animation [WPF], objects along paths (point animation)
- point animation [WPF]
ms.assetid: 1fa3f817-35bc-41a1-b366-f5a20b70da0c
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 47cafab505bcbab7008385393bbacf093e264cd9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-animate-an-object-along-a-path-point-animation"></a>如何：沿着路径针对对象进行动画处理（点动画）
此示例演示如何使用<xref:System.Windows.Media.Animation.PointAnimationUsingPath>对象要进行动画处理<xref:System.Windows.Point>沿曲线的路径。  
  
## <a name="example"></a>示例  
 下面的示例将<xref:System.Windows.Media.EllipseGeometry>沿路径由定义<xref:System.Windows.Media.PathGeometry>。 椭圆几何图形<xref:System.Windows.Media.EllipseGeometry.Center%2A>属性，采用<xref:System.Windows.Point>值时，请指定其位置; 若要移动的椭圆的几何图形，你动态显示其<xref:System.Windows.Media.EllipseGeometry.Center%2A>属性。 该示例使用<xref:System.Windows.Media.Animation.PointAnimationUsingPath>要进行动画处理<xref:System.Windows.Media.EllipseGeometry>对象的<xref:System.Windows.Media.EllipseGeometry.Center%2A>属性。  
  
 [!code-xaml[PathAnimationGallery_snippet#PointAnimationUsingPathWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_snippet/CS/pointanimationusingpathexample.xaml#pointanimationusingpathwholepage)]  
  
 [!code-csharp[PathAnimationGallery_procedural_snip#PointAnimationUsingPathWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/CSharp/PointAnimationUsingPathExample.cs#pointanimationusingpathwholepage)]
 [!code-vb[PathAnimationGallery_procedural_snip#PointAnimationUsingPathWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/VisualBasic/PointAnimationUsingPathExample.vb#pointanimationusingpathwholepage)]  
  
 有关完整的示例，请参阅[路径动画示例](http://go.microsoft.com/fwlink/?LinkID=160028)。  
  
 上面的示例使用的代码版本<xref:System.Windows.Media.Animation.Storyboard>要进行动画处理<xref:System.Windows.Media.EllipseGeometry>，即使只有一个动画已应用。 A<xref:System.Windows.Media.Animation.Storyboard>通常是因为这些动画可以控制由同一个应用的多个动画的最简单办法<xref:System.Windows.Media.Animation.Storyboard>。 但是，若要将单个动画应用到的属性，使用代码时更简单的方法是使用<xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A>方法。 有关示例，请参阅[在不使用情节提要的情况下对属性进行动画处理](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-without-using-a-storyboard.md)。  
  
## <a name="see-also"></a>另请参阅  
 [路径动画示例](http://go.microsoft.com/fwlink/?LinkID=160028)  
 [动画概述](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [路径动画操作说明主题](../../../../docs/framework/wpf/graphics-multimedia/path-animation-how-to-topics.md)
