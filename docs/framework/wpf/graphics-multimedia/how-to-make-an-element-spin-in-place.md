---
title: "如何：使元素就地旋转"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- graphics [WPF], spinning elements
- spinning elements [WPF]
ms.assetid: 1f011976-8b07-4c31-9faf-019e0ddaa24c
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: e7dac2b1afb9d0ed385f3c25c2e30a93ea8a24f5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-make-an-element-spin-in-place"></a>如何：使元素就地旋转
此示例演示如何使某个元素通过使用旋转<xref:System.Windows.Media.RotateTransform>和<xref:System.Windows.Media.Animation.DoubleAnimation>。  
  
 下面的示例应用<xref:System.Windows.Media.RotateTransform>到<xref:System.Windows.UIElement.RenderTransform%2A>元素的属性。 该示例使用<xref:System.Windows.Media.Animation.DoubleAnimation>要进行动画处理<xref:System.Windows.Media.RotateTransform.Angle%2A>的<xref:System.Windows.Media.RotateTransform>。 若要使就地旋转的元素，该示例设置<xref:System.Windows.UIElement.RenderTransformOrigin%2A>点 （0.5，0.5） 将元素的属性。  
  
## <a name="example"></a>示例  
 [!code-xaml[transformanimations_snip#11](../../../../samples/snippets/xaml/VS_Snippets_Wpf/transformanimations_snip/XAML/RotateAboutCenterExample.xaml#11)]  
  
 有关完整的示例，其中包括更多的转换示例，请参阅[二维转换示例](http://go.microsoft.com/fwlink/?LinkID=158252)。  
  
## <a name="see-also"></a>另请参阅  
 [动画概述](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [转换概述](../../../../docs/framework/wpf/graphics-multimedia/transforms-overview.md)
