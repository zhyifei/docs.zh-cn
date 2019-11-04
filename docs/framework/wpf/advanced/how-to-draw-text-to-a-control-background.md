---
title: 如何：将文本绘制到控件的背景上
ms.date: 03/30/2017
helpviewer_keywords:
- controls [WPF], drawing text to backgrounds
- text [WPF], drawing to control backgrounds
- drawing [WPF], text to control backgrounds
- backgrounds [WPF], drawing text to
- typography [WPF], drawing text to control backgrounds
ms.assetid: 686d8fba-f61c-4974-a871-c635d67a7f69
ms.openlocfilehash: 14300f763b67c6ac67ee408de2009c328d499c13
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/01/2019
ms.locfileid: "73424365"
---
# <a name="how-to-draw-text-to-a-controls-background"></a>如何：将文本绘制到控件的背景上
您可以通过将文本字符串转换为 <xref:System.Windows.Media.FormattedText> 的对象，然后将该对象绘制到控件的 <xref:System.Windows.Media.DrawingContext>中，直接将文本绘制到控件的背景中。 你还可以使用此方法来绘制到 <xref:System.Windows.Controls.Panel>的派生对象的背景，例如 <xref:System.Windows.Controls.Canvas> 和 <xref:System.Windows.Controls.StackPanel>。  
  
 ![以背景形式显示文本的控件的屏幕截图。](./media/how-to-draw-text-to-a-control-background/draw-text-background.png "DrawText2Background01")  
具有自定义文本背景的控件的示例  
  
## <a name="example"></a>示例  
 若要在控件的背景上绘制，请创建新的 <xref:System.Windows.Media.DrawingBrush> 对象，并将转换后的文本绘制到对象的 <xref:System.Windows.Media.DrawingContext>中。 然后，将新 <xref:System.Windows.Media.DrawingBrush> 分配给控件的背景属性。  
  
 下面的代码示例演示如何创建 <xref:System.Windows.Media.FormattedText> 对象并将其绘制到 <xref:System.Windows.Controls.Label> 和 <xref:System.Windows.Controls.Button> 对象的背景。  
  
 [!code-csharp[DrawTextToControlBackground#DrawTextToControlBackground1](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawTextToControlBackground/CSHARP/Window1.xaml.cs#drawtexttocontrolbackground1)]  
  
## <a name="see-also"></a>请参阅

- <xref:System.Windows.Media.FormattedText>
- [绘制格式化文本](drawing-formatted-text.md)
