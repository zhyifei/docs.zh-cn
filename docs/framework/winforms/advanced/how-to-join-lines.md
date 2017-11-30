---
title: "如何：联接线条"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: f02da181d66f7bb26a8414782e42eff2570e6918
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-join-lines"></a><span data-ttu-id="50131-102">如何：联接线条</span><span class="sxs-lookup"><span data-stu-id="50131-102">How to: Join Lines</span></span>
<span data-ttu-id="50131-103">线条联接是由其端点相交或重叠的两个行构成的常见区域。</span><span class="sxs-lookup"><span data-stu-id="50131-103">A line join is the common area that is formed by two lines whose ends meet or overlap.</span></span> [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]<span data-ttu-id="50131-104">提供三种线条联接样式： 斜接、 凹凸效果，和舍入。</span><span class="sxs-lookup"><span data-stu-id="50131-104"> provides three line join styles: miter, bevel, and round.</span></span> <span data-ttu-id="50131-105">线段联接样式是的一个属性<xref:System.Drawing.Pen>类。</span><span class="sxs-lookup"><span data-stu-id="50131-105">Line join style is a property of the <xref:System.Drawing.Pen> class.</span></span> <span data-ttu-id="50131-106">当指定的行联接样式<xref:System.Drawing.Pen>对象，联接样式，将应用于任何中所有连接的直线<xref:System.Drawing.Drawing2D.GraphicsPath>使用该笔绘制的对象。</span><span class="sxs-lookup"><span data-stu-id="50131-106">When you specify a line join style for a <xref:System.Drawing.Pen> object, that join style will be applied to all the connected lines in any <xref:System.Drawing.Drawing2D.GraphicsPath> object drawn using that pen.</span></span>  
  
 <span data-ttu-id="50131-107">下图显示凹凸效果的线条联接的结果。</span><span class="sxs-lookup"><span data-stu-id="50131-107">The following illustration shows the results of the beveled line join example.</span></span>  
  
 <span data-ttu-id="50131-108">![钢笔](../../../../docs/framework/winforms/advanced/media/pens5.gif "pens5")</span><span class="sxs-lookup"><span data-stu-id="50131-108">![Pens](../../../../docs/framework/winforms/advanced/media/pens5.gif "pens5")</span></span>  
  
## <a name="example"></a><span data-ttu-id="50131-109">示例</span><span class="sxs-lookup"><span data-stu-id="50131-109">Example</span></span>  
 <span data-ttu-id="50131-110">可以通过使用指定的行联接样式<xref:System.Drawing.Pen.LineJoin%2A>属性<xref:System.Drawing.Pen>类。</span><span class="sxs-lookup"><span data-stu-id="50131-110">You can specify the line join style by using the <xref:System.Drawing.Pen.LineJoin%2A> property of the <xref:System.Drawing.Pen> class.</span></span> <span data-ttu-id="50131-111">示例演示了一条水平线和垂直线之间的凹凸效果的行联接。</span><span class="sxs-lookup"><span data-stu-id="50131-111">The example demonstrates a beveled line join between a horizontal line and a vertical line.</span></span> <span data-ttu-id="50131-112">在下面的代码中，值<xref:System.Drawing.Drawing2D.LineJoin.Bevel>分配给<xref:System.Drawing.Pen.LineJoin%2A>属性是成员的<xref:System.Drawing.Drawing2D.LineJoin>枚举。</span><span class="sxs-lookup"><span data-stu-id="50131-112">In the following code, the value <xref:System.Drawing.Drawing2D.LineJoin.Bevel> assigned to the <xref:System.Drawing.Pen.LineJoin%2A> property is a member of the <xref:System.Drawing.Drawing2D.LineJoin> enumeration.</span></span> <span data-ttu-id="50131-113">其他成员<xref:System.Drawing.Drawing2D.LineJoin>枚举是<xref:System.Drawing.Drawing2D.LineJoin.Miter>和<xref:System.Drawing.Drawing2D.LineJoin.Round>。</span><span class="sxs-lookup"><span data-stu-id="50131-113">The other members of the <xref:System.Drawing.Drawing2D.LineJoin> enumeration are <xref:System.Drawing.Drawing2D.LineJoin.Miter> and <xref:System.Drawing.Drawing2D.LineJoin.Round>.</span></span>  
  
 [!code-csharp[System.Drawing.UsingAPen#31](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.UsingAPen#31](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#31)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="50131-114">编译代码</span><span class="sxs-lookup"><span data-stu-id="50131-114">Compiling the Code</span></span>  
 <span data-ttu-id="50131-115">前面的示例专用于 Windows 窗体，它需要 <xref:System.Windows.Forms.PaintEventArgs> `e`，后者是 <xref:System.Windows.Forms.Control.Paint> 事件处理程序的参数。</span><span class="sxs-lookup"><span data-stu-id="50131-115">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="50131-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="50131-116">See Also</span></span>  
 [<span data-ttu-id="50131-117">使用笔绘制直线和形状</span><span class="sxs-lookup"><span data-stu-id="50131-117">Using a Pen to Draw Lines and Shapes</span></span>](../../../../docs/framework/winforms/advanced/using-a-pen-to-draw-lines-and-shapes.md)
