---
title: 如何：在指定位置绘制文本
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- text [Windows Forms], drawing at specified locations [Windows Forms]
- drawing text
- drawing text [Windows Forms], specified locations [Windows Forms]
- Windows Forms, drawing text at a specified location
ms.assetid: 60816423-1c38-465e-980d-2c2b64d74086
ms.openlocfilehash: 3f54da182e6cc1489eadba6fa1d3cef683c3ba51
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59075504"
---
# <a name="how-to-draw-text-at-a-specified-location"></a><span data-ttu-id="9a247-102">如何：在指定位置绘制文本</span><span class="sxs-lookup"><span data-stu-id="9a247-102">How to: Draw Text at a Specified Location</span></span>
<span data-ttu-id="9a247-103">在执行自定义绘图时，可以从指定位置开始的一个水平行中绘制文本。</span><span class="sxs-lookup"><span data-stu-id="9a247-103">When you perform custom drawing, you can draw text in a single horizontal line starting at a specified point.</span></span> <span data-ttu-id="9a247-104">可以通过使用这种方式绘制文本<xref:System.Drawing.Graphics.DrawString%2A>重载的方法<xref:System.Drawing.Graphics>采用类<xref:System.Drawing.Point>或<xref:System.Drawing.PointF>参数。</span><span class="sxs-lookup"><span data-stu-id="9a247-104">You can draw text in this manner by using the <xref:System.Drawing.Graphics.DrawString%2A> overloaded method of the <xref:System.Drawing.Graphics> class that takes a <xref:System.Drawing.Point> or <xref:System.Drawing.PointF> parameter.</span></span> <span data-ttu-id="9a247-105"><xref:System.Drawing.Graphics.DrawString%2A>方法还需要<xref:System.Drawing.Brush>和</span><span class="sxs-lookup"><span data-stu-id="9a247-105">The <xref:System.Drawing.Graphics.DrawString%2A> method also requires a <xref:System.Drawing.Brush> and</span></span> <xref:System.Drawing.Font>  
  
 <span data-ttu-id="9a247-106">此外可以使用<xref:System.Windows.Forms.TextRenderer.DrawText%2A>重载的方法<xref:System.Windows.Forms.TextRenderer>采用<xref:System.Drawing.Point>。</span><span class="sxs-lookup"><span data-stu-id="9a247-106">You can also use the <xref:System.Windows.Forms.TextRenderer.DrawText%2A> overloaded method of the <xref:System.Windows.Forms.TextRenderer> that takes a <xref:System.Drawing.Point>.</span></span> <xref:System.Windows.Forms.TextRenderer.DrawText%2A> <span data-ttu-id="9a247-107">此外需要<xref:System.Drawing.Color>和一个<xref:System.Drawing.Font>。</span><span class="sxs-lookup"><span data-stu-id="9a247-107">also requires a <xref:System.Drawing.Color> and a <xref:System.Drawing.Font>.</span></span>  
  
 <span data-ttu-id="9a247-108">下图显示了在使用时，在指定点绘制文本的输出<xref:System.Drawing.Graphics.DrawString%2A>重载的方法。</span><span class="sxs-lookup"><span data-stu-id="9a247-108">The following illustration shows the output of text drawn at a specified point when you use the <xref:System.Drawing.Graphics.DrawString%2A> overloaded method.</span></span>  
  
 ![指定点处显示的文本输出的屏幕截图。](./media/how-to-draw-text-at-a-specified-location/font-text-specified-point.png)  
  
### <a name="to-draw-a-line-of-text-with-gdi"></a><span data-ttu-id="9a247-110">若要绘制一行使用 GDI + 文本</span><span class="sxs-lookup"><span data-stu-id="9a247-110">To draw a line of text with GDI+</span></span>  
  
1.  <span data-ttu-id="9a247-111">使用<xref:System.Drawing.Graphics.DrawString%2A>方法，并传递所需的文本<xref:System.Drawing.Point>或<xref:System.Drawing.PointF>， <xref:System.Drawing.Font>，和<xref:System.Drawing.Brush>。</span><span class="sxs-lookup"><span data-stu-id="9a247-111">Use the <xref:System.Drawing.Graphics.DrawString%2A> method, passing the text you want, <xref:System.Drawing.Point> or <xref:System.Drawing.PointF>, <xref:System.Drawing.Font>, and <xref:System.Drawing.Brush>.</span></span>  
  
     [!code-csharp[System.Drawing.AlignDrawnText#30](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/CS/Form1.cs#30)]
     [!code-vb[System.Drawing.AlignDrawnText#30](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/VB/Form1.vb#30)]  
  
### <a name="to-draw-a-line-of-text-with-gdi"></a><span data-ttu-id="9a247-112">若要绘制用 GDI 的文本行</span><span class="sxs-lookup"><span data-stu-id="9a247-112">To draw a line of text with GDI</span></span>  
  
1.  <span data-ttu-id="9a247-113">使用<xref:System.Windows.Forms.TextRenderer.DrawText%2A>方法，并传递所需的文本<xref:System.Drawing.Point>， <xref:System.Drawing.Font>，和<xref:System.Drawing.Color>。</span><span class="sxs-lookup"><span data-stu-id="9a247-113">Use the <xref:System.Windows.Forms.TextRenderer.DrawText%2A> method, passing the text you want, <xref:System.Drawing.Point>, <xref:System.Drawing.Font>, and <xref:System.Drawing.Color>.</span></span>  
  
     [!code-csharp[System.Drawing.AlignDrawnText#40](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/CS/Form1.cs#40)]
     [!code-vb[System.Drawing.AlignDrawnText#40](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/VB/Form1.vb#40)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="9a247-114">编译代码</span><span class="sxs-lookup"><span data-stu-id="9a247-114">Compiling the Code</span></span>  
 <span data-ttu-id="9a247-115">前面的示例需要：</span><span class="sxs-lookup"><span data-stu-id="9a247-115">The previous examples require:</span></span>  
  
-   <xref:System.Windows.Forms.PaintEventArgs>  `e`<span data-ttu-id="9a247-116">这是一个参数的<xref:System.Windows.Forms.PaintEventHandler>。</span><span class="sxs-lookup"><span data-stu-id="9a247-116">, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9a247-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="9a247-117">See also</span></span>

- [<span data-ttu-id="9a247-118">如何：用 GDI 绘制文本</span><span class="sxs-lookup"><span data-stu-id="9a247-118">How to: Draw Text with GDI</span></span>](how-to-draw-text-with-gdi.md)
- [<span data-ttu-id="9a247-119">使用字体和文本</span><span class="sxs-lookup"><span data-stu-id="9a247-119">Using Fonts and Text</span></span>](using-fonts-and-text.md)
- [<span data-ttu-id="9a247-120">如何：构造字体系列和字体</span><span class="sxs-lookup"><span data-stu-id="9a247-120">How to: Construct Font Families and Fonts</span></span>](how-to-construct-font-families-and-fonts.md)
- [<span data-ttu-id="9a247-121">如何：在矩形中绘制换行文本</span><span class="sxs-lookup"><span data-stu-id="9a247-121">How to: Draw Wrapped Text in a Rectangle</span></span>](how-to-draw-wrapped-text-in-a-rectangle.md)
