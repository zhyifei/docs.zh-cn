---
title: "如何：绘制线条"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- drawing [WPF], lines
- graphics [WPF], lines
- lines [WPF], drawing
ms.assetid: 0513ee01-6b27-4bb3-85f3-3a3e6710d80e
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 4911aea91416fb84e9a18d54c145b494737ef9dd
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-draw-a-line"></a>如何：绘制线条
此示例演示如何通过使用绘制线条<xref:System.Windows.Shapes.Line>元素。  
  
 若要绘制线条，创建<xref:System.Windows.Shapes.Line>元素。 使用其<xref:System.Windows.Shapes.Line.X1%2A>和<xref:System.Windows.Shapes.Line.Y1%2A>属性来设置其起始点; 并使用其<xref:System.Windows.Shapes.Line.X2%2A>和<xref:System.Windows.Shapes.Line.Y2%2A>要设置其终结点的属性。 最后，设置其<xref:System.Windows.Shapes.Shape.Stroke%2A>和<xref:System.Windows.Shapes.Shape.StrokeThickness%2A>因为没有笔画行是不可见。  
  
 设置<xref:System.Windows.Shapes.Shape.Fill%2A>的行的元素具有不起作用，因为行具有没有内部区域。  
  
 下面的示例绘制内的三行<xref:System.Windows.Controls.Canvas>元素。  
  
## <a name="example"></a>示例  
 [!code-xaml[drawingwithshapeelements#LineExample1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/lineexample.xaml#lineexample1)]  
  
 此示例摘自更大的示例;有关完整的示例，请参阅[形状元素示例](http://go.microsoft.com/fwlink/?LinkID=160037)。  
  
## <a name="see-also"></a>另请参阅  
 <xref:System.Windows.Shapes.Line>  
 [形状元素示例](http://go.microsoft.com/fwlink/?LinkID=160037)
