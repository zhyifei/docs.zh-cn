---
title: "如何：绘制具有线帽的线条"
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
- lines [Windows Forms], drawing
- pens [Windows Forms], drawing lines
- drawing lines [Windows Forms], line caps
ms.assetid: eb68c3e1-c400-4886-8a04-76978a429cb6
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 4048757e11724aa1e175d8b18c47f48d22d807e4
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-draw-a-line-with-line-caps"></a><span data-ttu-id="fee41-102">如何：绘制具有线帽的线条</span><span class="sxs-lookup"><span data-stu-id="fee41-102">How to: Draw a Line with Line Caps</span></span>
<span data-ttu-id="fee41-103">可以使用一个称为线帽的多个形状绘制的开始或行尾。</span><span class="sxs-lookup"><span data-stu-id="fee41-103">You can draw the start or end of a line in one of several shapes called line caps.</span></span> [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]<span data-ttu-id="fee41-104">支持多种的线帽，如循环、 方形、 菱形和箭头。</span><span class="sxs-lookup"><span data-stu-id="fee41-104"> supports several line caps, such as round, square, diamond, and arrowhead.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fee41-105">示例</span><span class="sxs-lookup"><span data-stu-id="fee41-105">Example</span></span>  
 <span data-ttu-id="fee41-106">你可以指定开头的行 （起始线帽），行 （结束端） 的末尾或虚线 (dash cap) 的短划线的线帽。</span><span class="sxs-lookup"><span data-stu-id="fee41-106">You can specify line caps for the start of a line (start cap), the end of a line (end cap), or the dashes of a dashed line (dash cap).</span></span>  
  
 <span data-ttu-id="fee41-107">下面的示例绘制某一端箭头与另一端圆端帽的线条。</span><span class="sxs-lookup"><span data-stu-id="fee41-107">The following example draws a line with an arrowhead at one end and a round cap at the other end.</span></span> <span data-ttu-id="fee41-108">图中显示生成的行：</span><span class="sxs-lookup"><span data-stu-id="fee41-108">The illustration shows the resulting line:</span></span>  
  
 <span data-ttu-id="fee41-109">![钢笔](../../../../docs/framework/winforms/advanced/media/pens4.gif "pens4")</span><span class="sxs-lookup"><span data-stu-id="fee41-109">![Pens](../../../../docs/framework/winforms/advanced/media/pens4.gif "pens4")</span></span>  
  
 [!code-csharp[System.Drawing.UsingAPen#71](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#71)]
 [!code-vb[System.Drawing.UsingAPen#71](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#71)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="fee41-110">编译代码</span><span class="sxs-lookup"><span data-stu-id="fee41-110">Compiling the Code</span></span>  
  
-   <span data-ttu-id="fee41-111">创建 Windows 窗体和处理该窗体<xref:System.Windows.Forms.Control.Paint>事件。</span><span class="sxs-lookup"><span data-stu-id="fee41-111">Create a Windows Form and handle the form's <xref:System.Windows.Forms.Control.Paint> event.</span></span> <span data-ttu-id="fee41-112">示例将代码粘贴到<xref:System.Windows.Forms.Control.Paint>传递的事件处理程序`e`作为<xref:System.Windows.Forms.PaintEventArgs>。</span><span class="sxs-lookup"><span data-stu-id="fee41-112">Paste the example code into the <xref:System.Windows.Forms.Control.Paint> event handler passing `e` as <xref:System.Windows.Forms.PaintEventArgs>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fee41-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="fee41-113">See Also</span></span>  
 <xref:System.Drawing.Pen?displayProperty=nameWithType>  
 <xref:System.Drawing.Drawing2D.LineCap?displayProperty=nameWithType>  
 [<span data-ttu-id="fee41-114">Windows 窗体中的图形和绘制</span><span class="sxs-lookup"><span data-stu-id="fee41-114">Graphics and Drawing in Windows Forms</span></span>](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)  
 [<span data-ttu-id="fee41-115">使用笔绘制直线和形状</span><span class="sxs-lookup"><span data-stu-id="fee41-115">Using a Pen to Draw Lines and Shapes</span></span>](../../../../docs/framework/winforms/advanced/using-a-pen-to-draw-lines-and-shapes.md)
