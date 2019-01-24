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
# <a name="how-to-draw-text-to-a-control39s-background"></a><span data-ttu-id="2d598-102">如何：将文本绘制到控件&#39;的背景</span><span class="sxs-lookup"><span data-stu-id="2d598-102">How to: Draw Text to a Control&#39;s Background</span></span>
<span data-ttu-id="2d598-103">可以直接到控件的背景中绘制文本的文本字符串转换为<xref:System.Windows.Media.FormattedText>对象，并在其中绘制到控件的对象<xref:System.Windows.Media.DrawingContext>。</span><span class="sxs-lookup"><span data-stu-id="2d598-103">You can draw text directly to the background of a control by converting a text string to a <xref:System.Windows.Media.FormattedText> object, and then drawing the object to the control's <xref:System.Windows.Media.DrawingContext>.</span></span> <span data-ttu-id="2d598-104">此外可以使用此技术用于绘制到的对象的背景派生自<xref:System.Windows.Controls.Panel>，如<xref:System.Windows.Controls.Canvas>和<xref:System.Windows.Controls.StackPanel>。</span><span class="sxs-lookup"><span data-stu-id="2d598-104">You can also use this technique for drawing to the background of objects derived from <xref:System.Windows.Controls.Panel>, such as <xref:System.Windows.Controls.Canvas> and <xref:System.Windows.Controls.StackPanel>.</span></span>  
  
 <span data-ttu-id="2d598-105">![文本显示为背景的控件](../../../../docs/framework/wpf/advanced/media/drawtext2background01.png "DrawText2Background01")</span><span class="sxs-lookup"><span data-stu-id="2d598-105">![Controls displaying text as background](../../../../docs/framework/wpf/advanced/media/drawtext2background01.png "DrawText2Background01")</span></span>  
<span data-ttu-id="2d598-106">具有自定义文本背景的控件的示例</span><span class="sxs-lookup"><span data-stu-id="2d598-106">Example of controls with custom text backgrounds</span></span>  
  
## <a name="example"></a><span data-ttu-id="2d598-107">示例</span><span class="sxs-lookup"><span data-stu-id="2d598-107">Example</span></span>  
 <span data-ttu-id="2d598-108">若要绘制到控件的背景，请创建一个新<xref:System.Windows.Media.DrawingBrush>对象，并绘制到对象的已转换的文本<xref:System.Windows.Media.DrawingContext>。</span><span class="sxs-lookup"><span data-stu-id="2d598-108">To draw to the background of a control, create a new <xref:System.Windows.Media.DrawingBrush> object and draw the converted text to the object's <xref:System.Windows.Media.DrawingContext>.</span></span> <span data-ttu-id="2d598-109">然后，将分配新<xref:System.Windows.Media.DrawingBrush>给控件的背景属性。</span><span class="sxs-lookup"><span data-stu-id="2d598-109">Then, assign the new <xref:System.Windows.Media.DrawingBrush> to the control's background property.</span></span>  
  
 <span data-ttu-id="2d598-110">下面的代码示例演示如何创建<xref:System.Windows.Media.FormattedText>对象，并绘制到背景<xref:System.Windows.Controls.Label>和<xref:System.Windows.Controls.Button>对象。</span><span class="sxs-lookup"><span data-stu-id="2d598-110">The following code example shows how to create a <xref:System.Windows.Media.FormattedText> object and draw to the background of a <xref:System.Windows.Controls.Label> and <xref:System.Windows.Controls.Button> object.</span></span>  
  
 [!code-csharp[DrawTextToControlBackground#DrawTextToControlBackground1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawTextToControlBackground/CSHARP/Window1.xaml.cs#drawtexttocontrolbackground1)]  
  
## <a name="see-also"></a><span data-ttu-id="2d598-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="2d598-111">See also</span></span>
- <xref:System.Windows.Media.FormattedText>
- [<span data-ttu-id="2d598-112">绘制格式化文本</span><span class="sxs-lookup"><span data-stu-id="2d598-112">Drawing Formatted Text</span></span>](../../../../docs/framework/wpf/advanced/drawing-formatted-text.md)
