---
title: 如何：用 GDI 绘制文本
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- GDI [Windows Forms], drawing text [Windows Forms]
- text [Windows Forms], drawing with TextRenderer
- drawing [Windows Forms], text
- Windows Forms, drawing text with GDI
ms.assetid: 2a19fe5d-2ace-451c-94db-01cb1118ef7b
ms.openlocfilehash: d4bf72998c798040451b814a7f0287bca65f5300
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61781480"
---
# <a name="how-to-draw-text-with-gdi"></a><span data-ttu-id="589f7-102">如何：用 GDI 绘制文本</span><span class="sxs-lookup"><span data-stu-id="589f7-102">How to: Draw Text with GDI</span></span>
<span data-ttu-id="589f7-103">与<xref:System.Windows.Forms.TextRenderer.DrawText%2A>中的方法<xref:System.Windows.Forms.TextRenderer>类，可以访问[!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)]窗体或控件上绘制文本的功能。</span><span class="sxs-lookup"><span data-stu-id="589f7-103">With the <xref:System.Windows.Forms.TextRenderer.DrawText%2A> method in the <xref:System.Windows.Forms.TextRenderer> class, you can access [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] functionality for drawing text on a form or control.</span></span> [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] <span data-ttu-id="589f7-104">文本呈现通常提供更好的性能和更准确的文本比测量[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="589f7-104">text rendering typically offers better performance and more accurate text measuring than [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)].</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="589f7-105"><xref:System.Windows.Forms.TextRenderer.DrawText%2A>方法的<xref:System.Windows.Forms.TextRenderer>类不支持打印。</span><span class="sxs-lookup"><span data-stu-id="589f7-105">The <xref:System.Windows.Forms.TextRenderer.DrawText%2A> methods of the <xref:System.Windows.Forms.TextRenderer> class are not supported for printing.</span></span> <span data-ttu-id="589f7-106">打印时，始终使用<xref:System.Drawing.Graphics.DrawString%2A>方法的<xref:System.Drawing.Graphics>类。</span><span class="sxs-lookup"><span data-stu-id="589f7-106">When printing, always use the <xref:System.Drawing.Graphics.DrawString%2A> methods of the <xref:System.Drawing.Graphics> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="589f7-107">示例</span><span class="sxs-lookup"><span data-stu-id="589f7-107">Example</span></span>  
 <span data-ttu-id="589f7-108">下面的代码示例演示如何在矩形使用中的多个行上绘制文本<xref:System.Windows.Forms.TextRenderer.DrawText%2A>方法。</span><span class="sxs-lookup"><span data-stu-id="589f7-108">The following code example demonstrates how to draw text on multiple lines within a rectangle using the <xref:System.Windows.Forms.TextRenderer.DrawText%2A> method.</span></span>  
  
 [!code-csharp[System.Windows.Forms.TextRendererExamples#7](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.TextRendererExamples/CS/Form1.cs#7)]
 [!code-vb[System.Windows.Forms.TextRendererExamples#7](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.TextRendererExamples/VB/Form1.vb#7)]  
  
 <span data-ttu-id="589f7-109">呈现文本<xref:System.Windows.Forms.TextRenderer>类中，你需要<xref:System.Drawing.IDeviceContext>，如<xref:System.Drawing.Graphics>和一个<xref:System.Drawing.Font>，用于绘制文本，并应绘制单元的颜色的位置。</span><span class="sxs-lookup"><span data-stu-id="589f7-109">To render text with the <xref:System.Windows.Forms.TextRenderer> class, you need an <xref:System.Drawing.IDeviceContext>, such as a <xref:System.Drawing.Graphics> and a <xref:System.Drawing.Font>, a location to draw the text, and the color in which it should be drawn.</span></span> <span data-ttu-id="589f7-110">或者，您可以指定文本格式设置使用<xref:System.Windows.Forms.TextFormatFlags>枚举。</span><span class="sxs-lookup"><span data-stu-id="589f7-110">Optionally, you can specify the text formatting by using the <xref:System.Windows.Forms.TextFormatFlags> enumeration.</span></span>  
  
 <span data-ttu-id="589f7-111">有关获取详细信息<xref:System.Drawing.Graphics>，请参阅[如何：创建用于绘制图形对象](how-to-create-graphics-objects-for-drawing.md)。</span><span class="sxs-lookup"><span data-stu-id="589f7-111">For more information about obtaining a <xref:System.Drawing.Graphics>, see [How to: Create Graphics Objects for Drawing](how-to-create-graphics-objects-for-drawing.md).</span></span> <span data-ttu-id="589f7-112">有关构造的详细信息<xref:System.Drawing.Font>，请参阅[如何：构造字体系列和字体](how-to-construct-font-families-and-fonts.md)。</span><span class="sxs-lookup"><span data-stu-id="589f7-112">For more information about constructing a <xref:System.Drawing.Font>, see [How to: Construct Font Families and Fonts](how-to-construct-font-families-and-fonts.md).</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="589f7-113">编译代码</span><span class="sxs-lookup"><span data-stu-id="589f7-113">Compiling the Code</span></span>  
 <span data-ttu-id="589f7-114">前面的代码示例设计为使用 Windows 窗体，并且它需要<xref:System.Windows.Forms.PaintEventArgs> `e`，这是一个参数的<xref:System.Windows.Forms.PaintEventHandler>。</span><span class="sxs-lookup"><span data-stu-id="589f7-114">The preceding code example is designed for use with Windows Forms, and it requires the <xref:System.Windows.Forms.PaintEventArgs>`e`, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="589f7-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="589f7-115">See also</span></span>

- <xref:System.Windows.Forms.TextRenderer>
- <xref:System.Drawing.Font>
- <xref:System.Drawing.Color>
- [<span data-ttu-id="589f7-116">使用字体和文本</span><span class="sxs-lookup"><span data-stu-id="589f7-116">Using Fonts and Text</span></span>](using-fonts-and-text.md)
