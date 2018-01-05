---
title: "如何：绘制带有线性渐变的区域"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- linear gradients [WPF], painting with
- brushes [WPF], painting with linear gradients
- painting [WPF], with linear gradients
ms.assetid: 00e0cd04-48c0-4ec5-850e-d321beb37a34
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: eec4ec2fc7ba99081eaafa6803d20c99bebc6c2f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-paint-an-area-with-a-linear-gradient"></a>如何：绘制带有线性渐变的区域
此示例演示如何使用<xref:System.Windows.Media.LinearGradientBrush>类，以使用线性渐变绘制区域。 在下面的示例中，<xref:System.Windows.Shapes.Shape.Fill%2A>的<xref:System.Windows.Shapes.Rectangle>用黄色从过渡到红色以蓝色和浅绿色对角线方向线性渐变绘制。  
  
## <a name="example"></a>示例  
 [!code-xaml[GradientBrushExamples_snip#DiagonalGradient1XAML](../../../../samples/snippets/xaml/VS_Snippets_Wpf/GradientBrushExamples_snip/XAML/LinearGradientBrushExample.xaml#diagonalgradient1xaml)]  
  
 [!code-csharp[GradientBrushExamples_snip#DiagonalGradient1CSharp](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GradientBrushExamples_snip/CSharp/LinearGradientBrushExample.cs#diagonalgradient1csharp)]  
  
 下图显示了前面的示例所创建的渐变。  
  
 ![对角线方向线性渐变](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-diagonallgb.jpg "graphicsmm_DiagonalLGB")  
  
 若要创建的水平线性渐变，更改<xref:System.Windows.Media.LinearGradientBrush.StartPoint%2A>和<xref:System.Windows.Media.LinearGradientBrush.EndPoint%2A>的<xref:System.Windows.Media.LinearGradientBrush>到 (0,0.5) 和 (1,0.5)。 在下面的示例中，<xref:System.Windows.Shapes.Rectangle>使用水平线性渐变绘制。  
  
 [!code-xaml[GradientBrushExamples_snip#HorizontalGradient1XAML](../../../../samples/snippets/xaml/VS_Snippets_Wpf/GradientBrushExamples_snip/XAML/LinearGradientBrushExample.xaml#horizontalgradient1xaml)]  
  
 [!code-csharp[GradientBrushExamples_snip#HorizontalGradient1CSharp](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GradientBrushExamples_snip/CSharp/LinearGradientBrushExample.cs#horizontalgradient1csharp)]  
  
 下图显示了前面的示例所创建的渐变。  
  
 ![水平线性渐变](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-horizontallgb.jpg "graphicsmm_HorizontalLGB")  
  
 若要创建垂直线性渐变，更改<xref:System.Windows.Media.LinearGradientBrush.StartPoint%2A>和<xref:System.Windows.Media.LinearGradientBrush.EndPoint%2A>的<xref:System.Windows.Media.LinearGradientBrush>到 (0.5，0) 和 (0.5，1)。 在下面的示例中，<xref:System.Windows.Shapes.Rectangle>使用垂直线性渐变绘制。  
  
 [!code-xaml[GradientBrushExamples_snip#VerticalGradient1XAML](../../../../samples/snippets/xaml/VS_Snippets_Wpf/GradientBrushExamples_snip/XAML/LinearGradientBrushExample.xaml#verticalgradient1xaml)]  
  
 [!code-csharp[GradientBrushExamples_snip#VerticalGradient1CSharp](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GradientBrushExamples_snip/CSharp/LinearGradientBrushExample.cs#verticalgradient1csharp)]  
  
 下图显示了前面的示例所创建的渐变。  
  
 ![垂直线性渐变](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-verticallgb.jpg "graphicsmm_VerticalLGB")  
  
> [!NOTE]
>  本主题中的示例使用默认坐标系统，用于设置的起始点和终结点。 默认坐标系统是相对于边界框： 0 表示的边界框中，0%和 1 表示 100%的边界框。 你可以通过设置来更改此坐标系<xref:System.Windows.Media.GradientBrush.MappingMode%2A>属性值<xref:System.Windows.Media.BrushMappingMode.Absolute?displayProperty=nameWithType>。 绝对坐标系与范围框无关。 值直接在本地空间中解释。  
  
 有关其他示例，请参阅[画笔示例](http://go.microsoft.com/fwlink/?LinkID=159973)。 有关渐变和画笔的其他类型的详细信息，请参阅[使用纯色和渐变概述绘制](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md)。
