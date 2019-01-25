---
title: 在 GDI+ 中裁切和缩放图像
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- GDI+, scaling images
- GDI+, cropping images
- images [Windows Forms], cropping
- compressing data [Windows Forms], images
- images [Windows Forms], expansion
- images [Windows Forms], scaling
- rectangles [Windows Forms], source
- rectangles [Windows Forms], destination
- images [Windows Forms], compression
ms.assetid: ad5daf26-005f-45bc-a2af-e0e97777a21a
ms.openlocfilehash: 6c3ad0892ea0892b7c4c0e21e14bdb75fe22b447
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54554213"
---
# <a name="cropping-and-scaling-images-in-gdi"></a><span data-ttu-id="2d318-102">在 GDI+ 中裁切和缩放图像</span><span class="sxs-lookup"><span data-stu-id="2d318-102">Cropping and Scaling Images in GDI+</span></span>
<span data-ttu-id="2d318-103">可以使用<xref:System.Drawing.Graphics.DrawImage%2A>方法的<xref:System.Drawing.Graphics>类可以绘制和位置矢量图像和光栅图像。</span><span class="sxs-lookup"><span data-stu-id="2d318-103">You can use the <xref:System.Drawing.Graphics.DrawImage%2A> method of the <xref:System.Drawing.Graphics> class to draw and position vector images and raster images.</span></span> <span data-ttu-id="2d318-104"><xref:System.Drawing.Graphics.DrawImage%2A> 是重载的方法，因此有几种方法可以提供该文件使用的参数。</span><span class="sxs-lookup"><span data-stu-id="2d318-104"><xref:System.Drawing.Graphics.DrawImage%2A> is an overloaded method, so there are several ways you can supply it with arguments.</span></span>  
  
## <a name="drawimage-variations"></a><span data-ttu-id="2d318-105">DrawImage 变体</span><span class="sxs-lookup"><span data-stu-id="2d318-105">DrawImage Variations</span></span>  
 <span data-ttu-id="2d318-106">一个变体<xref:System.Drawing.Graphics.DrawImage%2A>方法接收<xref:System.Drawing.Bitmap>和一个<xref:System.Drawing.Rectangle>。</span><span class="sxs-lookup"><span data-stu-id="2d318-106">One variation of the <xref:System.Drawing.Graphics.DrawImage%2A> method receives a <xref:System.Drawing.Bitmap> and a <xref:System.Drawing.Rectangle>.</span></span> <span data-ttu-id="2d318-107">矩形指定的目标为绘制操作;也就是说，它指定在其中绘制图像的矩形。</span><span class="sxs-lookup"><span data-stu-id="2d318-107">The rectangle specifies the destination for the drawing operation; that is, it specifies the rectangle in which to draw the image.</span></span> <span data-ttu-id="2d318-108">如果目标矩形的大小不同于原始图像的大小，缩放图像以适合目标矩形。</span><span class="sxs-lookup"><span data-stu-id="2d318-108">If the size of the destination rectangle is different from the size of the original image, the image is scaled to fit the destination rectangle.</span></span> <span data-ttu-id="2d318-109">下面的代码示例演示如何将同一图像绘制三次： 一次用于无需进行扩展，使用扩展，一次，一次用于压缩：</span><span class="sxs-lookup"><span data-stu-id="2d318-109">The following code example shows how to draw the same image three times: once with no scaling, once with an expansion, and once with a compression:</span></span>  
  
 [!code-csharp[System.Drawing.ImagesBitmapsMetafiles#31](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.ImagesBitmapsMetafiles#31](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/VB/Class1.vb#31)]  
  
 <span data-ttu-id="2d318-110">下图显示了三个图片。</span><span class="sxs-lookup"><span data-stu-id="2d318-110">The following illustration shows the three pictures.</span></span>  
  
 <span data-ttu-id="2d318-111">![Scaling](../../../../docs/framework/winforms/advanced/media/aboutgdip03-art06.gif "AboutGdip03_Art06")</span><span class="sxs-lookup"><span data-stu-id="2d318-111">![Scaling](../../../../docs/framework/winforms/advanced/media/aboutgdip03-art06.gif "AboutGdip03_Art06")</span></span>  
  
 <span data-ttu-id="2d318-112">某些变体<xref:System.Drawing.Graphics.DrawImage%2A>方法有源矩形参数，以及目标矩形参数。</span><span class="sxs-lookup"><span data-stu-id="2d318-112">Some variations of the <xref:System.Drawing.Graphics.DrawImage%2A> method have a source-rectangle parameter as well as a destination-rectangle parameter.</span></span> <span data-ttu-id="2d318-113">源矩形参数指定要绘制的原始图像的部分。</span><span class="sxs-lookup"><span data-stu-id="2d318-113">The source-rectangle parameter specifies the portion of the original image to draw.</span></span> <span data-ttu-id="2d318-114">目标矩形指定要在其中绘制图像的该部分的矩形。</span><span class="sxs-lookup"><span data-stu-id="2d318-114">The destination rectangle specifies the rectangle in which to draw that portion of the image.</span></span> <span data-ttu-id="2d318-115">如果目标矩形的大小不同于源矩形的大小，该图片进行缩放以适合目标矩形。</span><span class="sxs-lookup"><span data-stu-id="2d318-115">If the size of the destination rectangle is different from the size of the source rectangle, the picture is scaled to fit the destination rectangle.</span></span>  
  
 <span data-ttu-id="2d318-116">下面的代码示例演示如何构造<xref:System.Drawing.Bitmap>Runner.jpg 文件中。</span><span class="sxs-lookup"><span data-stu-id="2d318-116">The following code example shows how to construct a <xref:System.Drawing.Bitmap> from the file Runner.jpg.</span></span> <span data-ttu-id="2d318-117">使用无需进行扩展在绘制整个图像 （0，0）。</span><span class="sxs-lookup"><span data-stu-id="2d318-117">The entire image is drawn with no scaling at (0, 0).</span></span> <span data-ttu-id="2d318-118">然后两次绘制的图像的一小部分： 一次使用压缩，一次使用扩展。</span><span class="sxs-lookup"><span data-stu-id="2d318-118">Then a small portion of the image is drawn twice: once with a compression and once with an expansion.</span></span>  
  
 [!code-csharp[System.Drawing.ImagesBitmapsMetafiles#32](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/CS/Class1.cs#32)]
 [!code-vb[System.Drawing.ImagesBitmapsMetafiles#32](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/VB/Class1.vb#32)]  
  
 <span data-ttu-id="2d318-119">下图显示了未缩放的图像和压缩和扩展的图像部分。</span><span class="sxs-lookup"><span data-stu-id="2d318-119">The following illustration shows the unscaled image, and the compressed and expanded image portions.</span></span>  
  
 <span data-ttu-id="2d318-120">![裁剪和缩放](../../../../docs/framework/winforms/advanced/media/aboutgdip03-art07.gif "AboutGdip03_Art07")</span><span class="sxs-lookup"><span data-stu-id="2d318-120">![Cropping and Scaling](../../../../docs/framework/winforms/advanced/media/aboutgdip03-art07.gif "AboutGdip03_Art07")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2d318-121">请参阅</span><span class="sxs-lookup"><span data-stu-id="2d318-121">See also</span></span>
- [<span data-ttu-id="2d318-122">图像、位图和图元文件</span><span class="sxs-lookup"><span data-stu-id="2d318-122">Images, Bitmaps, and Metafiles</span></span>](../../../../docs/framework/winforms/advanced/images-bitmaps-and-metafiles.md)
- [<span data-ttu-id="2d318-123">使用图像、位图、图标和图元文件</span><span class="sxs-lookup"><span data-stu-id="2d318-123">Working with Images, Bitmaps, Icons, and Metafiles</span></span>](../../../../docs/framework/winforms/advanced/working-with-images-bitmaps-icons-and-metafiles.md)
