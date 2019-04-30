---
title: 如何：使用钢笔绘制矩形
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- rectangles [Windows Forms], drawing
- pens [Windows Forms], drawing rectangles
ms.assetid: 54a7fa14-3ad8-4d64-b424-2a12005b250c
ms.openlocfilehash: 0e51a1e3a2d14754147dbd36f170127a7e978acd
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61954476"
---
# <a name="how-to-use-a-pen-to-draw-rectangles"></a><span data-ttu-id="3f90a-102">如何：使用钢笔绘制矩形</span><span class="sxs-lookup"><span data-stu-id="3f90a-102">How to: Use a Pen to Draw Rectangles</span></span>
<span data-ttu-id="3f90a-103">若要绘制矩形，需要<xref:System.Drawing.Graphics>对象和一个<xref:System.Drawing.Pen>对象。</span><span class="sxs-lookup"><span data-stu-id="3f90a-103">To draw rectangles, you need a <xref:System.Drawing.Graphics> object and a <xref:System.Drawing.Pen> object.</span></span> <span data-ttu-id="3f90a-104"><xref:System.Drawing.Graphics>对象提供<xref:System.Drawing.Graphics.DrawRectangle%2A>方法，和<xref:System.Drawing.Pen>对象将存储的行中，如颜色和宽度的功能。</span><span class="sxs-lookup"><span data-stu-id="3f90a-104">The <xref:System.Drawing.Graphics> object provides the <xref:System.Drawing.Graphics.DrawRectangle%2A> method, and the <xref:System.Drawing.Pen> object stores features of the line, such as color and width.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3f90a-105">示例</span><span class="sxs-lookup"><span data-stu-id="3f90a-105">Example</span></span>  
 <span data-ttu-id="3f90a-106">下面的示例绘制一个具有在其左上角的矩形 （10，10）。</span><span class="sxs-lookup"><span data-stu-id="3f90a-106">The following example draws a rectangle with its upper-left corner at (10, 10).</span></span> <span data-ttu-id="3f90a-107">矩形的宽度为 100，50 的高度。</span><span class="sxs-lookup"><span data-stu-id="3f90a-107">The rectangle has a width of 100 and a height of 50.</span></span> <span data-ttu-id="3f90a-108">第二个参数传递给<xref:System.Drawing.Pen.%23ctor%2A>构造函数指示钢笔的宽度为 5 像素。</span><span class="sxs-lookup"><span data-stu-id="3f90a-108">The second argument passed to the <xref:System.Drawing.Pen.%23ctor%2A> constructor indicates that the pen width is 5 pixels.</span></span>  
  
 <span data-ttu-id="3f90a-109">当绘制矩形时，触笔上居中显示矩形的边界。</span><span class="sxs-lookup"><span data-stu-id="3f90a-109">When the rectangle is drawn, the pen is centered on the rectangle's boundary.</span></span> <span data-ttu-id="3f90a-110">矩形的边钢笔的宽度为 5，因为所绘制的 5 个像素宽，因此绘制该 1 像素上边界本身，2 个像素绘制内，和 2 个像素绘制在外部。</span><span class="sxs-lookup"><span data-stu-id="3f90a-110">Because the pen width is 5, the sides of the rectangle are drawn 5 pixels wide, such that 1 pixel is drawn on the boundary itself, 2 pixels are drawn on the inside, and 2 pixels are drawn on the outside.</span></span> <span data-ttu-id="3f90a-111">有关笔对齐方式的更多详细信息，请参阅[如何：设置笔的宽度和对齐方式](how-to-set-pen-width-and-alignment.md)。</span><span class="sxs-lookup"><span data-stu-id="3f90a-111">For more details on pen alignment, see [How to: Set Pen Width and Alignment](how-to-set-pen-width-and-alignment.md).</span></span>  
  
 <span data-ttu-id="3f90a-112">下图显示了所得矩形的大小。</span><span class="sxs-lookup"><span data-stu-id="3f90a-112">The following illustration shows the resulting rectangle.</span></span> <span data-ttu-id="3f90a-113">点线显示，其中矩形已绘制如果钢笔的宽度必须被一个像素。</span><span class="sxs-lookup"><span data-stu-id="3f90a-113">The dotted lines show where the rectangle would have been drawn if the pen width had been one pixel.</span></span> <span data-ttu-id="3f90a-114">矩形的左上角的放大的视图显示胖黑色线条在这些点线上居中。</span><span class="sxs-lookup"><span data-stu-id="3f90a-114">The enlarged view of the upper-left corner of the rectangle shows that the thick black lines are centered on those dotted lines.</span></span>  
  
 ![显示在绘制的矩形使用黑色和虚线的屏幕截图。](./media/how-to-use-a-pen-to-draw-rectangles/drawn-rectangle-black-lines-dotted-lines.gif)  
  
 [!code-csharp[System.Drawing.UsingAPen#21](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.UsingAPen#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#21)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="3f90a-116">编译代码</span><span class="sxs-lookup"><span data-stu-id="3f90a-116">Compiling the Code</span></span>  
 <span data-ttu-id="3f90a-117">前面的示例专用于 Windows 窗体，它需要 <xref:System.Windows.Forms.PaintEventArgs>`e`，后者是 <xref:System.Windows.Forms.Control.Paint> 事件处理程序的参数。</span><span class="sxs-lookup"><span data-stu-id="3f90a-117">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs>`e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3f90a-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="3f90a-118">See also</span></span>

- [<span data-ttu-id="3f90a-119">使用笔绘制直线和形状</span><span class="sxs-lookup"><span data-stu-id="3f90a-119">Using a Pen to Draw Lines and Shapes</span></span>](using-a-pen-to-draw-lines-and-shapes.md)
