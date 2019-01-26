---
title: 如何：将文本绘制到控件&#39;的背景
ms.date: 03/30/2017
helpviewer_keywords:
- controls [WPF], drawing text to backgrounds
- text [WPF], drawing to control backgrounds
- drawing [WPF], text to control backgrounds
- backgrounds [WPF], drawing text to
- typography [WPF], drawing text to control backgrounds
ms.assetid: 686d8fba-f61c-4974-a871-c635d67a7f69
ms.openlocfilehash: d580330de5ef3841979fffc61db336064f1643f0
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54740408"
---
# <a name="how-to-draw-text-to-a-control39s-background"></a>如何：将文本绘制到控件&#39;的背景
可以直接到控件的背景中绘制文本的文本字符串转换为<xref:System.Windows.Media.FormattedText>对象，并在其中绘制到控件的对象<xref:System.Windows.Media.DrawingContext>。 此外可以使用此技术用于绘制到的对象的背景派生自<xref:System.Windows.Controls.Panel>，如<xref:System.Windows.Controls.Canvas>和<xref:System.Windows.Controls.StackPanel>。  
  
 ![文本显示为背景的控件](../../../../docs/framework/wpf/advanced/media/drawtext2background01.png "DrawText2Background01")  
具有自定义文本背景的控件的示例  
  
## <a name="example"></a>示例  
 若要绘制到控件的背景，请创建一个新<xref:System.Windows.Media.DrawingBrush>对象，并绘制到对象的已转换的文本<xref:System.Windows.Media.DrawingContext>。 然后，将分配新<xref:System.Windows.Media.DrawingBrush>给控件的背景属性。  
  
 下面的代码示例演示如何创建<xref:System.Windows.Media.FormattedText>对象，并绘制到背景<xref:System.Windows.Controls.Label>和<xref:System.Windows.Controls.Button>对象。  
  
 [!code-csharp[DrawTextToControlBackground#DrawTextToControlBackground1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawTextToControlBackground/CSHARP/Window1.xaml.cs#drawtexttocontrolbackground1)]  
  
## <a name="see-also"></a>请参阅
- <xref:System.Windows.Media.FormattedText>
- [绘制格式化文本](../../../../docs/framework/wpf/advanced/drawing-formatted-text.md)
