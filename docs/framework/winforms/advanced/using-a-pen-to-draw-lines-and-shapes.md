---
title: 使用钢笔绘制线条和形状
ms.date: 03/30/2017
helpviewer_keywords:
- pens
- examples [Windows Forms], drawing lines and shapes
- examples [Windows Forms], pens
- drawing
ms.assetid: 8a7542ab-3e9e-443f-8405-2d6053528e20
ms.openlocfilehash: 3846c59712cec6003c35f336714041544dec94b3
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/09/2019
ms.locfileid: "57716269"
---
# <a name="using-a-pen-to-draw-lines-and-shapes"></a><span data-ttu-id="0f92b-102">使用钢笔绘制线条和形状</span><span class="sxs-lookup"><span data-stu-id="0f92b-102">Using a Pen to Draw Lines and Shapes</span></span>
<span data-ttu-id="0f92b-103">使用[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]`Pen`对象绘制的直线线段、 曲线和形状的轮廓。</span><span class="sxs-lookup"><span data-stu-id="0f92b-103">Use [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] `Pen` objects to draw line segments, curves, and the outlines of shapes.</span></span> <span data-ttu-id="0f92b-104">在本部分中，*行*指任何，除非指定为意味着只有一条线段。</span><span class="sxs-lookup"><span data-stu-id="0f92b-104">In this section, *line* refers to any of these, unless specified to mean only a line segment.</span></span> <span data-ttu-id="0f92b-105">设置笔来控制颜色、 宽度、 对齐方式和使用该笔绘制的直线的样式属性。</span><span class="sxs-lookup"><span data-stu-id="0f92b-105">Set the properties of a pen to control the color, width, alignment, and style of lines drawn with that pen.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="0f92b-106">本节内容</span><span class="sxs-lookup"><span data-stu-id="0f92b-106">In This Section</span></span>  
 [<span data-ttu-id="0f92b-107">如何：使用笔绘制直线</span><span class="sxs-lookup"><span data-stu-id="0f92b-107">How to: Use a Pen to Draw Lines</span></span>](how-to-use-a-pen-to-draw-lines.md)  
 <span data-ttu-id="0f92b-108">说明如何绘制线条。</span><span class="sxs-lookup"><span data-stu-id="0f92b-108">Explains how to draw lines.</span></span>  
  
 [<span data-ttu-id="0f92b-109">如何：使用笔绘制矩形</span><span class="sxs-lookup"><span data-stu-id="0f92b-109">How to: Use a Pen to Draw Rectangles</span></span>](how-to-use-a-pen-to-draw-rectangles.md)  
 <span data-ttu-id="0f92b-110">描述如何绘制矩形。</span><span class="sxs-lookup"><span data-stu-id="0f92b-110">Describes how to draw rectangles.</span></span>  
  
 [<span data-ttu-id="0f92b-111">如何：设置笔的宽度和对齐方式</span><span class="sxs-lookup"><span data-stu-id="0f92b-111">How to: Set Pen Width and Alignment</span></span>](how-to-set-pen-width-and-alignment.md)  
 <span data-ttu-id="0f92b-112">说明如何更改宽度和对齐方式`Pen`对象。</span><span class="sxs-lookup"><span data-stu-id="0f92b-112">Explains how to change the width and alignment of a `Pen` object.</span></span>  
  
 [<span data-ttu-id="0f92b-113">如何：绘制具有线帽的线条</span><span class="sxs-lookup"><span data-stu-id="0f92b-113">How to: Draw a Line with Line Caps</span></span>](how-to-draw-a-line-with-line-caps.md)  
 <span data-ttu-id="0f92b-114">介绍如何添加时绘制一条线终止线帽。</span><span class="sxs-lookup"><span data-stu-id="0f92b-114">Describes how to add end caps when drawing a line.</span></span>  
  
 [<span data-ttu-id="0f92b-115">如何：联接线</span><span class="sxs-lookup"><span data-stu-id="0f92b-115">How to: Join Lines</span></span>](how-to-join-lines.md)  
 <span data-ttu-id="0f92b-116">演示如何联接两个行。</span><span class="sxs-lookup"><span data-stu-id="0f92b-116">Shows how to join two lines.</span></span>  
  
 [<span data-ttu-id="0f92b-117">如何：绘制自定义虚线</span><span class="sxs-lookup"><span data-stu-id="0f92b-117">How to: Draw a Custom Dashed Line</span></span>](how-to-draw-a-custom-dashed-line.md)  
 <span data-ttu-id="0f92b-118">描述如何绘制虚线。</span><span class="sxs-lookup"><span data-stu-id="0f92b-118">Describes how to draw a dashed line.</span></span>  
  
 [<span data-ttu-id="0f92b-119">如何：绘制用纹理填充的行</span><span class="sxs-lookup"><span data-stu-id="0f92b-119">How to: Draw a Line Filled with a Texture</span></span>](how-to-draw-a-line-filled-with-a-texture.md)  
 <span data-ttu-id="0f92b-120">介绍了如何绘制纹理填充的行。</span><span class="sxs-lookup"><span data-stu-id="0f92b-120">Explains how to draw a texture-filled line.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="0f92b-121">参考</span><span class="sxs-lookup"><span data-stu-id="0f92b-121">Reference</span></span>  
 <xref:System.Drawing.Pen>  
 <span data-ttu-id="0f92b-122">对此类进行描述，并提供指向其所有成员的链接。</span><span class="sxs-lookup"><span data-stu-id="0f92b-122">Describes this class and has links to all its members.</span></span>
