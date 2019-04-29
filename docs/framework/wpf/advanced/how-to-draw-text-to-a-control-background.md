---
title: 如何：向控件的背景绘制文本
ms.date: 03/30/2017
helpviewer_keywords:
- controls [WPF], drawing text to backgrounds
- text [WPF], drawing to control backgrounds
- drawing [WPF], text to control backgrounds
- backgrounds [WPF], drawing text to
- typography [WPF], drawing text to control backgrounds
ms.assetid: 686d8fba-f61c-4974-a871-c635d67a7f69
ms.openlocfilehash: 76449c88f9a720741c8ed61255e04a40e6a8613f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61776191"
---
# <a name="how-to-draw-text-to-a-controls-background"></a><span data-ttu-id="2c227-102">如何：向控件的背景绘制文本</span><span class="sxs-lookup"><span data-stu-id="2c227-102">How to: Draw Text to a Control's Background</span></span>
<span data-ttu-id="2c227-103">可以直接到控件的背景中绘制文本的文本字符串转换为<xref:System.Windows.Media.FormattedText>对象，并在其中绘制到控件的对象<xref:System.Windows.Media.DrawingContext>。</span><span class="sxs-lookup"><span data-stu-id="2c227-103">You can draw text directly to the background of a control by converting a text string to a <xref:System.Windows.Media.FormattedText> object, and then drawing the object to the control's <xref:System.Windows.Media.DrawingContext>.</span></span> <span data-ttu-id="2c227-104">此外可以使用此技术用于绘制到的对象的背景派生自<xref:System.Windows.Controls.Panel>，如<xref:System.Windows.Controls.Canvas>和<xref:System.Windows.Controls.StackPanel>。</span><span class="sxs-lookup"><span data-stu-id="2c227-104">You can also use this technique for drawing to the background of objects derived from <xref:System.Windows.Controls.Panel>, such as <xref:System.Windows.Controls.Canvas> and <xref:System.Windows.Controls.StackPanel>.</span></span>  
  
 <span data-ttu-id="2c227-105">![文本显示为背景的控件](./media/drawtext2background01.png "DrawText2Background01")</span><span class="sxs-lookup"><span data-stu-id="2c227-105">![Controls displaying text as background](./media/drawtext2background01.png "DrawText2Background01")</span></span>  
<span data-ttu-id="2c227-106">具有自定义文本背景的控件的示例</span><span class="sxs-lookup"><span data-stu-id="2c227-106">Example of controls with custom text backgrounds</span></span>  
  
## <a name="example"></a><span data-ttu-id="2c227-107">示例</span><span class="sxs-lookup"><span data-stu-id="2c227-107">Example</span></span>  
 <span data-ttu-id="2c227-108">若要绘制到控件的背景，请创建一个新<xref:System.Windows.Media.DrawingBrush>对象，并绘制到对象的已转换的文本<xref:System.Windows.Media.DrawingContext>。</span><span class="sxs-lookup"><span data-stu-id="2c227-108">To draw to the background of a control, create a new <xref:System.Windows.Media.DrawingBrush> object and draw the converted text to the object's <xref:System.Windows.Media.DrawingContext>.</span></span> <span data-ttu-id="2c227-109">然后，将分配新<xref:System.Windows.Media.DrawingBrush>给控件的背景属性。</span><span class="sxs-lookup"><span data-stu-id="2c227-109">Then, assign the new <xref:System.Windows.Media.DrawingBrush> to the control's background property.</span></span>  
  
 <span data-ttu-id="2c227-110">下面的代码示例演示如何创建<xref:System.Windows.Media.FormattedText>对象，并绘制到背景<xref:System.Windows.Controls.Label>和<xref:System.Windows.Controls.Button>对象。</span><span class="sxs-lookup"><span data-stu-id="2c227-110">The following code example shows how to create a <xref:System.Windows.Media.FormattedText> object and draw to the background of a <xref:System.Windows.Controls.Label> and <xref:System.Windows.Controls.Button> object.</span></span>  
  
 [!code-csharp[DrawTextToControlBackground#DrawTextToControlBackground1](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawTextToControlBackground/CSHARP/Window1.xaml.cs#drawtexttocontrolbackground1)]  
  
## <a name="see-also"></a><span data-ttu-id="2c227-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="2c227-111">See also</span></span>

- <xref:System.Windows.Media.FormattedText>
- [<span data-ttu-id="2c227-112">绘制格式化文本</span><span class="sxs-lookup"><span data-stu-id="2c227-112">Drawing Formatted Text</span></span>](drawing-formatted-text.md)
