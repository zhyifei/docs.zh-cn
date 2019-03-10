---
title: 如何：设置笔的宽度和对齐方式
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- pens [Windows Forms], setting width
- pens [Windows Forms], setting alignment
ms.assetid: a202af36-4d31-4401-a126-b232f51db581
ms.openlocfilehash: e82f406b4fdca93df7a811eea5506846d56fda28
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/09/2019
ms.locfileid: "57703044"
---
# <a name="how-to-set-pen-width-and-alignment"></a><span data-ttu-id="67c7b-102">如何：设置笔的宽度和对齐方式</span><span class="sxs-lookup"><span data-stu-id="67c7b-102">How to: Set Pen Width and Alignment</span></span>
<span data-ttu-id="67c7b-103">当你创建<xref:System.Drawing.Pen>，可以作为构造函数的参数之一提供钢笔的宽度。</span><span class="sxs-lookup"><span data-stu-id="67c7b-103">When you create a <xref:System.Drawing.Pen>, you can supply the pen width as one of the arguments to the constructor.</span></span> <span data-ttu-id="67c7b-104">你可以使用笔的宽度<xref:System.Drawing.Pen.Width%2A>属性的<xref:System.Drawing.Pen>类。</span><span class="sxs-lookup"><span data-stu-id="67c7b-104">You can also change the pen width with the <xref:System.Drawing.Pen.Width%2A> property of the <xref:System.Drawing.Pen> class.</span></span>  
  
 <span data-ttu-id="67c7b-105">理论的线条具有宽度为 0。</span><span class="sxs-lookup"><span data-stu-id="67c7b-105">A theoretical line has a width of 0.</span></span> <span data-ttu-id="67c7b-106">当绘制 1 个像素宽的行时，像素理论的线条上居中。</span><span class="sxs-lookup"><span data-stu-id="67c7b-106">When you draw a line that is 1 pixel wide, the pixels are centered on the theoretical line.</span></span> <span data-ttu-id="67c7b-107">如果绘制多个像素宽的行，像素或者在理论的线条上居中或理论的线条的一侧显示。</span><span class="sxs-lookup"><span data-stu-id="67c7b-107">If you draw a line that is more than one pixel wide, the pixels are either centered on the theoretical line or appear to one side of the theoretical line.</span></span> <span data-ttu-id="67c7b-108">可以设置的笔对齐方式属性<xref:System.Drawing.Pen>来确定如何用其绘制的像素将相对于理论的线条进行定位。</span><span class="sxs-lookup"><span data-stu-id="67c7b-108">You can set the pen alignment property of a <xref:System.Drawing.Pen> to determine how the pixels drawn with that pen will be positioned relative to theoretical lines.</span></span>  
  
 <span data-ttu-id="67c7b-109">值<xref:System.Drawing.Drawing2D.PenAlignment.Center>， <xref:System.Drawing.Drawing2D.PenAlignment.Outset>，并<xref:System.Drawing.Drawing2D.PenAlignment.Inset>出现在下面的代码示例均隶属于<xref:System.Drawing.Drawing2D.PenAlignment>枚举。</span><span class="sxs-lookup"><span data-stu-id="67c7b-109">The values <xref:System.Drawing.Drawing2D.PenAlignment.Center>, <xref:System.Drawing.Drawing2D.PenAlignment.Outset>, and <xref:System.Drawing.Drawing2D.PenAlignment.Inset> that appear in the following code examples are members of the <xref:System.Drawing.Drawing2D.PenAlignment> enumeration.</span></span>  
  
 <span data-ttu-id="67c7b-110">下面的代码示例两次绘制一条线： 一次用黑色钢笔的宽度为 1，一次绿色手写笔的宽度为 10。</span><span class="sxs-lookup"><span data-stu-id="67c7b-110">The following code example draws a line twice: once with a black pen of width 1 and once with a green pen of width 10.</span></span>  
  
### <a name="to-vary-the-width-of-a-pen"></a><span data-ttu-id="67c7b-111">若要改变笔的宽度</span><span class="sxs-lookup"><span data-stu-id="67c7b-111">To vary the width of a pen</span></span>  
  
-   <span data-ttu-id="67c7b-112">设置的值<xref:System.Drawing.Pen.Alignment%2A>属性设置为<xref:System.Drawing.Drawing2D.PenAlignment.Center>（默认值） 以指定使用绿色笔绘制的像素会位于理论的线条。</span><span class="sxs-lookup"><span data-stu-id="67c7b-112">Set the value of the <xref:System.Drawing.Pen.Alignment%2A> property to <xref:System.Drawing.Drawing2D.PenAlignment.Center> (the default) to specify that pixels drawn with the green pen will be centered on the theoretical line.</span></span> <span data-ttu-id="67c7b-113">下图显示了生成的行。</span><span class="sxs-lookup"><span data-stu-id="67c7b-113">The following illustration shows the resulting line.</span></span>  
  
     <span data-ttu-id="67c7b-114">![笔](./media/pens1a.gif "pens1A")</span><span class="sxs-lookup"><span data-stu-id="67c7b-114">![Pens](./media/pens1a.gif "pens1A")</span></span>  
  
     <span data-ttu-id="67c7b-115">下面的代码示例绘制一个矩形两次： 一次用黑色钢笔的宽度为 1，一次绿色手写笔的宽度为 10。</span><span class="sxs-lookup"><span data-stu-id="67c7b-115">The following code example draws a rectangle twice: once with a black pen of width 1 and once with a green pen of width 10.</span></span>  
  
     [!code-csharp[System.Drawing.UsingAPen#41](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#41)]
     [!code-vb[System.Drawing.UsingAPen#41](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#41)]  
  
### <a name="to-change-the-alignment-of-a-pen"></a><span data-ttu-id="67c7b-116">若要更改笔的对齐方式</span><span class="sxs-lookup"><span data-stu-id="67c7b-116">To change the alignment of a pen</span></span>  
  
-   <span data-ttu-id="67c7b-117">设置的值<xref:System.Drawing.Pen.Alignment%2A>属性设置为<xref:System.Drawing.Drawing2D.PenAlignment.Center>指定用绿色笔绘制的像素会位于矩形的边界。</span><span class="sxs-lookup"><span data-stu-id="67c7b-117">Set the value of the <xref:System.Drawing.Pen.Alignment%2A> property to <xref:System.Drawing.Drawing2D.PenAlignment.Center> to specify that the pixels drawn with the green pen will be centered on the boundary of the rectangle.</span></span>  
  
     <span data-ttu-id="67c7b-118">下图显示了所得矩形的大小。</span><span class="sxs-lookup"><span data-stu-id="67c7b-118">The following illustration shows the resulting rectangle.</span></span>  
  
     <span data-ttu-id="67c7b-119">![笔](./media/pens2.gif "pens2")</span><span class="sxs-lookup"><span data-stu-id="67c7b-119">![Pens](./media/pens2.gif "pens2")</span></span>  
  
     [!code-csharp[System.Drawing.UsingAPen#42](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#42)]
     [!code-vb[System.Drawing.UsingAPen#42](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#42)]  
  
### <a name="to-create-an-inset-pen"></a><span data-ttu-id="67c7b-120">若要创建嵌入钢笔</span><span class="sxs-lookup"><span data-stu-id="67c7b-120">To create an inset pen</span></span>  
  
-   <span data-ttu-id="67c7b-121">通过按如下所示修改前面的代码示例中的第三个语句更改绿色笔对齐方式：</span><span class="sxs-lookup"><span data-stu-id="67c7b-121">Change the green pen's alignment by modifying the third statement in the preceding code example as follows:</span></span>  
  
     [!code-csharp[System.Drawing.UsingAPen#43](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#43)]
     [!code-vb[System.Drawing.UsingAPen#43](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#43)]  
  
     <span data-ttu-id="67c7b-122">现在宽绿线中的像素显示矩形的内部，如下图中所示。</span><span class="sxs-lookup"><span data-stu-id="67c7b-122">Now the pixels in the wide green line appear on the inside of the rectangle as shown in the following illustration.</span></span>  
  
     <span data-ttu-id="67c7b-123">![笔](./media/pens3.gif "pens3")</span><span class="sxs-lookup"><span data-stu-id="67c7b-123">![Pens](./media/pens3.gif "pens3")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="67c7b-124">请参阅</span><span class="sxs-lookup"><span data-stu-id="67c7b-124">See also</span></span>
- [<span data-ttu-id="67c7b-125">使用笔绘制直线和形状</span><span class="sxs-lookup"><span data-stu-id="67c7b-125">Using a Pen to Draw Lines and Shapes</span></span>](using-a-pen-to-draw-lines-and-shapes.md)
- [<span data-ttu-id="67c7b-126">Windows 窗体中的图形和绘制</span><span class="sxs-lookup"><span data-stu-id="67c7b-126">Graphics and Drawing in Windows Forms</span></span>](graphics-and-drawing-in-windows-forms.md)
