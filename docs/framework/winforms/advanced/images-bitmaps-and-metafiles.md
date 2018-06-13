---
title: 图像、位图和图元文件
ms.date: 03/30/2017
helpviewer_keywords:
- metafiles [Windows Forms], about metafiles
- bitmaps [Windows Forms], about bitmaps
- images [Windows Forms], about images
- Windows Forms, images
ms.assetid: 7152b45b-a55c-49bc-8c78-ae002a844f71
ms.openlocfilehash: 30887cd88bc8c08c78eb37c4fe8591ac528e6f01
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33522196"
---
# <a name="images-bitmaps-and-metafiles"></a><span data-ttu-id="fbb34-102">图像、位图和图元文件</span><span class="sxs-lookup"><span data-stu-id="fbb34-102">Images, Bitmaps, and Metafiles</span></span>
<span data-ttu-id="fbb34-103">`Image` 类是一个抽象基类，提供用于处理光栅图像（位图）和矢量图像（图元文件）的方法。</span><span class="sxs-lookup"><span data-stu-id="fbb34-103">The `Image` class is an abstract base class that provides methods for working with raster images (bitmaps) and vector images (metafiles).</span></span> <span data-ttu-id="fbb34-104">`Bitmap` 类和 <xref:System.Drawing.Imaging.Metafile> 类从 `Image` 类继承。</span><span class="sxs-lookup"><span data-stu-id="fbb34-104">The `Bitmap` class and the <xref:System.Drawing.Imaging.Metafile> class both inherit from the `Image` class.</span></span> <span data-ttu-id="fbb34-105">`Bitmap` 类通过提供用于加载、保存和操作光栅图像的附加方法，在 `Image` 类的功能上进行扩展。</span><span class="sxs-lookup"><span data-stu-id="fbb34-105">The `Bitmap` class expands on the capabilities of the `Image` class by providing additional methods for loading, saving, and manipulating raster images.</span></span> <span data-ttu-id="fbb34-106"><xref:System.Drawing.Imaging.Metafile> 类通过提供用于记录和检查矢量图像的附加方法，在 `Image` 类的功能上进行扩展。</span><span class="sxs-lookup"><span data-stu-id="fbb34-106">The <xref:System.Drawing.Imaging.Metafile> class expands on the capabilities of the `Image` class by providing additional methods for recording and examining vector images.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="fbb34-107">本节内容</span><span class="sxs-lookup"><span data-stu-id="fbb34-107">In This Section</span></span>  
 [<span data-ttu-id="fbb34-108">位图类型</span><span class="sxs-lookup"><span data-stu-id="fbb34-108">Types of Bitmaps</span></span>](../../../../docs/framework/winforms/advanced/types-of-bitmaps.md)  
 <span data-ttu-id="fbb34-109">解说不同的图像格式。</span><span class="sxs-lookup"><span data-stu-id="fbb34-109">Discusses the various image formats.</span></span>  
  
 [<span data-ttu-id="fbb34-110">GDI+ 中的图元文件</span><span class="sxs-lookup"><span data-stu-id="fbb34-110">Metafiles in GDI+</span></span>](../../../../docs/framework/winforms/advanced/metafiles-in-gdi.md)  
 <span data-ttu-id="fbb34-111">介绍 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] 对图元文件的支持。</span><span class="sxs-lookup"><span data-stu-id="fbb34-111">Discusses [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] support for metafiles.</span></span>  
  
 [<span data-ttu-id="fbb34-112">在 GDI+ 中绘制、定位和克隆图像</span><span class="sxs-lookup"><span data-stu-id="fbb34-112">Drawing, Positioning, and Cloning Images in GDI+</span></span>](../../../../docs/framework/winforms/advanced/drawing-positioning-and-cloning-images-in-gdi.md)  
 <span data-ttu-id="fbb34-113">讨论如何使用托管代码绘制矢量和光栅图像。</span><span class="sxs-lookup"><span data-stu-id="fbb34-113">Discusses methods for drawing vector and raster images with managed code.</span></span>  
  
 [<span data-ttu-id="fbb34-114">在 GDI+ 中裁剪和缩放图像</span><span class="sxs-lookup"><span data-stu-id="fbb34-114">Cropping and Scaling Images in GDI+</span></span>](../../../../docs/framework/winforms/advanced/cropping-and-scaling-images-in-gdi.md)  
 <span data-ttu-id="fbb34-115">介绍如何使用托管代码剪切和缩放矢量和光栅图像</span><span class="sxs-lookup"><span data-stu-id="fbb34-115">Discusses methods for cropping and scaling vector and raster images with managed code</span></span>  
  
## <a name="reference"></a><span data-ttu-id="fbb34-116">参考</span><span class="sxs-lookup"><span data-stu-id="fbb34-116">Reference</span></span>  
 <xref:System.Drawing.Image>  
 <span data-ttu-id="fbb34-117">对此类进行描述，并提供指向其所有成员的链接。</span><span class="sxs-lookup"><span data-stu-id="fbb34-117">Describes this class and has links to all of its members.</span></span>  
  
 <xref:System.Drawing.Bitmap>  
 <span data-ttu-id="fbb34-118">描述此类并提供指向其所有成员的链接</span><span class="sxs-lookup"><span data-stu-id="fbb34-118">Describes this class and has links to all of its members</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="fbb34-119">相关章节</span><span class="sxs-lookup"><span data-stu-id="fbb34-119">Related Sections</span></span>  
 [<span data-ttu-id="fbb34-120">使用图像、位图、图标和图元文件</span><span class="sxs-lookup"><span data-stu-id="fbb34-120">Working with Images, Bitmaps, Icons, and Metafiles</span></span>](../../../../docs/framework/winforms/advanced/working-with-images-bitmaps-icons-and-metafiles.md)  
 <span data-ttu-id="fbb34-121">包含指向演示如何在应用程序中使用图像的主题的链接。</span><span class="sxs-lookup"><span data-stu-id="fbb34-121">Contains links to topics that demonstrate how to use images in your application.</span></span>
