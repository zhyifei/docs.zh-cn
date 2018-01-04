---
title: "如何：用阴影图案填充形状"
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
- patterns [Windows Forms], adding to shapes
- shapes [Windows Forms], filling with patterns
- brushes [Windows Forms], using hatch brushes
ms.assetid: 9c8300ff-187b-404f-af1f-ebd499f5b16f
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f44289b79812f2330639cc333727bd21b6ef4fe6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-fill-a-shape-with-a-hatch-pattern"></a><span data-ttu-id="0590b-102">如何：用阴影图案填充形状</span><span class="sxs-lookup"><span data-stu-id="0590b-102">How to: Fill a Shape with a Hatch Pattern</span></span>
<span data-ttu-id="0590b-103">从两种颜色进行阴影图案： 一个用于后台，一个用于通过后台形成图案的行。</span><span class="sxs-lookup"><span data-stu-id="0590b-103">A hatch pattern is made from two colors: one for the background and one for the lines that form the pattern over the background.</span></span> <span data-ttu-id="0590b-104">若要用阴影图案填充的闭合的形状，使用<xref:System.Drawing.Drawing2D.HatchBrush>对象。</span><span class="sxs-lookup"><span data-stu-id="0590b-104">To fill a closed shape with a hatch pattern, use a <xref:System.Drawing.Drawing2D.HatchBrush> object.</span></span> <span data-ttu-id="0590b-105">下面的示例演示如何用阴影图案填充椭圆：</span><span class="sxs-lookup"><span data-stu-id="0590b-105">The following example demonstrates how to fill an ellipse with a hatch pattern:</span></span>  
  
## <a name="example"></a><span data-ttu-id="0590b-106">示例</span><span class="sxs-lookup"><span data-stu-id="0590b-106">Example</span></span>  
 <span data-ttu-id="0590b-107"><xref:System.Drawing.Drawing2D.HatchBrush.%23ctor%2A>构造函数取三个参数： 的阴影样式、 阴影线的颜色和背景的颜色。</span><span class="sxs-lookup"><span data-stu-id="0590b-107">The <xref:System.Drawing.Drawing2D.HatchBrush.%23ctor%2A> constructor takes three arguments: the hatch style, the color of the hatch line, and the color of the background.</span></span> <span data-ttu-id="0590b-108">阴影样式参数可以是任何值从<xref:System.Drawing.Drawing2D.HatchStyle>枚举。</span><span class="sxs-lookup"><span data-stu-id="0590b-108">The hatch style argument can be any value from the <xref:System.Drawing.Drawing2D.HatchStyle> enumeration.</span></span> <span data-ttu-id="0590b-109">有多个 50 个元素中的<xref:System.Drawing.Drawing2D.HatchStyle>枚举; 其中几个元素都显示在下面的列表：</span><span class="sxs-lookup"><span data-stu-id="0590b-109">There are more than fifty elements in the <xref:System.Drawing.Drawing2D.HatchStyle> enumeration; a few of those elements are shown in the following list:</span></span>  
  
-   <xref:System.Drawing.Drawing2D.HatchStyle.Horizontal>  
  
-   <xref:System.Drawing.Drawing2D.HatchStyle.Vertical>  
  
-   <xref:System.Drawing.Drawing2D.HatchStyle.ForwardDiagonal>  
  
-   <xref:System.Drawing.Drawing2D.HatchStyle.BackwardDiagonal>  
  
-   <xref:System.Drawing.Drawing2D.HatchStyle.Cross>  
  
-   <xref:System.Drawing.Drawing2D.HatchStyle.DiagonalCross>  
  
 <span data-ttu-id="0590b-110">下图显示实心的椭圆。</span><span class="sxs-lookup"><span data-stu-id="0590b-110">The following illustration shows the filled ellipse.</span></span>  
  
 <span data-ttu-id="0590b-111">![影线模式](../../../../docs/framework/winforms/advanced/media/hatch1.png "hatch1")</span><span class="sxs-lookup"><span data-stu-id="0590b-111">![Hatch Pattern](../../../../docs/framework/winforms/advanced/media/hatch1.png "hatch1")</span></span>  
  
 [!code-csharp[System.Drawing.UsingABrush#41](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingABrush/CS/Class1.cs#41)]
 [!code-vb[System.Drawing.UsingABrush#41](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingABrush/VB/Class1.vb#41)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="0590b-112">编译代码</span><span class="sxs-lookup"><span data-stu-id="0590b-112">Compiling the Code</span></span>  
 <span data-ttu-id="0590b-113">前面的示例专用于 Windows 窗体，并且它需要<xref:System.Windows.Forms.PaintEventArgs> `e`，这是一个参数的<xref:System.Windows.Forms.Control.Paint>事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="0590b-113">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs>`e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0590b-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="0590b-114">See Also</span></span>  
 [<span data-ttu-id="0590b-115">使用画笔填充形状</span><span class="sxs-lookup"><span data-stu-id="0590b-115">Using a Brush to Fill Shapes</span></span>](../../../../docs/framework/winforms/advanced/using-a-brush-to-fill-shapes.md)
