---
title: 构造并绘制曲线
ms.date: 03/30/2017
helpviewer_keywords:
- drawing [Windows Forms], curves
- examples [Windows Forms], drawing curves
- curves [Windows Forms], drawing
ms.assetid: 76e92623-4130-4644-b867-faca58bdb3a2
ms.openlocfilehash: d9a790060fdf0f0c2a739d99aba1b36cf0323f8b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33520612"
---
# <a name="constructing-and-drawing-curves"></a><span data-ttu-id="2ea8a-102">构造并绘制曲线</span><span class="sxs-lookup"><span data-stu-id="2ea8a-102">Constructing and Drawing Curves</span></span>
[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]<span data-ttu-id="2ea8a-103"> 支持多种类型的曲线： 省略号、 弧、 基数样条和贝塞尔样条。</span><span class="sxs-lookup"><span data-stu-id="2ea8a-103"> supports several types of curves: ellipses, arcs, cardinal splines, and Bézier splines.</span></span> <span data-ttu-id="2ea8a-104">椭圆定义其边界的矩形; 通过一段弧线，是椭圆的由起始角度和扫描角度定义的一部分。</span><span class="sxs-lookup"><span data-stu-id="2ea8a-104">An ellipse is defined by its bounding rectangle; an arc is a portion of an ellipse defined by a starting angle and a sweep angle.</span></span> <span data-ttu-id="2ea8a-105">由一组点和张力参数定义的基数样条-曲线平滑地通过在数组中，每个点和张力参数影响曲线弯曲的方式。</span><span class="sxs-lookup"><span data-stu-id="2ea8a-105">A cardinal spline is defined by an array of points and a tension parameter — the curve passes smoothly through each point in the array, and the tension parameter influences the way the curve bends.</span></span> <span data-ttu-id="2ea8a-106">由两个终结点和通过控点、 未通过曲线的两个控制点定义的贝塞尔样条，但控点影响方向，并将弯曲，因为在曲线将从一个终结点与其他。</span><span class="sxs-lookup"><span data-stu-id="2ea8a-106">A Bézier spline is defined by two endpoints and two control points  the curve does not pass through the control points, but the control points influence the direction and bend as the curve goes from one endpoint to the other.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="2ea8a-107">本节内容</span><span class="sxs-lookup"><span data-stu-id="2ea8a-107">In This Section</span></span>  
 [<span data-ttu-id="2ea8a-108">如何：绘制基本自由绘制曲线</span><span class="sxs-lookup"><span data-stu-id="2ea8a-108">How to: Draw Cardinal Splines</span></span>](../../../../docs/framework/winforms/advanced/how-to-draw-cardinal-splines.md)  
 <span data-ttu-id="2ea8a-109">描述基数样条以及如何绘制它们。</span><span class="sxs-lookup"><span data-stu-id="2ea8a-109">Describes cardinal splines and how to draw them.</span></span>  
  
 [<span data-ttu-id="2ea8a-110">如何：绘制单贝塞尔自由绘制曲线</span><span class="sxs-lookup"><span data-stu-id="2ea8a-110">How to: Draw a Single Bézier Spline</span></span>](../../../../docs/framework/winforms/advanced/how-to-draw-a-single-bezier-spline.md)  
 <span data-ttu-id="2ea8a-111">描述的贝塞尔样条和绘制一个的方式。</span><span class="sxs-lookup"><span data-stu-id="2ea8a-111">Describes a Bézier spline and how to draw one.</span></span>  
  
 [<span data-ttu-id="2ea8a-112">如何：绘制一系列贝塞尔自由绘制曲线</span><span class="sxs-lookup"><span data-stu-id="2ea8a-112">How to: Draw a Sequence of Bézier Splines</span></span>](../../../../docs/framework/winforms/advanced/how-to-draw-a-sequence-of-bezier-splines.md)  
 <span data-ttu-id="2ea8a-113">说明如何在序列中绘制贝塞尔样条。</span><span class="sxs-lookup"><span data-stu-id="2ea8a-113">Explains how to draw several Bézier splines in sequence.</span></span>
