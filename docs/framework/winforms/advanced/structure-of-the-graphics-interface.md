---
title: "图形界面的结构"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- GDI+, using managed interface
- graphics [Windows Forms], class structure
ms.assetid: 010a1e46-656b-40a1-8d5d-87aa05ee1243
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: cd1da930df151869ea3e891da7057f44ed0a4603
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="structure-of-the-graphics-interface"></a><span data-ttu-id="fa418-102">图形界面的结构</span><span class="sxs-lookup"><span data-stu-id="fa418-102">Structure of the Graphics Interface</span></span>
<span data-ttu-id="fa418-103">托管的类接口[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]包含大约 60 个类、 50 枚举和 8 个结构。</span><span class="sxs-lookup"><span data-stu-id="fa418-103">The managed class interface to [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] contains about 60 classes, 50 enumerations, and 8 structures.</span></span> <span data-ttu-id="fa418-104"><xref:System.Drawing.Graphics>类的核心是[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]功能; 它是实际绘制线条、 曲线、 图形、 图像和文本的类。</span><span class="sxs-lookup"><span data-stu-id="fa418-104">The <xref:System.Drawing.Graphics> class is at the core of [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] functionality; it is the class that actually draws lines, curves, figures, images, and text.</span></span>  
  
## <a name="important-classes"></a><span data-ttu-id="fa418-105">重要的类</span><span class="sxs-lookup"><span data-stu-id="fa418-105">Important Classes</span></span>  
 <span data-ttu-id="fa418-106">许多类可一起与<xref:System.Drawing.Graphics>类。</span><span class="sxs-lookup"><span data-stu-id="fa418-106">Many classes work together with the <xref:System.Drawing.Graphics> class.</span></span> <span data-ttu-id="fa418-107">例如，<xref:System.Drawing.Graphics.DrawLine%2A>方法接收<xref:System.Drawing.Pen>对象，包含要绘制的行的属性 （颜色、 宽度、 短划线样式和 like） 属性。</span><span class="sxs-lookup"><span data-stu-id="fa418-107">For example, the <xref:System.Drawing.Graphics.DrawLine%2A> method receives a <xref:System.Drawing.Pen> object, which holds attributes (color, width, dash style, and the like) of the line to be drawn.</span></span> <span data-ttu-id="fa418-108"><xref:System.Drawing.Graphics.FillRectangle%2A>方法可以接收指向的指针<xref:System.Drawing.Drawing2D.LinearGradientBrush>对象，适用于<xref:System.Drawing.Graphics>对象填充渐变的颜色的矩形。</span><span class="sxs-lookup"><span data-stu-id="fa418-108">The <xref:System.Drawing.Graphics.FillRectangle%2A> method can receive a pointer to a <xref:System.Drawing.Drawing2D.LinearGradientBrush> object, which works with the <xref:System.Drawing.Graphics> object to fill a rectangle with a gradually changing color.</span></span> <span data-ttu-id="fa418-109"><xref:System.Drawing.Font>和<xref:System.Drawing.StringFormat>对象影响方式<xref:System.Drawing.Graphics>对象绘制文本。</span><span class="sxs-lookup"><span data-stu-id="fa418-109"><xref:System.Drawing.Font> and <xref:System.Drawing.StringFormat> objects influence the way a <xref:System.Drawing.Graphics> object draws text.</span></span> <span data-ttu-id="fa418-110">A<xref:System.Drawing.Drawing2D.Matrix>对象存储和操作的世界变换<xref:System.Drawing.Graphics>对象，用于旋转、 缩放和翻转图像。</span><span class="sxs-lookup"><span data-stu-id="fa418-110">A <xref:System.Drawing.Drawing2D.Matrix> object stores and manipulates the world transformation of a <xref:System.Drawing.Graphics> object, which is used to rotate, scale, and flip images.</span></span>  
  
 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]<span data-ttu-id="fa418-111">提供多个结构 (例如， <xref:System.Drawing.Rectangle>， <xref:System.Drawing.Point>，和<xref:System.Drawing.Size>) 用于组织图形数据。</span><span class="sxs-lookup"><span data-stu-id="fa418-111"> provides several structures (for example, <xref:System.Drawing.Rectangle>, <xref:System.Drawing.Point>, and <xref:System.Drawing.Size>) for organizing graphics data.</span></span> <span data-ttu-id="fa418-112">此外，某些类充当主要结构化的数据类型。</span><span class="sxs-lookup"><span data-stu-id="fa418-112">Also, certain classes serve primarily as structured data types.</span></span> <span data-ttu-id="fa418-113">例如，<xref:System.Drawing.Imaging.BitmapData>类是帮助器<xref:System.Drawing.Bitmap>类，与<xref:System.Drawing.Drawing2D.PathData>类是帮助器<xref:System.Drawing.Drawing2D.GraphicsPath>类。</span><span class="sxs-lookup"><span data-stu-id="fa418-113">For example, the <xref:System.Drawing.Imaging.BitmapData> class is a helper for the <xref:System.Drawing.Bitmap> class, and the <xref:System.Drawing.Drawing2D.PathData> class is a helper for the <xref:System.Drawing.Drawing2D.GraphicsPath> class.</span></span>  
  
 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]<span data-ttu-id="fa418-114">定义了几种枚举，它们是相关的常数的集合。</span><span class="sxs-lookup"><span data-stu-id="fa418-114"> defines several enumerations, which are collections of related constants.</span></span> <span data-ttu-id="fa418-115">例如，<xref:System.Drawing.Drawing2D.LineJoin>枚举包含元素<xref:System.Drawing.Drawing2D.LineJoin.Bevel>， <xref:System.Drawing.Drawing2D.LineJoin.Miter>，和<xref:System.Drawing.Drawing2D.LineJoin.Round>，它指定可用于联接两条线的样式。</span><span class="sxs-lookup"><span data-stu-id="fa418-115">For example, the <xref:System.Drawing.Drawing2D.LineJoin> enumeration contains the elements <xref:System.Drawing.Drawing2D.LineJoin.Bevel>, <xref:System.Drawing.Drawing2D.LineJoin.Miter>, and <xref:System.Drawing.Drawing2D.LineJoin.Round>, which specify styles that can be used to join two lines.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fa418-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fa418-116">See Also</span></span>  
 [<span data-ttu-id="fa418-117">图形概述</span><span class="sxs-lookup"><span data-stu-id="fa418-117">Graphics Overview</span></span>](../../../../docs/framework/winforms/advanced/graphics-overview-windows-forms.md)  
 [<span data-ttu-id="fa418-118">关于 GDI+ 托管代码</span><span class="sxs-lookup"><span data-stu-id="fa418-118">About GDI+ Managed Code</span></span>](../../../../docs/framework/winforms/advanced/about-gdi-managed-code.md)  
 [<span data-ttu-id="fa418-119">使用托管图形类</span><span class="sxs-lookup"><span data-stu-id="fa418-119">Using Managed Graphics Classes</span></span>](../../../../docs/framework/winforms/advanced/using-managed-graphics-classes.md)
