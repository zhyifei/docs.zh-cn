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
# <a name="using-image-encoders-and-decoders-in-managed-gdi"></a>在托管 GDI+ 中使用图像编码器和解码器
<xref:System.Drawing>命名空间提供<xref:System.Drawing.Image>和<xref:System.Drawing.Bitmap>类用于存储和操作图像。 通过使用中的图像编码器[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]，你可以将映像从内存写入到磁盘。 通过使用中的图像解码器[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]，可以将映像从磁盘加载到内存。 编码器中的数据转换<xref:System.Drawing.Image>或<xref:System.Drawing.Bitmap>为指定的磁盘文件格式的对象。 解码器中的磁盘文件，以便所需的格式的数据转换<xref:System.Drawing.Image>和<xref:System.Drawing.Bitmap>对象。  
  
 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]具有内置编码器和解码器支持以下文件类型：  
  
-   BMP  
  
-   GIF  
  
-   JPEG  
  
-   PNG  
  
-   TIFF  
  
 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]此外具有内置的解码器支持以下文件类型：  
  
-   WMF  
  
-   EMF  
  
-   图标  
  
 以下主题讨论编码器和解码器中更多详细信息：  
  
## <a name="in-this-section"></a>本节内容  
 [如何：列出已安装的编码器](../../../../docs/framework/winforms/advanced/how-to-list-installed-encoders.md)  
 说明如何列出计算机上可用的编码器。  
  
 [如何：列出已安装的解码器](../../../../docs/framework/winforms/advanced/how-to-list-installed-decoders.md)  
 说明如何列出计算机上可用的解码器。  
  
 [如何：确定编码器支持的参数](../../../../docs/framework/winforms/advanced/how-to-determine-the-parameters-supported-by-an-encoder.md)  
 说明如何列出<xref:System.Drawing.Imaging.EncoderParameters>编码器支持。  
  
 [如何：将 BMP 图像转换成 PNG 图像](../../../../docs/framework/winforms/advanced/how-to-convert-a-bmp-image-to-a-png-image.md)  
 描述如何用不同的图像格式保存图像。  
  
 [如何：设置 JPEG 压缩级别](../../../../docs/framework/winforms/advanced/how-to-set-jpeg-compression-level.md)  
 描述如何更改图像的质量级别。  
  
## <a name="reference"></a>参考  
 <xref:System.Drawing.Image>  
  
 <xref:System.Drawing.Bitmap>  
  
 <xref:System.Drawing.Imaging.ImageCodecInfo>  
  
 <xref:System.Drawing.Imaging.EncoderParameter>  
  
 <xref:System.Drawing.Imaging.Encoder>  
  
## <a name="related-sections"></a>相关章节  
 [关于 GDI+ 托管代码](../../../../docs/framework/winforms/advanced/about-gdi-managed-code.md)  
  
 [图像、位图和图元文件](../../../../docs/framework/winforms/advanced/images-bitmaps-and-metafiles.md)
