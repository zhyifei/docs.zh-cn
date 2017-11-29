---
title: "如何：将曲线路径展平为直线"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- graphics [Windows Forms], flattening curves into lines
- curves [Windows Forms], flattening
- GraphicsPath object
- paths [Windows Forms], flattening
- drawing [Windows Forms], flattening curves
ms.assetid: e654b8de-25f4-4735-9208-42e4514a589c
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 62dedc987c2b622dc3f3aa81dac3cdea6dd75740
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-flatten-a-curved-path-into-a-line"></a><span data-ttu-id="234bd-102">如何：将曲线路径展平为直线</span><span class="sxs-lookup"><span data-stu-id="234bd-102">How to: Flatten a Curved Path into a Line</span></span>
<span data-ttu-id="234bd-103">A<xref:System.Drawing.Drawing2D.GraphicsPath>对象存储一系列行和贝塞尔样条。</span><span class="sxs-lookup"><span data-stu-id="234bd-103">A <xref:System.Drawing.Drawing2D.GraphicsPath> object stores a sequence of lines and Bézier splines.</span></span> <span data-ttu-id="234bd-104">可以将多种类型的曲线 （省略号、 弧、 基数样条） 添加到路径时，但之前存储在路径中，每个曲线转换为贝塞尔样条。</span><span class="sxs-lookup"><span data-stu-id="234bd-104">You can add several types of curves (ellipses, arcs, cardinal splines) to a path, but each curve is converted to a Bézier spline before it is stored in the path.</span></span> <span data-ttu-id="234bd-105">平展路径组成，将在路径中的每个贝塞尔样条转换为直线的序列。</span><span class="sxs-lookup"><span data-stu-id="234bd-105">Flattening a path consists of converting each Bézier spline in the path to a sequence of straight lines.</span></span> <span data-ttu-id="234bd-106">下图显示路径之前和之后平展。</span><span class="sxs-lookup"><span data-stu-id="234bd-106">The following illustration shows a path before and after flattening.</span></span>  
  
 <span data-ttu-id="234bd-107">![直线和曲线](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art32a.gif "AboutGdip02_Art32A")</span><span class="sxs-lookup"><span data-stu-id="234bd-107">![Straight Lines and Curves](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art32a.gif "AboutGdip02_Art32A")</span></span>  
  
### <a name="to-flatten-a-path"></a><span data-ttu-id="234bd-108">若要将路径展平</span><span class="sxs-lookup"><span data-stu-id="234bd-108">To Flatten a Path</span></span>  
  
-   <span data-ttu-id="234bd-109">调用<xref:System.Drawing.Drawing2D.GraphicsPath.Flatten%2A>方法<xref:System.Drawing.Drawing2D.GraphicsPath>对象。</span><span class="sxs-lookup"><span data-stu-id="234bd-109">call the <xref:System.Drawing.Drawing2D.GraphicsPath.Flatten%2A> method of a <xref:System.Drawing.Drawing2D.GraphicsPath> object.</span></span> <span data-ttu-id="234bd-110"><xref:System.Drawing.Drawing2D.GraphicsPath.Flatten%2A>方法接收指定的平展的路径和原始路径之间的最大距离的平坦度自变量。</span><span class="sxs-lookup"><span data-stu-id="234bd-110">The <xref:System.Drawing.Drawing2D.GraphicsPath.Flatten%2A> method receives a flatness argument that specifies the maximum distance between the flattened path and the original path.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="234bd-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="234bd-111">See Also</span></span>  
 <xref:System.Drawing.Drawing2D.GraphicsPath?displayProperty=nameWithType>  
 [<span data-ttu-id="234bd-112">直线、曲线和形状</span><span class="sxs-lookup"><span data-stu-id="234bd-112">Lines, Curves, and Shapes</span></span>](../../../../docs/framework/winforms/advanced/lines-curves-and-shapes.md)  
 [<span data-ttu-id="234bd-113">构造并绘制路径</span><span class="sxs-lookup"><span data-stu-id="234bd-113">Constructing and Drawing Paths</span></span>](../../../../docs/framework/winforms/advanced/constructing-and-drawing-paths.md)
