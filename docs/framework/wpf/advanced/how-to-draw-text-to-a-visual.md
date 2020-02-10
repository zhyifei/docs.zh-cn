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
ms.openlocfilehash: 654bfadb42f053b6dcf353d4423bddf281d69478
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/09/2020
ms.locfileid: "77094548"
---
# <a name="how-to-draw-text-to-a-visual"></a><span data-ttu-id="057c0-102">如何：将文本绘制到 Visual 中</span><span class="sxs-lookup"><span data-stu-id="057c0-102">How to: Draw Text to a Visual</span></span>
<span data-ttu-id="057c0-103">下面的示例演示如何使用 <xref:System.Windows.Media.DrawingContext> 对象将文本绘制到 <xref:System.Windows.Media.DrawingVisual>。</span><span class="sxs-lookup"><span data-stu-id="057c0-103">The following example shows how to draw text to a <xref:System.Windows.Media.DrawingVisual> using a <xref:System.Windows.Media.DrawingContext> object.</span></span> <span data-ttu-id="057c0-104">绘图上下文通过调用 <xref:System.Windows.Media.DrawingVisual> 对象的 <xref:System.Windows.Media.DrawingVisual.RenderOpen%2A> 方法返回。</span><span class="sxs-lookup"><span data-stu-id="057c0-104">A drawing context is returned by calling the <xref:System.Windows.Media.DrawingVisual.RenderOpen%2A> method of a <xref:System.Windows.Media.DrawingVisual> object.</span></span> <span data-ttu-id="057c0-105">您可以在绘图上下文中绘制图形和文本。</span><span class="sxs-lookup"><span data-stu-id="057c0-105">You can draw graphics and text into a drawing context.</span></span>  
  
 <span data-ttu-id="057c0-106">若要在绘图上下文中绘制文本，请使用 <xref:System.Windows.Media.DrawingContext> 对象的 <xref:System.Windows.Media.DrawingContext.DrawText%2A> 方法。</span><span class="sxs-lookup"><span data-stu-id="057c0-106">To draw text into the drawing context, use the <xref:System.Windows.Media.DrawingContext.DrawText%2A> method of a <xref:System.Windows.Media.DrawingContext> object.</span></span> <span data-ttu-id="057c0-107">完成将内容绘制到绘图上下文中后，调用 <xref:System.Windows.Media.DrawingContext.Close%2A> 方法来关闭绘图上下文并保留内容。</span><span class="sxs-lookup"><span data-stu-id="057c0-107">When you are finished drawing content into the drawing context, call the <xref:System.Windows.Media.DrawingContext.Close%2A> method to close the drawing context and persist the content.</span></span>  
  
## <a name="example"></a><span data-ttu-id="057c0-108">示例</span><span class="sxs-lookup"><span data-stu-id="057c0-108">Example</span></span>  
 [!code-csharp[DrawingVisualSample#110](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingVisualSample/CSharp/Window1.xaml.cs#110)]
 [!code-vb[DrawingVisualSample#110](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DrawingVisualSample/visualbasic/window1.xaml.vb#110)]  
  
> [!NOTE]
> <span data-ttu-id="057c0-109">有关从中提取上述代码示例的完整代码示例，请参阅[使用 DrawingVisual 的命中测试示例](https://github.com/Microsoft/WPF-Samples/tree/master/Visual%20Layer/DrawingVisual)。</span><span class="sxs-lookup"><span data-stu-id="057c0-109">For the complete code sample from which the preceding code example was extracted, see [Hit Test Using DrawingVisuals Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Visual%20Layer/DrawingVisual).</span></span>
