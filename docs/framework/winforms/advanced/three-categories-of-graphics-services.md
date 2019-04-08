---
title: 图形服务的三个类别
ms.date: 03/30/2017
helpviewer_keywords:
- imaging
- graphics [Windows Forms], categories
- 2-D vector graphics
- vector graphics
- typography
ms.assetid: 068c0ef3-f6ee-4d58-a7b6-eb2531ead408
ms.openlocfilehash: ccbd5e236b47d1d870c9b77cfa2b3880619cf3cd
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59083590"
---
# <a name="three-categories-of-graphics-services"></a><span data-ttu-id="3d4be-102">图形服务的三个类别</span><span class="sxs-lookup"><span data-stu-id="3d4be-102">Three Categories of Graphics Services</span></span>
<span data-ttu-id="3d4be-103">在 Windows 窗体中的图形产品/服务划分为以下三个大类：</span><span class="sxs-lookup"><span data-stu-id="3d4be-103">The graphics offerings in Windows Forms fall into the following three broad categories:</span></span>  
  
-   <span data-ttu-id="3d4be-104">二维 (2-d) 矢量图形</span><span class="sxs-lookup"><span data-stu-id="3d4be-104">Two-dimensional (2-D) vector graphics</span></span>  
  
-   <span data-ttu-id="3d4be-105">图像处理</span><span class="sxs-lookup"><span data-stu-id="3d4be-105">Imaging</span></span>  
  
-   <span data-ttu-id="3d4be-106">版式</span><span class="sxs-lookup"><span data-stu-id="3d4be-106">Typography</span></span>  
  
## <a name="2-d-vector-graphics"></a><span data-ttu-id="3d4be-107">二维矢量图形</span><span class="sxs-lookup"><span data-stu-id="3d4be-107">2-D Vector Graphics</span></span>  
 <span data-ttu-id="3d4be-108">二维矢量图形是基元;如直线、 曲线和图形;由组点坐标系统上指定的。</span><span class="sxs-lookup"><span data-stu-id="3d4be-108">Two-dimensional vector graphics are primitives; such as lines, curves, and figures; that are specified by sets of points on a coordinate system.</span></span> <span data-ttu-id="3d4be-109">例如，由其两个终结点，指定一条直线和矩形指定点使其左上角和一对数字使其宽度和高度的位置。</span><span class="sxs-lookup"><span data-stu-id="3d4be-109">For example, a straight line is specified by its two endpoints, and a rectangle is specified by a point giving the location of its upper-left corner and a pair of numbers giving its width and height.</span></span> <span data-ttu-id="3d4be-110">指定简单路径是由直线连接的点数组。</span><span class="sxs-lookup"><span data-stu-id="3d4be-110">A simple path is specified by an array of points that are connected by straight lines.</span></span> <span data-ttu-id="3d4be-111">贝塞尔样条是指定由四个控制点的复杂的曲线。</span><span class="sxs-lookup"><span data-stu-id="3d4be-111">A Bézier spline is a sophisticated curve specified by four control points.</span></span>  
  
 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] <span data-ttu-id="3d4be-112">提供类和存储有关基元本身的信息的结构、 存储有关如何将绘制基元，信息的类和实际执行绘制的类。</span><span class="sxs-lookup"><span data-stu-id="3d4be-112">provides classes and structures that store information about the primitives themselves, classes that store information about how the primitives will be drawn, and classes that actually do the drawing.</span></span> <span data-ttu-id="3d4be-113">例如，<xref:System.Drawing.Rectangle>结构存储的位置和大小的矩形;<xref:System.Drawing.Pen>类存储线条颜色、 线条宽度和线条样式; 有关的信息和<xref:System.Drawing.Graphics>类具有绘制线条、 矩形、 路径的方法和其他数字。</span><span class="sxs-lookup"><span data-stu-id="3d4be-113">For example, the <xref:System.Drawing.Rectangle> structure stores the location and size of a rectangle; the <xref:System.Drawing.Pen> class stores information about line color, line width, and line style; and the <xref:System.Drawing.Graphics> class has methods for drawing lines, rectangles, paths, and other figures.</span></span> <span data-ttu-id="3d4be-114">有几种<xref:System.Drawing.Brush>存储有关如何信息的类封闭图形和路径中将填充颜色或图案。</span><span class="sxs-lookup"><span data-stu-id="3d4be-114">There are also several <xref:System.Drawing.Brush> classes that store information about how closed figures and paths will be filled with colors or patterns.</span></span>  
  
 <span data-ttu-id="3d4be-115">可将矢量图像，这是一系列图形命令，记录中图元文件。</span><span class="sxs-lookup"><span data-stu-id="3d4be-115">You can record a vector image, which is a sequence of graphics commands, in a metafile.</span></span> [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] <span data-ttu-id="3d4be-116">提供了<xref:System.Drawing.Imaging.Metafile>类用于记录、 显示和保存图元文件。</span><span class="sxs-lookup"><span data-stu-id="3d4be-116">provides the <xref:System.Drawing.Imaging.Metafile> class for recording, displaying, and saving metafiles.</span></span> <span data-ttu-id="3d4be-117">与<xref:System.Drawing.Imaging.MetafileHeader>和<xref:System.Drawing.Imaging.MetaHeader>类，可以检查存储在图元文件头中的数据。</span><span class="sxs-lookup"><span data-stu-id="3d4be-117">With the <xref:System.Drawing.Imaging.MetafileHeader> and <xref:System.Drawing.Imaging.MetaHeader> classes, you can inspect the data stored in a metafile header.</span></span>  
  
## <a name="imaging"></a><span data-ttu-id="3d4be-118">图像处理</span><span class="sxs-lookup"><span data-stu-id="3d4be-118">Imaging</span></span>  
 <span data-ttu-id="3d4be-119">某些类型的图片很难或无法显示矢量图形的方法。</span><span class="sxs-lookup"><span data-stu-id="3d4be-119">Certain kinds of pictures are difficult or impossible to display with the techniques of vector graphics.</span></span> <span data-ttu-id="3d4be-120">例如，在工具栏按钮的图片和以图标形式显示的图片是难以指定为直线和曲线的集合。</span><span class="sxs-lookup"><span data-stu-id="3d4be-120">For example, the pictures on toolbar buttons and the pictures that appear as icons are difficult to specify as collections of lines and curves.</span></span> <span data-ttu-id="3d4be-121">高分辨率的数字照片的拥挤的棒球体育场，甚至更加困难，若要创建使用矢量技术。</span><span class="sxs-lookup"><span data-stu-id="3d4be-121">A high-resolution digital photograph of a crowded baseball stadium is even more difficult to create with vector techniques.</span></span> <span data-ttu-id="3d4be-122">此类型的映像存储为位图，是表示屏幕上的各个点的颜色的数字的数组。</span><span class="sxs-lookup"><span data-stu-id="3d4be-122">Images of this type are stored as bitmaps, which are arrays of numbers that represent the colors of individual dots on the screen.</span></span> [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] <span data-ttu-id="3d4be-123">提供了<xref:System.Drawing.Bitmap>用于显示、 操作和保存位图的类。</span><span class="sxs-lookup"><span data-stu-id="3d4be-123">provides the <xref:System.Drawing.Bitmap> class for displaying, manipulating, and saving bitmaps.</span></span>  
  
## <a name="typography"></a><span data-ttu-id="3d4be-124">版式</span><span class="sxs-lookup"><span data-stu-id="3d4be-124">Typography</span></span>  
 <span data-ttu-id="3d4be-125">版式是文本的不同的字体、 大小和样式的显示。</span><span class="sxs-lookup"><span data-stu-id="3d4be-125">Typography is the display of text in a variety of fonts, sizes, and styles.</span></span> [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] <span data-ttu-id="3d4be-126">为此项复杂的任务提供广泛支持。</span><span class="sxs-lookup"><span data-stu-id="3d4be-126">provides extensive support for this complex task.</span></span> <span data-ttu-id="3d4be-127">中的新功能之一[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]子像素抗锯齿功能，它可以使文本呈现在 LCD 屏幕外观更流畅。</span><span class="sxs-lookup"><span data-stu-id="3d4be-127">One of the new features in [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] is subpixel antialiasing, which gives text rendered on an LCD screen a smoother appearance.</span></span>  
  
 <span data-ttu-id="3d4be-128">此外，Windows 窗体提供用于绘制文本的选项[!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)]中的功能及其<xref:System.Windows.Forms.TextRenderer>类。</span><span class="sxs-lookup"><span data-stu-id="3d4be-128">In addition, Windows Forms offers the option to draw text with [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] capabilities in its <xref:System.Windows.Forms.TextRenderer> class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3d4be-129">请参阅</span><span class="sxs-lookup"><span data-stu-id="3d4be-129">See also</span></span>

- [<span data-ttu-id="3d4be-130">图形概述</span><span class="sxs-lookup"><span data-stu-id="3d4be-130">Graphics Overview</span></span>](graphics-overview-windows-forms.md)
- [<span data-ttu-id="3d4be-131">关于 GDI+ 托管代码</span><span class="sxs-lookup"><span data-stu-id="3d4be-131">About GDI+ Managed Code</span></span>](about-gdi-managed-code.md)
- [<span data-ttu-id="3d4be-132">使用托管图形类</span><span class="sxs-lookup"><span data-stu-id="3d4be-132">Using Managed Graphics Classes</span></span>](using-managed-graphics-classes.md)
