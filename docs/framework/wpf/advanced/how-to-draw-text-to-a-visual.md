---
title: 如何：将文本绘制到 Visual 中
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
ms.openlocfilehash: bc7a4f989137ec2b021d27a6e112ff1aebd99d07
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/04/2018
ms.locfileid: "43523238"
---
# <a name="how-to-draw-text-to-a-visual"></a>如何：将文本绘制到 Visual 中
下面的示例演示如何绘制到的文本<xref:System.Windows.Media.DrawingVisual>使用<xref:System.Windows.Media.DrawingContext>对象。 绘图上下文返回通过调用<xref:System.Windows.Media.DrawingVisual.RenderOpen%2A>方法的<xref:System.Windows.Media.DrawingVisual>对象。 您可以绘制图形和文本到绘图上下文。  
  
 若要绘制文本到绘图上下文，请使用<xref:System.Windows.Media.DrawingContext.DrawText%2A>方法的<xref:System.Windows.Media.DrawingContext>对象。 在完成到绘图上下文绘制内容，请调用<xref:System.Windows.Media.DrawingContext.Close%2A>方法来关闭绘图上下文并保留的内容。  
  
## <a name="example"></a>示例  
 [!code-csharp[DrawingVisualSample#110](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingVisualSample/CSharp/Window1.xaml.cs#110)]
 [!code-vb[DrawingVisualSample#110](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DrawingVisualSample/visualbasic/window1.xaml.vb#110)]  
  
> [!NOTE]
>  有关从中提取上述代码示例的完整代码示例，请参阅[使用 DrawingVisual 的命中测试示例](https://go.microsoft.com/fwlink/?LinkID=159994)。
