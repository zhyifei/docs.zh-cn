---
title: "如何：在指定位置绘制文本"
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
- text [Windows Forms], drawing at specified locations [Windows Forms]
- drawing text
- drawing text [Windows Forms], specified locations [Windows Forms]
- Windows Forms, drawing text at a specified location
ms.assetid: 60816423-1c38-465e-980d-2c2b64d74086
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: fe6e8563b19ef18b89ad970f3ca35bf5f0782a32
ms.sourcegitcommit: 8ed4ebc15b5ef89d06a7507dc9d5e306e30accf7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/14/2017
---
# <a name="how-to-draw-text-at-a-specified-location"></a><span data-ttu-id="c1c77-102">如何：在指定位置绘制文本</span><span class="sxs-lookup"><span data-stu-id="c1c77-102">How to: Draw Text at a Specified Location</span></span>
<span data-ttu-id="c1c77-103">在执行自定义绘制时，您可以在一个水平行从指定位置开始绘制文本。</span><span class="sxs-lookup"><span data-stu-id="c1c77-103">When you perform custom drawing, you can draw text in a single horizontal line starting at a specified point.</span></span> <span data-ttu-id="c1c77-104">可以通过使用这种方式中绘制文本<xref:System.Drawing.Graphics.DrawString%2A>重载的方法的<xref:System.Drawing.Graphics>采用类<xref:System.Drawing.Point>或<xref:System.Drawing.PointF>参数。</span><span class="sxs-lookup"><span data-stu-id="c1c77-104">You can draw text in this manner by using the <xref:System.Drawing.Graphics.DrawString%2A> overloaded method of the <xref:System.Drawing.Graphics> class that takes a <xref:System.Drawing.Point> or <xref:System.Drawing.PointF> parameter.</span></span> <span data-ttu-id="c1c77-105"><xref:System.Drawing.Graphics.DrawString%2A>方法还要求<xref:System.Drawing.Brush>和<xref:System.Drawing.Font></span><span class="sxs-lookup"><span data-stu-id="c1c77-105">The <xref:System.Drawing.Graphics.DrawString%2A> method also requires a <xref:System.Drawing.Brush> and <xref:System.Drawing.Font></span></span>  
  
 <span data-ttu-id="c1c77-106">你还可以使用<xref:System.Windows.Forms.TextRenderer.DrawText%2A>重载的方法的<xref:System.Windows.Forms.TextRenderer>采用<xref:System.Drawing.Point>。</span><span class="sxs-lookup"><span data-stu-id="c1c77-106">You can also use the <xref:System.Windows.Forms.TextRenderer.DrawText%2A> overloaded method of the <xref:System.Windows.Forms.TextRenderer> that takes a <xref:System.Drawing.Point>.</span></span> <span data-ttu-id="c1c77-107"><xref:System.Windows.Forms.TextRenderer.DrawText%2A>此外需要<xref:System.Drawing.Color>和<xref:System.Drawing.Font>。</span><span class="sxs-lookup"><span data-stu-id="c1c77-107"><xref:System.Windows.Forms.TextRenderer.DrawText%2A> also requires a <xref:System.Drawing.Color> and a <xref:System.Drawing.Font>.</span></span>  
  
 <span data-ttu-id="c1c77-108">下图显示当你使用的指定点处绘制的文本的输出<xref:System.Drawing.Graphics.DrawString%2A>重载的方法。</span><span class="sxs-lookup"><span data-stu-id="c1c77-108">The following illustration shows the output of text drawn at a specified point when you use the <xref:System.Drawing.Graphics.DrawString%2A> overloaded method.</span></span>  
  
 <span data-ttu-id="c1c77-109">![字体文本](../../../../docs/framework/winforms/advanced/media/csfontstext1.png "csfontstext1")</span><span class="sxs-lookup"><span data-stu-id="c1c77-109">![Fonts Text](../../../../docs/framework/winforms/advanced/media/csfontstext1.png "csfontstext1")</span></span>  
  
### <a name="to-draw-a-line-of-text-with-gdi"></a><span data-ttu-id="c1c77-110">若要绘制的文本使用 GDI + 线条</span><span class="sxs-lookup"><span data-stu-id="c1c77-110">To draw a line of text with GDI+</span></span>  
  
1.  <span data-ttu-id="c1c77-111">使用<xref:System.Drawing.Graphics.DrawString%2A>方法，并传递所需的文本<xref:System.Drawing.Point>或<xref:System.Drawing.PointF>， <xref:System.Drawing.Font>，和<xref:System.Drawing.Brush>。</span><span class="sxs-lookup"><span data-stu-id="c1c77-111">Use the <xref:System.Drawing.Graphics.DrawString%2A> method, passing the text you want, <xref:System.Drawing.Point> or <xref:System.Drawing.PointF>, <xref:System.Drawing.Font>, and <xref:System.Drawing.Brush>.</span></span>  
  
     [!code-csharp[System.Drawing.AlignDrawnText#30](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/CS/Form1.cs#30)]
     [!code-vb[System.Drawing.AlignDrawnText#30](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/VB/Form1.vb#30)]  
  
### <a name="to-draw-a-line-of-text-with-gdi"></a><span data-ttu-id="c1c77-112">若要绘制的文本与 GDI 线条</span><span class="sxs-lookup"><span data-stu-id="c1c77-112">To draw a line of text with GDI</span></span>  
  
1.  <span data-ttu-id="c1c77-113">使用<xref:System.Windows.Forms.TextRenderer.DrawText%2A>方法，并传递所需的文本<xref:System.Drawing.Point>， <xref:System.Drawing.Font>，和<xref:System.Drawing.Color>。</span><span class="sxs-lookup"><span data-stu-id="c1c77-113">Use the <xref:System.Windows.Forms.TextRenderer.DrawText%2A> method, passing the text you want, <xref:System.Drawing.Point>, <xref:System.Drawing.Font>, and <xref:System.Drawing.Color>.</span></span>  
  
     [!code-csharp[System.Drawing.AlignDrawnText#40](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/CS/Form1.cs#40)]
     [!code-vb[System.Drawing.AlignDrawnText#40](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/VB/Form1.vb#40)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="c1c77-114">编译代码</span><span class="sxs-lookup"><span data-stu-id="c1c77-114">Compiling the Code</span></span>  
 <span data-ttu-id="c1c77-115">前面的示例需要：</span><span class="sxs-lookup"><span data-stu-id="c1c77-115">The previous examples require:</span></span>  
  
-   <span data-ttu-id="c1c77-116"><xref:System.Windows.Forms.PaintEventArgs>  `e`这是一个参数的<xref:System.Windows.Forms.PaintEventHandler>。</span><span class="sxs-lookup"><span data-stu-id="c1c77-116"><xref:System.Windows.Forms.PaintEventArgs>  `e`, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c1c77-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c1c77-117">See Also</span></span>  
 [<span data-ttu-id="c1c77-118">如何：用 GDI 绘制文本</span><span class="sxs-lookup"><span data-stu-id="c1c77-118">How to: Draw Text with GDI</span></span>](../../../../docs/framework/winforms/advanced/how-to-draw-text-with-gdi.md)  
 [<span data-ttu-id="c1c77-119">使用字体和文本</span><span class="sxs-lookup"><span data-stu-id="c1c77-119">Using Fonts and Text</span></span>](../../../../docs/framework/winforms/advanced/using-fonts-and-text.md)  
 [<span data-ttu-id="c1c77-120">如何：构造字体系列和字体</span><span class="sxs-lookup"><span data-stu-id="c1c77-120">How to: Construct Font Families and Fonts</span></span>](../../../../docs/framework/winforms/advanced/how-to-construct-font-families-and-fonts.md)  
 [<span data-ttu-id="c1c77-121">如何：在矩形中绘制换行文本</span><span class="sxs-lookup"><span data-stu-id="c1c77-121">How to: Draw Wrapped Text in a Rectangle</span></span>](../../../../docs/framework/winforms/advanced/how-to-draw-wrapped-text-in-a-rectangle.md)
