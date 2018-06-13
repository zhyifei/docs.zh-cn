---
title: 使用渐变画笔填充形状
ms.date: 03/30/2017
helpviewer_keywords:
- brushes [Windows Forms], gradient brushes
- gradient brushes
- examples [Windows Forms], gradient brushes
ms.assetid: 2c6037b9-05bd-44c0-a22a-19584b722524
ms.openlocfilehash: 857a9276a731ae5e69b3caa1a639d1315aba9901
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33525029"
---
# <a name="using-a-gradient-brush-to-fill-shapes"></a><span data-ttu-id="4801e-102">使用渐变画笔填充形状</span><span class="sxs-lookup"><span data-stu-id="4801e-102">Using a Gradient Brush to Fill Shapes</span></span>
<span data-ttu-id="4801e-103">渐变画笔用于填充形状的渐变的颜色。</span><span class="sxs-lookup"><span data-stu-id="4801e-103">You can use a gradient brush to fill a shape with a gradually changing color.</span></span> <span data-ttu-id="4801e-104">例如，水平渐变可用于填充形状的右边缘移动距左边缘的形状时逐渐改变的颜色。</span><span class="sxs-lookup"><span data-stu-id="4801e-104">For example, you can use a horizontal gradient to fill a shape with color that changes gradually as you move from the left edge of the shape to the right edge.</span></span> <span data-ttu-id="4801e-105">设想这样一个矩形的左边缘为黑色 （0，0，0，则表示由红色、 绿色和蓝色组件） 和右边缘，即红色 （表示 255，0，0）。</span><span class="sxs-lookup"><span data-stu-id="4801e-105">Imagine a rectangle with a left edge that is black (represented by red, green, and blue components 0, 0, 0) and a right edge that is red (represented by 255, 0, 0).</span></span> <span data-ttu-id="4801e-106">如果矩形为 256 像素宽，给定像素的红色组件将一个大于其左侧像素的红色组件。</span><span class="sxs-lookup"><span data-stu-id="4801e-106">If the rectangle is 256 pixels wide, the red component of a given pixel will be one greater than the red component of the pixel to its left.</span></span> <span data-ttu-id="4801e-107">行中的最左侧像素的颜色分量为 （0，0，0），第二个像素 （1，0，0），第三个像素都有 （2，0，0），依此类推，直到你到达最右边的像素，它具有颜色组件 （255，0，0）。</span><span class="sxs-lookup"><span data-stu-id="4801e-107">The leftmost pixel in a row has color components (0, 0, 0), the second pixel has (1, 0, 0), the third pixel has (2, 0, 0), and so on, until you get to the rightmost pixel, which has color components (255, 0, 0).</span></span> <span data-ttu-id="4801e-108">这些相比内, 插的颜色值构成的颜色渐变。</span><span class="sxs-lookup"><span data-stu-id="4801e-108">These interpolated color values make up the color gradient.</span></span>  
  
 <span data-ttu-id="4801e-109">线性渐变颜色更改，当您移动水平、 垂直或并行到指定的斜线。</span><span class="sxs-lookup"><span data-stu-id="4801e-109">A linear gradient changes color as you move horizontally, vertically, or parallel to a specified slanted line.</span></span> <span data-ttu-id="4801e-110">路径渐变更改颜色，随着有关内部和路径的边界。</span><span class="sxs-lookup"><span data-stu-id="4801e-110">A path gradient changes color as you move about the interior and boundary of a path.</span></span> <span data-ttu-id="4801e-111">你可以自定义路径渐变以获得各种效果。</span><span class="sxs-lookup"><span data-stu-id="4801e-111">You can customize path gradients to achieve a wide variety of effects.</span></span>  
  
 <span data-ttu-id="4801e-112">下图显示使用线性渐变画笔填充的矩形和椭圆填入路径渐变画笔。</span><span class="sxs-lookup"><span data-stu-id="4801e-112">The following illustration shows a rectangle filled with a linear gradient brush and an ellipse filled with a path gradient brush.</span></span>  
  
 <span data-ttu-id="4801e-113">![渐变](../../../../docs/framework/winforms/advanced/media/gradient2.png "gradient2")</span><span class="sxs-lookup"><span data-stu-id="4801e-113">![Gradient](../../../../docs/framework/winforms/advanced/media/gradient2.png "gradient2")</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="4801e-114">本节内容</span><span class="sxs-lookup"><span data-stu-id="4801e-114">In This Section</span></span>  
 [<span data-ttu-id="4801e-115">如何：创建线性渐变</span><span class="sxs-lookup"><span data-stu-id="4801e-115">How to: Create a Linear Gradient</span></span>](../../../../docs/framework/winforms/advanced/how-to-create-a-linear-gradient.md)  
 <span data-ttu-id="4801e-116">演示如何创建线性渐变 using<xref:System.Drawing.Drawing2D.LinearGradientBrush>类。</span><span class="sxs-lookup"><span data-stu-id="4801e-116">Shows how to create a linear gradient using the <xref:System.Drawing.Drawing2D.LinearGradientBrush> class.</span></span>  
  
 [<span data-ttu-id="4801e-117">如何：创建路径渐变</span><span class="sxs-lookup"><span data-stu-id="4801e-117">How to: Create a Path Gradient</span></span>](../../../../docs/framework/winforms/advanced/how-to-create-a-path-gradient.md)  
 <span data-ttu-id="4801e-118">描述如何创建路径渐变 using<xref:System.Drawing.Drawing2D.PathGradientBrush>类。</span><span class="sxs-lookup"><span data-stu-id="4801e-118">Describes how to create a path gradient using the <xref:System.Drawing.Drawing2D.PathGradientBrush> class.</span></span>  
  
 [<span data-ttu-id="4801e-119">如何：对渐变应用 gamma 矫正</span><span class="sxs-lookup"><span data-stu-id="4801e-119">How to: Apply Gamma Correction to a Gradient</span></span>](../../../../docs/framework/winforms/advanced/how-to-apply-gamma-correction-to-a-gradient.md)  
 <span data-ttu-id="4801e-120">说明如何使用渐变画笔的灰度校正。</span><span class="sxs-lookup"><span data-stu-id="4801e-120">Explains how to use gamma correction with a gradient brush.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="4801e-121">参考</span><span class="sxs-lookup"><span data-stu-id="4801e-121">Reference</span></span>  
 <xref:System.Drawing.Drawing2D.LinearGradientBrush?displayProperty=nameWithType>  
 <span data-ttu-id="4801e-122">包含此类的说明，并提供指向其所有成员。</span><span class="sxs-lookup"><span data-stu-id="4801e-122">Contains a description of this class and has links to all of its members.</span></span>  
  
 <xref:System.Drawing.Drawing2D.PathGradientBrush?displayProperty=nameWithType>  
 <span data-ttu-id="4801e-123">包含此类的说明，并提供指向其所有成员。</span><span class="sxs-lookup"><span data-stu-id="4801e-123">Contains a description of this class and has links to all of its members.</span></span>
