---
title: "如何：在 Windows 窗体上绘制文本"
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
- cpp
helpviewer_keywords:
- forms [Windows Forms], drawing text
- text [Windows Forms], drawing
ms.assetid: 5d2447a9-21a1-4adc-b954-5516f2bb9b2c
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 03e663f455a348b2699331ec5bf1ea6df2e54493
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-draw-text-on-a-windows-form"></a><span data-ttu-id="688a4-102">如何：在 Windows 窗体上绘制文本</span><span class="sxs-lookup"><span data-stu-id="688a4-102">How to: Draw Text on a Windows Form</span></span>
<span data-ttu-id="688a4-103">下面的代码示例演示如何使用<xref:System.Drawing.Graphics.DrawString%2A>方法<xref:System.Drawing.Graphics>窗体上绘制文本。</span><span class="sxs-lookup"><span data-stu-id="688a4-103">The following code example shows how to use the <xref:System.Drawing.Graphics.DrawString%2A> method of the <xref:System.Drawing.Graphics> to draw text on a form.</span></span> <span data-ttu-id="688a4-104">或者，可以使用<xref:System.Windows.Forms.TextRenderer>窗体上绘制文本。</span><span class="sxs-lookup"><span data-stu-id="688a4-104">Alternatively, you can use <xref:System.Windows.Forms.TextRenderer> for drawing text on a form.</span></span> <span data-ttu-id="688a4-105">有关详细信息，请参阅[如何： 用 GDI 绘制文本](../../../../docs/framework/winforms/advanced/how-to-draw-text-with-gdi.md)。</span><span class="sxs-lookup"><span data-stu-id="688a4-105">For more information, see [How to: Draw Text with GDI](../../../../docs/framework/winforms/advanced/how-to-draw-text-with-gdi.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="688a4-106">示例</span><span class="sxs-lookup"><span data-stu-id="688a4-106">Example</span></span>  
 [!code-cpp[System.Drawing.ConceptualHowTos#7](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/cpp/form1.cpp#7)]
 [!code-csharp[System.Drawing.ConceptualHowTos#7](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/CS/form1.cs#7)]
 [!code-vb[System.Drawing.ConceptualHowTos#7](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/VB/form1.vb#7)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="688a4-107">编译代码</span><span class="sxs-lookup"><span data-stu-id="688a4-107">Compiling the Code</span></span>  
 <span data-ttu-id="688a4-108">不能调用<xref:System.Drawing.Graphics.DrawString%2A>中的方法<xref:System.Windows.Forms.Form.Load>事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="688a4-108">You cannot call the <xref:System.Drawing.Graphics.DrawString%2A> method in the <xref:System.Windows.Forms.Form.Load> event handler.</span></span> <span data-ttu-id="688a4-109">不会重新绘制的内容的绘制，如果窗体调整大小或另一种形式被遮盖。</span><span class="sxs-lookup"><span data-stu-id="688a4-109">The drawn content will not be redrawn if the form is resized or obscured by another form.</span></span> <span data-ttu-id="688a4-110">若要使你自动重绘的内容，则应重写<xref:System.Windows.Forms.Control.OnPaint%2A>方法。</span><span class="sxs-lookup"><span data-stu-id="688a4-110">To make your content automatically repaint, you should override the <xref:System.Windows.Forms.Control.OnPaint%2A> method.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="688a4-111">可靠编程</span><span class="sxs-lookup"><span data-stu-id="688a4-111">Robust Programming</span></span>  
 <span data-ttu-id="688a4-112">以下情况可能会导致异常：</span><span class="sxs-lookup"><span data-stu-id="688a4-112">The following conditions may cause an exception:</span></span>  
  
-   <span data-ttu-id="688a4-113">未安装 Arial 字体。</span><span class="sxs-lookup"><span data-stu-id="688a4-113">The Arial font is not installed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="688a4-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="688a4-114">See Also</span></span>  
 <xref:System.Drawing.Graphics.DrawString%2A>  
 <xref:System.Windows.Forms.TextRenderer.DrawText%2A>  
 <xref:System.Drawing.StringFormat.FormatFlags%2A>  
 <xref:System.Drawing.StringFormatFlags>  
 <xref:System.Windows.Forms.TextFormatFlags>  
 <xref:System.Windows.Forms.Control.OnPaint%2A>  
 [<span data-ttu-id="688a4-115">图形编程入门</span><span class="sxs-lookup"><span data-stu-id="688a4-115">Getting Started with Graphics Programming</span></span>](../../../../docs/framework/winforms/advanced/getting-started-with-graphics-programming.md)  
 [<span data-ttu-id="688a4-116">如何：用 GDI 绘制文本</span><span class="sxs-lookup"><span data-stu-id="688a4-116">How to: Draw Text with GDI</span></span>](../../../../docs/framework/winforms/advanced/how-to-draw-text-with-gdi.md)
