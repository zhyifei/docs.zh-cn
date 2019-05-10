---
title: 在托管 GDI+ 中使用图像编码器和解码器
ms.date: 03/30/2017
helpviewer_keywords:
- image encoders [Windows Forms], using
- image decoders [Windows Forms], using
ms.assetid: 0e838ea1-4e7e-4334-b882-ab25df607b8b
ms.openlocfilehash: e56bc20eb55d694d19b25d9e94e5c9d9e3952628
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "64666448"
---
# <a name="using-image-encoders-and-decoders-in-managed-gdi"></a><span data-ttu-id="69dc8-102">在托管 GDI+ 中使用图像编码器和解码器</span><span class="sxs-lookup"><span data-stu-id="69dc8-102">Using Image Encoders and Decoders in Managed GDI+</span></span>
<span data-ttu-id="69dc8-103"><xref:System.Drawing>命名空间提供<xref:System.Drawing.Image>和<xref:System.Drawing.Bitmap>用于存储和操作图像的类。</span><span class="sxs-lookup"><span data-stu-id="69dc8-103">The <xref:System.Drawing> namespace provides the <xref:System.Drawing.Image> and <xref:System.Drawing.Bitmap> classes for storing and manipulating images.</span></span> <span data-ttu-id="69dc8-104">通过使用中的图像编码器[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]，可以将映像从内存写入到磁盘。</span><span class="sxs-lookup"><span data-stu-id="69dc8-104">By using image encoders in [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)], you can write images from memory to disk.</span></span> <span data-ttu-id="69dc8-105">通过使用中的图像解码器[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]，可以将映像从磁盘加载到内存。</span><span class="sxs-lookup"><span data-stu-id="69dc8-105">By using image decoders in [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)], you can load images from disk into memory.</span></span> <span data-ttu-id="69dc8-106">编码器中的数据转换<xref:System.Drawing.Image>或<xref:System.Drawing.Bitmap>到指定的磁盘的文件格式的对象。</span><span class="sxs-lookup"><span data-stu-id="69dc8-106">An encoder translates the data in an <xref:System.Drawing.Image> or <xref:System.Drawing.Bitmap> object into a designated disk file format.</span></span> <span data-ttu-id="69dc8-107">解码器将转换为所需的格式的磁盘文件中的数据<xref:System.Drawing.Image>和<xref:System.Drawing.Bitmap>对象。</span><span class="sxs-lookup"><span data-stu-id="69dc8-107">A decoder translates the data in a disk file to the format required by the <xref:System.Drawing.Image> and <xref:System.Drawing.Bitmap> objects.</span></span>  
  
 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] <span data-ttu-id="69dc8-108">具有内置编码器和解码器支持以下文件类型：</span><span class="sxs-lookup"><span data-stu-id="69dc8-108">has built-in encoders and decoders that support the following file types:</span></span>  
  
- <span data-ttu-id="69dc8-109">BMP</span><span class="sxs-lookup"><span data-stu-id="69dc8-109">BMP</span></span>  
  
- <span data-ttu-id="69dc8-110">GIF</span><span class="sxs-lookup"><span data-stu-id="69dc8-110">GIF</span></span>  
  
- <span data-ttu-id="69dc8-111">JPEG</span><span class="sxs-lookup"><span data-stu-id="69dc8-111">JPEG</span></span>  
  
- <span data-ttu-id="69dc8-112">PNG</span><span class="sxs-lookup"><span data-stu-id="69dc8-112">PNG</span></span>  
  
- <span data-ttu-id="69dc8-113">TIFF</span><span class="sxs-lookup"><span data-stu-id="69dc8-113">TIFF</span></span>  
  
 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] <span data-ttu-id="69dc8-114">此外提供了支持以下文件类型的内置解码器：</span><span class="sxs-lookup"><span data-stu-id="69dc8-114">also has built-in decoders that support the following file types:</span></span>  
  
- <span data-ttu-id="69dc8-115">WMF</span><span class="sxs-lookup"><span data-stu-id="69dc8-115">WMF</span></span>  
  
- <span data-ttu-id="69dc8-116">EMF</span><span class="sxs-lookup"><span data-stu-id="69dc8-116">EMF</span></span>  
  
- <span data-ttu-id="69dc8-117">图标</span><span class="sxs-lookup"><span data-stu-id="69dc8-117">ICON</span></span>  
  
 <span data-ttu-id="69dc8-118">以下主题讨论编码器和解码器中更多详细信息：</span><span class="sxs-lookup"><span data-stu-id="69dc8-118">The following topics discuss encoders and decoders in more detail:</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="69dc8-119">本节内容</span><span class="sxs-lookup"><span data-stu-id="69dc8-119">In This Section</span></span>  
 [<span data-ttu-id="69dc8-120">如何：列出已安装的编码器</span><span class="sxs-lookup"><span data-stu-id="69dc8-120">How to: List Installed Encoders</span></span>](how-to-list-installed-encoders.md)  
 <span data-ttu-id="69dc8-121">介绍了如何列出计算机上可用的编码器。</span><span class="sxs-lookup"><span data-stu-id="69dc8-121">Describes how to list the encoders available on a computer.</span></span>  
  
 [<span data-ttu-id="69dc8-122">如何：列出已安装的解码器</span><span class="sxs-lookup"><span data-stu-id="69dc8-122">How to: List Installed Decoders</span></span>](how-to-list-installed-decoders.md)  
 <span data-ttu-id="69dc8-123">介绍了如何列出计算机上可用解码器。</span><span class="sxs-lookup"><span data-stu-id="69dc8-123">Describes how to list the decoders available on a computer.</span></span>  
  
 [<span data-ttu-id="69dc8-124">如何：确定编码器支持的参数</span><span class="sxs-lookup"><span data-stu-id="69dc8-124">How to: Determine the Parameters Supported by an Encoder</span></span>](how-to-determine-the-parameters-supported-by-an-encoder.md)  
 <span data-ttu-id="69dc8-125">介绍了如何列出<xref:System.Drawing.Imaging.EncoderParameters>编码器支持。</span><span class="sxs-lookup"><span data-stu-id="69dc8-125">Describes how to list the <xref:System.Drawing.Imaging.EncoderParameters> supported by an encoder.</span></span>  
  
 [<span data-ttu-id="69dc8-126">如何：将 BMP 图像转换为 PNG 图像</span><span class="sxs-lookup"><span data-stu-id="69dc8-126">How to: Convert a BMP image to a PNG image</span></span>](how-to-convert-a-bmp-image-to-a-png-image.md)  
 <span data-ttu-id="69dc8-127">介绍如何将图像保存在不同的图像格式。</span><span class="sxs-lookup"><span data-stu-id="69dc8-127">Describes how to save a image in a different image format.</span></span>  
  
 [<span data-ttu-id="69dc8-128">如何：设置 JPEG 压缩级别</span><span class="sxs-lookup"><span data-stu-id="69dc8-128">How to: Set JPEG Compression Level</span></span>](how-to-set-jpeg-compression-level.md)  
 <span data-ttu-id="69dc8-129">介绍如何更改图像的质量级别。</span><span class="sxs-lookup"><span data-stu-id="69dc8-129">Describes how to change the quality level of an image.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="69dc8-130">参考</span><span class="sxs-lookup"><span data-stu-id="69dc8-130">Reference</span></span>  
 <xref:System.Drawing.Image>  
  
 <xref:System.Drawing.Bitmap>  
  
 <xref:System.Drawing.Imaging.ImageCodecInfo>  
  
 <xref:System.Drawing.Imaging.EncoderParameter>  
  
 <xref:System.Drawing.Imaging.Encoder>  
  
## <a name="related-sections"></a><span data-ttu-id="69dc8-131">相关章节</span><span class="sxs-lookup"><span data-stu-id="69dc8-131">Related Sections</span></span>  
 [<span data-ttu-id="69dc8-132">关于 GDI+ 托管代码</span><span class="sxs-lookup"><span data-stu-id="69dc8-132">About GDI+ Managed Code</span></span>](about-gdi-managed-code.md)  
  
 [<span data-ttu-id="69dc8-133">图像、位图和图元文件</span><span class="sxs-lookup"><span data-stu-id="69dc8-133">Images, Bitmaps, and Metafiles</span></span>](images-bitmaps-and-metafiles.md)
