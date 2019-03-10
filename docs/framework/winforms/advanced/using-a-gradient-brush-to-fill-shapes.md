---
title: 使用渐变画笔填充形状
ms.date: 03/30/2017
helpviewer_keywords:
- brushes [Windows Forms], gradient brushes
- gradient brushes
- examples [Windows Forms], gradient brushes
ms.assetid: 2c6037b9-05bd-44c0-a22a-19584b722524
ms.openlocfilehash: 5771aaabd283d71f5fa6934f86a1c24a57f38dca
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/09/2019
ms.locfileid: "57704383"
---
# <a name="using-a-gradient-brush-to-fill-shapes"></a><span data-ttu-id="9f1f0-102">使用渐变画笔填充形状</span><span class="sxs-lookup"><span data-stu-id="9f1f0-102">Using a Gradient Brush to Fill Shapes</span></span>
<span data-ttu-id="9f1f0-103">可以使用渐变画笔填充形状的渐变的颜色。</span><span class="sxs-lookup"><span data-stu-id="9f1f0-103">You can use a gradient brush to fill a shape with a gradually changing color.</span></span> <span data-ttu-id="9f1f0-104">例如，可以使用水平渐变来逐渐更改，当您从该形状的左边缘移动到右边缘的颜色填充形状。</span><span class="sxs-lookup"><span data-stu-id="9f1f0-104">For example, you can use a horizontal gradient to fill a shape with color that changes gradually as you move from the left edge of the shape to the right edge.</span></span> <span data-ttu-id="9f1f0-105">设想这样一个矩形是黑色的左边缘 （由红色、 绿色和蓝色分量 0，0，0） 和右边缘，它是红色 （255，0，0 表示）。</span><span class="sxs-lookup"><span data-stu-id="9f1f0-105">Imagine a rectangle with a left edge that is black (represented by red, green, and blue components 0, 0, 0) and a right edge that is red (represented by 255, 0, 0).</span></span> <span data-ttu-id="9f1f0-106">如果矩形为 256 像素宽，给定的像素的红色组件将比其左侧的像素的红色组件。</span><span class="sxs-lookup"><span data-stu-id="9f1f0-106">If the rectangle is 256 pixels wide, the red component of a given pixel will be one greater than the red component of the pixel to its left.</span></span> <span data-ttu-id="9f1f0-107">在行中的最左侧像素的颜色分量为 （0，0，0），第二个像素 （1，0，0），第三个像素都有 （2，0，0），依次类推，直到你转到最右边的像素颜色组件 （255，0，0）。</span><span class="sxs-lookup"><span data-stu-id="9f1f0-107">The leftmost pixel in a row has color components (0, 0, 0), the second pixel has (1, 0, 0), the third pixel has (2, 0, 0), and so on, until you get to the rightmost pixel, which has color components (255, 0, 0).</span></span> <span data-ttu-id="9f1f0-108">这些内插的颜色值组成的颜色渐变。</span><span class="sxs-lookup"><span data-stu-id="9f1f0-108">These interpolated color values make up the color gradient.</span></span>  
  
 <span data-ttu-id="9f1f0-109">线性渐变更改颜色，当您移动水平、 垂直，或并行到指定的斜线。</span><span class="sxs-lookup"><span data-stu-id="9f1f0-109">A linear gradient changes color as you move horizontally, vertically, or parallel to a specified slanted line.</span></span> <span data-ttu-id="9f1f0-110">路径渐变的内部和路径的边界中移动时更改颜色。</span><span class="sxs-lookup"><span data-stu-id="9f1f0-110">A path gradient changes color as you move about the interior and boundary of a path.</span></span> <span data-ttu-id="9f1f0-111">您可以自定义路径渐变来实现各种效果。</span><span class="sxs-lookup"><span data-stu-id="9f1f0-111">You can customize path gradients to achieve a wide variety of effects.</span></span>  
  
 <span data-ttu-id="9f1f0-112">下图显示了使用线性渐变画笔填充矩形和椭圆使用路径渐变画笔填充。</span><span class="sxs-lookup"><span data-stu-id="9f1f0-112">The following illustration shows a rectangle filled with a linear gradient brush and an ellipse filled with a path gradient brush.</span></span>  
  
 <span data-ttu-id="9f1f0-113">![渐变](./media/gradient2.png "gradient2")</span><span class="sxs-lookup"><span data-stu-id="9f1f0-113">![Gradient](./media/gradient2.png "gradient2")</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="9f1f0-114">本节内容</span><span class="sxs-lookup"><span data-stu-id="9f1f0-114">In This Section</span></span>  
 [<span data-ttu-id="9f1f0-115">如何：创建线性渐变</span><span class="sxs-lookup"><span data-stu-id="9f1f0-115">How to: Create a Linear Gradient</span></span>](how-to-create-a-linear-gradient.md)  
 <span data-ttu-id="9f1f0-116">演示如何创建线性渐变 using<xref:System.Drawing.Drawing2D.LinearGradientBrush>类。</span><span class="sxs-lookup"><span data-stu-id="9f1f0-116">Shows how to create a linear gradient using the <xref:System.Drawing.Drawing2D.LinearGradientBrush> class.</span></span>  
  
 [<span data-ttu-id="9f1f0-117">如何：创建路径渐变</span><span class="sxs-lookup"><span data-stu-id="9f1f0-117">How to: Create a Path Gradient</span></span>](how-to-create-a-path-gradient.md)  
 <span data-ttu-id="9f1f0-118">介绍如何创建路径渐变 using<xref:System.Drawing.Drawing2D.PathGradientBrush>类。</span><span class="sxs-lookup"><span data-stu-id="9f1f0-118">Describes how to create a path gradient using the <xref:System.Drawing.Drawing2D.PathGradientBrush> class.</span></span>  
  
 [<span data-ttu-id="9f1f0-119">如何：对渐变应用灰度校正</span><span class="sxs-lookup"><span data-stu-id="9f1f0-119">How to: Apply Gamma Correction to a Gradient</span></span>](how-to-apply-gamma-correction-to-a-gradient.md)  
 <span data-ttu-id="9f1f0-120">介绍如何使用渐变画笔的灰度校正。</span><span class="sxs-lookup"><span data-stu-id="9f1f0-120">Explains how to use gamma correction with a gradient brush.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="9f1f0-121">参考</span><span class="sxs-lookup"><span data-stu-id="9f1f0-121">Reference</span></span>  
 <xref:System.Drawing.Drawing2D.LinearGradientBrush?displayProperty=nameWithType>  
 <span data-ttu-id="9f1f0-122">包含此类的说明，并提供指向其所有成员。</span><span class="sxs-lookup"><span data-stu-id="9f1f0-122">Contains a description of this class and has links to all of its members.</span></span>  
  
 <xref:System.Drawing.Drawing2D.PathGradientBrush?displayProperty=nameWithType>  
 <span data-ttu-id="9f1f0-123">包含此类的说明，并提供指向其所有成员。</span><span class="sxs-lookup"><span data-stu-id="9f1f0-123">Contains a description of this class and has links to all of its members.</span></span>
