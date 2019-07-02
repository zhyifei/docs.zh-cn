---
title: GDI+ 中的画笔和实心形状
ms.date: 03/30/2017
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
ms.openlocfilehash: ad3a4af2474ace61bbf35ea1357a2a6037af039a
ms.sourcegitcommit: b1cfd260928d464d91e20121f9bdba7611c94d71
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/02/2019
ms.locfileid: "67506236"
---
# <a name="brushes-and-filled-shapes-in-gdi"></a><span data-ttu-id="68ba1-102">GDI+ 中的画笔和实心形状</span><span class="sxs-lookup"><span data-stu-id="68ba1-102">Brushes and Filled Shapes in GDI+</span></span>
<span data-ttu-id="68ba1-103">闭合的形状，如矩形或椭圆，由边框和内部组成。</span><span class="sxs-lookup"><span data-stu-id="68ba1-103">A closed shape, such as a rectangle or an ellipse, consists of an outline and an interior.</span></span> <span data-ttu-id="68ba1-104">使用笔绘制出轮廓，并使用画笔填充其内部。</span><span class="sxs-lookup"><span data-stu-id="68ba1-104">The outline is drawn with a pen and the interior is filled with a brush.</span></span> <span data-ttu-id="68ba1-105">GDI + 提供了几个画笔类填充绘制闭合形状的内部： <xref:System.Drawing.SolidBrush>， <xref:System.Drawing.Drawing2D.HatchBrush>， <xref:System.Drawing.TextureBrush>， <xref:System.Drawing.Drawing2D.LinearGradientBrush>，和<xref:System.Drawing.Drawing2D.PathGradientBrush>。</span><span class="sxs-lookup"><span data-stu-id="68ba1-105">GDI+ provides several brush classes for filling the interiors of closed shapes: <xref:System.Drawing.SolidBrush>, <xref:System.Drawing.Drawing2D.HatchBrush>, <xref:System.Drawing.TextureBrush>, <xref:System.Drawing.Drawing2D.LinearGradientBrush>, and <xref:System.Drawing.Drawing2D.PathGradientBrush>.</span></span> <span data-ttu-id="68ba1-106">所有这些类继承自<xref:System.Drawing.Brush>类。</span><span class="sxs-lookup"><span data-stu-id="68ba1-106">All of these classes inherit from the <xref:System.Drawing.Brush> class.</span></span> <span data-ttu-id="68ba1-107">下图显示了以实线画笔填充矩形和椭圆用阴影画笔填充。</span><span class="sxs-lookup"><span data-stu-id="68ba1-107">The following illustration shows a rectangle filled with a solid brush and an ellipse filled with a hatch brush.</span></span>  
  
 <span data-ttu-id="68ba1-108">![填充形状](./media/aboutgdip02-art17.gif "Aboutgdip02_art17")</span><span class="sxs-lookup"><span data-stu-id="68ba1-108">![Filled Shapes](./media/aboutgdip02-art17.gif "Aboutgdip02_art17")</span></span>  
  
## <a name="solid-brushes"></a><span data-ttu-id="68ba1-109">纯色画笔</span><span class="sxs-lookup"><span data-stu-id="68ba1-109">Solid Brushes</span></span>  
 <span data-ttu-id="68ba1-110">若要填充闭合的形状，你需要的实例<xref:System.Drawing.Graphics>类和一个<xref:System.Drawing.Brush>。</span><span class="sxs-lookup"><span data-stu-id="68ba1-110">To fill a closed shape, you need an instance of the <xref:System.Drawing.Graphics> class and a <xref:System.Drawing.Brush>.</span></span> <span data-ttu-id="68ba1-111">实例<xref:System.Drawing.Graphics>类提供了方法，如<xref:System.Drawing.Graphics.FillRectangle%2A>并<xref:System.Drawing.Graphics.FillEllipse%2A>，和<xref:System.Drawing.Brush>存储填充，如颜色和模式的特性。</span><span class="sxs-lookup"><span data-stu-id="68ba1-111">The instance of the <xref:System.Drawing.Graphics> class provides methods, such as <xref:System.Drawing.Graphics.FillRectangle%2A> and <xref:System.Drawing.Graphics.FillEllipse%2A>, and the <xref:System.Drawing.Brush> stores attributes of the fill, such as color and pattern.</span></span> <span data-ttu-id="68ba1-112"><xref:System.Drawing.Brush>作为一个参数传递给填充方法。</span><span class="sxs-lookup"><span data-stu-id="68ba1-112">The <xref:System.Drawing.Brush> is passed as one of the arguments to the fill method.</span></span> <span data-ttu-id="68ba1-113">下面的代码示例演示如何用红色纯色填充椭圆。</span><span class="sxs-lookup"><span data-stu-id="68ba1-113">The following code example shows how to fill an ellipse with a solid red color.</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#121](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#121)]
 [!code-vb[LinesCurvesAndShapes#121](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#121)]  
  
> [!NOTE]
>  <span data-ttu-id="68ba1-114">在上述示例中的类型是画笔<xref:System.Drawing.SolidBrush>，后者又继承<xref:System.Drawing.Brush>。</span><span class="sxs-lookup"><span data-stu-id="68ba1-114">In the preceding example, the brush is of type <xref:System.Drawing.SolidBrush>, which inherits from <xref:System.Drawing.Brush>.</span></span>  
  
## <a name="hatch-brushes"></a><span data-ttu-id="68ba1-115">阴影画笔</span><span class="sxs-lookup"><span data-stu-id="68ba1-115">Hatch Brushes</span></span>  
 <span data-ttu-id="68ba1-116">当使用阴影画笔填充形状时，您指定前景色、 背景色和阴影样式。</span><span class="sxs-lookup"><span data-stu-id="68ba1-116">When you fill a shape with a hatch brush, you specify a foreground color, a background color, and a hatch style.</span></span> <span data-ttu-id="68ba1-117">前景颜色为阴影的颜色。</span><span class="sxs-lookup"><span data-stu-id="68ba1-117">The foreground color is the color of the hatching.</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#122](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#122)]
 [!code-vb[LinesCurvesAndShapes#122](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#122)]  
  
 <span data-ttu-id="68ba1-118">GDI + 提供了超过 50 个阴影样式;以下插图所示的三个样式都<xref:System.Drawing.Drawing2D.HatchStyle.Horizontal>， <xref:System.Drawing.Drawing2D.HatchStyle.ForwardDiagonal>，和<xref:System.Drawing.Drawing2D.HatchStyle.Cross>。</span><span class="sxs-lookup"><span data-stu-id="68ba1-118">GDI+ provides more than 50 hatch styles; the three styles shown in the following illustration are <xref:System.Drawing.Drawing2D.HatchStyle.Horizontal>, <xref:System.Drawing.Drawing2D.HatchStyle.ForwardDiagonal>, and <xref:System.Drawing.Drawing2D.HatchStyle.Cross>.</span></span>  
  
 <span data-ttu-id="68ba1-119">![填充形状](./media/aboutgdip02-art18.gif "Aboutgdip02_art18")</span><span class="sxs-lookup"><span data-stu-id="68ba1-119">![Filled Shapes](./media/aboutgdip02-art18.gif "Aboutgdip02_art18")</span></span>  
  
## <a name="texture-brushes"></a><span data-ttu-id="68ba1-120">纹理画笔</span><span class="sxs-lookup"><span data-stu-id="68ba1-120">Texture Brushes</span></span>  
 <span data-ttu-id="68ba1-121">使用纹理画笔，可以使用存储在位图中的模式来填充形状。</span><span class="sxs-lookup"><span data-stu-id="68ba1-121">With a texture brush, you can fill a shape with a pattern stored in a bitmap.</span></span> <span data-ttu-id="68ba1-122">例如，假设以下图片存储在名为的磁盘文件`MyTexture.bmp`。</span><span class="sxs-lookup"><span data-stu-id="68ba1-122">For example, suppose the following picture is stored in a disk file named `MyTexture.bmp`.</span></span>  
  
 <span data-ttu-id="68ba1-123">![填充形状](./media/aboutgdip02-art19.gif "Aboutgdip02_Art19")</span><span class="sxs-lookup"><span data-stu-id="68ba1-123">![Filled Shape](./media/aboutgdip02-art19.gif "Aboutgdip02_Art19")</span></span>  
  
 <span data-ttu-id="68ba1-124">下面的代码示例演示如何通过重复图片存储为填充椭圆`MyTexture.bmp`。</span><span class="sxs-lookup"><span data-stu-id="68ba1-124">The following code example shows how to fill an ellipse by repeating the picture stored in `MyTexture.bmp`.</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#123](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#123)]
 [!code-vb[LinesCurvesAndShapes#123](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#123)]  
  
 <span data-ttu-id="68ba1-125">下图显示了实心的椭圆。</span><span class="sxs-lookup"><span data-stu-id="68ba1-125">The following illustration shows the filled ellipse.</span></span>  
  
 <span data-ttu-id="68ba1-126">![填充形状](./media/aboutgdip02-art20.gif "AboutGdip02_Art20")</span><span class="sxs-lookup"><span data-stu-id="68ba1-126">![Filled Shape](./media/aboutgdip02-art20.gif "AboutGdip02_Art20")</span></span>  
  
## <a name="gradient-brushes"></a><span data-ttu-id="68ba1-127">渐变画笔</span><span class="sxs-lookup"><span data-stu-id="68ba1-127">Gradient Brushes</span></span>  
 <span data-ttu-id="68ba1-128">GDI + 提供了两种类型的渐变画笔： 线性和路径。</span><span class="sxs-lookup"><span data-stu-id="68ba1-128">GDI+ provides two kinds of gradient brushes: linear and path.</span></span> <span data-ttu-id="68ba1-129">线性渐变画笔用于填充形状更改逐渐水平、 垂直移过图形或沿对角线方向的颜色。</span><span class="sxs-lookup"><span data-stu-id="68ba1-129">You can use a linear gradient brush to fill a shape with color that changes gradually as you move across the shape horizontally, vertically, or diagonally.</span></span> <span data-ttu-id="68ba1-130">下面的代码示例演示如何用会从蓝色变为绿色，当您从椭圆的左边缘移动到右边缘的水平渐变画笔填充椭圆。</span><span class="sxs-lookup"><span data-stu-id="68ba1-130">The following code example shows how to fill an ellipse with a horizontal gradient brush that changes from blue to green as you move from the left edge of the ellipse to the right edge.</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#124](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#124)]
 [!code-vb[LinesCurvesAndShapes#124](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#124)]  
  
 <span data-ttu-id="68ba1-131">下图显示了实心的椭圆。</span><span class="sxs-lookup"><span data-stu-id="68ba1-131">The following illustration shows the filled ellipse.</span></span>  
  
 <span data-ttu-id="68ba1-132">![填充形状](./media/aboutgdip02-art21.gif "AboutGdip02_Art21")</span><span class="sxs-lookup"><span data-stu-id="68ba1-132">![Filled Shape](./media/aboutgdip02-art21.gif "AboutGdip02_Art21")</span></span>  
  
 <span data-ttu-id="68ba1-133">若要更改颜色，当您从边缘形状的中心，可以配置路径渐变画笔。</span><span class="sxs-lookup"><span data-stu-id="68ba1-133">A path gradient brush can be configured to change color as you move from the center of a shape toward the edge.</span></span>  
  
 <span data-ttu-id="68ba1-134">![填充形状](./media/aboutgdip02-art22.gif "AboutGdip02_Art22")</span><span class="sxs-lookup"><span data-stu-id="68ba1-134">![Filled Shape](./media/aboutgdip02-art22.gif "AboutGdip02_Art22")</span></span>  
  
 <span data-ttu-id="68ba1-135">路径渐变画笔时非常灵活。</span><span class="sxs-lookup"><span data-stu-id="68ba1-135">Path gradient brushes are quite flexible.</span></span> <span data-ttu-id="68ba1-136">渐变画笔用于填充中的以下图更改逐渐从中心的红色向每个顶点在三个不同的颜色的三角形。</span><span class="sxs-lookup"><span data-stu-id="68ba1-136">The gradient brush used to fill the triangle in the following illustration changes gradually from red at the center to each of three different colors at the vertices.</span></span>  
  
 <span data-ttu-id="68ba1-137">![填充形状](./media/aboutgdip02-art23.gif "AboutGdip02_Art23")</span><span class="sxs-lookup"><span data-stu-id="68ba1-137">![Filled Shape](./media/aboutgdip02-art23.gif "AboutGdip02_Art23")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="68ba1-138">请参阅</span><span class="sxs-lookup"><span data-stu-id="68ba1-138">See also</span></span>

- <xref:System.Drawing.SolidBrush?displayProperty=nameWithType>
- <xref:System.Drawing.Drawing2D.HatchBrush?displayProperty=nameWithType>
- <xref:System.Drawing.TextureBrush?displayProperty=nameWithType>
- <xref:System.Drawing.Drawing2D.LinearGradientBrush?displayProperty=nameWithType>
- [<span data-ttu-id="68ba1-139">直线、曲线和形状</span><span class="sxs-lookup"><span data-stu-id="68ba1-139">Lines, Curves, and Shapes</span></span>](lines-curves-and-shapes.md)
- [<span data-ttu-id="68ba1-140">如何：Windows 窗体上绘制实心的矩形</span><span class="sxs-lookup"><span data-stu-id="68ba1-140">How to: Draw a Filled Rectangle on a Windows Form</span></span>](how-to-draw-a-filled-rectangle-on-a-windows-form.md)
- [<span data-ttu-id="68ba1-141">如何：Windows 窗体上绘制实心的椭圆</span><span class="sxs-lookup"><span data-stu-id="68ba1-141">How to: Draw a Filled Ellipse on a Windows Form</span></span>](how-to-draw-a-filled-ellipse-on-a-windows-form.md)
