---
title: "如何：绘制用纹理填充的线条"
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
- drawing [Windows Forms], lines
- lines [Windows Forms], texture
- drawing lines [Windows Forms], texture
ms.assetid: dc9118cc-f3c2-42e5-8173-f46d41d18fd5
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 0aaba7981dc68bf7bdfe6dbd45685e61f7b763a5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-draw-a-line-filled-with-a-texture"></a><span data-ttu-id="c6d21-102">如何：绘制用纹理填充的线条</span><span class="sxs-lookup"><span data-stu-id="c6d21-102">How to: Draw a Line Filled with a Texture</span></span>
<span data-ttu-id="c6d21-103">而不是绘制一条线使用纯色，您可以绘制用纹理行。</span><span class="sxs-lookup"><span data-stu-id="c6d21-103">Instead of drawing a line with a solid color, you can draw a line with a texture.</span></span> <span data-ttu-id="c6d21-104">若要绘制的直线和曲线用纹理，创建<xref:System.Drawing.TextureBrush>对象，并将其传递<xref:System.Drawing.TextureBrush>对象传递给<xref:System.Drawing.Pen.%23ctor%2A>构造函数。</span><span class="sxs-lookup"><span data-stu-id="c6d21-104">To draw lines and curves with a texture, create a <xref:System.Drawing.TextureBrush> object, and pass that <xref:System.Drawing.TextureBrush> object to a <xref:System.Drawing.Pen.%23ctor%2A> constructor.</span></span> <span data-ttu-id="c6d21-105">使用纹理画笔相关联的位图可用于平铺平面 （不可见的方式），并当钢笔绘制线条或曲线，钢笔笔画发现特定的平铺的纹理的像素。</span><span class="sxs-lookup"><span data-stu-id="c6d21-105">The bitmap associated with the texture brush is used to tile the plane (invisibly), and when the pen draws a line or curve, the stroke of the pen uncovers certain pixels of the tiled texture.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c6d21-106">示例</span><span class="sxs-lookup"><span data-stu-id="c6d21-106">Example</span></span>  
 <span data-ttu-id="c6d21-107">下面的示例创建<xref:System.Drawing.Bitmap>文件中的对象`Texture1.jpg`。</span><span class="sxs-lookup"><span data-stu-id="c6d21-107">The following example creates a <xref:System.Drawing.Bitmap> object from the file `Texture1.jpg`.</span></span> <span data-ttu-id="c6d21-108">该位图用于构造<xref:System.Drawing.TextureBrush>对象，与<xref:System.Drawing.TextureBrush>对象用于构造<xref:System.Drawing.Pen>对象。</span><span class="sxs-lookup"><span data-stu-id="c6d21-108">That bitmap is used to construct a <xref:System.Drawing.TextureBrush> object, and the <xref:System.Drawing.TextureBrush> object is used to construct a <xref:System.Drawing.Pen> object.</span></span> <span data-ttu-id="c6d21-109">调用<xref:System.Drawing.Graphics.DrawImage%2A>绘制位图，并使用在其左上角 （0，0）。</span><span class="sxs-lookup"><span data-stu-id="c6d21-109">The call to <xref:System.Drawing.Graphics.DrawImage%2A> draws the bitmap with its upper-left corner at (0, 0).</span></span> <span data-ttu-id="c6d21-110">调用<xref:System.Drawing.Graphics.DrawEllipse%2A>使用<xref:System.Drawing.Pen>对象中要绘制带纹理的椭圆。</span><span class="sxs-lookup"><span data-stu-id="c6d21-110">The call to <xref:System.Drawing.Graphics.DrawEllipse%2A> uses the <xref:System.Drawing.Pen> object to draw a textured ellipse.</span></span>  
  
 <span data-ttu-id="c6d21-111">下图显示位图和带纹理的椭圆。</span><span class="sxs-lookup"><span data-stu-id="c6d21-111">The following illustration shows the bitmap and the textured ellipse.</span></span>  
  
 <span data-ttu-id="c6d21-112">![钢笔](../../../../docs/framework/winforms/advanced/media/pens7.png "pens7")</span><span class="sxs-lookup"><span data-stu-id="c6d21-112">![Pens](../../../../docs/framework/winforms/advanced/media/pens7.png "pens7")</span></span>  
  
 [!code-csharp[System.Drawing.UsingAPen#61](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#61)]
 [!code-vb[System.Drawing.UsingAPen#61](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#61)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="c6d21-113">编译代码</span><span class="sxs-lookup"><span data-stu-id="c6d21-113">Compiling the Code</span></span>  
 <span data-ttu-id="c6d21-114">创建 Windows 窗体和处理该窗体<xref:System.Windows.Forms.Control.Paint>事件。</span><span class="sxs-lookup"><span data-stu-id="c6d21-114">Create a Windows Form and handle the form's <xref:System.Windows.Forms.Control.Paint> event.</span></span> <span data-ttu-id="c6d21-115">前面将代码粘贴到<xref:System.Windows.Forms.Control.Paint>事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="c6d21-115">Paste the preceding code into the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span> <span data-ttu-id="c6d21-116">替换`Texture.jpg`你系统上有效的映像。</span><span class="sxs-lookup"><span data-stu-id="c6d21-116">Replace `Texture.jpg` with an image valid on your system.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c6d21-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="c6d21-117">See Also</span></span>  
 [<span data-ttu-id="c6d21-118">使用笔绘制直线和形状</span><span class="sxs-lookup"><span data-stu-id="c6d21-118">Using a Pen to Draw Lines and Shapes</span></span>](../../../../docs/framework/winforms/advanced/using-a-pen-to-draw-lines-and-shapes.md)  
 [<span data-ttu-id="c6d21-119">Windows 窗体中的图形和绘制</span><span class="sxs-lookup"><span data-stu-id="c6d21-119">Graphics and Drawing in Windows Forms</span></span>](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)
