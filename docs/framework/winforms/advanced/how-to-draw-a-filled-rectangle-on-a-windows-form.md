---
title: 如何：在 Windows 窗体上绘制实心矩形
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
f1_keywords:
- Graphics.FillRectangle
helpviewer_keywords:
- drawing [Windows Forms], rectangles
- rectangles [Windows Forms], drawing
- drawing rectangles
ms.assetid: d656a93c-987d-4809-aafd-493fe17450f0
ms.openlocfilehash: e551eacf0924c9bffa802fb5d2ba8bae7c1c3a98
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59072022"
---
# <a name="how-to-draw-a-filled-rectangle-on-a-windows-form"></a><span data-ttu-id="ed15e-102">如何：在 Windows 窗体上绘制实心矩形</span><span class="sxs-lookup"><span data-stu-id="ed15e-102">How to: Draw a Filled Rectangle on a Windows Form</span></span>
<span data-ttu-id="ed15e-103">此示例窗体上绘制实心的矩形。</span><span class="sxs-lookup"><span data-stu-id="ed15e-103">This example draws a filled rectangle on a form.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ed15e-104">示例</span><span class="sxs-lookup"><span data-stu-id="ed15e-104">Example</span></span>  
 [!code-cpp[System.Drawing.ConceptualHowTos#2](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/cpp/form1.cpp#2)]
 [!code-csharp[System.Drawing.ConceptualHowTos#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/CS/form1.cs#2)]
 [!code-vb[System.Drawing.ConceptualHowTos#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/VB/form1.vb#2)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="ed15e-105">编译代码</span><span class="sxs-lookup"><span data-stu-id="ed15e-105">Compiling the Code</span></span>  
 <span data-ttu-id="ed15e-106">不能在调用此方法<xref:System.Windows.Forms.Form.Load>事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="ed15e-106">You cannot call this method in the <xref:System.Windows.Forms.Form.Load> event handler.</span></span> <span data-ttu-id="ed15e-107">不会重新绘制的内容的绘制，如果窗体进行大小调整或另一个窗体被遮盖。</span><span class="sxs-lookup"><span data-stu-id="ed15e-107">The drawn content will not be redrawn if the form is resized or obscured by another form.</span></span> <span data-ttu-id="ed15e-108">若要使你自动重绘的内容，应重写<xref:System.Windows.Forms.Control.OnPaint%2A>方法。</span><span class="sxs-lookup"><span data-stu-id="ed15e-108">To make your content automatically repaint, you should override the <xref:System.Windows.Forms.Control.OnPaint%2A> method.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="ed15e-109">可靠编程</span><span class="sxs-lookup"><span data-stu-id="ed15e-109">Robust Programming</span></span>  
 <span data-ttu-id="ed15e-110">应始终调用<xref:System.IDisposable.Dispose%2A>占用系统资源，如任何对象<xref:System.Drawing.Brush>和<xref:System.Drawing.Graphics>对象。</span><span class="sxs-lookup"><span data-stu-id="ed15e-110">You should always call <xref:System.IDisposable.Dispose%2A> on any objects that consume system resources, such as <xref:System.Drawing.Brush> and <xref:System.Drawing.Graphics> objects.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ed15e-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="ed15e-111">See also</span></span>

- <xref:System.Drawing.Graphics.FillRectangle%2A>
- <xref:System.Windows.Forms.Control.OnPaint%2A>
- [<span data-ttu-id="ed15e-112">图形编程入门</span><span class="sxs-lookup"><span data-stu-id="ed15e-112">Getting Started with Graphics Programming</span></span>](getting-started-with-graphics-programming.md)
- [<span data-ttu-id="ed15e-113">Windows 窗体中的图形和绘制</span><span class="sxs-lookup"><span data-stu-id="ed15e-113">Graphics and Drawing in Windows Forms</span></span>](graphics-and-drawing-in-windows-forms.md)
- [<span data-ttu-id="ed15e-114">使用钢笔绘制线条和形状</span><span class="sxs-lookup"><span data-stu-id="ed15e-114">Using a Pen to Draw Lines and Shapes</span></span>](using-a-pen-to-draw-lines-and-shapes.md)
- [<span data-ttu-id="ed15e-115">GDI+ 中的画笔和实心形状</span><span class="sxs-lookup"><span data-stu-id="ed15e-115">Brushes and Filled Shapes in GDI+</span></span>](brushes-and-filled-shapes-in-gdi.md)
