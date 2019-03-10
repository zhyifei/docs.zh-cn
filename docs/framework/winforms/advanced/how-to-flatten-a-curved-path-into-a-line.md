---
title: 如何：曲线的路径展行
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [Windows Forms], flattening curves into lines
- curves [Windows Forms], flattening
- GraphicsPath object
- paths [Windows Forms], flattening
- drawing [Windows Forms], flattening curves
ms.assetid: e654b8de-25f4-4735-9208-42e4514a589c
ms.openlocfilehash: d4847124c7af2e0b35d6874f53b85be4891b22df
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/09/2019
ms.locfileid: "57711039"
---
# <a name="how-to-flatten-a-curved-path-into-a-line"></a><span data-ttu-id="69e3b-102">如何：曲线的路径展行</span><span class="sxs-lookup"><span data-stu-id="69e3b-102">How to: Flatten a Curved Path into a Line</span></span>
<span data-ttu-id="69e3b-103">一个<xref:System.Drawing.Drawing2D.GraphicsPath>对象将存储一系列行和贝塞尔自由绘制曲线。</span><span class="sxs-lookup"><span data-stu-id="69e3b-103">A <xref:System.Drawing.Drawing2D.GraphicsPath> object stores a sequence of lines and Bézier splines.</span></span> <span data-ttu-id="69e3b-104">可以将多种类型的曲线 （省略号，弧线，基数样条） 添加到路径，但之后再将它存储在路径中的各段曲线转换为贝塞尔样条。</span><span class="sxs-lookup"><span data-stu-id="69e3b-104">You can add several types of curves (ellipses, arcs, cardinal splines) to a path, but each curve is converted to a Bézier spline before it is stored in the path.</span></span> <span data-ttu-id="69e3b-105">拉平路径组成，将在路径中的每个贝塞尔自由绘制曲线转换为一系列直线。</span><span class="sxs-lookup"><span data-stu-id="69e3b-105">Flattening a path consists of converting each Bézier spline in the path to a sequence of straight lines.</span></span> <span data-ttu-id="69e3b-106">下图显示一个路径之前和之后平展。</span><span class="sxs-lookup"><span data-stu-id="69e3b-106">The following illustration shows a path before and after flattening.</span></span>  
  
 <span data-ttu-id="69e3b-107">![直线和曲线](./media/aboutgdip02-art32a.gif "AboutGdip02_Art32A")</span><span class="sxs-lookup"><span data-stu-id="69e3b-107">![Straight Lines and Curves](./media/aboutgdip02-art32a.gif "AboutGdip02_Art32A")</span></span>  
  
### <a name="to-flatten-a-path"></a><span data-ttu-id="69e3b-108">若要平展路径</span><span class="sxs-lookup"><span data-stu-id="69e3b-108">To Flatten a Path</span></span>  
  
-   <span data-ttu-id="69e3b-109">调用<xref:System.Drawing.Drawing2D.GraphicsPath.Flatten%2A>方法的<xref:System.Drawing.Drawing2D.GraphicsPath>对象。</span><span class="sxs-lookup"><span data-stu-id="69e3b-109">call the <xref:System.Drawing.Drawing2D.GraphicsPath.Flatten%2A> method of a <xref:System.Drawing.Drawing2D.GraphicsPath> object.</span></span> <span data-ttu-id="69e3b-110"><xref:System.Drawing.Drawing2D.GraphicsPath.Flatten%2A>方法接收指定平展和原始路径之间的最大距离的展平自变量。</span><span class="sxs-lookup"><span data-stu-id="69e3b-110">The <xref:System.Drawing.Drawing2D.GraphicsPath.Flatten%2A> method receives a flatness argument that specifies the maximum distance between the flattened path and the original path.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="69e3b-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="69e3b-111">See also</span></span>
- <xref:System.Drawing.Drawing2D.GraphicsPath?displayProperty=nameWithType>
- [<span data-ttu-id="69e3b-112">直线、曲线和形状</span><span class="sxs-lookup"><span data-stu-id="69e3b-112">Lines, Curves, and Shapes</span></span>](lines-curves-and-shapes.md)
- [<span data-ttu-id="69e3b-113">构造并绘制路径</span><span class="sxs-lookup"><span data-stu-id="69e3b-113">Constructing and Drawing Paths</span></span>](constructing-and-drawing-paths.md)
