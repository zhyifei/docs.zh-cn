---
title: 如何：Windows 窗体上绘制实心的椭圆
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
f1_keywords:
- Graphics.FillEllipse
helpviewer_keywords:
- ellipses [Windows Forms], drawing
- circles [Windows Forms], drawing
- circular shapes
- drawing [Windows Forms], ellipses
- shapes [Windows Forms], drawing
- forms [Windows Forms], drawing ellipses
ms.assetid: 781db806-950d-4c5b-b022-493f7fd0c4a8
ms.openlocfilehash: 09c98ec2874566cc49319d174ef7f1650a436d38
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54616897"
---
# <a name="how-to-draw-a-filled-ellipse-on-a-windows-form"></a><span data-ttu-id="fa4ba-102">如何：Windows 窗体上绘制实心的椭圆</span><span class="sxs-lookup"><span data-stu-id="fa4ba-102">How to: Draw a Filled Ellipse on a Windows Form</span></span>
<span data-ttu-id="fa4ba-103">此示例窗体上绘制实心的椭圆。</span><span class="sxs-lookup"><span data-stu-id="fa4ba-103">This example draws a filled ellipse on a form.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fa4ba-104">示例</span><span class="sxs-lookup"><span data-stu-id="fa4ba-104">Example</span></span>  
 [!code-cpp[System.Drawing.ConceptualHowTos#1](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/cpp/form1.cpp#1)]
 [!code-csharp[System.Drawing.ConceptualHowTos#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/CS/form1.cs#1)]
 [!code-vb[System.Drawing.ConceptualHowTos#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/VB/form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="fa4ba-105">编译代码</span><span class="sxs-lookup"><span data-stu-id="fa4ba-105">Compiling the Code</span></span>  
 <span data-ttu-id="fa4ba-106">不能在调用此方法<xref:System.Windows.Forms.Form.Load>事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="fa4ba-106">You cannot call this method in the <xref:System.Windows.Forms.Form.Load> event handler.</span></span> <span data-ttu-id="fa4ba-107">不会重新绘制的内容的绘制，如果窗体进行大小调整或另一个窗体被遮盖。</span><span class="sxs-lookup"><span data-stu-id="fa4ba-107">The drawn content will not be redrawn if the form is resized or obscured by another form.</span></span> <span data-ttu-id="fa4ba-108">若要使你自动重绘的内容，应重写<xref:System.Windows.Forms.Control.OnPaint%2A>方法。</span><span class="sxs-lookup"><span data-stu-id="fa4ba-108">To make your content automatically repaint, you should override the <xref:System.Windows.Forms.Control.OnPaint%2A> method.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="fa4ba-109">可靠编程</span><span class="sxs-lookup"><span data-stu-id="fa4ba-109">Robust Programming</span></span>  
 <span data-ttu-id="fa4ba-110">应始终调用<xref:System.IDisposable.Dispose%2A>占用系统资源，如任何对象<xref:System.Drawing.Brush>和<xref:System.Drawing.Graphics>对象。</span><span class="sxs-lookup"><span data-stu-id="fa4ba-110">You should always call <xref:System.IDisposable.Dispose%2A> on any objects that consume system resources, such as <xref:System.Drawing.Brush> and <xref:System.Drawing.Graphics> objects.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fa4ba-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="fa4ba-111">See also</span></span>
- [<span data-ttu-id="fa4ba-112">Windows 窗体中的图形和绘制</span><span class="sxs-lookup"><span data-stu-id="fa4ba-112">Graphics and Drawing in Windows Forms</span></span>](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)
- [<span data-ttu-id="fa4ba-113">图形编程入门</span><span class="sxs-lookup"><span data-stu-id="fa4ba-113">Getting Started with Graphics Programming</span></span>](../../../../docs/framework/winforms/advanced/getting-started-with-graphics-programming.md)
- [<span data-ttu-id="fa4ba-114">alpha 值混合处理直线和填充</span><span class="sxs-lookup"><span data-stu-id="fa4ba-114">Alpha Blending Lines and Fills</span></span>](../../../../docs/framework/winforms/advanced/alpha-blending-lines-and-fills.md)
- [<span data-ttu-id="fa4ba-115">使用画笔填充形状</span><span class="sxs-lookup"><span data-stu-id="fa4ba-115">Using a Brush to Fill Shapes</span></span>](../../../../docs/framework/winforms/advanced/using-a-brush-to-fill-shapes.md)
