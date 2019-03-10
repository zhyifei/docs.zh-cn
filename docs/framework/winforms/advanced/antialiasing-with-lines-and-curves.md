---
title: 用直线和曲线抗锯齿
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- antialiasing
- antialiasing [Windows Forms], smoothing modes
- GDI+, antialiasing
ms.assetid: 810da1a4-c136-4abf-88df-68e49efdd8d4
ms.openlocfilehash: 6ea49c591b43d3f70bfd39058fd5ee256c537ec2
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/09/2019
ms.locfileid: "57725007"
---
# <a name="antialiasing-with-lines-and-curves"></a><span data-ttu-id="73a76-102">用直线和曲线抗锯齿</span><span class="sxs-lookup"><span data-stu-id="73a76-102">Antialiasing with Lines and Curves</span></span>
<span data-ttu-id="73a76-103">当你使用[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]若要绘制一条线，提供的起始点和终点的行，但不是需要在行中提供有关单个像素的任何信息。</span><span class="sxs-lookup"><span data-stu-id="73a76-103">When you use [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] to draw a line, you provide the starting point and ending point of the line, but you do not have to provide any information about the individual pixels on the line.</span></span> [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] <span data-ttu-id="73a76-104">显示驱动程序软件，以确定哪些像素将打开特定显示设备上显示行结合工作。</span><span class="sxs-lookup"><span data-stu-id="73a76-104">works in conjunction with the display driver software to determine which pixels will be turned on to show the line on a particular display device.</span></span>  
  
## <a name="aliasing"></a><span data-ttu-id="73a76-105">别名</span><span class="sxs-lookup"><span data-stu-id="73a76-105">Aliasing</span></span>  
 <span data-ttu-id="73a76-106">请考虑从点 （4，2） 转到 （16，10） 的点的垂直红线。</span><span class="sxs-lookup"><span data-stu-id="73a76-106">Consider the straight red line that goes from the point (4, 2) to the point (16, 10).</span></span> <span data-ttu-id="73a76-107">假定在左上角的坐标系统的原点和度量值的单位是像素。</span><span class="sxs-lookup"><span data-stu-id="73a76-107">Assume the coordinate system has its origin in the upper-left corner and that the unit of measure is the pixel.</span></span> <span data-ttu-id="73a76-108">另外，假设 x 轴向下指到右边，y 轴点。</span><span class="sxs-lookup"><span data-stu-id="73a76-108">Also assume that the x-axis points to the right and the y-axis points down.</span></span> <span data-ttu-id="73a76-109">下图显示彩色背景上绘制的红色线条的放大的视图。</span><span class="sxs-lookup"><span data-stu-id="73a76-109">The following illustration shows an enlarged view of the red line drawn on a multicolored background.</span></span>  
  
 <span data-ttu-id="73a76-110">![行、 没有抗锯齿](./media/aboutgdip02-art33.gif "AboutGdip02_Art33")</span><span class="sxs-lookup"><span data-stu-id="73a76-110">![Line, no antialiasing](./media/aboutgdip02-art33.gif "AboutGdip02_Art33")</span></span>  
  
 <span data-ttu-id="73a76-111">用于呈现行红色像素都是不透明的。</span><span class="sxs-lookup"><span data-stu-id="73a76-111">The red pixels used to render the line are opaque.</span></span> <span data-ttu-id="73a76-112">在行中有任何部分透明的像素为单位。</span><span class="sxs-lookup"><span data-stu-id="73a76-112">There are no partially transparent pixels in the line.</span></span> <span data-ttu-id="73a76-113">这种类型的一行的呈现提供行锯齿状的外观，并在行看起来有点像楼梯。</span><span class="sxs-lookup"><span data-stu-id="73a76-113">This type of line rendering gives the line a jagged appearance, and the line looks somewhat like a staircase.</span></span> <span data-ttu-id="73a76-114">表示一个行，其中楼梯的这一技术称为别名;楼梯是理论的线条的别名。</span><span class="sxs-lookup"><span data-stu-id="73a76-114">This technique of representing a line with a staircase is called aliasing; the staircase is an alias for the theoretical line.</span></span>  
  
## <a name="antialiasing"></a><span data-ttu-id="73a76-115">抗锯齿</span><span class="sxs-lookup"><span data-stu-id="73a76-115">Antialiasing</span></span>  
 <span data-ttu-id="73a76-116">用于呈现行更复杂的方法是使用部分透明像素和不透明的像素为单位。</span><span class="sxs-lookup"><span data-stu-id="73a76-116">A more sophisticated technique for rendering a line involves using partially transparent pixels along with opaque pixels.</span></span> <span data-ttu-id="73a76-117">像素为单位设置为纯红色，或到某种形式的红色和背景色组合，具体取决于如何关闭到行。</span><span class="sxs-lookup"><span data-stu-id="73a76-117">Pixels are set to pure red, or to some blend of red and the background color, depending on how close they are to the line.</span></span> <span data-ttu-id="73a76-118">这种类型的呈现称为抗锯齿功能，导致人眼感知作为更平滑的行。</span><span class="sxs-lookup"><span data-stu-id="73a76-118">This type of rendering is called antialiasing and results in a line that the human eye perceives as more smooth.</span></span> <span data-ttu-id="73a76-119">下图显示了如何将特定的像素混合和背景来生成抗锯齿的直线。</span><span class="sxs-lookup"><span data-stu-id="73a76-119">The following illustration shows how certain pixels are blended with the background to produce an antialiased line.</span></span>  
  
 <span data-ttu-id="73a76-120">![消除直线的锯齿](./media/aboutgdip02-art34.gif "AboutGdip02_Art34")</span><span class="sxs-lookup"><span data-stu-id="73a76-120">![Antialiasing a Line](./media/aboutgdip02-art34.gif "AboutGdip02_Art34")</span></span>  
  
 <span data-ttu-id="73a76-121">抗锯齿功能，也称为平滑处理，也可以应用于曲线。</span><span class="sxs-lookup"><span data-stu-id="73a76-121">Antialiasing, also called smoothing, can also be applied to curves.</span></span> <span data-ttu-id="73a76-122">下图显示了平滑椭圆的放大的视图。</span><span class="sxs-lookup"><span data-stu-id="73a76-122">The following illustration shows an enlarged view of a smoothed ellipse.</span></span>  
  
 <span data-ttu-id="73a76-123">![曲线的锯齿](./media/aboutgdip02-art35.gif "AboutGdip02_Art35")</span><span class="sxs-lookup"><span data-stu-id="73a76-123">![Antialiasing Curves](./media/aboutgdip02-art35.gif "AboutGdip02_Art35")</span></span>  
  
 <span data-ttu-id="73a76-124">下图显示的实际大小，一次没有抗锯齿功能，一次使用抗锯齿的同一个椭圆。</span><span class="sxs-lookup"><span data-stu-id="73a76-124">The following illustration shows the same ellipse in its actual size, once without antialiasing and once with antialiasing.</span></span>  
  
 <span data-ttu-id="73a76-125">![抗锯齿示例](./media/aboutgdip02-art36.gif "AboutGdip02_Art36")</span><span class="sxs-lookup"><span data-stu-id="73a76-125">![Antialiasing example](./media/aboutgdip02-art36.gif "AboutGdip02_Art36")</span></span>  
  
 <span data-ttu-id="73a76-126">若要绘制的直线和曲线使用抗锯齿效果，创建的实例<xref:System.Drawing.Graphics>类，然后设置其<xref:System.Drawing.Graphics.SmoothingMode%2A>属性设置为<xref:System.Drawing.Drawing2D.SmoothingMode.AntiAlias>或<xref:System.Drawing.Drawing2D.SmoothingMode.HighQuality>。</span><span class="sxs-lookup"><span data-stu-id="73a76-126">To draw lines and curves that use antialiasing, create an instance of the <xref:System.Drawing.Graphics> class and set its <xref:System.Drawing.Graphics.SmoothingMode%2A> property to <xref:System.Drawing.Drawing2D.SmoothingMode.AntiAlias> or <xref:System.Drawing.Drawing2D.SmoothingMode.HighQuality>.</span></span> <span data-ttu-id="73a76-127">然后调用绘制方法之一的同一<xref:System.Drawing.Graphics>类。</span><span class="sxs-lookup"><span data-stu-id="73a76-127">Then call one of the drawing methods of that same <xref:System.Drawing.Graphics> class.</span></span>  
  
 [!code-csharp[LinesCurvesAndShapes#81](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#81)]
 [!code-vb[LinesCurvesAndShapes#81](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#81)]  
  
## <a name="see-also"></a><span data-ttu-id="73a76-128">请参阅</span><span class="sxs-lookup"><span data-stu-id="73a76-128">See also</span></span>
- <xref:System.Drawing.Drawing2D.SmoothingMode?displayProperty=nameWithType>
- [<span data-ttu-id="73a76-129">直线、曲线和形状</span><span class="sxs-lookup"><span data-stu-id="73a76-129">Lines, Curves, and Shapes</span></span>](lines-curves-and-shapes.md)
- [<span data-ttu-id="73a76-130">如何：对文本使用抗锯齿效果</span><span class="sxs-lookup"><span data-stu-id="73a76-130">How to: Use Antialiasing with Text</span></span>](how-to-use-antialiasing-with-text.md)
