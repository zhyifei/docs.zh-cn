---
title: "如何：使用线条、曲线和形状创建图形"
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
- figures [Windows Forms], creating from shapes
- figures [Windows Forms], creating from lines
ms.assetid: 82fd56c7-b443-4765-9b7c-62ce030656ec
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: b382e0e1a627d7f61ce8ac664ac47d98c3725cad
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-figures-from-lines-curves-and-shapes"></a><span data-ttu-id="7e216-102">如何：使用线条、曲线和形状创建图形</span><span class="sxs-lookup"><span data-stu-id="7e216-102">How to: Create Figures from Lines, Curves, and Shapes</span></span>
<span data-ttu-id="7e216-103">若要创建一个数字，构造<xref:System.Drawing.Drawing2D.GraphicsPath>，然后调用方法，如<xref:System.Drawing.Drawing2D.GraphicsPath.AddLine%2A>和<xref:System.Drawing.Drawing2D.GraphicsPath.AddCurve%2A>，以将基元添加到路径。</span><span class="sxs-lookup"><span data-stu-id="7e216-103">To create a figure, construct a <xref:System.Drawing.Drawing2D.GraphicsPath>, and then call methods, such as <xref:System.Drawing.Drawing2D.GraphicsPath.AddLine%2A> and <xref:System.Drawing.Drawing2D.GraphicsPath.AddCurve%2A>, to add primitives to the path.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7e216-104">示例</span><span class="sxs-lookup"><span data-stu-id="7e216-104">Example</span></span>  
 <span data-ttu-id="7e216-105">下面的代码示例创建具有图形的路径：</span><span class="sxs-lookup"><span data-stu-id="7e216-105">The following code examples create paths that have figures:</span></span>  
  
-   <span data-ttu-id="7e216-106">第一个示例创建具有单一图的路径。</span><span class="sxs-lookup"><span data-stu-id="7e216-106">The first example creates a path that has a single figure.</span></span> <span data-ttu-id="7e216-107">图包含一段弧。圆弧有扫描角度为-180 度，这是默认坐标系统中按逆时针方向。</span><span class="sxs-lookup"><span data-stu-id="7e216-107">The figure consists of a single arc. The arc has a sweep angle of –180 degrees, which is counterclockwise in the default coordinate system.</span></span>  
  
-   <span data-ttu-id="7e216-108">第二个示例创建具有两个图片的路径。</span><span class="sxs-lookup"><span data-stu-id="7e216-108">The second example creates a path that has two figures.</span></span> <span data-ttu-id="7e216-109">第一个图是一段弧线后, 跟行。</span><span class="sxs-lookup"><span data-stu-id="7e216-109">The first figure is an arc followed by a line.</span></span> <span data-ttu-id="7e216-110">第二个图是后跟一条线的曲线接行。</span><span class="sxs-lookup"><span data-stu-id="7e216-110">The second figure is a line followed by a curve followed by a line.</span></span> <span data-ttu-id="7e216-111">第一张图处于打开状态，并关闭第二个图。</span><span class="sxs-lookup"><span data-stu-id="7e216-111">The first figure is left open, and the second figure is closed.</span></span>  
  
 [!code-csharp[System.Drawing.ConstructingDrawingPaths#21](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingPaths/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.ConstructingDrawingPaths#21](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingPaths/VB/Class1.vb#21)]  
  
 [!code-csharp[System.Drawing.ConstructingDrawingPaths#22](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingPaths/CS/Class1.cs#22)]
 [!code-vb[System.Drawing.ConstructingDrawingPaths#22](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingPaths/VB/Class1.vb#22)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="7e216-112">编译代码</span><span class="sxs-lookup"><span data-stu-id="7e216-112">Compiling the Code</span></span>  
 <span data-ttu-id="7e216-113">前面的示例专用于 Windows 窗体，并且它们要求<xref:System.Windows.Forms.PaintEventArgs> `e`，这是一个参数的<xref:System.Windows.Forms.Control.Paint>事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="7e216-113">The previous examples are designed for use with Windows Forms, and they require <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7e216-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7e216-114">See Also</span></span>  
 <xref:System.Drawing.Drawing2D.GraphicsPath>  
 [<span data-ttu-id="7e216-115">构造并绘制路径</span><span class="sxs-lookup"><span data-stu-id="7e216-115">Constructing and Drawing Paths</span></span>](../../../../docs/framework/winforms/advanced/constructing-and-drawing-paths.md)  
 [<span data-ttu-id="7e216-116">使用笔绘制直线和形状</span><span class="sxs-lookup"><span data-stu-id="7e216-116">Using a Pen to Draw Lines and Shapes</span></span>](../../../../docs/framework/winforms/advanced/using-a-pen-to-draw-lines-and-shapes.md)
