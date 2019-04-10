---
title: 如何：对齐绘制的文本
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- text [Windows Forms], aligning
- Windows Forms, aligning drawn text
ms.assetid: 83c10a81-1a90-4b5c-98aa-2c6c4b280079
ms.openlocfilehash: 0e77e4d8eeb9d7a07115b89525ac80074afeb6e8
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2019
ms.locfileid: "59323260"
---
# <a name="how-to-align-drawn-text"></a><span data-ttu-id="385cf-102">如何：对齐绘制的文本</span><span class="sxs-lookup"><span data-stu-id="385cf-102">How to: Align Drawn Text</span></span>
<span data-ttu-id="385cf-103">当执行自定义绘制时，通常可以窗体或控件上的绘制的文本居中。</span><span class="sxs-lookup"><span data-stu-id="385cf-103">When you perform custom drawing, you may often want to center drawn text on a form or control.</span></span> <span data-ttu-id="385cf-104">可以轻松地将使用绘制的文本对齐<xref:System.Drawing.Graphics.DrawString%2A>或<xref:System.Windows.Forms.TextRenderer.DrawText%2A>通过创建正确的格式设置对象并设置适当的格式标志的方法。</span><span class="sxs-lookup"><span data-stu-id="385cf-104">You can easily align text drawn with the <xref:System.Drawing.Graphics.DrawString%2A> or <xref:System.Windows.Forms.TextRenderer.DrawText%2A> methods by creating the correct formatting object and setting the appropriate format flags.</span></span>  
  
### <a name="to-draw-centered-text-with-gdi-drawstring"></a><span data-ttu-id="385cf-105">若要绘制文本居中使用 GDI + (DrawString)</span><span class="sxs-lookup"><span data-stu-id="385cf-105">To draw centered text with GDI+ (DrawString)</span></span>  
  
1. <span data-ttu-id="385cf-106">使用<xref:System.Drawing.StringFormat>使用相应<xref:System.Drawing.Graphics.DrawString%2A>方法，以指定文本居中。</span><span class="sxs-lookup"><span data-stu-id="385cf-106">Use a <xref:System.Drawing.StringFormat> with the appropriate <xref:System.Drawing.Graphics.DrawString%2A> method to specify centered text.</span></span>  
  
     [!code-csharp[System.Drawing.AlignDrawnText#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/CS/Form1.cs#10)]
     [!code-vb[System.Drawing.AlignDrawnText#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/VB/Form1.vb#10)]  
  
### <a name="to-draw-centered-text-with-gdi-drawtext"></a><span data-ttu-id="385cf-107">若要绘制文本居中用 GDI (DrawText)</span><span class="sxs-lookup"><span data-stu-id="385cf-107">To draw centered text with GDI (DrawText)</span></span>  
  
1. <span data-ttu-id="385cf-108">使用<xref:System.Windows.Forms.TextFormatFlags>包装，以及垂直和水平居中文本使用相应的枚举<xref:System.Windows.Forms.TextRenderer.DrawText%2A>方法。</span><span class="sxs-lookup"><span data-stu-id="385cf-108">Use the <xref:System.Windows.Forms.TextFormatFlags> enumeration for wrapping as well as vertically and horizontally centering text with the appropriate <xref:System.Windows.Forms.TextRenderer.DrawText%2A> method.</span></span>  
  
     [!code-csharp[System.Drawing.AlignDrawnText#20](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/CS/Form1.cs#20)]
     [!code-vb[System.Drawing.AlignDrawnText#20](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/VB/Form1.vb#20)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="385cf-109">编译代码</span><span class="sxs-lookup"><span data-stu-id="385cf-109">Compiling the Code</span></span>  
 <span data-ttu-id="385cf-110">前面的代码示例设计为使用 Windows 窗体，并且它们要求<xref:System.Windows.Forms.PaintEventArgs>`e`，这是一个参数的<xref:System.Windows.Forms.PaintEventHandler>。</span><span class="sxs-lookup"><span data-stu-id="385cf-110">The preceding code examples are designed for use with Windows Forms, and they require <xref:System.Windows.Forms.PaintEventArgs>`e`, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="385cf-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="385cf-111">See also</span></span>

- [<span data-ttu-id="385cf-112">如何：用 GDI 绘制文本</span><span class="sxs-lookup"><span data-stu-id="385cf-112">How to: Draw Text with GDI</span></span>](how-to-draw-text-with-gdi.md)
- [<span data-ttu-id="385cf-113">使用字体和文本</span><span class="sxs-lookup"><span data-stu-id="385cf-113">Using Fonts and Text</span></span>](using-fonts-and-text.md)
- [<span data-ttu-id="385cf-114">如何：构造字体系列和字体</span><span class="sxs-lookup"><span data-stu-id="385cf-114">How to: Construct Font Families and Fonts</span></span>](how-to-construct-font-families-and-fonts.md)
