---
title: "如何：在事件发生时向元素应用变换"
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
- graphics [WPF], transformations as event responses
- properties [WPF], LayoutTransform
- transformations as event responses [WPF]
- properties [WPF], RenderTransform
- LayoutTransform property [WPF]
ms.assetid: 71e4327e-ca57-444c-a3cf-09fb381491a0
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 58ef8c008eea4c10228ebb10ceadb5806dfbc0f4
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-apply-a-transform-to-an-element-when-an-event-occurs"></a>如何：在事件发生时向元素应用变换
此示例演示如何将应用<xref:System.Windows.Media.ScaleTransform>事件发生时。 此处说明的概念与用于应用其他类型的转换的概念相同。 有关可用类型的转换的详细信息，请参阅<xref:System.Windows.Media.Transform>类或[转换概述](../../../../docs/framework/wpf/graphics-multimedia/transforms-overview.md)。  
  
 可以通过以下两种方式之一向元素应用转换：  
  
-   如果这样做*不*想要将影响布局，请使用的转换<xref:System.Windows.UIElement.RenderTransform%2A>元素的属性。  
  
-   如果你确实想要将影响布局的转换，使用<xref:System.Windows.FrameworkElement.LayoutTransform%2A>元素的属性。  
  
 下面的示例应用<xref:System.Windows.Media.ScaleTransform>到<xref:System.Windows.UIElement.RenderTransform%2A>的按钮的属性。 当鼠标移到按钮时,<xref:System.Windows.Media.ScaleTransform.ScaleX%2A>和<xref:System.Windows.Media.ScaleTransform.ScaleY%2A>属性<xref:System.Windows.Media.ScaleTransform>设置为`2`，这将导致按钮变得更大。 当鼠标离开该按钮，<xref:System.Windows.Media.ScaleTransform.ScaleX%2A>和<xref:System.Windows.Media.ScaleTransform.ScaleY%2A>设置为`1`，这将导致按钮以返回到其原始大小。  
  
## <a name="example"></a>示例  
 [!code-xaml[ButtonTransform#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ButtonTransform/CSharp/ButtonTransformExample.xaml#1)]  
  
 [!code-csharp[ButtonTransform#1cb](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ButtonTransform/CSharp/ButtonTransformExample.xaml.cs#1cb)]
 [!code-vb[ButtonTransform#1cb](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ButtonTransform/VisualBasic/ButtonTransformExample.xaml.vb#1cb)]  
  
## <a name="see-also"></a>另请参阅  
 <xref:System.Windows.Media.Transform>  
 <xref:System.Windows.Media.ScaleTransform>  
 [转换概述](../../../../docs/framework/wpf/graphics-multimedia/transforms-overview.md)  
 [操作说明主题](../../../../docs/framework/wpf/graphics-multimedia/transformations-how-to-topics.md)  
 [路由事件概述](../../../../docs/framework/wpf/advanced/routed-events-overview.md)
