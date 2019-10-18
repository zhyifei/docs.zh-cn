---
title: 如何：用阴影图案填充形状
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- patterns [Windows Forms], adding to shapes
- shapes [Windows Forms], filling with patterns
- brushes [Windows Forms], using hatch brushes
ms.assetid: 9c8300ff-187b-404f-af1f-ebd499f5b16f
ms.openlocfilehash: b80708f0ce722b1809fe49190639231e7e4c8329
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/15/2019
ms.locfileid: "72320053"
---
# <a name="how-to-fill-a-shape-with-a-hatch-pattern"></a><span data-ttu-id="7815c-102">如何：用阴影图案填充形状</span><span class="sxs-lookup"><span data-stu-id="7815c-102">How to: Fill a Shape with a Hatch Pattern</span></span>
<span data-ttu-id="7815c-103">阴影模式是从两种颜色组成的：一个用于背景，另一个用于在背景上形成图案的线条。</span><span class="sxs-lookup"><span data-stu-id="7815c-103">A hatch pattern is made from two colors: one for the background and one for the lines that form the pattern over the background.</span></span> <span data-ttu-id="7815c-104">若要使用阴影模式填充闭合形状，请使用 <xref:System.Drawing.Drawing2D.HatchBrush> 对象。</span><span class="sxs-lookup"><span data-stu-id="7815c-104">To fill a closed shape with a hatch pattern, use a <xref:System.Drawing.Drawing2D.HatchBrush> object.</span></span> <span data-ttu-id="7815c-105">下面的示例演示如何使用阴影模式填充椭圆：</span><span class="sxs-lookup"><span data-stu-id="7815c-105">The following example demonstrates how to fill an ellipse with a hatch pattern:</span></span>  
  
## <a name="example"></a><span data-ttu-id="7815c-106">示例</span><span class="sxs-lookup"><span data-stu-id="7815c-106">Example</span></span>  
 <span data-ttu-id="7815c-107">@No__t_0 构造函数采用三个参数：阴影样式、阴影线颜色和背景颜色。</span><span class="sxs-lookup"><span data-stu-id="7815c-107">The <xref:System.Drawing.Drawing2D.HatchBrush.%23ctor%2A> constructor takes three arguments: the hatch style, the color of the hatch line, and the color of the background.</span></span> <span data-ttu-id="7815c-108">阴影样式参数可以是 <xref:System.Drawing.Drawing2D.HatchStyle> 枚举中的任何值。</span><span class="sxs-lookup"><span data-stu-id="7815c-108">The hatch style argument can be any value from the <xref:System.Drawing.Drawing2D.HatchStyle> enumeration.</span></span> <span data-ttu-id="7815c-109">@No__t_0 枚举中的元素超过50个;下面的列表显示了其中的几个元素：</span><span class="sxs-lookup"><span data-stu-id="7815c-109">There are more than fifty elements in the <xref:System.Drawing.Drawing2D.HatchStyle> enumeration; a few of those elements are shown in the following list:</span></span>  
  
- <xref:System.Drawing.Drawing2D.HatchStyle.Horizontal>  
  
- <xref:System.Drawing.Drawing2D.HatchStyle.Vertical>  
  
- <xref:System.Drawing.Drawing2D.HatchStyle.ForwardDiagonal>  
  
- <xref:System.Drawing.Drawing2D.HatchStyle.BackwardDiagonal>  
  
- <xref:System.Drawing.Drawing2D.HatchStyle.Cross>  
  
- <xref:System.Drawing.Drawing2D.HatchStyle.DiagonalCross>  
  
 <span data-ttu-id="7815c-110">下图显示了实心椭圆。</span><span class="sxs-lookup"><span data-stu-id="7815c-110">The following illustration shows the filled ellipse.</span></span>  
  
  <span data-ttu-id="7815c-111">![用阴影模式填充的椭圆外观的屏幕截图。](./media/how-to-fill-a-shape-with-a-hatch-pattern/ellipse-filled-hatch.png "hatch1")</span><span class="sxs-lookup"><span data-stu-id="7815c-111">![Screenshot of what an ellipse filled with a hatch pattern looks like.](./media/how-to-fill-a-shape-with-a-hatch-pattern/ellipse-filled-hatch.png "hatch1")</span></span>
  
 [!code-csharp[System.Drawing.UsingABrush#41](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingABrush/CS/Class1.cs#41)]
 [!code-vb[System.Drawing.UsingABrush#41](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingABrush/VB/Class1.vb#41)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="7815c-112">编译代码</span><span class="sxs-lookup"><span data-stu-id="7815c-112">Compiling the Code</span></span>  
 <span data-ttu-id="7815c-113">前面的示例专用于 Windows 窗体，它需要 <xref:System.Windows.Forms.PaintEventArgs>`e`，后者是 <xref:System.Windows.Forms.Control.Paint> 事件处理程序的参数。</span><span class="sxs-lookup"><span data-stu-id="7815c-113">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs>`e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7815c-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="7815c-114">See also</span></span>

- [<span data-ttu-id="7815c-115">使用画笔填充形状</span><span class="sxs-lookup"><span data-stu-id="7815c-115">Using a Brush to Fill Shapes</span></span>](using-a-brush-to-fill-shapes.md)
