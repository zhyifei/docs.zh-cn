---
title: 如何：设置钢笔颜色
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- pens [Windows Forms], setting color
- colored pens
ms.assetid: a9df06f9-a6d5-4d9b-a2d1-583943540775
ms.openlocfilehash: 37bc289fa1eeb7ef5510474dff062ae76be5fc65
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33522377"
---
# <a name="how-to-set-the-color-of-a-pen"></a><span data-ttu-id="92575-102">如何：设置钢笔颜色</span><span class="sxs-lookup"><span data-stu-id="92575-102">How to: Set the Color of a Pen</span></span>
<span data-ttu-id="92575-103">此示例将更改预先存在的颜色<xref:System.Drawing.Pen>对象</span><span class="sxs-lookup"><span data-stu-id="92575-103">This example changes the color of a pre-existing <xref:System.Drawing.Pen> object</span></span>  
  
## <a name="example"></a><span data-ttu-id="92575-104">示例</span><span class="sxs-lookup"><span data-stu-id="92575-104">Example</span></span>  
 [!code-cpp[System.Drawing.ConceptualHowTos#9](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/cpp/form1.cpp#9)]
 [!code-csharp[System.Drawing.ConceptualHowTos#9](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/CS/form1.cs#9)]
 [!code-vb[System.Drawing.ConceptualHowTos#9](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/VB/form1.vb#9)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="92575-105">编译代码</span><span class="sxs-lookup"><span data-stu-id="92575-105">Compiling the Code</span></span>  
 <span data-ttu-id="92575-106">此示例需要：</span><span class="sxs-lookup"><span data-stu-id="92575-106">This example requires:</span></span>  
  
-   <span data-ttu-id="92575-107">A<xref:System.Drawing.Pen>对象名为`myPen`。</span><span class="sxs-lookup"><span data-stu-id="92575-107">A <xref:System.Drawing.Pen> object named `myPen`.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="92575-108">可靠编程</span><span class="sxs-lookup"><span data-stu-id="92575-108">Robust Programming</span></span>  
 <span data-ttu-id="92575-109">应调用<xref:System.Drawing.Pen.Dispose%2A>对对象所消耗的系统资源 (如<xref:System.Drawing.Pen>对象) 在完成使用它们后。</span><span class="sxs-lookup"><span data-stu-id="92575-109">You should call <xref:System.Drawing.Pen.Dispose%2A> on objects that consume system resources (such as <xref:System.Drawing.Pen> objects) after you are finished using them.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="92575-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="92575-110">See Also</span></span>  
 <xref:System.Drawing.Pen>  
 [<span data-ttu-id="92575-111">图形编程入门</span><span class="sxs-lookup"><span data-stu-id="92575-111">Getting Started with Graphics Programming</span></span>](../../../../docs/framework/winforms/advanced/getting-started-with-graphics-programming.md)  
 [<span data-ttu-id="92575-112">如何：创建笔</span><span class="sxs-lookup"><span data-stu-id="92575-112">How to: Create a Pen</span></span>](../../../../docs/framework/winforms/advanced/how-to-create-a-pen.md)  
 [<span data-ttu-id="92575-113">使用笔绘制直线和形状</span><span class="sxs-lookup"><span data-stu-id="92575-113">Using a Pen to Draw Lines and Shapes</span></span>](../../../../docs/framework/winforms/advanced/using-a-pen-to-draw-lines-and-shapes.md)  
 [<span data-ttu-id="92575-114">GDI+ 中的笔、直线和矩形</span><span class="sxs-lookup"><span data-stu-id="92575-114">Pens, Lines, and Rectangles in GDI+</span></span>](../../../../docs/framework/winforms/advanced/pens-lines-and-rectangles-in-gdi.md)
