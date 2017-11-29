---
title: "如何：在矩形中绘制换行文本"
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
- Windows Forms, drawing text in a rectangle
- text [Windows Forms], drawing in a rectangle
- strings [Windows Forms], drawing in a rectangle
ms.assetid: e1fb432a-dc90-48b5-9b6b-acc14507133d
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 773216c30adf1c684ec705a909038354aab0fec9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-draw-wrapped-text-in-a-rectangle"></a><span data-ttu-id="db57a-102">如何：在矩形中绘制换行文本</span><span class="sxs-lookup"><span data-stu-id="db57a-102">How to: Draw Wrapped Text in a Rectangle</span></span>
<span data-ttu-id="db57a-103">你可以在矩形中绘制换行的文本，通过使用<xref:System.Drawing.Graphics.DrawString%2A>重载的方法的<xref:System.Drawing.Graphics>采用类<xref:System.Drawing.Rectangle>或<xref:System.Drawing.RectangleF>参数。</span><span class="sxs-lookup"><span data-stu-id="db57a-103">You can draw wrapped text in a rectangle by using the <xref:System.Drawing.Graphics.DrawString%2A> overloaded method of the <xref:System.Drawing.Graphics> class that takes a <xref:System.Drawing.Rectangle> or <xref:System.Drawing.RectangleF> parameter.</span></span> <span data-ttu-id="db57a-104">你还将使用<xref:System.Drawing.Brush>和<xref:System.Drawing.Font>。</span><span class="sxs-lookup"><span data-stu-id="db57a-104">You will also use a <xref:System.Drawing.Brush> and a <xref:System.Drawing.Font>.</span></span>  
  
 <span data-ttu-id="db57a-105">您还可以绘制换行的文本矩形内使用<xref:System.Windows.Forms.TextRenderer.DrawText%2A>重载的方法的<xref:System.Windows.Forms.TextRenderer>采用<xref:System.Drawing.Rectangle>和<xref:System.Windows.Forms.TextFormatFlags>参数。</span><span class="sxs-lookup"><span data-stu-id="db57a-105">You can also draw wrapped text in a rectangle by using the <xref:System.Windows.Forms.TextRenderer.DrawText%2A> overloaded method of the <xref:System.Windows.Forms.TextRenderer> that takes a <xref:System.Drawing.Rectangle> and a <xref:System.Windows.Forms.TextFormatFlags> parameter.</span></span> <span data-ttu-id="db57a-106">你还将使用<xref:System.Drawing.Color>和<xref:System.Drawing.Font>。</span><span class="sxs-lookup"><span data-stu-id="db57a-106">You will also use a <xref:System.Drawing.Color> and a <xref:System.Drawing.Font>.</span></span>  
  
 <span data-ttu-id="db57a-107">下图显示当你使用在矩形中绘制的文本的输出<xref:System.Drawing.Graphics.DrawString%2A>方法。</span><span class="sxs-lookup"><span data-stu-id="db57a-107">The following illustration shows the output of text drawn in the rectangle when you use the <xref:System.Drawing.Graphics.DrawString%2A> method.</span></span>  
  
 <span data-ttu-id="db57a-108">![字体文本](../../../../docs/framework/winforms/advanced/media/csfontstext2.png "csfontstext2")</span><span class="sxs-lookup"><span data-stu-id="db57a-108">![Fonts Text](../../../../docs/framework/winforms/advanced/media/csfontstext2.png "csfontstext2")</span></span>  
  
### <a name="to-draw-wrapped-text-in-a-rectangle-with-gdi"></a><span data-ttu-id="db57a-109">绘制换行文本中使用 GDI + 矩形</span><span class="sxs-lookup"><span data-stu-id="db57a-109">To draw wrapped text in a rectangle with GDI+</span></span>  
  
1.  <span data-ttu-id="db57a-110">使用<xref:System.Drawing.Graphics.DrawString%2A>重载方法，并传递所需的文本<xref:System.Drawing.Rectangle>或<xref:System.Drawing.RectangleF>，<xref:System.Drawing.Font>和<xref:System.Drawing.Brush>。</span><span class="sxs-lookup"><span data-stu-id="db57a-110">Use the <xref:System.Drawing.Graphics.DrawString%2A> overloaded method, passing the text you want, <xref:System.Drawing.Rectangle> or <xref:System.Drawing.RectangleF>, <xref:System.Drawing.Font> and <xref:System.Drawing.Brush>.</span></span>  
  
     [!code-csharp[System.Drawing.AlignDrawnText#50](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/CS/Form1.cs#50)]
     [!code-vb[System.Drawing.AlignDrawnText#50](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/VB/Form1.vb#50)]  
  
### <a name="to-draw-wrapped-text-in-a-rectangle-with-gdi"></a><span data-ttu-id="db57a-111">绘制换行文本中使用 GDI 矩形</span><span class="sxs-lookup"><span data-stu-id="db57a-111">To draw wrapped text in a rectangle with GDI</span></span>  
  
1.  <span data-ttu-id="db57a-112">使用<xref:System.Windows.Forms.TextFormatFlags>枚举值，以指定的文本应与包装<xref:System.Windows.Forms.TextRenderer.DrawText%2A>重载方法，并传递所需的文本<xref:System.Drawing.Rectangle>，<xref:System.Drawing.Font>和<xref:System.Drawing.Color>。</span><span class="sxs-lookup"><span data-stu-id="db57a-112">Use the <xref:System.Windows.Forms.TextFormatFlags> enumeration value to specify the text should be wrapped with the <xref:System.Windows.Forms.TextRenderer.DrawText%2A> overloaded method, passing the text you want, <xref:System.Drawing.Rectangle>, <xref:System.Drawing.Font> and <xref:System.Drawing.Color>.</span></span>  
  
     [!code-csharp[System.Drawing.AlignDrawnText#60](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/CS/Form1.cs#60)]
     [!code-vb[System.Drawing.AlignDrawnText#60](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/VB/Form1.vb#60)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="db57a-113">编译代码</span><span class="sxs-lookup"><span data-stu-id="db57a-113">Compiling the Code</span></span>  
 <span data-ttu-id="db57a-114">前面的示例需要：</span><span class="sxs-lookup"><span data-stu-id="db57a-114">The previous examples require:</span></span>  
  
-   <span data-ttu-id="db57a-115"><xref:System.Windows.Forms.PaintEventArgs>`e`，这是一个参数的<xref:System.Windows.Forms.PaintEventHandler>。</span><span class="sxs-lookup"><span data-stu-id="db57a-115"><xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="db57a-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="db57a-116">See Also</span></span>  
 [<span data-ttu-id="db57a-117">如何：用 GDI 绘制文本</span><span class="sxs-lookup"><span data-stu-id="db57a-117">How to: Draw Text with GDI</span></span>](../../../../docs/framework/winforms/advanced/how-to-draw-text-with-gdi.md)  
 [<span data-ttu-id="db57a-118">使用字体和文本</span><span class="sxs-lookup"><span data-stu-id="db57a-118">Using Fonts and Text</span></span>](../../../../docs/framework/winforms/advanced/using-fonts-and-text.md)  
 [<span data-ttu-id="db57a-119">如何：构造字体系列和字体</span><span class="sxs-lookup"><span data-stu-id="db57a-119">How to: Construct Font Families and Fonts</span></span>](../../../../docs/framework/winforms/advanced/how-to-construct-font-families-and-fonts.md)  
 [<span data-ttu-id="db57a-120">如何：在指定位置绘制文本</span><span class="sxs-lookup"><span data-stu-id="db57a-120">How to: Draw Text at a Specified Location</span></span>](../../../../docs/framework/winforms/advanced/how-to-draw-text-at-a-specified-location.md)
