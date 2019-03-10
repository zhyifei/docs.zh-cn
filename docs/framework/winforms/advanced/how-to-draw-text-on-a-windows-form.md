---
title: 如何：在 Windows 窗体上绘制文本
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- forms [Windows Forms], drawing text
- text [Windows Forms], drawing
ms.assetid: 5d2447a9-21a1-4adc-b954-5516f2bb9b2c
ms.openlocfilehash: ed7aa89c3bd3751ed93f5bda33a26a8309d39143
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/09/2019
ms.locfileid: "57703499"
---
# <a name="how-to-draw-text-on-a-windows-form"></a><span data-ttu-id="9ea5a-102">如何：在 Windows 窗体上绘制文本</span><span class="sxs-lookup"><span data-stu-id="9ea5a-102">How to: Draw Text on a Windows Form</span></span>
<span data-ttu-id="9ea5a-103">下面的代码示例演示如何使用<xref:System.Drawing.Graphics.DrawString%2A>方法的<xref:System.Drawing.Graphics>窗体上绘制文本。</span><span class="sxs-lookup"><span data-stu-id="9ea5a-103">The following code example shows how to use the <xref:System.Drawing.Graphics.DrawString%2A> method of the <xref:System.Drawing.Graphics> to draw text on a form.</span></span> <span data-ttu-id="9ea5a-104">或者，可以使用<xref:System.Windows.Forms.TextRenderer>窗体上绘制文本。</span><span class="sxs-lookup"><span data-stu-id="9ea5a-104">Alternatively, you can use <xref:System.Windows.Forms.TextRenderer> for drawing text on a form.</span></span> <span data-ttu-id="9ea5a-105">有关详细信息，请参阅[如何：用 GDI 绘制文本](how-to-draw-text-with-gdi.md)。</span><span class="sxs-lookup"><span data-stu-id="9ea5a-105">For more information, see [How to: Draw Text with GDI](how-to-draw-text-with-gdi.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="9ea5a-106">示例</span><span class="sxs-lookup"><span data-stu-id="9ea5a-106">Example</span></span>  
 [!code-cpp[System.Drawing.ConceptualHowTos#7](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/cpp/form1.cpp#7)]
 [!code-csharp[System.Drawing.ConceptualHowTos#7](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/CS/form1.cs#7)]
 [!code-vb[System.Drawing.ConceptualHowTos#7](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/VB/form1.vb#7)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="9ea5a-107">编译代码</span><span class="sxs-lookup"><span data-stu-id="9ea5a-107">Compiling the Code</span></span>  
 <span data-ttu-id="9ea5a-108">不能调用<xref:System.Drawing.Graphics.DrawString%2A>中的方法<xref:System.Windows.Forms.Form.Load>事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="9ea5a-108">You cannot call the <xref:System.Drawing.Graphics.DrawString%2A> method in the <xref:System.Windows.Forms.Form.Load> event handler.</span></span> <span data-ttu-id="9ea5a-109">不会重新绘制的内容的绘制，如果窗体进行大小调整或另一个窗体被遮盖。</span><span class="sxs-lookup"><span data-stu-id="9ea5a-109">The drawn content will not be redrawn if the form is resized or obscured by another form.</span></span> <span data-ttu-id="9ea5a-110">若要使你自动重绘的内容，应重写<xref:System.Windows.Forms.Control.OnPaint%2A>方法。</span><span class="sxs-lookup"><span data-stu-id="9ea5a-110">To make your content automatically repaint, you should override the <xref:System.Windows.Forms.Control.OnPaint%2A> method.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="9ea5a-111">可靠编程</span><span class="sxs-lookup"><span data-stu-id="9ea5a-111">Robust Programming</span></span>  
 <span data-ttu-id="9ea5a-112">以下情况可能会导致异常：</span><span class="sxs-lookup"><span data-stu-id="9ea5a-112">The following conditions may cause an exception:</span></span>  
  
-   <span data-ttu-id="9ea5a-113">未安装 Arial 字体。</span><span class="sxs-lookup"><span data-stu-id="9ea5a-113">The Arial font is not installed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9ea5a-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="9ea5a-114">See also</span></span>
- <xref:System.Drawing.Graphics.DrawString%2A>
- <xref:System.Windows.Forms.TextRenderer.DrawText%2A>
- <xref:System.Drawing.StringFormat.FormatFlags%2A>
- <xref:System.Drawing.StringFormatFlags>
- <xref:System.Windows.Forms.TextFormatFlags>
- <xref:System.Windows.Forms.Control.OnPaint%2A>
- [<span data-ttu-id="9ea5a-115">图形编程入门</span><span class="sxs-lookup"><span data-stu-id="9ea5a-115">Getting Started with Graphics Programming</span></span>](getting-started-with-graphics-programming.md)
- [<span data-ttu-id="9ea5a-116">如何：用 GDI 绘制文本</span><span class="sxs-lookup"><span data-stu-id="9ea5a-116">How to: Draw Text with GDI</span></span>](how-to-draw-text-with-gdi.md)
