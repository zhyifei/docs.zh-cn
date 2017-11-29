---
title: "如何：对 FrameworkElement 的大小进行动画处理"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- animation [WPF], FrameworkElement size
- FrameworkElement [WPF], animating size of
ms.assetid: d4cd5a13-c20d-4a6f-a2ba-14f2c9ce4cef
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 17882494e48c5d692c8a774e6d77408557976c71
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-animate-the-size-of-a-frameworkelement"></a>如何：对 FrameworkElement 的大小进行动画处理
要进行动画处理的大小<xref:System.Windows.FrameworkElement>，你可以对其<xref:System.Windows.FrameworkElement.Width%2A>和<xref:System.Windows.FrameworkElement.Height%2A>属性或使用经过动画处理的<xref:System.Windows.Media.ScaleTransform>。  
  
 在下面的示例以进行动画处理使用这两种方法的两个按钮的大小。 通过对进行动画处理调整一个按钮的大小及其<xref:System.Windows.FrameworkElement.Width%2A>通过进行动画处理调整大小属性，另一个<xref:System.Windows.Media.ScaleTransform>应用于其<xref:System.Windows.UIElement.RenderTransform%2A>属性。 每个按钮包含一些文本。 最初，则将显示文本中两个按钮相同，但按钮是调整大小时，在第二个按钮的文本会显得失真。  
  
## <a name="example"></a>示例  
 [!code-xaml[transformanimations_snip#1](../../../../samples/snippets/xaml/VS_Snippets_Wpf/transformanimations_snip/XAML/AnimatingSizeExample.xaml#1)]  
  
 当你转换元素时, 转换整个元素和其内容。 当您直接改变元素，如下所示的第一个按钮，这种情况的大小除非其大小和位置取决于其父元素的大小无法调整大小的元素的内容。  
  
 通过应用到动画的转换对元素的大小进行动画处理其<xref:System.Windows.UIElement.RenderTransform%2A>属性提供更好的性能不是动画处理其<xref:System.Windows.FrameworkElement.Width%2A>和<xref:System.Windows.FrameworkElement.Height%2A>直接，因为<xref:System.Windows.UIElement.RenderTransform%2A>属性不会触发了布局过程。  
  
 有关对属性进行动画处理的详细信息，请参阅[动画概述](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)。 有关转换的详细信息，请参阅[转换概述](../../../../docs/framework/wpf/graphics-multimedia/transforms-overview.md)。
