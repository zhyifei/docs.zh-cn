---
title: "如何：创建复合形状"
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
- shapes [WPF], composite
- composite shapes [WPF]
- graphics [WPF], composite shapes
ms.assetid: 8e5c7ef4-d7ed-4c43-afc9-ca01325c300b
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 9ded7bd25f7f416bc512051f883b4ae12b2fa56d
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-create-a-composite-shape"></a>如何：创建复合形状
此示例演示如何创建使用复合形状<xref:System.Windows.Media.Geometry>对象并将其显示使用<xref:System.Windows.Shapes.Path>元素。 在下面的示例中， <xref:System.Windows.Media.LineGeometry>， <xref:System.Windows.Media.EllipseGeometry>，和一个<xref:System.Windows.Media.RectangleGeometry>用于<xref:System.Windows.Media.GeometryGroup>来创建的复合的形状。 然后使用绘制几何图形的<xref:System.Windows.Shapes.Path>元素。  
  
## <a name="example"></a>示例  
 [!code-xaml[GeometrySample#19](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/combininggeometriesexample.xaml#19)]  
  
 [!code-csharp[GeometriesMiscSnippets_procedural_snip#CompositeShapeCodeExampleInline1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometriesMiscSnippets_procedural_snip/CSharp/CompositeShapeExample.cs#compositeshapecodeexampleinline1)]
 [!code-vb[GeometriesMiscSnippets_procedural_snip#CompositeShapeCodeExampleInline1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/GeometriesMiscSnippets_procedural_snip/visualbasic/compositeshapeexample.vb#compositeshapecodeexampleinline1)]  
  
 下图显示在上一个示例中创建的形状。  
  
 ![使用 GeometryGroup 创建的复合几何图形](../../../../docs/framework/wpf/graphics-multimedia/media/wcpsdk-graphicsmm-compositegeometryexample1.jpg "wcpsdk_graphicsmm_compositegeometryexample1")  
复合几何图形  
  
 可能使用创建更复杂的形状，如多边形和使用曲线的段的形状<xref:System.Windows.Media.PathGeometry>。 有关演示如何创建形状使用的示例<xref:System.Windows.Media.PathGeometry>，请参阅[通过使用一个 PathGeometry 创建的形状](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-shape-by-using-a-pathgeometry.md)。  虽然此示例的呈现到屏幕使用形状<xref:System.Windows.Shapes.Path>元素，<xref:System.Windows.Media.Geometry>对象也可能用于描述的内容<xref:System.Windows.Media.GeometryDrawing>或<xref:System.Windows.Media.DrawingContext>。 它们可能还用于剪辑和命中测试。  
  
 此示例是更大示例的组成部分；有关完整示例，请参阅[几何图形示例](http://go.microsoft.com/fwlink/?LinkID=159989)。
