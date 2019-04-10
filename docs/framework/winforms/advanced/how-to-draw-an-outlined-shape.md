---
title: 如何：绘制轮廓形状
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
f1_keywords:
- Graphics.DrawEllipse
helpviewer_keywords:
- ellipses [Windows Forms], drawing
- circles [Windows Forms], drawing
- drawing [Windows Forms], shapes
- circular shapes
- forms [Windows Forms], drawing circular shapes
- circles
- outlined shapes [Windows Forms], examples
- outlined shapes [Windows Forms], drawing
- drawing [Windows Forms], circular shapes
- shapes [Windows Forms], drawing
ms.assetid: f4f9214c-607e-407d-8cdd-6549f0278451
ms.openlocfilehash: 019bbc19cc4b26c42f8539eccd93ec4ff87fab12
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59192195"
---
# <a name="how-to-draw-an-outlined-shape"></a><span data-ttu-id="46af9-102">如何：绘制轮廓形状</span><span class="sxs-lookup"><span data-stu-id="46af9-102">How to: Draw an Outlined Shape</span></span>
<span data-ttu-id="46af9-103">此示例窗体上绘制空心的椭圆和矩形。</span><span class="sxs-lookup"><span data-stu-id="46af9-103">This example draws outlined ellipses and rectangles on a form.</span></span>  
  
## <a name="example"></a><span data-ttu-id="46af9-104">示例</span><span class="sxs-lookup"><span data-stu-id="46af9-104">Example</span></span>  
 [!code-cpp[System.Drawing.ConceptualHowTos#6](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/cpp/form1.cpp#6)]
 [!code-csharp[System.Drawing.ConceptualHowTos#6](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/CS/form1.cs#6)]
 [!code-vb[System.Drawing.ConceptualHowTos#6](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/VB/form1.vb#6)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="46af9-105">编译代码</span><span class="sxs-lookup"><span data-stu-id="46af9-105">Compiling the Code</span></span>  
 <span data-ttu-id="46af9-106">不能在调用此方法<xref:System.Windows.Forms.Form.Load>事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="46af9-106">You cannot call this method in the <xref:System.Windows.Forms.Form.Load> event handler.</span></span> <span data-ttu-id="46af9-107">不会重新绘制的内容的绘制，如果窗体进行大小调整或另一个窗体被遮盖。</span><span class="sxs-lookup"><span data-stu-id="46af9-107">The drawn content will not be redrawn if the form is resized or obscured by another form.</span></span> <span data-ttu-id="46af9-108">若要使你自动重绘的内容，应重写<xref:System.Windows.Forms.Control.OnPaint%2A>方法。</span><span class="sxs-lookup"><span data-stu-id="46af9-108">To make your content automatically repaint, you should override the <xref:System.Windows.Forms.Control.OnPaint%2A> method.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="46af9-109">可靠编程</span><span class="sxs-lookup"><span data-stu-id="46af9-109">Robust Programming</span></span>  
 <span data-ttu-id="46af9-110">应始终调用<xref:System.IDisposable.Dispose%2A>占用系统资源，如任何对象<xref:System.Drawing.Pen>和<xref:System.Drawing.Graphics>对象。</span><span class="sxs-lookup"><span data-stu-id="46af9-110">You should always call <xref:System.IDisposable.Dispose%2A> on any objects that consume system resources, such as <xref:System.Drawing.Pen> and <xref:System.Drawing.Graphics> objects.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="46af9-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="46af9-111">See also</span></span>

- <xref:System.Drawing.Graphics.DrawEllipse%2A>
- <xref:System.Windows.Forms.Control.OnPaint%2A>
- <xref:System.Drawing.Graphics.DrawRectangle%2A>
- [<span data-ttu-id="46af9-112">图形编程入门</span><span class="sxs-lookup"><span data-stu-id="46af9-112">Getting Started with Graphics Programming</span></span>](getting-started-with-graphics-programming.md)
- [<span data-ttu-id="46af9-113">使用钢笔绘制线条和形状</span><span class="sxs-lookup"><span data-stu-id="46af9-113">Using a Pen to Draw Lines and Shapes</span></span>](using-a-pen-to-draw-lines-and-shapes.md)
- [<span data-ttu-id="46af9-114">Windows 窗体中的图形和绘制</span><span class="sxs-lookup"><span data-stu-id="46af9-114">Graphics and Drawing in Windows Forms</span></span>](graphics-and-drawing-in-windows-forms.md)
