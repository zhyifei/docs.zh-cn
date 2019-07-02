---
title: 如何：联接线
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- miter line join style
- bevel line join style
- line join
- drawing [Windows Forms], joining lines
- GraphicsPath object
- round line join style
- lines [Windows Forms], joining
- graphics [Windows Forms], joining lines
ms.assetid: 9fc480c2-3c75-4fd1-8ab5-296a99e820e2
ms.openlocfilehash: 362ce0c701d6e5f640fecd143a60cf471045629c
ms.sourcegitcommit: b1cfd260928d464d91e20121f9bdba7611c94d71
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/02/2019
ms.locfileid: "67505864"
---
# <a name="how-to-join-lines"></a><span data-ttu-id="7d990-102">如何：联接线</span><span class="sxs-lookup"><span data-stu-id="7d990-102">How to: Join Lines</span></span>
<span data-ttu-id="7d990-103">线条联接是由两个线条的端点相交或重叠的常见区域。</span><span class="sxs-lookup"><span data-stu-id="7d990-103">A line join is the common area that is formed by two lines whose ends meet or overlap.</span></span> <span data-ttu-id="7d990-104">GDI + 提供了三个行联接样式： 斜接、 凹凸效果，和舍入。</span><span class="sxs-lookup"><span data-stu-id="7d990-104">GDI+ provides three line join styles: miter, bevel, and round.</span></span> <span data-ttu-id="7d990-105">线段联接样式是的一个属性<xref:System.Drawing.Pen>类。</span><span class="sxs-lookup"><span data-stu-id="7d990-105">Line join style is a property of the <xref:System.Drawing.Pen> class.</span></span> <span data-ttu-id="7d990-106">当指定为线段联接样式<xref:System.Drawing.Pen>对象，联接样式，将应用于任何中所有连接的直线<xref:System.Drawing.Drawing2D.GraphicsPath>使用该笔绘制的对象。</span><span class="sxs-lookup"><span data-stu-id="7d990-106">When you specify a line join style for a <xref:System.Drawing.Pen> object, that join style will be applied to all the connected lines in any <xref:System.Drawing.Drawing2D.GraphicsPath> object drawn using that pen.</span></span>  
  
 <span data-ttu-id="7d990-107">下图显示斜切的线条联接示例的结果。</span><span class="sxs-lookup"><span data-stu-id="7d990-107">The following illustration shows the results of the beveled line join example.</span></span>  
  
 ![显示联接的直线的图例。](./media/how-to-join-lines/joined-beveled-lines.gif)  
  
## <a name="example"></a><span data-ttu-id="7d990-109">示例</span><span class="sxs-lookup"><span data-stu-id="7d990-109">Example</span></span>  
 <span data-ttu-id="7d990-110">可以通过使用指定线段联接样式<xref:System.Drawing.Pen.LineJoin%2A>属性的<xref:System.Drawing.Pen>类。</span><span class="sxs-lookup"><span data-stu-id="7d990-110">You can specify the line join style by using the <xref:System.Drawing.Pen.LineJoin%2A> property of the <xref:System.Drawing.Pen> class.</span></span> <span data-ttu-id="7d990-111">该示例演示一条水平线和垂直线之间斜角的行联接。</span><span class="sxs-lookup"><span data-stu-id="7d990-111">The example demonstrates a beveled line join between a horizontal line and a vertical line.</span></span> <span data-ttu-id="7d990-112">在下面的代码中，值<xref:System.Drawing.Drawing2D.LineJoin.Bevel>分配给<xref:System.Drawing.Pen.LineJoin%2A>属性是的成员<xref:System.Drawing.Drawing2D.LineJoin>枚举。</span><span class="sxs-lookup"><span data-stu-id="7d990-112">In the following code, the value <xref:System.Drawing.Drawing2D.LineJoin.Bevel> assigned to the <xref:System.Drawing.Pen.LineJoin%2A> property is a member of the <xref:System.Drawing.Drawing2D.LineJoin> enumeration.</span></span> <span data-ttu-id="7d990-113">其他成员<xref:System.Drawing.Drawing2D.LineJoin>枚举都<xref:System.Drawing.Drawing2D.LineJoin.Miter>和<xref:System.Drawing.Drawing2D.LineJoin.Round>。</span><span class="sxs-lookup"><span data-stu-id="7d990-113">The other members of the <xref:System.Drawing.Drawing2D.LineJoin> enumeration are <xref:System.Drawing.Drawing2D.LineJoin.Miter> and <xref:System.Drawing.Drawing2D.LineJoin.Round>.</span></span>  
  
 [!code-csharp[System.Drawing.UsingAPen#31](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.UsingAPen#31](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#31)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="7d990-114">编译代码</span><span class="sxs-lookup"><span data-stu-id="7d990-114">Compiling the Code</span></span>  
 <span data-ttu-id="7d990-115">前面的示例专用于 Windows 窗体，并且它需要<xref:System.Windows.Forms.PaintEventArgs> `e`，这是一个参数的<xref:System.Windows.Forms.Control.Paint>事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="7d990-115">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7d990-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="7d990-116">See also</span></span>

- [<span data-ttu-id="7d990-117">使用笔绘制直线和形状</span><span class="sxs-lookup"><span data-stu-id="7d990-117">Using a Pen to Draw Lines and Shapes</span></span>](using-a-pen-to-draw-lines-and-shapes.md)
