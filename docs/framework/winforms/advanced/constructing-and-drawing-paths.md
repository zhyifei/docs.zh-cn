---
title: "构造并绘制轨迹"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- paths [Windows Forms], drawing
- drawing paths [Windows Forms]
- graphics paths [Windows Forms], creating
- graphics paths [Windows Forms], drawing
- examples [Windows Forms], drawing paths
ms.assetid: f16ec921-56cf-46d1-9741-d7316ad06b23
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e6cec2356159b59e58ac6785a2988df7b2fac0e4
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="constructing-and-drawing-paths"></a><span data-ttu-id="0367a-102">构造并绘制轨迹</span><span class="sxs-lookup"><span data-stu-id="0367a-102">Constructing and Drawing Paths</span></span>
<span data-ttu-id="0367a-103">路径是可操作并作为单个单元绘制图形基元 （线条、 矩形、 曲线、 文本和 like） 的序列。</span><span class="sxs-lookup"><span data-stu-id="0367a-103">A path is a sequence of graphics primitives (lines, rectangles, curves, text, and the like) that can be manipulated and drawn as a single unit.</span></span> <span data-ttu-id="0367a-104">路径可以划分为*数字*，是打开还是关闭。</span><span class="sxs-lookup"><span data-stu-id="0367a-104">A path can be divided into *figures* that are either open or closed.</span></span> <span data-ttu-id="0367a-105">图可以包含多个基元。</span><span class="sxs-lookup"><span data-stu-id="0367a-105">A figure can contain several primitives.</span></span>  
  
 <span data-ttu-id="0367a-106">你可以通过调用绘制路径<xref:System.Drawing.Graphics.DrawPath%2A>方法<xref:System.Drawing.Graphics>类，并且你可以通过调用填充路径<xref:System.Drawing.Graphics.FillPath%2A>方法<xref:System.Drawing.Graphics>类。</span><span class="sxs-lookup"><span data-stu-id="0367a-106">You can draw a path by calling the <xref:System.Drawing.Graphics.DrawPath%2A> method of the <xref:System.Drawing.Graphics> class, and you can fill a path by calling the <xref:System.Drawing.Graphics.FillPath%2A> method of the <xref:System.Drawing.Graphics> class.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="0367a-107">本节内容</span><span class="sxs-lookup"><span data-stu-id="0367a-107">In This Section</span></span>  
 [<span data-ttu-id="0367a-108">如何：通过直线、曲线和形状创建图</span><span class="sxs-lookup"><span data-stu-id="0367a-108">How to: Create Figures from Lines, Curves, and Shapes</span></span>](../../../../docs/framework/winforms/advanced/how-to-create-figures-from-lines-curves-and-shapes.md)  
 <span data-ttu-id="0367a-109">演示如何使用<xref:System.Drawing.Drawing2D.GraphicsPath>创建图表。</span><span class="sxs-lookup"><span data-stu-id="0367a-109">Shows how to use a <xref:System.Drawing.Drawing2D.GraphicsPath> to create figures.</span></span>  
  
 [<span data-ttu-id="0367a-110">如何：填充开放图形</span><span class="sxs-lookup"><span data-stu-id="0367a-110">How to: Fill Open Figures</span></span>](../../../../docs/framework/winforms/advanced/how-to-fill-open-figures.md)  
 <span data-ttu-id="0367a-111">说明如何填充<xref:System.Drawing.Drawing2D.GraphicsPath>。</span><span class="sxs-lookup"><span data-stu-id="0367a-111">Explains how to fill a <xref:System.Drawing.Drawing2D.GraphicsPath>.</span></span>  
  
 [<span data-ttu-id="0367a-112">如何：将曲线路径展平成直线</span><span class="sxs-lookup"><span data-stu-id="0367a-112">How to: Flatten a Curved Path into a Line</span></span>](../../../../docs/framework/winforms/advanced/how-to-flatten-a-curved-path-into-a-line.md)  
 <span data-ttu-id="0367a-113">演示如何以平展<xref:System.Drawing.Drawing2D.GraphicsPath>。</span><span class="sxs-lookup"><span data-stu-id="0367a-113">Shows how to flatten a <xref:System.Drawing.Drawing2D.GraphicsPath>.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="0367a-114">参考</span><span class="sxs-lookup"><span data-stu-id="0367a-114">Reference</span></span>  
 <xref:System.Drawing.Drawing2D.GraphicsPath>  
 <span data-ttu-id="0367a-115">对此类进行描述，并包含其所有成员的链接。</span><span class="sxs-lookup"><span data-stu-id="0367a-115">Describes this class and contains links to all of its members.</span></span>
