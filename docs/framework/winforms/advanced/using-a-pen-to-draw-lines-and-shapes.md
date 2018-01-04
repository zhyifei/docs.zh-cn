---
title: "使用钢笔绘制线条和形状"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- pens
- examples [Windows Forms], drawing lines and shapes
- examples [Windows Forms], pens
- drawing
ms.assetid: 8a7542ab-3e9e-443f-8405-2d6053528e20
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 35f43316e2535aae6622ccf7952f649cdb92fc81
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="using-a-pen-to-draw-lines-and-shapes"></a><span data-ttu-id="f91d2-102">使用钢笔绘制线条和形状</span><span class="sxs-lookup"><span data-stu-id="f91d2-102">Using a Pen to Draw Lines and Shapes</span></span>
<span data-ttu-id="f91d2-103">使用[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]`Pen`对象绘制直线线段、 曲线和形状的轮廓。</span><span class="sxs-lookup"><span data-stu-id="f91d2-103">Use [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] `Pen` objects to draw line segments, curves, and the outlines of shapes.</span></span> <span data-ttu-id="f91d2-104">在本部分中，*行*指任一这些，除非另行指定，表示仅一条直线段。</span><span class="sxs-lookup"><span data-stu-id="f91d2-104">In this section, *line* refers to any of these, unless specified to mean only a line segment.</span></span> <span data-ttu-id="f91d2-105">设置钢笔若要控制颜色、 宽度、 对齐方式，以及使用该钢笔绘制的直线的样式的属性。</span><span class="sxs-lookup"><span data-stu-id="f91d2-105">Set the properties of a pen to control the color, width, alignment, and style of lines drawn with that pen.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="f91d2-106">本节内容</span><span class="sxs-lookup"><span data-stu-id="f91d2-106">In This Section</span></span>  
 [<span data-ttu-id="f91d2-107">如何：使用笔绘制直线</span><span class="sxs-lookup"><span data-stu-id="f91d2-107">How to: Use a Pen to Draw Lines</span></span>](../../../../docs/framework/winforms/advanced/how-to-use-a-pen-to-draw-lines.md)  
 <span data-ttu-id="f91d2-108">说明如何绘制线条。</span><span class="sxs-lookup"><span data-stu-id="f91d2-108">Explains how to draw lines.</span></span>  
  
 [<span data-ttu-id="f91d2-109">如何：使用笔绘制矩形</span><span class="sxs-lookup"><span data-stu-id="f91d2-109">How to: Use a Pen to Draw Rectangles</span></span>](../../../../docs/framework/winforms/advanced/how-to-use-a-pen-to-draw-rectangles.md)  
 <span data-ttu-id="f91d2-110">描述如何绘制矩形。</span><span class="sxs-lookup"><span data-stu-id="f91d2-110">Describes how to draw rectangles.</span></span>  
  
 [<span data-ttu-id="f91d2-111">如何：设置笔的宽度和对齐方式</span><span class="sxs-lookup"><span data-stu-id="f91d2-111">How to: Set Pen Width and Alignment</span></span>](../../../../docs/framework/winforms/advanced/how-to-set-pen-width-and-alignment.md)  
 <span data-ttu-id="f91d2-112">说明如何更改宽度和对齐方式`Pen`对象。</span><span class="sxs-lookup"><span data-stu-id="f91d2-112">Explains how to change the width and alignment of a `Pen` object.</span></span>  
  
 [<span data-ttu-id="f91d2-113">如何：绘制具有线帽的直线</span><span class="sxs-lookup"><span data-stu-id="f91d2-113">How to: Draw a Line with Line Caps</span></span>](../../../../docs/framework/winforms/advanced/how-to-draw-a-line-with-line-caps.md)  
 <span data-ttu-id="f91d2-114">描述如何添加时绘制一条线终止线帽。</span><span class="sxs-lookup"><span data-stu-id="f91d2-114">Describes how to add end caps when drawing a line.</span></span>  
  
 [<span data-ttu-id="f91d2-115">如何：联接直线</span><span class="sxs-lookup"><span data-stu-id="f91d2-115">How to: Join Lines</span></span>](../../../../docs/framework/winforms/advanced/how-to-join-lines.md)  
 <span data-ttu-id="f91d2-116">演示如何连接两个线条。</span><span class="sxs-lookup"><span data-stu-id="f91d2-116">Shows how to join two lines.</span></span>  
  
 [<span data-ttu-id="f91d2-117">如何：绘制自定义虚线</span><span class="sxs-lookup"><span data-stu-id="f91d2-117">How to: Draw a Custom Dashed Line</span></span>](../../../../docs/framework/winforms/advanced/how-to-draw-a-custom-dashed-line.md)  
 <span data-ttu-id="f91d2-118">描述如何绘制的虚线。</span><span class="sxs-lookup"><span data-stu-id="f91d2-118">Describes how to draw a dashed line.</span></span>  
  
 [<span data-ttu-id="f91d2-119">如何：绘制填充了纹理的直线</span><span class="sxs-lookup"><span data-stu-id="f91d2-119">How to: Draw a Line Filled with a Texture</span></span>](../../../../docs/framework/winforms/advanced/how-to-draw-a-line-filled-with-a-texture.md)  
 <span data-ttu-id="f91d2-120">说明如何绘制纹理填充的行。</span><span class="sxs-lookup"><span data-stu-id="f91d2-120">Explains how to draw a texture-filled line.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="f91d2-121">参考</span><span class="sxs-lookup"><span data-stu-id="f91d2-121">Reference</span></span>  
 <xref:System.Drawing.Pen>  
 <span data-ttu-id="f91d2-122">对此类进行描述，并提供指向其所有成员的链接。</span><span class="sxs-lookup"><span data-stu-id="f91d2-122">Describes this class and has links to all its members.</span></span>
