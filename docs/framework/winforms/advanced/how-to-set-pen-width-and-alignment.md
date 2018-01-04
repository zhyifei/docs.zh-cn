---
title: "如何：设置钢笔的宽度和对齐方式"
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
- pens [Windows Forms], setting width
- pens [Windows Forms], setting alignment
ms.assetid: a202af36-4d31-4401-a126-b232f51db581
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 1e5858da25174c8bc1de18d534023b57b58253e0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-set-pen-width-and-alignment"></a><span data-ttu-id="3f762-102">如何：设置钢笔的宽度和对齐方式</span><span class="sxs-lookup"><span data-stu-id="3f762-102">How to: Set Pen Width and Alignment</span></span>
<span data-ttu-id="3f762-103">当你创建<xref:System.Drawing.Pen>，你可以作为构造函数的自变量之一提供钢笔的宽度。</span><span class="sxs-lookup"><span data-stu-id="3f762-103">When you create a <xref:System.Drawing.Pen>, you can supply the pen width as one of the arguments to the constructor.</span></span> <span data-ttu-id="3f762-104">你还可以更改钢笔的宽度与<xref:System.Drawing.Pen.Width%2A>属性<xref:System.Drawing.Pen>类。</span><span class="sxs-lookup"><span data-stu-id="3f762-104">You can also change the pen width with the <xref:System.Drawing.Pen.Width%2A> property of the <xref:System.Drawing.Pen> class.</span></span>  
  
 <span data-ttu-id="3f762-105">理论上的行都有宽度为 0。</span><span class="sxs-lookup"><span data-stu-id="3f762-105">A theoretical line has a width of 0.</span></span> <span data-ttu-id="3f762-106">当你绘制为 1 个像素宽的行时，像素在理论上的行上居中。</span><span class="sxs-lookup"><span data-stu-id="3f762-106">When you draw a line that is 1 pixel wide, the pixels are centered on the theoretical line.</span></span> <span data-ttu-id="3f762-107">如果绘制为多个像素宽的行，像素在理论上的行上或者居中或向理论的线条的一侧显示。</span><span class="sxs-lookup"><span data-stu-id="3f762-107">If you draw a line that is more than one pixel wide, the pixels are either centered on the theoretical line or appear to one side of the theoretical line.</span></span> <span data-ttu-id="3f762-108">你可以设置的钢笔对齐属性<xref:System.Drawing.Pen>以确定将如何相对于理论线条放置用其绘制的像素。</span><span class="sxs-lookup"><span data-stu-id="3f762-108">You can set the pen alignment property of a <xref:System.Drawing.Pen> to determine how the pixels drawn with that pen will be positioned relative to theoretical lines.</span></span>  
  
 <span data-ttu-id="3f762-109">值<xref:System.Drawing.Drawing2D.PenAlignment.Center>， <xref:System.Drawing.Drawing2D.PenAlignment.Outset>，和<xref:System.Drawing.Drawing2D.PenAlignment.Inset>显示在下面的代码示例是的成员<xref:System.Drawing.Drawing2D.PenAlignment>枚举。</span><span class="sxs-lookup"><span data-stu-id="3f762-109">The values <xref:System.Drawing.Drawing2D.PenAlignment.Center>, <xref:System.Drawing.Drawing2D.PenAlignment.Outset>, and <xref:System.Drawing.Drawing2D.PenAlignment.Inset> that appear in the following code examples are members of the <xref:System.Drawing.Drawing2D.PenAlignment> enumeration.</span></span>  
  
 <span data-ttu-id="3f762-110">下面的代码示例绘制一条线条两次： 一次使用黑色钢笔的宽度为 1，一次使用绿色钢笔的宽度为 10。</span><span class="sxs-lookup"><span data-stu-id="3f762-110">The following code example draws a line twice: once with a black pen of width 1 and once with a green pen of width 10.</span></span>  
  
### <a name="to-vary-the-width-of-a-pen"></a><span data-ttu-id="3f762-111">改变钢笔的宽度</span><span class="sxs-lookup"><span data-stu-id="3f762-111">To vary the width of a pen</span></span>  
  
-   <span data-ttu-id="3f762-112">设置的值<xref:System.Drawing.Pen.Alignment%2A>属性<xref:System.Drawing.Drawing2D.PenAlignment.Center>（默认） 指定，将在理论上的行上居中用绿色钢笔绘制的像素为单位。</span><span class="sxs-lookup"><span data-stu-id="3f762-112">Set the value of the <xref:System.Drawing.Pen.Alignment%2A> property to <xref:System.Drawing.Drawing2D.PenAlignment.Center> (the default) to specify that pixels drawn with the green pen will be centered on the theoretical line.</span></span> <span data-ttu-id="3f762-113">下图显示生成的行。</span><span class="sxs-lookup"><span data-stu-id="3f762-113">The following illustration shows the resulting line.</span></span>  
  
     <span data-ttu-id="3f762-114">![钢笔](../../../../docs/framework/winforms/advanced/media/pens1a.gif "pens1A")</span><span class="sxs-lookup"><span data-stu-id="3f762-114">![Pens](../../../../docs/framework/winforms/advanced/media/pens1a.gif "pens1A")</span></span>  
  
     <span data-ttu-id="3f762-115">下面的代码示例绘制矩形两次： 一次使用黑色钢笔的宽度为 1，一次使用绿色钢笔的宽度为 10。</span><span class="sxs-lookup"><span data-stu-id="3f762-115">The following code example draws a rectangle twice: once with a black pen of width 1 and once with a green pen of width 10.</span></span>  
  
     [!code-csharp[System.Drawing.UsingAPen#41](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#41)]
     [!code-vb[System.Drawing.UsingAPen#41](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#41)]  
  
### <a name="to-change-the-alignment-of-a-pen"></a><span data-ttu-id="3f762-116">若要更改钢笔的对齐方式</span><span class="sxs-lookup"><span data-stu-id="3f762-116">To change the alignment of a pen</span></span>  
  
-   <span data-ttu-id="3f762-117">设置的值<xref:System.Drawing.Pen.Alignment%2A>属性<xref:System.Drawing.Drawing2D.PenAlignment.Center>指定用绿色钢笔绘制的像素居于矩形的边界上。</span><span class="sxs-lookup"><span data-stu-id="3f762-117">Set the value of the <xref:System.Drawing.Pen.Alignment%2A> property to <xref:System.Drawing.Drawing2D.PenAlignment.Center> to specify that the pixels drawn with the green pen will be centered on the boundary of the rectangle.</span></span>  
  
     <span data-ttu-id="3f762-118">下图显示生成的矩形。</span><span class="sxs-lookup"><span data-stu-id="3f762-118">The following illustration shows the resulting rectangle.</span></span>  
  
     <span data-ttu-id="3f762-119">![钢笔](../../../../docs/framework/winforms/advanced/media/pens2.gif "pens2")</span><span class="sxs-lookup"><span data-stu-id="3f762-119">![Pens](../../../../docs/framework/winforms/advanced/media/pens2.gif "pens2")</span></span>  
  
     [!code-csharp[System.Drawing.UsingAPen#42](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#42)]
     [!code-vb[System.Drawing.UsingAPen#42](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#42)]  
  
### <a name="to-create-an-inset-pen"></a><span data-ttu-id="3f762-120">若要创建嵌入钢笔</span><span class="sxs-lookup"><span data-stu-id="3f762-120">To create an inset pen</span></span>  
  
-   <span data-ttu-id="3f762-121">通过修改前面的代码示例中的第三个语句，如下所示更改绿色钢笔的对齐方式：</span><span class="sxs-lookup"><span data-stu-id="3f762-121">Change the green pen's alignment by modifying the third statement in the preceding code example as follows:</span></span>  
  
     [!code-csharp[System.Drawing.UsingAPen#43](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#43)]
     [!code-vb[System.Drawing.UsingAPen#43](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#43)]  
  
     <span data-ttu-id="3f762-122">现在像素宽绿线显示矩形的内部下, 图中所示。</span><span class="sxs-lookup"><span data-stu-id="3f762-122">Now the pixels in the wide green line appear on the inside of the rectangle as shown in the following illustration.</span></span>  
  
     <span data-ttu-id="3f762-123">![钢笔](../../../../docs/framework/winforms/advanced/media/pens3.gif "pens3")</span><span class="sxs-lookup"><span data-stu-id="3f762-123">![Pens](../../../../docs/framework/winforms/advanced/media/pens3.gif "pens3")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3f762-124">请参阅</span><span class="sxs-lookup"><span data-stu-id="3f762-124">See Also</span></span>  
 [<span data-ttu-id="3f762-125">使用笔绘制直线和形状</span><span class="sxs-lookup"><span data-stu-id="3f762-125">Using a Pen to Draw Lines and Shapes</span></span>](../../../../docs/framework/winforms/advanced/using-a-pen-to-draw-lines-and-shapes.md)  
 [<span data-ttu-id="3f762-126">Windows 窗体中的图形和绘制</span><span class="sxs-lookup"><span data-stu-id="3f762-126">Graphics and Drawing in Windows Forms</span></span>](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)
