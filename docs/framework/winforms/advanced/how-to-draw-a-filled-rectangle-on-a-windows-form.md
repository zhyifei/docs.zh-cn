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
ms.openlocfilehash: 96e8f5babb194cfd2934c2bb71f3007483c68fd9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33520833"
---
# <a name="how-to-draw-a-filled-rectangle-on-a-windows-form"></a><span data-ttu-id="9fae4-102">如何：在 Windows 窗体上绘制实心矩形</span><span class="sxs-lookup"><span data-stu-id="9fae4-102">How to: Draw a Filled Rectangle on a Windows Form</span></span>
<span data-ttu-id="9fae4-103">此示例窗体上绘制实心的矩形。</span><span class="sxs-lookup"><span data-stu-id="9fae4-103">This example draws a filled rectangle on a form.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9fae4-104">示例</span><span class="sxs-lookup"><span data-stu-id="9fae4-104">Example</span></span>  
 [!code-cpp[System.Drawing.ConceptualHowTos#2](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/cpp/form1.cpp#2)]
 [!code-csharp[System.Drawing.ConceptualHowTos#2](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/CS/form1.cs#2)]
 [!code-vb[System.Drawing.ConceptualHowTos#2](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/VB/form1.vb#2)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="9fae4-105">编译代码</span><span class="sxs-lookup"><span data-stu-id="9fae4-105">Compiling the Code</span></span>  
 <span data-ttu-id="9fae4-106">无法调用此方法中<xref:System.Windows.Forms.Form.Load>事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="9fae4-106">You cannot call this method in the <xref:System.Windows.Forms.Form.Load> event handler.</span></span> <span data-ttu-id="9fae4-107">不会重新绘制的内容的绘制，如果窗体调整大小或另一种形式被遮盖。</span><span class="sxs-lookup"><span data-stu-id="9fae4-107">The drawn content will not be redrawn if the form is resized or obscured by another form.</span></span> <span data-ttu-id="9fae4-108">若要使你自动重绘的内容，则应重写<xref:System.Windows.Forms.Control.OnPaint%2A>方法。</span><span class="sxs-lookup"><span data-stu-id="9fae4-108">To make your content automatically repaint, you should override the <xref:System.Windows.Forms.Control.OnPaint%2A> method.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="9fae4-109">可靠编程</span><span class="sxs-lookup"><span data-stu-id="9fae4-109">Robust Programming</span></span>  
 <span data-ttu-id="9fae4-110">始终应调用<xref:System.IDisposable.Dispose%2A>对任何对象所消耗的系统资源，如<xref:System.Drawing.Brush>和<xref:System.Drawing.Graphics>对象。</span><span class="sxs-lookup"><span data-stu-id="9fae4-110">You should always call <xref:System.IDisposable.Dispose%2A> on any objects that consume system resources, such as <xref:System.Drawing.Brush> and <xref:System.Drawing.Graphics> objects.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9fae4-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="9fae4-111">See Also</span></span>  
 <xref:System.Drawing.Graphics.FillRectangle%2A>  
 <xref:System.Windows.Forms.Control.OnPaint%2A>  
 [<span data-ttu-id="9fae4-112">图形编程入门</span><span class="sxs-lookup"><span data-stu-id="9fae4-112">Getting Started with Graphics Programming</span></span>](../../../../docs/framework/winforms/advanced/getting-started-with-graphics-programming.md)  
 [<span data-ttu-id="9fae4-113">Windows 窗体中的图形和绘制</span><span class="sxs-lookup"><span data-stu-id="9fae4-113">Graphics and Drawing in Windows Forms</span></span>](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)  
 [<span data-ttu-id="9fae4-114">使用笔绘制直线和形状</span><span class="sxs-lookup"><span data-stu-id="9fae4-114">Using a Pen to Draw Lines and Shapes</span></span>](../../../../docs/framework/winforms/advanced/using-a-pen-to-draw-lines-and-shapes.md)  
 [<span data-ttu-id="9fae4-115">GDI+ 中的画笔和填充形状</span><span class="sxs-lookup"><span data-stu-id="9fae4-115">Brushes and Filled Shapes in GDI+</span></span>](../../../../docs/framework/winforms/advanced/brushes-and-filled-shapes-in-gdi.md)
