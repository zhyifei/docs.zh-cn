---
title: 图形服务的三个类别
ms.date: 03/30/2017
helpviewer_keywords:
- imaging
- graphics [Windows Forms], categories
- 2D vector graphics
- vector graphics
- typography
ms.assetid: 068c0ef3-f6ee-4d58-a7b6-eb2531ead408
ms.openlocfilehash: b0f2ad8293daf6ad53899a0f8be82985c24ff50d
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/21/2020
ms.locfileid: "80111200"
---
# <a name="three-categories-of-graphics-services"></a><span data-ttu-id="458b9-102">图形服务的三个类别</span><span class="sxs-lookup"><span data-stu-id="458b9-102">Three Categories of Graphics Services</span></span>
<span data-ttu-id="458b9-103">Windows 窗体中的图形产品分为以下三大类：</span><span class="sxs-lookup"><span data-stu-id="458b9-103">The graphics offerings in Windows Forms fall into the following three broad categories:</span></span>  
  
- <span data-ttu-id="458b9-104">二维 （二-D） 矢量图形</span><span class="sxs-lookup"><span data-stu-id="458b9-104">Two-dimensional (2-D) vector graphics</span></span>  
  
- <span data-ttu-id="458b9-105">映像</span><span class="sxs-lookup"><span data-stu-id="458b9-105">Imaging</span></span>  
  
- <span data-ttu-id="458b9-106">版式</span><span class="sxs-lookup"><span data-stu-id="458b9-106">Typography</span></span>  
  
## <a name="2d-vector-graphics"></a><span data-ttu-id="458b9-107">2D 矢量图形</span><span class="sxs-lookup"><span data-stu-id="458b9-107">2D Vector Graphics</span></span>  
 <span data-ttu-id="458b9-108">二维矢量图形是基元图形;如直线、曲线和图形;由坐标系上的点集指定。</span><span class="sxs-lookup"><span data-stu-id="458b9-108">Two-dimensional vector graphics are primitives; such as lines, curves, and figures; that are specified by sets of points on a coordinate system.</span></span> <span data-ttu-id="458b9-109">例如，直线由其两个端点指定，矩形由一个点指定，该点给出其左上角的位置，以及一对表示其宽度和高度的数字。</span><span class="sxs-lookup"><span data-stu-id="458b9-109">For example, a straight line is specified by its two endpoints, and a rectangle is specified by a point giving the location of its upper-left corner and a pair of numbers giving its width and height.</span></span> <span data-ttu-id="458b9-110">简单路径由由直线连接的点数组指定。</span><span class="sxs-lookup"><span data-stu-id="458b9-110">A simple path is specified by an array of points that are connected by straight lines.</span></span> <span data-ttu-id="458b9-111">贝塞尔样条线是由四个控制点指定的复杂曲线。</span><span class="sxs-lookup"><span data-stu-id="458b9-111">A Bézier spline is a sophisticated curve specified by four control points.</span></span>  
  
 <span data-ttu-id="458b9-112">GDI+ 提供类和结构，这些类和结构存储有关基元本身的信息、存储有关基元绘制方式的信息的类以及实际执行绘图的类。</span><span class="sxs-lookup"><span data-stu-id="458b9-112">GDI+ provides classes and structures that store information about the primitives themselves, classes that store information about how the primitives will be drawn, and classes that actually do the drawing.</span></span> <span data-ttu-id="458b9-113">例如，结构存储<xref:System.Drawing.Rectangle>矩形的位置和大小;例如，该结构存储矩形的位置和大小。类<xref:System.Drawing.Pen>存储有关线颜色、线宽和线样式的信息;<xref:System.Drawing.Graphics>类具有绘制线条、矩形、路径和其他图形的方法。</span><span class="sxs-lookup"><span data-stu-id="458b9-113">For example, the <xref:System.Drawing.Rectangle> structure stores the location and size of a rectangle; the <xref:System.Drawing.Pen> class stores information about line color, line width, and line style; and the <xref:System.Drawing.Graphics> class has methods for drawing lines, rectangles, paths, and other figures.</span></span> <span data-ttu-id="458b9-114">还有几个<xref:System.Drawing.Brush>类存储有关如何用颜色或图案填充闭合的数字和路径的信息。</span><span class="sxs-lookup"><span data-stu-id="458b9-114">There are also several <xref:System.Drawing.Brush> classes that store information about how closed figures and paths will be filled with colors or patterns.</span></span>  
  
 <span data-ttu-id="458b9-115">您可以在元文件中记录矢量图像（即图形命令序列）。</span><span class="sxs-lookup"><span data-stu-id="458b9-115">You can record a vector image, which is a sequence of graphics commands, in a metafile.</span></span> <span data-ttu-id="458b9-116">GDI+ 提供<xref:System.Drawing.Imaging.Metafile>用于录制、显示和保存元文件的类。</span><span class="sxs-lookup"><span data-stu-id="458b9-116">GDI+ provides the <xref:System.Drawing.Imaging.Metafile> class for recording, displaying, and saving metafiles.</span></span> <span data-ttu-id="458b9-117">使用<xref:System.Drawing.Imaging.MetafileHeader>和<xref:System.Drawing.Imaging.MetaHeader>类，可以检查存储在元文件标头中的数据。</span><span class="sxs-lookup"><span data-stu-id="458b9-117">With the <xref:System.Drawing.Imaging.MetafileHeader> and <xref:System.Drawing.Imaging.MetaHeader> classes, you can inspect the data stored in a metafile header.</span></span>  
  
## <a name="imaging"></a><span data-ttu-id="458b9-118">映像</span><span class="sxs-lookup"><span data-stu-id="458b9-118">Imaging</span></span>  
 <span data-ttu-id="458b9-119">使用矢量图形技术很难或不可能显示某些类型的图片。</span><span class="sxs-lookup"><span data-stu-id="458b9-119">Certain kinds of pictures are difficult or impossible to display with the techniques of vector graphics.</span></span> <span data-ttu-id="458b9-120">例如，工具栏按钮上的图片和显示为图标的图片很难指定为线条和曲线的集合。</span><span class="sxs-lookup"><span data-stu-id="458b9-120">For example, the pictures on toolbar buttons and the pictures that appear as icons are difficult to specify as collections of lines and curves.</span></span> <span data-ttu-id="458b9-121">使用矢量技术，制作拥挤的棒球场的高分辨率数字照片就更加困难了。</span><span class="sxs-lookup"><span data-stu-id="458b9-121">A high-resolution digital photograph of a crowded baseball stadium is even more difficult to create with vector techniques.</span></span> <span data-ttu-id="458b9-122">此类型的图像存储为位图，即表示屏幕上单个点颜色的数字数组。</span><span class="sxs-lookup"><span data-stu-id="458b9-122">Images of this type are stored as bitmaps, which are arrays of numbers that represent the colors of individual dots on the screen.</span></span> <span data-ttu-id="458b9-123">GDI+ 提供<xref:System.Drawing.Bitmap>用于显示、操作和保存位图的类。</span><span class="sxs-lookup"><span data-stu-id="458b9-123">GDI+ provides the <xref:System.Drawing.Bitmap> class for displaying, manipulating, and saving bitmaps.</span></span>  
  
## <a name="typography"></a><span data-ttu-id="458b9-124">版式</span><span class="sxs-lookup"><span data-stu-id="458b9-124">Typography</span></span>  
 <span data-ttu-id="458b9-125">排版是文本以各种字体、大小和样式显示的。</span><span class="sxs-lookup"><span data-stu-id="458b9-125">Typography is the display of text in a variety of fonts, sizes, and styles.</span></span> <span data-ttu-id="458b9-126">GDI+ 为这一复杂任务提供了广泛的支持。</span><span class="sxs-lookup"><span data-stu-id="458b9-126">GDI+ provides extensive support for this complex task.</span></span> <span data-ttu-id="458b9-127">GDI+ 中的新功能之一是子像素抗锯齿，它使在 LCD 屏幕上呈现的文本外观更平滑。</span><span class="sxs-lookup"><span data-stu-id="458b9-127">One of the new features in GDI+ is subpixel antialiasing, which gives text rendered on an LCD screen a smoother appearance.</span></span>  
  
 <span data-ttu-id="458b9-128">此外，Windows 窗体还提供使用类<xref:System.Windows.Forms.TextRenderer>中的 GDI 功能绘制文本的选项。</span><span class="sxs-lookup"><span data-stu-id="458b9-128">In addition, Windows Forms offers the option to draw text with GDI capabilities in its <xref:System.Windows.Forms.TextRenderer> class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="458b9-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="458b9-129">See also</span></span>

- [<span data-ttu-id="458b9-130">图形概述</span><span class="sxs-lookup"><span data-stu-id="458b9-130">Graphics Overview</span></span>](graphics-overview-windows-forms.md)
- [<span data-ttu-id="458b9-131">关于 GDI+ 托管代码</span><span class="sxs-lookup"><span data-stu-id="458b9-131">About GDI+ Managed Code</span></span>](about-gdi-managed-code.md)
- [<span data-ttu-id="458b9-132">使用托管图形类</span><span class="sxs-lookup"><span data-stu-id="458b9-132">Using Managed Graphics Classes</span></span>](using-managed-graphics-classes.md)
