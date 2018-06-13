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
ms.openlocfilehash: b7422ae2a4dc4d59fd337ab2294caa0d65057bae
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33521155"
---
# <a name="how-to-fill-open-figures"></a><span data-ttu-id="be9fa-102">如何：填充开放图形</span><span class="sxs-lookup"><span data-stu-id="be9fa-102">How to: Fill Open Figures</span></span>
<span data-ttu-id="be9fa-103">你可以通过传递填写路径<xref:System.Drawing.Drawing2D.GraphicsPath>对象传递给<xref:System.Drawing.Graphics.FillPath%2A>方法。</span><span class="sxs-lookup"><span data-stu-id="be9fa-103">You can fill a path by passing a <xref:System.Drawing.Drawing2D.GraphicsPath> object to the <xref:System.Drawing.Graphics.FillPath%2A> method.</span></span> <span data-ttu-id="be9fa-104"><xref:System.Drawing.Graphics.FillPath%2A>方法填充的填充模式 （备用或绕） 根据当前设置的路径的路径。</span><span class="sxs-lookup"><span data-stu-id="be9fa-104">The <xref:System.Drawing.Graphics.FillPath%2A> method fills the path according to the fill mode (alternate or winding) currently set for the path.</span></span> <span data-ttu-id="be9fa-105">如果路径具有任何开放图形，路径已填充，就像这些图形闭合。</span><span class="sxs-lookup"><span data-stu-id="be9fa-105">If the path has any open figures, the path is filled as if those figures were closed.</span></span> [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]<span data-ttu-id="be9fa-106"> 通过从其结束的点到起始点绘制一条直线闭合图形。</span><span class="sxs-lookup"><span data-stu-id="be9fa-106"> closes a figure by drawing a straight line from its ending point to its starting point.</span></span>  
  
## <a name="example"></a><span data-ttu-id="be9fa-107">示例</span><span class="sxs-lookup"><span data-stu-id="be9fa-107">Example</span></span>  
 <span data-ttu-id="be9fa-108">下面的示例创建具有一个开放图形 （一段弧线） 和一个闭合的图形 （椭圆） 的路径。</span><span class="sxs-lookup"><span data-stu-id="be9fa-108">The following example creates a path that has one open figure (an arc) and one closed figure (an ellipse).</span></span> <span data-ttu-id="be9fa-109"><xref:System.Drawing.Graphics.FillPath%2A>方法填充根据默认的填充模式，即路径<xref:System.Drawing.Drawing2D.FillMode.Alternate>。</span><span class="sxs-lookup"><span data-stu-id="be9fa-109">The <xref:System.Drawing.Graphics.FillPath%2A> method fills the path according to the default fill mode, which is <xref:System.Drawing.Drawing2D.FillMode.Alternate>.</span></span>  
  
 <span data-ttu-id="be9fa-110">下图显示示例代码的输出。</span><span class="sxs-lookup"><span data-stu-id="be9fa-110">The following illustration shows the output of the example code.</span></span> <span data-ttu-id="be9fa-111">请注意路径已填充 (根据<xref:System.Drawing.Drawing2D.FillMode.Alternate>) 就像打开图关闭的一条直线从其结束的点到起始点。</span><span class="sxs-lookup"><span data-stu-id="be9fa-111">Note that the path is filled (according to <xref:System.Drawing.Drawing2D.FillMode.Alternate>) as if the open figure were closed by a straight line from its ending point to its starting point.</span></span>  
  
 <span data-ttu-id="be9fa-112">![填充开放路径](../../../../docs/framework/winforms/advanced/media/fillopenpath.png "FillOpenPath")</span><span class="sxs-lookup"><span data-stu-id="be9fa-112">![Fill Open Path](../../../../docs/framework/winforms/advanced/media/fillopenpath.png "FillOpenPath")</span></span>  
  
 [!code-csharp[System.Drawing.ConstructingDrawingPaths#11](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingPaths/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.ConstructingDrawingPaths#11](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingPaths/VB/Class1.vb#11)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="be9fa-113">编译代码</span><span class="sxs-lookup"><span data-stu-id="be9fa-113">Compiling the Code</span></span>  
 <span data-ttu-id="be9fa-114">前面的示例专用于 Windows 窗体，它需要 <xref:System.Windows.Forms.PaintEventArgs> `e`，后者是 <xref:System.Windows.Forms.Control.Paint> 事件处理程序的参数。</span><span class="sxs-lookup"><span data-stu-id="be9fa-114">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="be9fa-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="be9fa-115">See Also</span></span>  
 <xref:System.Drawing.Drawing2D.GraphicsPath>  
 [<span data-ttu-id="be9fa-116">GDI+ 中的图形路径</span><span class="sxs-lookup"><span data-stu-id="be9fa-116">Graphics Paths in GDI+</span></span>](../../../../docs/framework/winforms/advanced/graphics-paths-in-gdi.md)
