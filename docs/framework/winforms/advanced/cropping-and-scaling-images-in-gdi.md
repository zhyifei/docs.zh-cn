---
title: "在 GDI+ 中裁切和缩放图像"
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
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 0bbe7ac4b8c541ea76392f94f538e41816cf5c3f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="cropping-and-scaling-images-in-gdi"></a><span data-ttu-id="2b06a-102">在 GDI+ 中裁切和缩放图像</span><span class="sxs-lookup"><span data-stu-id="2b06a-102">Cropping and Scaling Images in GDI+</span></span>
<span data-ttu-id="2b06a-103">你可以使用<xref:System.Drawing.Graphics.DrawImage%2A>方法<xref:System.Drawing.Graphics>类可以绘制和位置矢量图像和光栅图像。</span><span class="sxs-lookup"><span data-stu-id="2b06a-103">You can use the <xref:System.Drawing.Graphics.DrawImage%2A> method of the <xref:System.Drawing.Graphics> class to draw and position vector images and raster images.</span></span> <span data-ttu-id="2b06a-104"><xref:System.Drawing.Graphics.DrawImage%2A>是重载的方法，因此有几种方法，你可以向其提供自变量。</span><span class="sxs-lookup"><span data-stu-id="2b06a-104"><xref:System.Drawing.Graphics.DrawImage%2A> is an overloaded method, so there are several ways you can supply it with arguments.</span></span>  
  
## <a name="drawimage-variations"></a><span data-ttu-id="2b06a-105">DrawImage 变体</span><span class="sxs-lookup"><span data-stu-id="2b06a-105">DrawImage Variations</span></span>  
 <span data-ttu-id="2b06a-106">一个变体<xref:System.Drawing.Graphics.DrawImage%2A>方法接收<xref:System.Drawing.Bitmap>和<xref:System.Drawing.Rectangle>。</span><span class="sxs-lookup"><span data-stu-id="2b06a-106">One variation of the <xref:System.Drawing.Graphics.DrawImage%2A> method receives a <xref:System.Drawing.Bitmap> and a <xref:System.Drawing.Rectangle>.</span></span> <span data-ttu-id="2b06a-107">矩形指定绘制操作; 的目标也就是说，它指定在其中绘制图像的矩形。</span><span class="sxs-lookup"><span data-stu-id="2b06a-107">The rectangle specifies the destination for the drawing operation; that is, it specifies the rectangle in which to draw the image.</span></span> <span data-ttu-id="2b06a-108">如果目标矩形的大小不同于原始图像的大小，缩放图像以适合目标矩形。</span><span class="sxs-lookup"><span data-stu-id="2b06a-108">If the size of the destination rectangle is different from the size of the original image, the image is scaled to fit the destination rectangle.</span></span> <span data-ttu-id="2b06a-109">下面的代码示例演示如何将同一图像绘制三次： 一次没有缩放、 使用扩展，一次，并且一次使用压缩：</span><span class="sxs-lookup"><span data-stu-id="2b06a-109">The following code example shows how to draw the same image three times: once with no scaling, once with an expansion, and once with a compression:</span></span>  
  
 [!code-csharp[System.Drawing.ImagesBitmapsMetafiles#31](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.ImagesBitmapsMetafiles#31](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/VB/Class1.vb#31)]  
  
 <span data-ttu-id="2b06a-110">下图显示三个图片。</span><span class="sxs-lookup"><span data-stu-id="2b06a-110">The following illustration shows the three pictures.</span></span>  
  
 <span data-ttu-id="2b06a-111">![缩放](../../../../docs/framework/winforms/advanced/media/aboutgdip03-art06.gif "AboutGdip03_Art06")</span><span class="sxs-lookup"><span data-stu-id="2b06a-111">![Scaling](../../../../docs/framework/winforms/advanced/media/aboutgdip03-art06.gif "AboutGdip03_Art06")</span></span>  
  
 <span data-ttu-id="2b06a-112">某些变体<xref:System.Drawing.Graphics.DrawImage%2A>方法有源矩形参数，以及目标矩形参数。</span><span class="sxs-lookup"><span data-stu-id="2b06a-112">Some variations of the <xref:System.Drawing.Graphics.DrawImage%2A> method have a source-rectangle parameter as well as a destination-rectangle parameter.</span></span> <span data-ttu-id="2b06a-113">源矩形参数指定要绘制的原始图像的部分。</span><span class="sxs-lookup"><span data-stu-id="2b06a-113">The source-rectangle parameter specifies the portion of the original image to draw.</span></span> <span data-ttu-id="2b06a-114">目标矩形指定要在其中绘制图像的该部分的矩形。</span><span class="sxs-lookup"><span data-stu-id="2b06a-114">The destination rectangle specifies the rectangle in which to draw that portion of the image.</span></span> <span data-ttu-id="2b06a-115">如果目标矩形的大小不同于源矩形的大小，图进行缩放以适合目标矩形。</span><span class="sxs-lookup"><span data-stu-id="2b06a-115">If the size of the destination rectangle is different from the size of the source rectangle, the picture is scaled to fit the destination rectangle.</span></span>  
  
 <span data-ttu-id="2b06a-116">下面的代码示例显示如何构造<xref:System.Drawing.Bitmap>从 Runner.jpg 的文件。</span><span class="sxs-lookup"><span data-stu-id="2b06a-116">The following code example shows how to construct a <xref:System.Drawing.Bitmap> from the file Runner.jpg.</span></span> <span data-ttu-id="2b06a-117">在无缩放绘制整个图像 （0，0）。</span><span class="sxs-lookup"><span data-stu-id="2b06a-117">The entire image is drawn with no scaling at (0, 0).</span></span> <span data-ttu-id="2b06a-118">然后两次绘制图像的一小部分： 一次使用压缩，一次使用扩展。</span><span class="sxs-lookup"><span data-stu-id="2b06a-118">Then a small portion of the image is drawn twice: once with a compression and once with an expansion.</span></span>  
  
 [!code-csharp[System.Drawing.ImagesBitmapsMetafiles#32](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/CS/Class1.cs#32)]
 [!code-vb[System.Drawing.ImagesBitmapsMetafiles#32](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/VB/Class1.vb#32)]  
  
 <span data-ttu-id="2b06a-119">下图显示未缩放的图像和压缩和扩展的图像部分。</span><span class="sxs-lookup"><span data-stu-id="2b06a-119">The following illustration shows the unscaled image, and the compressed and expanded image portions.</span></span>  
  
 <span data-ttu-id="2b06a-120">![剪切和缩放](../../../../docs/framework/winforms/advanced/media/aboutgdip03-art07.gif "AboutGdip03_Art07")</span><span class="sxs-lookup"><span data-stu-id="2b06a-120">![Cropping and Scaling](../../../../docs/framework/winforms/advanced/media/aboutgdip03-art07.gif "AboutGdip03_Art07")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2b06a-121">请参阅</span><span class="sxs-lookup"><span data-stu-id="2b06a-121">See Also</span></span>  
 [<span data-ttu-id="2b06a-122">图像、位图和图元文件</span><span class="sxs-lookup"><span data-stu-id="2b06a-122">Images, Bitmaps, and Metafiles</span></span>](../../../../docs/framework/winforms/advanced/images-bitmaps-and-metafiles.md)  
 [<span data-ttu-id="2b06a-123">使用图像、位图、图标和图元文件</span><span class="sxs-lookup"><span data-stu-id="2b06a-123">Working with Images, Bitmaps, Icons, and Metafiles</span></span>](../../../../docs/framework/winforms/advanced/working-with-images-bitmaps-icons-and-metafiles.md)
