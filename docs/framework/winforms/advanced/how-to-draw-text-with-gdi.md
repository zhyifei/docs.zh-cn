---
title: "如何：用 GDI 绘制文本"
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
- GDI [Windows Forms], drawing text [Windows Forms]
- text [Windows Forms], drawing with TextRenderer
- drawing [Windows Forms], text
- Windows Forms, drawing text with GDI
ms.assetid: 2a19fe5d-2ace-451c-94db-01cb1118ef7b
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: c6c7fb4d8c6bd93481935a9f2ef7dd4b34af7e71
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-draw-text-with-gdi"></a><span data-ttu-id="95cb0-102">如何：用 GDI 绘制文本</span><span class="sxs-lookup"><span data-stu-id="95cb0-102">How to: Draw Text with GDI</span></span>
<span data-ttu-id="95cb0-103">与<xref:System.Windows.Forms.TextRenderer.DrawText%2A>中的方法<xref:System.Windows.Forms.TextRenderer>类，可以访问[!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)]在窗体或控件上绘制文本的功能。</span><span class="sxs-lookup"><span data-stu-id="95cb0-103">With the <xref:System.Windows.Forms.TextRenderer.DrawText%2A> method in the <xref:System.Windows.Forms.TextRenderer> class, you can access [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] functionality for drawing text on a form or control.</span></span> [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)]<span data-ttu-id="95cb0-104">文本呈现通常提供更好的性能和更准确的文本比测量[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="95cb0-104"> text rendering typically offers better performance and more accurate text measuring than [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)].</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="95cb0-105"><xref:System.Windows.Forms.TextRenderer.DrawText%2A>方法<xref:System.Windows.Forms.TextRenderer>不支持打印的类。</span><span class="sxs-lookup"><span data-stu-id="95cb0-105">The <xref:System.Windows.Forms.TextRenderer.DrawText%2A> methods of the <xref:System.Windows.Forms.TextRenderer> class are not supported for printing.</span></span> <span data-ttu-id="95cb0-106">打印时，始终使用<xref:System.Drawing.Graphics.DrawString%2A>方法<xref:System.Drawing.Graphics>类。</span><span class="sxs-lookup"><span data-stu-id="95cb0-106">When printing, always use the <xref:System.Drawing.Graphics.DrawString%2A> methods of the <xref:System.Drawing.Graphics> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="95cb0-107">示例</span><span class="sxs-lookup"><span data-stu-id="95cb0-107">Example</span></span>  
 <span data-ttu-id="95cb0-108">下面的代码示例演示如何在矩形使用中的多个行上绘制文本<xref:System.Windows.Forms.TextRenderer.DrawText%2A>方法。</span><span class="sxs-lookup"><span data-stu-id="95cb0-108">The following code example demonstrates how to draw text on multiple lines within a rectangle using the <xref:System.Windows.Forms.TextRenderer.DrawText%2A> method.</span></span>  
  
 [!code-csharp[System.Windows.Forms.TextRendererExamples#7](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.TextRendererExamples/CS/Form1.cs#7)]
 [!code-vb[System.Windows.Forms.TextRendererExamples#7](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.TextRendererExamples/VB/Form1.vb#7)]  
  
 <span data-ttu-id="95cb0-109">呈现与文本<xref:System.Windows.Forms.TextRenderer>类，你需要<xref:System.Drawing.IDeviceContext>，如<xref:System.Drawing.Graphics>和<xref:System.Drawing.Font>，用于绘制文本，并在其中应绘制的颜色的位置。</span><span class="sxs-lookup"><span data-stu-id="95cb0-109">To render text with the <xref:System.Windows.Forms.TextRenderer> class, you need an <xref:System.Drawing.IDeviceContext>, such as a <xref:System.Drawing.Graphics> and a <xref:System.Drawing.Font>, a location to draw the text, and the color in which it should be drawn.</span></span> <span data-ttu-id="95cb0-110">或者，可以指定文本格式使用<xref:System.Windows.Forms.TextFormatFlags>枚举。</span><span class="sxs-lookup"><span data-stu-id="95cb0-110">Optionally, you can specify the text formatting by using the <xref:System.Windows.Forms.TextFormatFlags> enumeration.</span></span>  
  
 <span data-ttu-id="95cb0-111">有关获取详细信息<xref:System.Drawing.Graphics>，请参阅[如何： 创建图形对象的绘图](../../../../docs/framework/winforms/advanced/how-to-create-graphics-objects-for-drawing.md)。</span><span class="sxs-lookup"><span data-stu-id="95cb0-111">For more information about obtaining a <xref:System.Drawing.Graphics>, see [How to: Create Graphics Objects for Drawing](../../../../docs/framework/winforms/advanced/how-to-create-graphics-objects-for-drawing.md).</span></span> <span data-ttu-id="95cb0-112">有关构造<xref:System.Drawing.Font>，请参阅[如何： 构造字体系列和字体](../../../../docs/framework/winforms/advanced/how-to-construct-font-families-and-fonts.md)。</span><span class="sxs-lookup"><span data-stu-id="95cb0-112">For more information about constructing a <xref:System.Drawing.Font>, see [How to: Construct Font Families and Fonts](../../../../docs/framework/winforms/advanced/how-to-construct-font-families-and-fonts.md).</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="95cb0-113">编译代码</span><span class="sxs-lookup"><span data-stu-id="95cb0-113">Compiling the Code</span></span>  
 <span data-ttu-id="95cb0-114">前面的代码示例专用于 Windows 窗体，并且它需要<xref:System.Windows.Forms.PaintEventArgs> `e`，这是一个参数的<xref:System.Windows.Forms.PaintEventHandler>。</span><span class="sxs-lookup"><span data-stu-id="95cb0-114">The preceding code example is designed for use with Windows Forms, and it requires the <xref:System.Windows.Forms.PaintEventArgs>`e`, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="95cb0-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="95cb0-115">See Also</span></span>  
 <xref:System.Windows.Forms.TextRenderer>  
 <xref:System.Drawing.Font>  
 <xref:System.Drawing.Color>  
 <xref:System.Drawing.Color>  
 [<span data-ttu-id="95cb0-116">使用字体和文本</span><span class="sxs-lookup"><span data-stu-id="95cb0-116">Using Fonts and Text</span></span>](../../../../docs/framework/winforms/advanced/using-fonts-and-text.md)
