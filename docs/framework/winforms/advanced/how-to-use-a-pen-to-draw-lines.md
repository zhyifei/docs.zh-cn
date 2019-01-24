---
title: 如何：使用笔绘制直线
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- lines [Windows Forms], drawing
- pens [Windows Forms], drawing lines
ms.assetid: 0828c331-a438-4bdd-a4d6-3ef1e59e8795
ms.openlocfilehash: e24d02c2c6ab7537f968c013eb91838eb0bb812a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54730927"
---
# <a name="how-to-use-a-pen-to-draw-lines"></a><span data-ttu-id="fc2b8-102">如何：使用笔绘制直线</span><span class="sxs-lookup"><span data-stu-id="fc2b8-102">How to: Use a Pen to Draw Lines</span></span>
<span data-ttu-id="fc2b8-103">若要绘制线条，需要<xref:System.Drawing.Graphics>对象和一个<xref:System.Drawing.Pen>对象。</span><span class="sxs-lookup"><span data-stu-id="fc2b8-103">To draw lines, you need a <xref:System.Drawing.Graphics> object and a <xref:System.Drawing.Pen> object.</span></span> <span data-ttu-id="fc2b8-104"><xref:System.Drawing.Graphics>对象提供<xref:System.Drawing.Graphics.DrawLine%2A>方法，和<xref:System.Drawing.Pen>对象将存储的行中，如颜色和宽度的功能。</span><span class="sxs-lookup"><span data-stu-id="fc2b8-104">The <xref:System.Drawing.Graphics> object provides the <xref:System.Drawing.Graphics.DrawLine%2A> method, and the <xref:System.Drawing.Pen> object stores features of the line, such as color and width.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fc2b8-105">示例</span><span class="sxs-lookup"><span data-stu-id="fc2b8-105">Example</span></span>  
 <span data-ttu-id="fc2b8-106">下面的示例绘制中的一行 （20、 10） 到 （300，100）。</span><span class="sxs-lookup"><span data-stu-id="fc2b8-106">The following example draws a line from (20, 10) to (300, 100).</span></span> <span data-ttu-id="fc2b8-107">第一个语句使用<xref:System.Drawing.Pen.%23ctor%2A>类构造函数创建黑色的笔。</span><span class="sxs-lookup"><span data-stu-id="fc2b8-107">The first statement uses the <xref:System.Drawing.Pen.%23ctor%2A> class constructor to create a black pen.</span></span> <span data-ttu-id="fc2b8-108">一个自变量传递给<xref:System.Drawing.Pen.%23ctor%2A>构造函数是<xref:System.Drawing.Color>使用创建的对象<xref:System.Drawing.Color.FromArgb%2A>方法。</span><span class="sxs-lookup"><span data-stu-id="fc2b8-108">The one argument passed to the <xref:System.Drawing.Pen.%23ctor%2A> constructor is a <xref:System.Drawing.Color> object created with the <xref:System.Drawing.Color.FromArgb%2A> method.</span></span> <span data-ttu-id="fc2b8-109">用来创建的值<xref:System.Drawing.Color>对象 — （255，0，0，0） — 对应于颜色的 alpha、 红色、 绿色和蓝色组件。</span><span class="sxs-lookup"><span data-stu-id="fc2b8-109">The values used to create the <xref:System.Drawing.Color> object — (255, 0, 0, 0) — correspond to the alpha, red, green, and blue components of the color.</span></span> <span data-ttu-id="fc2b8-110">这些值定义不透明的黑色笔。</span><span class="sxs-lookup"><span data-stu-id="fc2b8-110">These values define an opaque black pen.</span></span>  
  
 [!code-csharp[System.Drawing.UsingAPen#11](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.UsingAPen#11](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#11)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="fc2b8-111">编译代码</span><span class="sxs-lookup"><span data-stu-id="fc2b8-111">Compiling the Code</span></span>  
 <span data-ttu-id="fc2b8-112">前面的示例专用于 Windows 窗体，并且它需要<xref:System.Windows.Forms.PaintEventArgs> `e`，这是一个参数的<xref:System.Windows.Forms.Control.Paint>事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="fc2b8-112">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs>`e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fc2b8-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="fc2b8-113">See also</span></span>
- <xref:System.Drawing.Pen>
- [<span data-ttu-id="fc2b8-114">使用笔绘制直线和形状</span><span class="sxs-lookup"><span data-stu-id="fc2b8-114">Using a Pen to Draw Lines and Shapes</span></span>](../../../../docs/framework/winforms/advanced/using-a-pen-to-draw-lines-and-shapes.md)
- [<span data-ttu-id="fc2b8-115">GDI+ 中的笔、直线和矩形</span><span class="sxs-lookup"><span data-stu-id="fc2b8-115">Pens, Lines, and Rectangles in GDI+</span></span>](../../../../docs/framework/winforms/advanced/pens-lines-and-rectangles-in-gdi.md)
