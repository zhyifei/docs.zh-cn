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
ms.openlocfilehash: 3af91611eef4b97dc3461ad8cd7e36c7aa10a16f
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/09/2019
ms.locfileid: "57713359"
---
# <a name="how-to-use-a-pen-to-draw-lines"></a><span data-ttu-id="3c68e-102">如何：使用笔绘制直线</span><span class="sxs-lookup"><span data-stu-id="3c68e-102">How to: Use a Pen to Draw Lines</span></span>
<span data-ttu-id="3c68e-103">若要绘制线条，需要<xref:System.Drawing.Graphics>对象和一个<xref:System.Drawing.Pen>对象。</span><span class="sxs-lookup"><span data-stu-id="3c68e-103">To draw lines, you need a <xref:System.Drawing.Graphics> object and a <xref:System.Drawing.Pen> object.</span></span> <span data-ttu-id="3c68e-104"><xref:System.Drawing.Graphics>对象提供<xref:System.Drawing.Graphics.DrawLine%2A>方法，和<xref:System.Drawing.Pen>对象将存储的行中，如颜色和宽度的功能。</span><span class="sxs-lookup"><span data-stu-id="3c68e-104">The <xref:System.Drawing.Graphics> object provides the <xref:System.Drawing.Graphics.DrawLine%2A> method, and the <xref:System.Drawing.Pen> object stores features of the line, such as color and width.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3c68e-105">示例</span><span class="sxs-lookup"><span data-stu-id="3c68e-105">Example</span></span>  
 <span data-ttu-id="3c68e-106">下面的示例绘制中的一行 （20、 10） 到 （300，100）。</span><span class="sxs-lookup"><span data-stu-id="3c68e-106">The following example draws a line from (20, 10) to (300, 100).</span></span> <span data-ttu-id="3c68e-107">第一个语句使用<xref:System.Drawing.Pen.%23ctor%2A>类构造函数创建黑色的笔。</span><span class="sxs-lookup"><span data-stu-id="3c68e-107">The first statement uses the <xref:System.Drawing.Pen.%23ctor%2A> class constructor to create a black pen.</span></span> <span data-ttu-id="3c68e-108">一个自变量传递给<xref:System.Drawing.Pen.%23ctor%2A>构造函数是<xref:System.Drawing.Color>使用创建的对象<xref:System.Drawing.Color.FromArgb%2A>方法。</span><span class="sxs-lookup"><span data-stu-id="3c68e-108">The one argument passed to the <xref:System.Drawing.Pen.%23ctor%2A> constructor is a <xref:System.Drawing.Color> object created with the <xref:System.Drawing.Color.FromArgb%2A> method.</span></span> <span data-ttu-id="3c68e-109">用来创建的值<xref:System.Drawing.Color>对象 — （255，0，0，0） — 对应于颜色的 alpha、 红色、 绿色和蓝色组件。</span><span class="sxs-lookup"><span data-stu-id="3c68e-109">The values used to create the <xref:System.Drawing.Color> object — (255, 0, 0, 0) — correspond to the alpha, red, green, and blue components of the color.</span></span> <span data-ttu-id="3c68e-110">这些值定义不透明的黑色笔。</span><span class="sxs-lookup"><span data-stu-id="3c68e-110">These values define an opaque black pen.</span></span>  
  
 [!code-csharp[System.Drawing.UsingAPen#11](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.UsingAPen#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#11)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="3c68e-111">编译代码</span><span class="sxs-lookup"><span data-stu-id="3c68e-111">Compiling the Code</span></span>  
 <span data-ttu-id="3c68e-112">前面的示例专用于 Windows 窗体，它需要 <xref:System.Windows.Forms.PaintEventArgs>`e`，后者是 <xref:System.Windows.Forms.Control.Paint> 事件处理程序的参数。</span><span class="sxs-lookup"><span data-stu-id="3c68e-112">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs>`e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3c68e-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="3c68e-113">See also</span></span>
- <xref:System.Drawing.Pen>
- [<span data-ttu-id="3c68e-114">使用笔绘制直线和形状</span><span class="sxs-lookup"><span data-stu-id="3c68e-114">Using a Pen to Draw Lines and Shapes</span></span>](using-a-pen-to-draw-lines-and-shapes.md)
- [<span data-ttu-id="3c68e-115">GDI+ 中的笔、直线和矩形</span><span class="sxs-lookup"><span data-stu-id="3c68e-115">Pens, Lines, and Rectangles in GDI+</span></span>](pens-lines-and-rectangles-in-gdi.md)
