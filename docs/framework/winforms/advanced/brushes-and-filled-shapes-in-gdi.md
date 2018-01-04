---
title: "GDI+ 中的画笔和实心形状"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- brushes [Windows Forms], GDI+
- filled shapes [Windows Forms], GDI+
- shapes [Windows Forms], GDI+
- GDI+, brushes
- GDI+, filled shapes
- gradient brushes
- brushes [Windows Forms], gradient
ms.assetid: e863e2a7-0294-4130-99b6-f1ea3201e7cd
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 89f0a7c86a83222030d9b50e20228f32e85ce730
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="brushes-and-filled-shapes-in-gdi"></a><span data-ttu-id="ea844-102">GDI+ 中的画笔和实心形状</span><span class="sxs-lookup"><span data-stu-id="ea844-102">Brushes and Filled Shapes in GDI+</span></span>
<span data-ttu-id="ea844-103">闭合的形状，如矩形或椭圆由概述和内部组成。</span><span class="sxs-lookup"><span data-stu-id="ea844-103">A closed shape, such as a rectangle or an ellipse, consists of an outline and an interior.</span></span> <span data-ttu-id="ea844-104">使用钢笔绘制轮廓和使用画笔填充其内部。</span><span class="sxs-lookup"><span data-stu-id="ea844-104">The outline is drawn with a pen and the interior is filled with a brush.</span></span> [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]<span data-ttu-id="ea844-105">提供了几个画笔类填充的闭合形状的内部： <xref:System.Drawing.SolidBrush>， <xref:System.Drawing.Drawing2D.HatchBrush>， <xref:System.Drawing.TextureBrush>， <xref:System.Drawing.Drawing2D.LinearGradientBrush>，和<xref:System.Drawing.Drawing2D.PathGradientBrush>。</span><span class="sxs-lookup"><span data-stu-id="ea844-105"> provides several brush classes for filling the interiors of closed shapes: <xref:System.Drawing.SolidBrush>, <xref:System.Drawing.Drawing2D.HatchBrush>, <xref:System.Drawing.TextureBrush>, <xref:System.Drawing.Drawing2D.LinearGradientBrush>, and <xref:System.Drawing.Drawing2D.PathGradientBrush>.</span></span> <span data-ttu-id="ea844-106">这些类都继承自<xref:System.Drawing.Brush>类。</span><span class="sxs-lookup"><span data-stu-id="ea844-106">All of these classes inherit from the <xref:System.Drawing.Brush> class.</span></span> <span data-ttu-id="ea844-107">下图显示用纯色画笔填充的矩形和椭圆用阴影画笔填充。</span><span class="sxs-lookup"><span data-stu-id="ea844-107">The following illustration shows a rectangle filled with a solid brush and an ellipse filled with a hatch brush.</span></span>  
  
 <span data-ttu-id="ea844-108">![填充形状](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art17.gif "Aboutgdip02_art17")</span><span class="sxs-lookup"><span data-stu-id="ea844-108">![Filled Shapes](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art17.gif "Aboutgdip02_art17")</span></span>  
  
## <a name="solid-brushes"></a><span data-ttu-id="ea844-109">实心画笔</span><span class="sxs-lookup"><span data-stu-id="ea844-109">Solid Brushes</span></span>  
 <span data-ttu-id="ea844-110">若要填充的闭合的形状，你需要的实例<xref:System.Drawing.Graphics>类和一个<xref:System.Drawing.Brush>。</span><span class="sxs-lookup"><span data-stu-id="ea844-110">To fill a closed shape, you need an instance of the <xref:System.Drawing.Graphics> class and a <xref:System.Drawing.Brush>.</span></span> <span data-ttu-id="ea844-111">实例<xref:System.Drawing.Graphics>类提供了方法，如<xref:System.Drawing.Graphics.FillRectangle%2A>和<xref:System.Drawing.Graphics.FillEllipse%2A>，和<xref:System.Drawing.Brush>存储填充，如颜色和模式的特性。</span><span class="sxs-lookup"><span data-stu-id="ea844-111">The instance of the <xref:System.Drawing.Graphics> class provides methods, such as <xref:System.Drawing.Graphics.FillRectangle%2A> and <xref:System.Drawing.Graphics.FillEllipse%2A>, and the <xref:System.Drawing.Brush> stores attributes of the fill, such as color and pattern.</span></span> <span data-ttu-id="ea844-112"><xref:System.Drawing.Brush>作为一个参数传递给填充方法。</span><span class="sxs-lookup"><span data-stu-id="ea844-112">The <xref:System.Drawing.Brush> is passed as one of the arguments to the fill method.</span></span> <span data-ttu-id="ea844-113">下面的代码示例演示如何用红色纯色填充椭圆。</span><span class="sxs-lookup"><span data-stu-id="ea844-113">The following code example shows how to fill an ellipse with a solid red color.</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#121](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#121)]
 [!code-vb[LinesCurvesAndShapes#121](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#121)]  
  
> [!NOTE]
>  <span data-ttu-id="ea844-114">在前面的示例中，画笔属于类型<xref:System.Drawing.SolidBrush>，它继承自<xref:System.Drawing.Brush>。</span><span class="sxs-lookup"><span data-stu-id="ea844-114">In the preceding example, the brush is of type <xref:System.Drawing.SolidBrush>, which inherits from <xref:System.Drawing.Brush>.</span></span>  
  
## <a name="hatch-brushes"></a><span data-ttu-id="ea844-115">阴影画笔</span><span class="sxs-lookup"><span data-stu-id="ea844-115">Hatch Brushes</span></span>  
 <span data-ttu-id="ea844-116">当使用阴影画笔填充形状时，指定前景颜色、 背景色和阴影样式。</span><span class="sxs-lookup"><span data-stu-id="ea844-116">When you fill a shape with a hatch brush, you specify a foreground color, a background color, and a hatch style.</span></span> <span data-ttu-id="ea844-117">前景色为阴影的颜色。</span><span class="sxs-lookup"><span data-stu-id="ea844-117">The foreground color is the color of the hatching.</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#122](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#122)]
 [!code-vb[LinesCurvesAndShapes#122](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#122)]  
  
 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]<span data-ttu-id="ea844-118">提供 50 多台的阴影样式;下图中所示的三个样式<xref:System.Drawing.Drawing2D.HatchStyle.Horizontal>， <xref:System.Drawing.Drawing2D.HatchStyle.ForwardDiagonal>，和<xref:System.Drawing.Drawing2D.HatchStyle.Cross>。</span><span class="sxs-lookup"><span data-stu-id="ea844-118"> provides more than 50 hatch styles; the three styles shown in the following illustration are <xref:System.Drawing.Drawing2D.HatchStyle.Horizontal>, <xref:System.Drawing.Drawing2D.HatchStyle.ForwardDiagonal>, and <xref:System.Drawing.Drawing2D.HatchStyle.Cross>.</span></span>  
  
 <span data-ttu-id="ea844-119">![填充形状](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art18.gif "Aboutgdip02_art18")</span><span class="sxs-lookup"><span data-stu-id="ea844-119">![Filled Shapes](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art18.gif "Aboutgdip02_art18")</span></span>  
  
## <a name="texture-brushes"></a><span data-ttu-id="ea844-120">纹理画笔</span><span class="sxs-lookup"><span data-stu-id="ea844-120">Texture Brushes</span></span>  
 <span data-ttu-id="ea844-121">使用纹理画笔，你可以用位图中存储的图案填充形状。</span><span class="sxs-lookup"><span data-stu-id="ea844-121">With a texture brush, you can fill a shape with a pattern stored in a bitmap.</span></span> <span data-ttu-id="ea844-122">例如，假设以下图片存储在名为磁盘文件`MyTexture.bmp`。</span><span class="sxs-lookup"><span data-stu-id="ea844-122">For example, suppose the following picture is stored in a disk file named `MyTexture.bmp`.</span></span>  
  
 <span data-ttu-id="ea844-123">![填充形状](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art19.gif "Aboutgdip02_Art19")</span><span class="sxs-lookup"><span data-stu-id="ea844-123">![Filled Shape](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art19.gif "Aboutgdip02_Art19")</span></span>  
  
 <span data-ttu-id="ea844-124">下面的代码示例演示如何通过重复图片存储在填充椭圆`MyTexture.bmp`。</span><span class="sxs-lookup"><span data-stu-id="ea844-124">The following code example shows how to fill an ellipse by repeating the picture stored in `MyTexture.bmp`.</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#123](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#123)]
 [!code-vb[LinesCurvesAndShapes#123](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#123)]  
  
 <span data-ttu-id="ea844-125">下图显示实心的椭圆。</span><span class="sxs-lookup"><span data-stu-id="ea844-125">The following illustration shows the filled ellipse.</span></span>  
  
 <span data-ttu-id="ea844-126">![填充形状](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art20.gif "AboutGdip02_Art20")</span><span class="sxs-lookup"><span data-stu-id="ea844-126">![Filled Shape](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art20.gif "AboutGdip02_Art20")</span></span>  
  
## <a name="gradient-brushes"></a><span data-ttu-id="ea844-127">渐变画刷</span><span class="sxs-lookup"><span data-stu-id="ea844-127">Gradient Brushes</span></span>  
 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]<span data-ttu-id="ea844-128">提供两种类型的渐变画刷： 线性和路径。</span><span class="sxs-lookup"><span data-stu-id="ea844-128"> provides two kinds of gradient brushes: linear and path.</span></span> <span data-ttu-id="ea844-129">可以使用线性渐变画笔填充形状更改逐渐水平、 垂直移过图形或对角线方向的颜色。</span><span class="sxs-lookup"><span data-stu-id="ea844-129">You can use a linear gradient brush to fill a shape with color that changes gradually as you move across the shape horizontally, vertically, or diagonally.</span></span> <span data-ttu-id="ea844-130">下面的代码示例演示如何用从蓝绿色到移动时改变距左边缘的椭圆的右边缘的水平渐变画笔填充椭圆。</span><span class="sxs-lookup"><span data-stu-id="ea844-130">The following code example shows how to fill an ellipse with a horizontal gradient brush that changes from blue to green as you move from the left edge of the ellipse to the right edge.</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#124](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#124)]
 [!code-vb[LinesCurvesAndShapes#124](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#124)]  
  
 <span data-ttu-id="ea844-131">下图显示实心的椭圆。</span><span class="sxs-lookup"><span data-stu-id="ea844-131">The following illustration shows the filled ellipse.</span></span>  
  
 <span data-ttu-id="ea844-132">![填充形状](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art21.gif "AboutGdip02_Art21")</span><span class="sxs-lookup"><span data-stu-id="ea844-132">![Filled Shape](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art21.gif "AboutGdip02_Art21")</span></span>  
  
 <span data-ttu-id="ea844-133">路径渐变画笔可以配置为当您从边缘形状的中心移动更改颜色。</span><span class="sxs-lookup"><span data-stu-id="ea844-133">A path gradient brush can be configured to change color as you move from the center of a shape toward the edge.</span></span>  
  
 <span data-ttu-id="ea844-134">![填充形状](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art22.gif "AboutGdip02_Art22")</span><span class="sxs-lookup"><span data-stu-id="ea844-134">![Filled Shape](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art22.gif "AboutGdip02_Art22")</span></span>  
  
 <span data-ttu-id="ea844-135">路径渐变画刷是非常灵活。</span><span class="sxs-lookup"><span data-stu-id="ea844-135">Path gradient brushes are quite flexible.</span></span> <span data-ttu-id="ea844-136">渐变画笔用于填充逐渐从在中心的红色对每个顶点处的三种不同颜色的以下图更改中的三角形。</span><span class="sxs-lookup"><span data-stu-id="ea844-136">The gradient brush used to fill the triangle in the following illustration changes gradually from red at the center to each of three different colors at the vertices.</span></span>  
  
 <span data-ttu-id="ea844-137">![填充形状](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art23.gif "AboutGdip02_Art23")</span><span class="sxs-lookup"><span data-stu-id="ea844-137">![Filled Shape](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art23.gif "AboutGdip02_Art23")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ea844-138">请参阅</span><span class="sxs-lookup"><span data-stu-id="ea844-138">See Also</span></span>  
 <xref:System.Drawing.SolidBrush?displayProperty=nameWithType>  
 <xref:System.Drawing.Drawing2D.HatchBrush?displayProperty=nameWithType>  
 <xref:System.Drawing.TextureBrush?displayProperty=nameWithType>  
 <xref:System.Drawing.Drawing2D.LinearGradientBrush?displayProperty=nameWithType>  
 [<span data-ttu-id="ea844-139">直线、曲线和形状</span><span class="sxs-lookup"><span data-stu-id="ea844-139">Lines, Curves, and Shapes</span></span>](../../../../docs/framework/winforms/advanced/lines-curves-and-shapes.md)  
 [<span data-ttu-id="ea844-140">如何：在 Windows 窗体上绘制填充矩形</span><span class="sxs-lookup"><span data-stu-id="ea844-140">How to: Draw a Filled Rectangle on a Windows Form</span></span>](../../../../docs/framework/winforms/advanced/how-to-draw-a-filled-rectangle-on-a-windows-form.md)  
 [<span data-ttu-id="ea844-141">如何：在 Windows 窗体上绘制填充椭圆形</span><span class="sxs-lookup"><span data-stu-id="ea844-141">How to: Draw a Filled Ellipse on a Windows Form</span></span>](../../../../docs/framework/winforms/advanced/how-to-draw-a-filled-ellipse-on-a-windows-form.md)
