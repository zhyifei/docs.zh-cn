---
title: 构造并绘制曲线
ms.date: 03/30/2017
helpviewer_keywords:
- drawing [Windows Forms], curves
- examples [Windows Forms], drawing curves
- curves [Windows Forms], drawing
ms.assetid: 76e92623-4130-4644-b867-faca58bdb3a2
ms.openlocfilehash: 4c1b0cc6c6f878569fcf0c392f1b6f9683ec8afc
ms.sourcegitcommit: b1cfd260928d464d91e20121f9bdba7611c94d71
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/02/2019
ms.locfileid: "67506099"
---
# <a name="constructing-and-drawing-curves"></a><span data-ttu-id="f4987-102">构造并绘制曲线</span><span class="sxs-lookup"><span data-stu-id="f4987-102">Constructing and Drawing Curves</span></span>
<span data-ttu-id="f4987-103">GDI + 支持多种类型的曲线： 省略号、 弧线、 基数样条和贝塞尔自由绘制曲线。</span><span class="sxs-lookup"><span data-stu-id="f4987-103">GDI+ supports several types of curves: ellipses, arcs, cardinal splines, and Bézier splines.</span></span> <span data-ttu-id="f4987-104">一个椭圆定义其边界的矩形;一段弧线，是椭圆的由起始角度和扫描角度定义的一部分。</span><span class="sxs-lookup"><span data-stu-id="f4987-104">An ellipse is defined by its bounding rectangle; an arc is a portion of an ellipse defined by a starting angle and a sweep angle.</span></span> <span data-ttu-id="f4987-105">由一系列点和张力参数定义的基数样条 — 曲线平滑地通过在数组中，每个点和张力参数影响曲线弯曲的方式。</span><span class="sxs-lookup"><span data-stu-id="f4987-105">A cardinal spline is defined by an array of points and a tension parameter — the curve passes smoothly through each point in the array, and the tension parameter influences the way the curve bends.</span></span> <span data-ttu-id="f4987-106">由两个终结点和两个控制点曲线不会经历的控制点定义的贝塞尔样条，但影响方向和条曲线到另一个终结点从未能弯曲程度的控点。</span><span class="sxs-lookup"><span data-stu-id="f4987-106">A Bézier spline is defined by two endpoints and two control points  the curve does not pass through the control points, but the control points influence the direction and bend as the curve goes from one endpoint to the other.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="f4987-107">本节内容</span><span class="sxs-lookup"><span data-stu-id="f4987-107">In This Section</span></span>  
 [<span data-ttu-id="f4987-108">如何：绘制基数样条</span><span class="sxs-lookup"><span data-stu-id="f4987-108">How to: Draw Cardinal Splines</span></span>](how-to-draw-cardinal-splines.md)  
 <span data-ttu-id="f4987-109">介绍基本样条和绘制它们的方式。</span><span class="sxs-lookup"><span data-stu-id="f4987-109">Describes cardinal splines and how to draw them.</span></span>  
  
 [<span data-ttu-id="f4987-110">如何：绘制单个贝塞尔样条</span><span class="sxs-lookup"><span data-stu-id="f4987-110">How to: Draw a Single Bézier Spline</span></span>](how-to-draw-a-single-bezier-spline.md)  
 <span data-ttu-id="f4987-111">介绍的贝塞尔样条和绘制一个的方式。</span><span class="sxs-lookup"><span data-stu-id="f4987-111">Describes a Bézier spline and how to draw one.</span></span>  
  
 [<span data-ttu-id="f4987-112">如何：绘制一系列贝塞尔自由绘制曲线</span><span class="sxs-lookup"><span data-stu-id="f4987-112">How to: Draw a Sequence of Bézier Splines</span></span>](how-to-draw-a-sequence-of-bezier-splines.md)  
 <span data-ttu-id="f4987-113">介绍如何在序列中绘制贝塞尔样条。</span><span class="sxs-lookup"><span data-stu-id="f4987-113">Explains how to draw several Bézier splines in sequence.</span></span>
