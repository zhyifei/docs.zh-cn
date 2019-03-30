---
title: 如何：填充开放图形
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- open figures [Windows Forms], filling
- figures [Windows Forms], filling
ms.assetid: 5a36b0e4-f1f4-46c0-a85a-22ae98491950
ms.openlocfilehash: c7d193fdad554048ecd0f2cca5a83cfccbc2a403
ms.sourcegitcommit: 15ab532fd5e1f8073a4b678922d93b68b521bfa0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/29/2019
ms.locfileid: "58654076"
---
# <a name="how-to-fill-open-figures"></a><span data-ttu-id="49de9-102">如何：填充开放图形</span><span class="sxs-lookup"><span data-stu-id="49de9-102">How to: Fill Open Figures</span></span>
<span data-ttu-id="49de9-103">可以通过传递填充路径<xref:System.Drawing.Drawing2D.GraphicsPath>对象传递给<xref:System.Drawing.Graphics.FillPath%2A>方法。</span><span class="sxs-lookup"><span data-stu-id="49de9-103">You can fill a path by passing a <xref:System.Drawing.Drawing2D.GraphicsPath> object to the <xref:System.Drawing.Graphics.FillPath%2A> method.</span></span> <span data-ttu-id="49de9-104"><xref:System.Drawing.Graphics.FillPath%2A>方法填充填充模式 （备用或缠绕） 根据当前设置的路径的路径。</span><span class="sxs-lookup"><span data-stu-id="49de9-104">The <xref:System.Drawing.Graphics.FillPath%2A> method fills the path according to the fill mode (alternate or winding) currently set for the path.</span></span> <span data-ttu-id="49de9-105">如果该路径包含任何开放的图形，就像这些图形闭合填充的路径。</span><span class="sxs-lookup"><span data-stu-id="49de9-105">If the path has any open figures, the path is filled as if those figures were closed.</span></span> [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] <span data-ttu-id="49de9-106">通过从其结束点到起始点绘制一条直线，闭合图。</span><span class="sxs-lookup"><span data-stu-id="49de9-106">closes a figure by drawing a straight line from its ending point to its starting point.</span></span>  
  
## <a name="example"></a><span data-ttu-id="49de9-107">示例</span><span class="sxs-lookup"><span data-stu-id="49de9-107">Example</span></span>  
 <span data-ttu-id="49de9-108">以下示例创建具有一个开放的图形 (arc) 和一个闭合的图形 （椭圆） 的路径。</span><span class="sxs-lookup"><span data-stu-id="49de9-108">The following example creates a path that has one open figure (an arc) and one closed figure (an ellipse).</span></span> <span data-ttu-id="49de9-109"><xref:System.Drawing.Graphics.FillPath%2A>方法填充默认值填充模式中，是根据路径<xref:System.Drawing.Drawing2D.FillMode.Alternate>。</span><span class="sxs-lookup"><span data-stu-id="49de9-109">The <xref:System.Drawing.Graphics.FillPath%2A> method fills the path according to the default fill mode, which is <xref:System.Drawing.Drawing2D.FillMode.Alternate>.</span></span>  
  
 <span data-ttu-id="49de9-110">下图显示了示例代码的输出。</span><span class="sxs-lookup"><span data-stu-id="49de9-110">The following illustration shows the output of the example code.</span></span> <span data-ttu-id="49de9-111">请注意，填充路径 (根据<xref:System.Drawing.Drawing2D.FillMode.Alternate>) 像打开图关闭的一条直线从其结束点到起始点。</span><span class="sxs-lookup"><span data-stu-id="49de9-111">Note that the path is filled (according to <xref:System.Drawing.Drawing2D.FillMode.Alternate>) as if the open figure were closed by a straight line from its ending point to its starting point.</span></span>  
  
 ![图示显示 FillPath 方法的输出](./media/how-to-fill-open-figures/fill-path-alternate-mode.png)  
  
 [!code-csharp[System.Drawing.ConstructingDrawingPaths#11](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingPaths/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.ConstructingDrawingPaths#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingPaths/VB/Class1.vb#11)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="49de9-113">编译代码</span><span class="sxs-lookup"><span data-stu-id="49de9-113">Compiling the Code</span></span>  
 <span data-ttu-id="49de9-114">前面的示例专用于 Windows 窗体，并且它需要<xref:System.Windows.Forms.PaintEventArgs> `e`，这是一个参数的<xref:System.Windows.Forms.Control.Paint>事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="49de9-114">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="49de9-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="49de9-115">See also</span></span>
- <xref:System.Drawing.Drawing2D.GraphicsPath>
- [<span data-ttu-id="49de9-116">GDI+ 中的图形路径</span><span class="sxs-lookup"><span data-stu-id="49de9-116">Graphics Paths in GDI+</span></span>](graphics-paths-in-gdi.md)
