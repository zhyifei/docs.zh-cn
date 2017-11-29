---
title: "如何：缩放元素"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- scaling [WPF], elements
- graphics [WPF], scaling elements
ms.assetid: 18158d94-bbe7-4f6a-814e-84d27fa748bf
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 23b3086452526e804bfdbe50bb0c134f33158f5d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-scale-an-element"></a>如何：缩放元素
此示例演示如何使用<xref:System.Windows.Media.ScaleTransform>来缩放元素。  
  
 使用<xref:System.Windows.Media.ScaleTransform.ScaleX%2A>和<xref:System.Windows.Media.ScaleTransform.ScaleY%2A>属性，以调整元素大小按指定的因子。 例如，<xref:System.Windows.Media.ScaleTransform.ScaleX%2A>值为 1.5 拉伸到其原始宽度的 150%的元素。 A<xref:System.Windows.Media.ScaleTransform.ScaleY%2A>值为 0.5 时，会元素的高度缩小 50%。  
  
 使用<xref:System.Windows.Media.ScaleTransform.CenterX%2A>和<xref:System.Windows.Media.ScaleTransform.CenterY%2A>属性以指定的点的缩放操作的中心。 默认情况下，<xref:System.Windows.Media.ScaleTransform>以对应的矩形的左上角的点 (0，0)，为中心。 此操作将该元素移动以及使其看上去更大，因为当你将<xref:System.Windows.Media.Transform>，更改对象驻留在其中的坐标空间。  
  
 下面的示例使用<xref:System.Windows.Media.ScaleTransform>为双精度，大小为 50 的 50 <xref:System.Windows.Shapes.Rectangle>。 <xref:System.Windows.Media.ScaleTransform>两个具有值为 0 （默认值）<xref:System.Windows.Media.ScaleTransform.CenterX%2A>和<xref:System.Windows.Media.ScaleTransform.CenterY%2A>。  
  
## <a name="example"></a>示例  
 [!code-xaml[transformsSample#21](../../../../samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/ScaleTransformExample.xaml#21)]  
  
 通常情况下，设置<xref:System.Windows.Media.ScaleTransform.CenterX%2A>和<xref:System.Windows.Media.ScaleTransform.CenterY%2A>到中心进行缩放后的对象: (<xref:System.Windows.FrameworkElement.Width%2A>/月 2 日，  <xref:System.Windows.FrameworkElement.Height%2A> /2)。  
  
 下面的示例显示另一种<xref:System.Windows.Shapes.Rectangle>，加倍大小; 但是，这<xref:System.Windows.Media.ScaleTransform>两个具有值为 25<xref:System.Windows.Media.ScaleTransform.CenterX%2A>和<xref:System.Windows.Media.ScaleTransform.CenterY%2A>，这对应于矩形的中心。  
  
 [!code-xaml[transformsSample#22](../../../../samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/ScaleTransformExample.xaml#22)]  
  
 下图显示这两者之间的差异<xref:System.Windows.Media.ScaleTransform>操作。 虚线显示的是矩形在缩放之前的大小和位置。  
  
 ![以不同中心点进行的 2x 缩放](../../../../docs/framework/wpf/graphics-multimedia/media/wcpsdk-graphicsmm-scalecenter.gif "wcpsdk_graphicsmm_scalecenter")  
两个具有相同 ScaleX 和 ScaleY 值但中心不同的 ScaleTransform 操作  
  
 有关完整示例，请参阅 [2D 转换示例](http://go.microsoft.com/fwlink/?LinkID=158252)。  
  
## <a name="see-also"></a>另请参阅  
 <xref:System.Windows.Media.Transform>  
 <xref:System.Windows.Media.ScaleTransform>  
 [转换概述](../../../../docs/framework/wpf/graphics-multimedia/transforms-overview.md)  
 [操作说明主题](../../../../docs/framework/wpf/graphics-multimedia/transformations-how-to-topics.md)
