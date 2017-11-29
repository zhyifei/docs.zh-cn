---
title: "图形服务的三个类别"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- imaging
- graphics [Windows Forms], categories
- 2-D vector graphics
- vector graphics
- typography
ms.assetid: 068c0ef3-f6ee-4d58-a7b6-eb2531ead408
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 53429513426d3b197da4740e5e92d44d8b3a5533
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="three-categories-of-graphics-services"></a><span data-ttu-id="e3407-102">图形服务的三个类别</span><span class="sxs-lookup"><span data-stu-id="e3407-102">Three Categories of Graphics Services</span></span>
<span data-ttu-id="e3407-103">Windows 窗体中的图形产品划分为以下三大类：</span><span class="sxs-lookup"><span data-stu-id="e3407-103">The graphics offerings in Windows Forms fall into the following three broad categories:</span></span>  
  
-   <span data-ttu-id="e3407-104">二维 (2-d) 向量图形</span><span class="sxs-lookup"><span data-stu-id="e3407-104">Two-dimensional (2-D) vector graphics</span></span>  
  
-   <span data-ttu-id="e3407-105">映像</span><span class="sxs-lookup"><span data-stu-id="e3407-105">Imaging</span></span>  
  
-   <span data-ttu-id="e3407-106">版式</span><span class="sxs-lookup"><span data-stu-id="e3407-106">Typography</span></span>  
  
## <a name="2-d-vector-graphics"></a><span data-ttu-id="e3407-107">二维向量图形</span><span class="sxs-lookup"><span data-stu-id="e3407-107">2-D Vector Graphics</span></span>  
 <span data-ttu-id="e3407-108">二维向量图形是基元;直线、 曲线和图形; 例如指定的坐标系统上的点集。</span><span class="sxs-lookup"><span data-stu-id="e3407-108">Two-dimensional vector graphics are primitives; such as lines, curves, and figures; that are specified by sets of points on a coordinate system.</span></span> <span data-ttu-id="e3407-109">例如，由其两个终结点，指定一条直线和矩形指定通过提供其左上角和一对数字使其宽度和高度的位置的点。</span><span class="sxs-lookup"><span data-stu-id="e3407-109">For example, a straight line is specified by its two endpoints, and a rectangle is specified by a point giving the location of its upper-left corner and a pair of numbers giving its width and height.</span></span> <span data-ttu-id="e3407-110">通过由直线连接的点数组指定简单的路径。</span><span class="sxs-lookup"><span data-stu-id="e3407-110">A simple path is specified by an array of points that are connected by straight lines.</span></span> <span data-ttu-id="e3407-111">指定由四个控制点的复杂的曲线的贝塞尔样条。</span><span class="sxs-lookup"><span data-stu-id="e3407-111">A Bézier spline is a sophisticated curve specified by four control points.</span></span>  
  
 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]<span data-ttu-id="e3407-112">提供类和存储有关的基元本身的信息的结构、 存储有关如何将绘制基元，信息的类和实际执行绘图的类。</span><span class="sxs-lookup"><span data-stu-id="e3407-112"> provides classes and structures that store information about the primitives themselves, classes that store information about how the primitives will be drawn, and classes that actually do the drawing.</span></span> <span data-ttu-id="e3407-113">例如，<xref:System.Drawing.Rectangle>结构存储的位置和大小的矩形;<xref:System.Drawing.Pen>类存储线条颜色、 线条宽度和线条样式; 有关的信息和<xref:System.Drawing.Graphics>类具有绘制线条、 矩形、 路径的方法和其他图中。</span><span class="sxs-lookup"><span data-stu-id="e3407-113">For example, the <xref:System.Drawing.Rectangle> structure stores the location and size of a rectangle; the <xref:System.Drawing.Pen> class stores information about line color, line width, and line style; and the <xref:System.Drawing.Graphics> class has methods for drawing lines, rectangles, paths, and other figures.</span></span> <span data-ttu-id="e3407-114">有几种<xref:System.Drawing.Brush>存储有关如何信息的类封闭图形和路径中将填充颜色或图案。</span><span class="sxs-lookup"><span data-stu-id="e3407-114">There are also several <xref:System.Drawing.Brush> classes that store information about how closed figures and paths will be filled with colors or patterns.</span></span>  
  
 <span data-ttu-id="e3407-115">你可以在图元文件中记录的图形命令序列矢量图像。</span><span class="sxs-lookup"><span data-stu-id="e3407-115">You can record a vector image, which is a sequence of graphics commands, in a metafile.</span></span> [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]<span data-ttu-id="e3407-116">提供<xref:System.Drawing.Imaging.Metafile>类录制、 显示和保存图元文件。</span><span class="sxs-lookup"><span data-stu-id="e3407-116"> provides the <xref:System.Drawing.Imaging.Metafile> class for recording, displaying, and saving metafiles.</span></span> <span data-ttu-id="e3407-117">与<xref:System.Drawing.Imaging.MetafileHeader>和<xref:System.Drawing.Imaging.MetaHeader>类，你可以检查图元文件标头中存储的数据。</span><span class="sxs-lookup"><span data-stu-id="e3407-117">With the <xref:System.Drawing.Imaging.MetafileHeader> and <xref:System.Drawing.Imaging.MetaHeader> classes, you can inspect the data stored in a metafile header.</span></span>  
  
## <a name="imaging"></a><span data-ttu-id="e3407-118">映像</span><span class="sxs-lookup"><span data-stu-id="e3407-118">Imaging</span></span>  
 <span data-ttu-id="e3407-119">某些种类的图片很难或无法显示使用矢量图形的技术。</span><span class="sxs-lookup"><span data-stu-id="e3407-119">Certain kinds of pictures are difficult or impossible to display with the techniques of vector graphics.</span></span> <span data-ttu-id="e3407-120">例如，在工具栏按钮的图片和以图标形式显示的图片就是难以指定为集合的直线和曲线。</span><span class="sxs-lookup"><span data-stu-id="e3407-120">For example, the pictures on toolbar buttons and the pictures that appear as icons are difficult to specify as collections of lines and curves.</span></span> <span data-ttu-id="e3407-121">高分辨率数码相片拥挤的棒体育场是创建使用矢量技术变得更加困难。</span><span class="sxs-lookup"><span data-stu-id="e3407-121">A high-resolution digital photograph of a crowded baseball stadium is even more difficult to create with vector techniques.</span></span> <span data-ttu-id="e3407-122">此类型的图像存储为位图，是表示屏幕上的各个点的颜色的数字的数组。</span><span class="sxs-lookup"><span data-stu-id="e3407-122">Images of this type are stored as bitmaps, which are arrays of numbers that represent the colors of individual dots on the screen.</span></span> [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]<span data-ttu-id="e3407-123">提供<xref:System.Drawing.Bitmap>用于显示、 操作和保存位图的类。</span><span class="sxs-lookup"><span data-stu-id="e3407-123"> provides the <xref:System.Drawing.Bitmap> class for displaying, manipulating, and saving bitmaps.</span></span>  
  
## <a name="typography"></a><span data-ttu-id="e3407-124">版式</span><span class="sxs-lookup"><span data-stu-id="e3407-124">Typography</span></span>  
 <span data-ttu-id="e3407-125">版式是文本的在多个字体、 大小和样式的显示。</span><span class="sxs-lookup"><span data-stu-id="e3407-125">Typography is the display of text in a variety of fonts, sizes, and styles.</span></span> [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]<span data-ttu-id="e3407-126">此复杂的任务提供广泛支持。</span><span class="sxs-lookup"><span data-stu-id="e3407-126"> provides extensive support for this complex task.</span></span> <span data-ttu-id="e3407-127">中的新功能之一[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]子像素抗锯齿，它可以使文本上呈现 LCD 屏幕模型更流畅的外观。</span><span class="sxs-lookup"><span data-stu-id="e3407-127">One of the new features in [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] is subpixel antialiasing, which gives text rendered on an LCD screen a smoother appearance.</span></span>  
  
 <span data-ttu-id="e3407-128">此外，Windows 窗体提供的选项，绘制文本[!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)]中的功能其<xref:System.Windows.Forms.TextRenderer>类。</span><span class="sxs-lookup"><span data-stu-id="e3407-128">In addition, Windows Forms offers the option to draw text with [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] capabilities in its <xref:System.Windows.Forms.TextRenderer> class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e3407-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e3407-129">See Also</span></span>  
 [<span data-ttu-id="e3407-130">图形概述</span><span class="sxs-lookup"><span data-stu-id="e3407-130">Graphics Overview</span></span>](../../../../docs/framework/winforms/advanced/graphics-overview-windows-forms.md)  
 [<span data-ttu-id="e3407-131">关于 GDI+ 托管代码</span><span class="sxs-lookup"><span data-stu-id="e3407-131">About GDI+ Managed Code</span></span>](../../../../docs/framework/winforms/advanced/about-gdi-managed-code.md)  
 [<span data-ttu-id="e3407-132">使用托管图形类</span><span class="sxs-lookup"><span data-stu-id="e3407-132">Using Managed Graphics Classes</span></span>](../../../../docs/framework/winforms/advanced/using-managed-graphics-classes.md)
