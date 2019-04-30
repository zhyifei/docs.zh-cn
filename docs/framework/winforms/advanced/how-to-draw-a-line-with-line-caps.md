---
title: 如何：绘制具有线帽的线条
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- drawing [Windows Forms], lines
- lines [Windows Forms], drawing
- pens [Windows Forms], drawing lines
- drawing lines [Windows Forms], line caps
ms.assetid: eb68c3e1-c400-4886-8a04-76978a429cb6
ms.openlocfilehash: c4a78569f6c0b14c32154611412d6b3ccd8a84ce
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "62004194"
---
# <a name="how-to-draw-a-line-with-line-caps"></a><span data-ttu-id="d96eb-102">如何：绘制具有线帽的线条</span><span class="sxs-lookup"><span data-stu-id="d96eb-102">How to: Draw a Line with Line Caps</span></span>
<span data-ttu-id="d96eb-103">可以在一个名为线帽的多个形状绘制的开始或结束的行。</span><span class="sxs-lookup"><span data-stu-id="d96eb-103">You can draw the start or end of a line in one of several shapes called line caps.</span></span> [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] <span data-ttu-id="d96eb-104">支持多种线帽，如 round、 正方形、 菱形和箭头。</span><span class="sxs-lookup"><span data-stu-id="d96eb-104">supports several line caps, such as round, square, diamond, and arrowhead.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d96eb-105">示例</span><span class="sxs-lookup"><span data-stu-id="d96eb-105">Example</span></span>  
 <span data-ttu-id="d96eb-106">您可以指定行 （起始端），行 （末端） 的末尾或虚线 (dash cap) 的短划线开头的线帽。</span><span class="sxs-lookup"><span data-stu-id="d96eb-106">You can specify line caps for the start of a line (start cap), the end of a line (end cap), or the dashes of a dashed line (dash cap).</span></span>  
  
 <span data-ttu-id="d96eb-107">下面的示例绘制一个行，其中一端箭头和另一端圆端帽。</span><span class="sxs-lookup"><span data-stu-id="d96eb-107">The following example draws a line with an arrowhead at one end and a round cap at the other end.</span></span> <span data-ttu-id="d96eb-108">该图显示了最终得到的行：</span><span class="sxs-lookup"><span data-stu-id="d96eb-108">The illustration shows the resulting line:</span></span>  
  
 ![显示具有圆端帽的线条的图例。](./media/how-to-draw-a-line-with-line-caps/line-cap-arrowhead-example.gif)  
  
 [!code-csharp[System.Drawing.UsingAPen#71](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#71)]
 [!code-vb[System.Drawing.UsingAPen#71](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#71)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="d96eb-110">编译代码</span><span class="sxs-lookup"><span data-stu-id="d96eb-110">Compiling the Code</span></span>  
  
- <span data-ttu-id="d96eb-111">创建 Windows 窗体和处理该窗体<xref:System.Windows.Forms.Control.Paint>事件。</span><span class="sxs-lookup"><span data-stu-id="d96eb-111">Create a Windows Form and handle the form's <xref:System.Windows.Forms.Control.Paint> event.</span></span> <span data-ttu-id="d96eb-112">示例将代码粘贴到<xref:System.Windows.Forms.Control.Paint>事件处理程序传递`e`作为<xref:System.Windows.Forms.PaintEventArgs>。</span><span class="sxs-lookup"><span data-stu-id="d96eb-112">Paste the example code into the <xref:System.Windows.Forms.Control.Paint> event handler passing `e` as <xref:System.Windows.Forms.PaintEventArgs>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d96eb-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="d96eb-113">See also</span></span>

- <xref:System.Drawing.Pen?displayProperty=nameWithType>
- <xref:System.Drawing.Drawing2D.LineCap?displayProperty=nameWithType>
- [<span data-ttu-id="d96eb-114">Windows 窗体中的图形和绘制</span><span class="sxs-lookup"><span data-stu-id="d96eb-114">Graphics and Drawing in Windows Forms</span></span>](graphics-and-drawing-in-windows-forms.md)
- [<span data-ttu-id="d96eb-115">使用笔绘制直线和形状</span><span class="sxs-lookup"><span data-stu-id="d96eb-115">Using a Pen to Draw Lines and Shapes</span></span>](using-a-pen-to-draw-lines-and-shapes.md)
