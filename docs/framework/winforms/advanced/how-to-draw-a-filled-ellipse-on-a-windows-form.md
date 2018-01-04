---
title: "如何：在 Windows 窗体上绘制实心椭圆"
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
f1_keywords: Graphics.FillEllipse
helpviewer_keywords:
- ellipses [Windows Forms], drawing
- circles [Windows Forms], drawing
- circular shapes
- drawing [Windows Forms], ellipses
- shapes [Windows Forms], drawing
- forms [Windows Forms], drawing ellipses
ms.assetid: 781db806-950d-4c5b-b022-493f7fd0c4a8
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 12b17f92fc90cde1e0c1841fc7f9d63728d50294
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-draw-a-filled-ellipse-on-a-windows-form"></a><span data-ttu-id="54171-102">如何：在 Windows 窗体上绘制实心椭圆</span><span class="sxs-lookup"><span data-stu-id="54171-102">How to: Draw a Filled Ellipse on a Windows Form</span></span>
<span data-ttu-id="54171-103">此示例窗体上绘制实心的椭圆。</span><span class="sxs-lookup"><span data-stu-id="54171-103">This example draws a filled ellipse on a form.</span></span>  
  
## <a name="example"></a><span data-ttu-id="54171-104">示例</span><span class="sxs-lookup"><span data-stu-id="54171-104">Example</span></span>  
 [!code-cpp[System.Drawing.ConceptualHowTos#1](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/cpp/form1.cpp#1)]
 [!code-csharp[System.Drawing.ConceptualHowTos#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/CS/form1.cs#1)]
 [!code-vb[System.Drawing.ConceptualHowTos#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/VB/form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="54171-105">编译代码</span><span class="sxs-lookup"><span data-stu-id="54171-105">Compiling the Code</span></span>  
 <span data-ttu-id="54171-106">无法调用此方法中<xref:System.Windows.Forms.Form.Load>事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="54171-106">You cannot call this method in the <xref:System.Windows.Forms.Form.Load> event handler.</span></span> <span data-ttu-id="54171-107">不会重新绘制的内容的绘制，如果窗体调整大小或另一种形式被遮盖。</span><span class="sxs-lookup"><span data-stu-id="54171-107">The drawn content will not be redrawn if the form is resized or obscured by another form.</span></span> <span data-ttu-id="54171-108">若要使你自动重绘的内容，则应重写<xref:System.Windows.Forms.Control.OnPaint%2A>方法。</span><span class="sxs-lookup"><span data-stu-id="54171-108">To make your content automatically repaint, you should override the <xref:System.Windows.Forms.Control.OnPaint%2A> method.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="54171-109">可靠编程</span><span class="sxs-lookup"><span data-stu-id="54171-109">Robust Programming</span></span>  
 <span data-ttu-id="54171-110">始终应调用<xref:System.IDisposable.Dispose%2A>对任何对象所消耗的系统资源，如<xref:System.Drawing.Brush>和<xref:System.Drawing.Graphics>对象。</span><span class="sxs-lookup"><span data-stu-id="54171-110">You should always call <xref:System.IDisposable.Dispose%2A> on any objects that consume system resources, such as <xref:System.Drawing.Brush> and <xref:System.Drawing.Graphics> objects.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="54171-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="54171-111">See Also</span></span>  
 [<span data-ttu-id="54171-112">Windows 窗体中的图形和绘制</span><span class="sxs-lookup"><span data-stu-id="54171-112">Graphics and Drawing in Windows Forms</span></span>](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)  
 [<span data-ttu-id="54171-113">图形编程入门</span><span class="sxs-lookup"><span data-stu-id="54171-113">Getting Started with Graphics Programming</span></span>](../../../../docs/framework/winforms/advanced/getting-started-with-graphics-programming.md)  
 [<span data-ttu-id="54171-114">alpha 值混合处理直线和填充</span><span class="sxs-lookup"><span data-stu-id="54171-114">Alpha Blending Lines and Fills</span></span>](../../../../docs/framework/winforms/advanced/alpha-blending-lines-and-fills.md)  
 [<span data-ttu-id="54171-115">使用画笔填充形状</span><span class="sxs-lookup"><span data-stu-id="54171-115">Using a Brush to Fill Shapes</span></span>](../../../../docs/framework/winforms/advanced/using-a-brush-to-fill-shapes.md)
