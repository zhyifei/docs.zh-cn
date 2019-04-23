---
title: 如何：在矩形中绘制换行文本
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Windows Forms, drawing text in a rectangle
- text [Windows Forms], drawing in a rectangle
- strings [Windows Forms], drawing in a rectangle
ms.assetid: e1fb432a-dc90-48b5-9b6b-acc14507133d
ms.openlocfilehash: 8e5c7cab1f977bef0570b2e540d7bf3a630aceb0
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59301915"
---
# <a name="how-to-draw-wrapped-text-in-a-rectangle"></a><span data-ttu-id="d5de8-102">如何：在矩形中绘制换行文本</span><span class="sxs-lookup"><span data-stu-id="d5de8-102">How to: Draw Wrapped Text in a Rectangle</span></span>
<span data-ttu-id="d5de8-103">可以通过使用在矩形中绘制换行的文本<xref:System.Drawing.Graphics.DrawString%2A>重载的方法<xref:System.Drawing.Graphics>采用类<xref:System.Drawing.Rectangle>或<xref:System.Drawing.RectangleF>参数。</span><span class="sxs-lookup"><span data-stu-id="d5de8-103">You can draw wrapped text in a rectangle by using the <xref:System.Drawing.Graphics.DrawString%2A> overloaded method of the <xref:System.Drawing.Graphics> class that takes a <xref:System.Drawing.Rectangle> or <xref:System.Drawing.RectangleF> parameter.</span></span> <span data-ttu-id="d5de8-104">你还将使用<xref:System.Drawing.Brush>和一个<xref:System.Drawing.Font>。</span><span class="sxs-lookup"><span data-stu-id="d5de8-104">You will also use a <xref:System.Drawing.Brush> and a <xref:System.Drawing.Font>.</span></span>  
  
 <span data-ttu-id="d5de8-105">您还可以绘制换行的文本在矩形中通过使用<xref:System.Windows.Forms.TextRenderer.DrawText%2A>重载的方法<xref:System.Windows.Forms.TextRenderer>采用<xref:System.Drawing.Rectangle>和一个<xref:System.Windows.Forms.TextFormatFlags>参数。</span><span class="sxs-lookup"><span data-stu-id="d5de8-105">You can also draw wrapped text in a rectangle by using the <xref:System.Windows.Forms.TextRenderer.DrawText%2A> overloaded method of the <xref:System.Windows.Forms.TextRenderer> that takes a <xref:System.Drawing.Rectangle> and a <xref:System.Windows.Forms.TextFormatFlags> parameter.</span></span> <span data-ttu-id="d5de8-106">你还将使用<xref:System.Drawing.Color>和一个<xref:System.Drawing.Font>。</span><span class="sxs-lookup"><span data-stu-id="d5de8-106">You will also use a <xref:System.Drawing.Color> and a <xref:System.Drawing.Font>.</span></span>  
  
 <span data-ttu-id="d5de8-107">下图显示了当你使用的矩形中绘制文本的输出<xref:System.Drawing.Graphics.DrawString%2A>方法：</span><span class="sxs-lookup"><span data-stu-id="d5de8-107">The following illustration shows the output of text drawn in the rectangle when you use the <xref:System.Drawing.Graphics.DrawString%2A> method:</span></span>
  
 ![显示时使用 DrawString 方法的输出的屏幕截图。](./media/how-to-draw-wrapped-text-in-a-rectangle/drawstring-method-font-text.png)  
  
### <a name="to-draw-wrapped-text-in-a-rectangle-with-gdi"></a><span data-ttu-id="d5de8-109">若要绘制换行中使用 GDI + 矩形文本</span><span class="sxs-lookup"><span data-stu-id="d5de8-109">To draw wrapped text in a rectangle with GDI+</span></span>  
  
1. <span data-ttu-id="d5de8-110">使用<xref:System.Drawing.Graphics.DrawString%2A>重载方法，并传递所需的文本<xref:System.Drawing.Rectangle>或<xref:System.Drawing.RectangleF>，<xref:System.Drawing.Font>和<xref:System.Drawing.Brush>。</span><span class="sxs-lookup"><span data-stu-id="d5de8-110">Use the <xref:System.Drawing.Graphics.DrawString%2A> overloaded method, passing the text you want, <xref:System.Drawing.Rectangle> or <xref:System.Drawing.RectangleF>, <xref:System.Drawing.Font> and <xref:System.Drawing.Brush>.</span></span>  
  
     [!code-csharp[System.Drawing.AlignDrawnText#50](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/CS/Form1.cs#50)]
     [!code-vb[System.Drawing.AlignDrawnText#50](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/VB/Form1.vb#50)]  
  
### <a name="to-draw-wrapped-text-in-a-rectangle-with-gdi"></a><span data-ttu-id="d5de8-111">绘制换行文本中用 GDI 矩形</span><span class="sxs-lookup"><span data-stu-id="d5de8-111">To draw wrapped text in a rectangle with GDI</span></span>  
  
1. <span data-ttu-id="d5de8-112">使用<xref:System.Windows.Forms.TextFormatFlags>枚举值指定的文本应与包装<xref:System.Windows.Forms.TextRenderer.DrawText%2A>重载方法，并传递所需的文本<xref:System.Drawing.Rectangle>，<xref:System.Drawing.Font>和<xref:System.Drawing.Color>。</span><span class="sxs-lookup"><span data-stu-id="d5de8-112">Use the <xref:System.Windows.Forms.TextFormatFlags> enumeration value to specify the text should be wrapped with the <xref:System.Windows.Forms.TextRenderer.DrawText%2A> overloaded method, passing the text you want, <xref:System.Drawing.Rectangle>, <xref:System.Drawing.Font> and <xref:System.Drawing.Color>.</span></span>  
  
     [!code-csharp[System.Drawing.AlignDrawnText#60](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/CS/Form1.cs#60)]
     [!code-vb[System.Drawing.AlignDrawnText#60](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/VB/Form1.vb#60)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="d5de8-113">编译代码</span><span class="sxs-lookup"><span data-stu-id="d5de8-113">Compiling the Code</span></span>  
 <span data-ttu-id="d5de8-114">前面的示例需要：</span><span class="sxs-lookup"><span data-stu-id="d5de8-114">The previous examples require:</span></span>  
  
-   <span data-ttu-id="d5de8-115"><xref:System.Windows.Forms.PaintEventArgs> `e`这是一个参数的<xref:System.Windows.Forms.PaintEventHandler>。</span><span class="sxs-lookup"><span data-stu-id="d5de8-115"><xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d5de8-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="d5de8-116">See also</span></span>

- [<span data-ttu-id="d5de8-117">如何：用 GDI 绘制文本</span><span class="sxs-lookup"><span data-stu-id="d5de8-117">How to: Draw Text with GDI</span></span>](how-to-draw-text-with-gdi.md)
- [<span data-ttu-id="d5de8-118">使用字体和文本</span><span class="sxs-lookup"><span data-stu-id="d5de8-118">Using Fonts and Text</span></span>](using-fonts-and-text.md)
- [<span data-ttu-id="d5de8-119">如何：构造字体系列和字体</span><span class="sxs-lookup"><span data-stu-id="d5de8-119">How to: Construct Font Families and Fonts</span></span>](how-to-construct-font-families-and-fonts.md)
- [<span data-ttu-id="d5de8-120">如何：在指定位置绘制文本</span><span class="sxs-lookup"><span data-stu-id="d5de8-120">How to: Draw Text at a Specified Location</span></span>](how-to-draw-text-at-a-specified-location.md)
