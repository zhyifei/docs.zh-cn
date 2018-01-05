---
title: "如何：对 Visual 中的几何图形进行命中测试"
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
- hit tests [WPF], on visual objects comprising Geometry objects [WPF]
- visual objects [WPF], hit tests on
- Geometry objects [WPF], visual objects comprising
ms.assetid: 8bf2643f-d7f9-4cb4-9ea6-5b893c23200d
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a990a43853e375c1c97f88dc6792932ad64c8d37
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-hit-test-geometry-in-a-visual"></a>如何：对 Visual 中的几何图形进行命中测试
此示例演示如何在一个或多个组成的视觉对象上执行命中的测试<xref:System.Windows.Media.Geometry>对象。  
  
## <a name="example"></a>示例  
 下面的示例演示如何检索<xref:System.Windows.Media.DrawingGroup>使用的视觉对象从<xref:System.Windows.Media.VisualTreeHelper.GetDrawing%2A>方法。 然后，每个绘图的所呈现内容执行命中的测试<xref:System.Windows.Media.DrawingGroup>来确定点击了哪个几何图形。  
  
> [!NOTE]
>  在大多数情况下，你应该使用<xref:System.Windows.Media.VisualTreeHelper.HitTest%2A>方法来确定点是否与所呈现内容的视觉对象的任何相交。  
  
 [!code-csharp[VisualsOverview#VisualsOverviewSnippet4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/VisualsOverview/CSharp/Window1.xaml.cs#visualsoverviewsnippet4)]
 [!code-vb[VisualsOverview#VisualsOverviewSnippet4](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/VisualsOverview/visualbasic/window1.xaml.vb#visualsoverviewsnippet4)]  
  
 <xref:System.Windows.Media.Geometry.FillContains%2A>方法属于重载的方法，您可以使用指定的命中测试<xref:System.Windows.Point>或<xref:System.Windows.Media.Geometry>。 绘制几何图形时，笔画可以延伸到填充边界之外。 在这种情况下，你可能想要调用<xref:System.Windows.Media.Geometry.StrokeContains%2A>除了<xref:System.Windows.Media.Geometry.FillContains%2A>。  
  
 你还可以提供<xref:System.Windows.Media.ToleranceType>用于贝塞尔平展的目的。  
  
> [!NOTE]
>  此示例并未考虑可能应用到几何图形中的任何变形或剪裁。 此外，此示例不会使用已设置样式的控件，因为这种控件没有与它直接关联的绘图。  
  
## <a name="see-also"></a>请参阅  
 [可视化层中的命中测试](../../../../docs/framework/wpf/graphics-multimedia/hit-testing-in-the-visual-layer.md)  
 [将几何图形用作参数的命中测试](../../../../docs/framework/wpf/graphics-multimedia/how-to-hit-test-using-geometry-as-a-parameter.md)
