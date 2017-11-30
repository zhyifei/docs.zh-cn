---
title: "在托管 GDI+ 中使用图像编码器和解码器"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- image encoders [Windows Forms], using
- image decoders [Windows Forms], using
ms.assetid: 0e838ea1-4e7e-4334-b882-ab25df607b8b
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 64384e3c283b6596e36d5b2bd583a304faf080b4
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/22/2017
---
# <a name="using-image-encoders-and-decoders-in-managed-gdi"></a><span data-ttu-id="2daff-102">在托管 GDI+ 中使用图像编码器和解码器</span><span class="sxs-lookup"><span data-stu-id="2daff-102">Using Image Encoders and Decoders in Managed GDI+</span></span>
<span data-ttu-id="2daff-103"><xref:System.Drawing>命名空间提供<xref:System.Drawing.Image>和<xref:System.Drawing.Bitmap>类用于存储和操作图像。</span><span class="sxs-lookup"><span data-stu-id="2daff-103">The <xref:System.Drawing> namespace provides the <xref:System.Drawing.Image> and <xref:System.Drawing.Bitmap> classes for storing and manipulating images.</span></span> <span data-ttu-id="2daff-104">通过使用中的图像编码器[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]，你可以将映像从内存写入到磁盘。</span><span class="sxs-lookup"><span data-stu-id="2daff-104">By using image encoders in [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)], you can write images from memory to disk.</span></span> <span data-ttu-id="2daff-105">通过使用中的图像解码器[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]，可以将映像从磁盘加载到内存。</span><span class="sxs-lookup"><span data-stu-id="2daff-105">By using image decoders in [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)], you can load images from disk into memory.</span></span> <span data-ttu-id="2daff-106">编码器中的数据转换<xref:System.Drawing.Image>或<xref:System.Drawing.Bitmap>为指定的磁盘文件格式的对象。</span><span class="sxs-lookup"><span data-stu-id="2daff-106">An encoder translates the data in an <xref:System.Drawing.Image> or <xref:System.Drawing.Bitmap> object into a designated disk file format.</span></span> <span data-ttu-id="2daff-107">解码器中的磁盘文件，以便所需的格式的数据转换<xref:System.Drawing.Image>和<xref:System.Drawing.Bitmap>对象。</span><span class="sxs-lookup"><span data-stu-id="2daff-107">A decoder translates the data in a disk file to the format required by the <xref:System.Drawing.Image> and <xref:System.Drawing.Bitmap> objects.</span></span>  
  
 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]<span data-ttu-id="2daff-108">具有内置编码器和解码器支持以下文件类型：</span><span class="sxs-lookup"><span data-stu-id="2daff-108"> has built-in encoders and decoders that support the following file types:</span></span>  
  
-   <span data-ttu-id="2daff-109">BMP</span><span class="sxs-lookup"><span data-stu-id="2daff-109">BMP</span></span>  
  
-   <span data-ttu-id="2daff-110">GIF</span><span class="sxs-lookup"><span data-stu-id="2daff-110">GIF</span></span>  
  
-   <span data-ttu-id="2daff-111">JPEG</span><span class="sxs-lookup"><span data-stu-id="2daff-111">JPEG</span></span>  
  
-   <span data-ttu-id="2daff-112">PNG</span><span class="sxs-lookup"><span data-stu-id="2daff-112">PNG</span></span>  
  
-   <span data-ttu-id="2daff-113">TIFF</span><span class="sxs-lookup"><span data-stu-id="2daff-113">TIFF</span></span>  
  
 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]<span data-ttu-id="2daff-114">此外具有内置的解码器支持以下文件类型：</span><span class="sxs-lookup"><span data-stu-id="2daff-114"> also has built-in decoders that support the following file types:</span></span>  
  
-   <span data-ttu-id="2daff-115">WMF</span><span class="sxs-lookup"><span data-stu-id="2daff-115">WMF</span></span>  
  
-   <span data-ttu-id="2daff-116">EMF</span><span class="sxs-lookup"><span data-stu-id="2daff-116">EMF</span></span>  
  
-   <span data-ttu-id="2daff-117">图标</span><span class="sxs-lookup"><span data-stu-id="2daff-117">ICON</span></span>  
  
 <span data-ttu-id="2daff-118">以下主题讨论编码器和解码器中更多详细信息：</span><span class="sxs-lookup"><span data-stu-id="2daff-118">The following topics discuss encoders and decoders in more detail:</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="2daff-119">本节内容</span><span class="sxs-lookup"><span data-stu-id="2daff-119">In This Section</span></span>  
 [<span data-ttu-id="2daff-120">如何：列出已安装的编码器</span><span class="sxs-lookup"><span data-stu-id="2daff-120">How to: List Installed Encoders</span></span>](../../../../docs/framework/winforms/advanced/how-to-list-installed-encoders.md)  
 <span data-ttu-id="2daff-121">说明如何列出计算机上可用的编码器。</span><span class="sxs-lookup"><span data-stu-id="2daff-121">Describes how to list the encoders available on a computer.</span></span>  
  
 [<span data-ttu-id="2daff-122">如何：列出已安装的解码器</span><span class="sxs-lookup"><span data-stu-id="2daff-122">How to: List Installed Decoders</span></span>](../../../../docs/framework/winforms/advanced/how-to-list-installed-decoders.md)  
 <span data-ttu-id="2daff-123">说明如何列出计算机上可用的解码器。</span><span class="sxs-lookup"><span data-stu-id="2daff-123">Describes how to list the decoders available on a computer.</span></span>  
  
 [<span data-ttu-id="2daff-124">如何：确定编码器支持的参数</span><span class="sxs-lookup"><span data-stu-id="2daff-124">How to: Determine the Parameters Supported by an Encoder</span></span>](../../../../docs/framework/winforms/advanced/how-to-determine-the-parameters-supported-by-an-encoder.md)  
 <span data-ttu-id="2daff-125">说明如何列出<xref:System.Drawing.Imaging.EncoderParameters>编码器支持。</span><span class="sxs-lookup"><span data-stu-id="2daff-125">Describes how to list the <xref:System.Drawing.Imaging.EncoderParameters> supported by an encoder.</span></span>  
  
 [<span data-ttu-id="2daff-126">如何：将 BMP 图像转换成 PNG 图像</span><span class="sxs-lookup"><span data-stu-id="2daff-126">How to: Convert a BMP image to a PNG image</span></span>](../../../../docs/framework/winforms/advanced/how-to-convert-a-bmp-image-to-a-png-image.md)  
 <span data-ttu-id="2daff-127">描述如何用不同的图像格式保存图像。</span><span class="sxs-lookup"><span data-stu-id="2daff-127">Describes how to save a image in a different image format.</span></span>  
  
 [<span data-ttu-id="2daff-128">如何：设置 JPEG 压缩级别</span><span class="sxs-lookup"><span data-stu-id="2daff-128">How to: Set JPEG Compression Level</span></span>](../../../../docs/framework/winforms/advanced/how-to-set-jpeg-compression-level.md)  
 <span data-ttu-id="2daff-129">描述如何更改图像的质量级别。</span><span class="sxs-lookup"><span data-stu-id="2daff-129">Describes how to change the quality level of an image.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="2daff-130">参考</span><span class="sxs-lookup"><span data-stu-id="2daff-130">Reference</span></span>  
 <xref:System.Drawing.Image>  
  
 <xref:System.Drawing.Bitmap>  
  
 <xref:System.Drawing.Imaging.ImageCodecInfo>  
  
 <xref:System.Drawing.Imaging.EncoderParameter>  
  
 <xref:System.Drawing.Imaging.Encoder>  
  
## <a name="related-sections"></a><span data-ttu-id="2daff-131">相关章节</span><span class="sxs-lookup"><span data-stu-id="2daff-131">Related Sections</span></span>  
 [<span data-ttu-id="2daff-132">关于 GDI+ 托管代码</span><span class="sxs-lookup"><span data-stu-id="2daff-132">About GDI+ Managed Code</span></span>](../../../../docs/framework/winforms/advanced/about-gdi-managed-code.md)  
  
 [<span data-ttu-id="2daff-133">图像、位图和图元文件</span><span class="sxs-lookup"><span data-stu-id="2daff-133">Images, Bitmaps, and Metafiles</span></span>](../../../../docs/framework/winforms/advanced/images-bitmaps-and-metafiles.md)
