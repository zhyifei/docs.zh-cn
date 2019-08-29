---
title: 如何：向视觉对象绘制文本
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- typography [WPF], drawing text to visuals
- visuals [WPF], drawing text to
- text [WPF], drawing to visuals
- drawing [WPF], text to visuals
ms.assetid: fee4003c-e8a6-46ec-babd-2c7f4231a101
ms.openlocfilehash: bd760a06150098d0fff17dbdce95b55a0e5fe713
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69963846"
---
# <a name="how-to-draw-text-to-a-visual"></a>如何：向视觉对象绘制文本
下面的示例演示如何<xref:System.Windows.Media.DrawingVisual> <xref:System.Windows.Media.DrawingContext>使用对象将文本绘制到。 通过调用<xref:System.Windows.Media.DrawingVisual.RenderOpen%2A> <xref:System.Windows.Media.DrawingVisual>对象的方法来返回一个绘图上下文。 您可以在绘图上下文中绘制图形和文本。  
  
 若要在绘图上下文中绘制文本, 请<xref:System.Windows.Media.DrawingContext.DrawText%2A>使用<xref:System.Windows.Media.DrawingContext>对象的方法。 完成将内容绘制到绘图上下文中后, 调用<xref:System.Windows.Media.DrawingContext.Close%2A>方法关闭绘图上下文并保存内容。  
  
## <a name="example"></a>示例  
 [!code-csharp[DrawingVisualSample#110](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingVisualSample/CSharp/Window1.xaml.cs#110)]
 [!code-vb[DrawingVisualSample#110](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DrawingVisualSample/visualbasic/window1.xaml.vb#110)]  
  
> [!NOTE]
> 有关从中提取上述代码示例的完整代码示例，请参阅[使用 DrawingVisual 的命中测试示例](https://go.microsoft.com/fwlink/?LinkID=159994)。
