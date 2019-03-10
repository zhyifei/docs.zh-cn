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
ms.openlocfilehash: 885f0d22e83767bda3ef76c54f0857dd2a148344
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/09/2019
ms.locfileid: "57719710"
---
# <a name="how-to-fill-a-shape-with-a-hatch-pattern"></a><span data-ttu-id="36928-102">如何：用阴影图案填充形状</span><span class="sxs-lookup"><span data-stu-id="36928-102">How to: Fill a Shape with a Hatch Pattern</span></span>
<span data-ttu-id="36928-103">从两种颜色进行阴影图案： 一个用于在后台，一个用于在后台上形成图案的行。</span><span class="sxs-lookup"><span data-stu-id="36928-103">A hatch pattern is made from two colors: one for the background and one for the lines that form the pattern over the background.</span></span> <span data-ttu-id="36928-104">若要用阴影图案填充闭合的形状，请使用<xref:System.Drawing.Drawing2D.HatchBrush>对象。</span><span class="sxs-lookup"><span data-stu-id="36928-104">To fill a closed shape with a hatch pattern, use a <xref:System.Drawing.Drawing2D.HatchBrush> object.</span></span> <span data-ttu-id="36928-105">下面的示例演示如何用阴影图案填充椭圆，使用：</span><span class="sxs-lookup"><span data-stu-id="36928-105">The following example demonstrates how to fill an ellipse with a hatch pattern:</span></span>  
  
## <a name="example"></a><span data-ttu-id="36928-106">示例</span><span class="sxs-lookup"><span data-stu-id="36928-106">Example</span></span>  
 <span data-ttu-id="36928-107"><xref:System.Drawing.Drawing2D.HatchBrush.%23ctor%2A>构造函数采用三个参数： 的阴影样式、 阴影线条的颜色和背景颜色。</span><span class="sxs-lookup"><span data-stu-id="36928-107">The <xref:System.Drawing.Drawing2D.HatchBrush.%23ctor%2A> constructor takes three arguments: the hatch style, the color of the hatch line, and the color of the background.</span></span> <span data-ttu-id="36928-108">阴影样式参数可以为任何值<xref:System.Drawing.Drawing2D.HatchStyle>枚举。</span><span class="sxs-lookup"><span data-stu-id="36928-108">The hatch style argument can be any value from the <xref:System.Drawing.Drawing2D.HatchStyle> enumeration.</span></span> <span data-ttu-id="36928-109">有超过 50 个元素中的<xref:System.Drawing.Drawing2D.HatchStyle>枚举; 其中几个元素显示在下面的列表：</span><span class="sxs-lookup"><span data-stu-id="36928-109">There are more than fifty elements in the <xref:System.Drawing.Drawing2D.HatchStyle> enumeration; a few of those elements are shown in the following list:</span></span>  
  
-   <xref:System.Drawing.Drawing2D.HatchStyle.Horizontal>  
  
-   <xref:System.Drawing.Drawing2D.HatchStyle.Vertical>  
  
-   <xref:System.Drawing.Drawing2D.HatchStyle.ForwardDiagonal>  
  
-   <xref:System.Drawing.Drawing2D.HatchStyle.BackwardDiagonal>  
  
-   <xref:System.Drawing.Drawing2D.HatchStyle.Cross>  
  
-   <xref:System.Drawing.Drawing2D.HatchStyle.DiagonalCross>  
  
 <span data-ttu-id="36928-110">下图显示了实心的椭圆。</span><span class="sxs-lookup"><span data-stu-id="36928-110">The following illustration shows the filled ellipse.</span></span>  
  
 <span data-ttu-id="36928-111">![阴影图案](./media/hatch1.png "hatch1")</span><span class="sxs-lookup"><span data-stu-id="36928-111">![Hatch Pattern](./media/hatch1.png "hatch1")</span></span>  
  
 [!code-csharp[System.Drawing.UsingABrush#41](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingABrush/CS/Class1.cs#41)]
 [!code-vb[System.Drawing.UsingABrush#41](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingABrush/VB/Class1.vb#41)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="36928-112">编译代码</span><span class="sxs-lookup"><span data-stu-id="36928-112">Compiling the Code</span></span>  
 <span data-ttu-id="36928-113">前面的示例专用于 Windows 窗体，它需要 <xref:System.Windows.Forms.PaintEventArgs>`e`，后者是 <xref:System.Windows.Forms.Control.Paint> 事件处理程序的参数。</span><span class="sxs-lookup"><span data-stu-id="36928-113">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs>`e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="36928-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="36928-114">See also</span></span>
- [<span data-ttu-id="36928-115">使用画笔填充形状</span><span class="sxs-lookup"><span data-stu-id="36928-115">Using a Brush to Fill Shapes</span></span>](using-a-brush-to-fill-shapes.md)
