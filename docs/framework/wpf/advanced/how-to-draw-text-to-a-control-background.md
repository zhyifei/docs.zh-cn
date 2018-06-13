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
ms.openlocfilehash: f79ec4f2c394fdc9462f4fd00942673b4536d713
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33542972"
---
# <a name="how-to-draw-text-to-a-control39s-background"></a><span data-ttu-id="82ac6-102">如何：将文本绘制到控件的背景上</span><span class="sxs-lookup"><span data-stu-id="82ac6-102">How to: Draw Text to a Control&#39;s Background</span></span>
<span data-ttu-id="82ac6-103">通过将文本字符串转换，可以直接到控件的背景绘制文本<xref:System.Windows.Media.FormattedText>对象，并在其中绘制对象到控件的<xref:System.Windows.Media.DrawingContext>。</span><span class="sxs-lookup"><span data-stu-id="82ac6-103">You can draw text directly to the background of a control by converting a text string to a <xref:System.Windows.Media.FormattedText> object, and then drawing the object to the control's <xref:System.Windows.Media.DrawingContext>.</span></span> <span data-ttu-id="82ac6-104">你也可以使用此方法，从派生的对象的背景的绘制的<xref:System.Windows.Controls.Panel>，如<xref:System.Windows.Controls.Canvas>和<xref:System.Windows.Controls.StackPanel>。</span><span class="sxs-lookup"><span data-stu-id="82ac6-104">You can also use this technique for drawing to the background of objects derived from <xref:System.Windows.Controls.Panel>, such as <xref:System.Windows.Controls.Canvas> and <xref:System.Windows.Controls.StackPanel>.</span></span>  
  
 <span data-ttu-id="82ac6-105">![控件文本作为背景显示](../../../../docs/framework/wpf/advanced/media/drawtext2background01.png "DrawText2Background01")</span><span class="sxs-lookup"><span data-stu-id="82ac6-105">![Controls displaying text as background](../../../../docs/framework/wpf/advanced/media/drawtext2background01.png "DrawText2Background01")</span></span>  
<span data-ttu-id="82ac6-106">具有自定义文本背景的控件的示例</span><span class="sxs-lookup"><span data-stu-id="82ac6-106">Example of controls with custom text backgrounds</span></span>  
  
## <a name="example"></a><span data-ttu-id="82ac6-107">示例</span><span class="sxs-lookup"><span data-stu-id="82ac6-107">Example</span></span>  
 <span data-ttu-id="82ac6-108">若要绘制到控件的背景，创建一个新<xref:System.Windows.Media.DrawingBrush>对象，并绘制对象的已转换的文本<xref:System.Windows.Media.DrawingContext>。</span><span class="sxs-lookup"><span data-stu-id="82ac6-108">To draw to the background of a control, create a new <xref:System.Windows.Media.DrawingBrush> object and draw the converted text to the object's <xref:System.Windows.Media.DrawingContext>.</span></span> <span data-ttu-id="82ac6-109">然后，将分配新<xref:System.Windows.Media.DrawingBrush>到控件的背景属性。</span><span class="sxs-lookup"><span data-stu-id="82ac6-109">Then, assign the new <xref:System.Windows.Media.DrawingBrush> to the control's background property.</span></span>  
  
 <span data-ttu-id="82ac6-110">下面的代码示例演示如何创建<xref:System.Windows.Media.FormattedText>对象，并绘制到的背景<xref:System.Windows.Controls.Label>和<xref:System.Windows.Controls.Button>对象。</span><span class="sxs-lookup"><span data-stu-id="82ac6-110">The following code example shows how to create a <xref:System.Windows.Media.FormattedText> object and draw to the background of a <xref:System.Windows.Controls.Label> and <xref:System.Windows.Controls.Button> object.</span></span>  
  
 [!code-csharp[DrawTextToControlBackground#DrawTextToControlBackground1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawTextToControlBackground/CSHARP/Window1.xaml.cs#drawtexttocontrolbackground1)]  
  
## <a name="see-also"></a><span data-ttu-id="82ac6-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="82ac6-111">See Also</span></span>  
 <xref:System.Windows.Media.FormattedText>  
 [<span data-ttu-id="82ac6-112">绘制格式化文本</span><span class="sxs-lookup"><span data-stu-id="82ac6-112">Drawing Formatted Text</span></span>](../../../../docs/framework/wpf/advanced/drawing-formatted-text.md)
