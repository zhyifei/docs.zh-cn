---
title: "位图类型"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- jpeg files
- TIFF files
- gif files
- Graphics Interchange Format
- Joint Photographic Experts Group
- .jpeg files
- .gif files
- graphics [Windows Forms], file formats
- images [Windows Forms], file formats
- Portable Network Graphics
- .bmp files
- EXIF file format
- PNG files
- pictures [Windows Forms], file formats
- Tag Image File Format
- bitmaps [Windows Forms], file format
- Exchangeable Image File
ms.assetid: 6be085a2-2c13-47c8-b80a-c18b32777d8d
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: b33e710e7f57e1a84372dc556d904e32584a75ea
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="types-of-bitmaps"></a>位图类型
位图的像素为单位的矩形数组中指定的每个像素的颜色的位数组。 专用于单个像素的比特数确定可以分配给该像素的颜色数。 例如，如果每个像素都由 4 位，然后给定的像素可以分配 16 种不同颜色之一 (2 ^4 = 16)。 下表显示可以指定数目的 bits 通过分配给表示像素的颜色数的几个示例。  
  
|每像素位数为|可以分配给一个像素的颜色数|  
|--------------------|------------------------------------------------------|  
|1|2^1 = 2|  
|2|2^2 = 4|  
|4|2^4 = 16|  
|8|2^8 = 256|  
|16|2^16 = 65,536|  
|24|2^24 = 16,777,216|  
  
 通常存储位图的磁盘文件包含一个或多个数组中存储信息，如每个像素，每个行中的像素数和行数的比特数的信息块。 此类文件可能还包含颜色表 （有时称为颜色调色板）。 颜色表将位图中的数值映射到特定的颜色。 下图显示以及其位图和颜色表的放大的图像。 每个像素都由 4 位数字，因此没有 2 ^4 = 16 种颜色颜色表中。 表中的每个颜色表示为一个 24 位数字： 8 位用于红色、 绿色，8 位和蓝色的 8 位。 以十六进制 (以 16 为基数) 形式显示数字： A = 10，B = 11，C = 12，D = 13，E = 14，F = 15。  
  
 ![位图示例](../../../../docs/framework/winforms/advanced/media/aboutgdip03-art01.gif "AboutGdip03_Art01")  
  
 查看行 3，5 列的映像中的像素。 在位图中对应的号为 1。 颜色表告诉我们 1 表示的颜色为红色，因此该像素是红色。 位图的顶行中的所有条目都都为 3。 颜色表告诉我们，3 表示蓝色，因此图像的第一行中的所有像素都是蓝色。  
  
> [!NOTE]
>  有些位图存储在自下而上的格式;位图的第一行中的数字对应于映像的底部行中的像素。  
  
 将索引存储到颜色表的位图称为调色板索引位图。 有些位图具有颜色表不需要。 例如，如果位图使用每个像素的 24 位，该位图可以存储在自己的颜色，而不是索引到颜色表。 下图显示而不是使用颜色表存储直接颜色 （24 位 / 像素） 的位图。 该插图还显示相应的映像的放大的视图。 位图中, FFFFFF 表示空白、 FF0000 表示红色、 00FF00 表示绿色，和 0000ff> 表示蓝色。  
  
 ![位图示例](../../../../docs/framework/winforms/advanced/media/aboutgdip03-art02.gif "AboutGdip03_Art02")  
  
## <a name="graphics-file-formats"></a>图形文件格式  
 有许多磁盘文件中保存位图的标准格式。 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]支持的图形文件以下各段中所述的格式。  
  
### <a name="bmp"></a>BMP  
 BMP 是标准 Windows 用来存储独立于设备的和独立于应用程序的图像的格式。 文件头中指定的每个像素 （1、 4、 8、 15、 24、 32 或 64） 对于给定的 BMP 文件的位数。 每个像素的 24 位 BMP 文件很常见。 BMP 文件通常未压缩，并且因此，不是非常适合传输跨 Internet。  
  
### <a name="graphics-interchange-format-gif"></a>图形交换格式 (GIF)  
 GIF 是用于在网页显示图像的通用格式。 Gif 适用于行绘图、 用纯色，块的图片和颜色之间有清晰边界的图片。 Gif 文件被压缩，但压缩进程; 在丢失任何信息解压缩的映像正是与原始对象相同。 可为透明，指定 gif 文件中的一种颜色，以便映像都具有其显示任何 Web 页面的背景色。 可以在一个文件中以形成一个动画的 GIF 存储一系列 GIF 图像。 Gif 存储最多 8 位 / 像素，因此它们限制为 256 种颜色。  
  
### <a name="joint-photographic-experts-group-jpeg"></a>联合摄影专家组 (JPEG)  
 JPEG 是一种非常适用于扫描的照片如自然场景压缩方案。 某些信息会丢失在压缩过程中，但通常丢失是察觉不到人眼。 Jpeg 存储 24 位 / 像素，这样便能够显示超过 16 个颜色。 Jpeg 不支持透明度或动画。  
  
 JPEG 图像中的压缩级别可配置，但更高的压缩级别 （较小的文件） 导致的信息的更多丢失。 20:1 的压缩率通常生成了人眼查找难区分原始的图像。 下图显示 BMP 图像和两个 JPEG 图像压缩从该 BMP 图像。 第一个 JPEG 具有 4:1 的压缩率，第二个 JPEG 具有大约 8:1 的压缩率。  
  
 ![Filetype 示例](../../../../docs/framework/winforms/advanced/media/aboutgdip03-art03.gif "AboutGdip03_Art03")  
  
 不能 JPEG 压缩不适合于线条图形、 纯色，块和清晰边界。 下图显示以及两个 Jpeg 和 GIF BMP。 Jpeg 图像和 GIF 从 BMP 压缩。 压缩率是 4:1 表示 GIF、 4:1 的较小的 JPEG，和较大的 JPEG 8:3。 请注意，GIF 维护着清晰的边界沿行，但 Jpeg 往往会变得模糊边界。  
  
 ![文件类型](../../../../docs/framework/winforms/advanced/media/aboutgdip03-art03a.gif "AboutGdip03_Art03A")  
  
 JPEG 是压缩方案，而不是文件格式。 JPEG 文件交换格式 (JFIF) 是通常用于存储和传输 JPEG 方案根据压缩的图像文件格式。 通过 Web 浏览器显示的 JFIF 文件使用.jpg 扩展名。  
  
### <a name="exchangeable-image-file-exif"></a>可交换图像文件 (EXIF)  
 EXIF 是一种文件格式，用于捕获数字摄像头的照片。 EXIF 文件包含压缩根据 JPEG 规范的映像。 EXIF 文件还包含有关照片的信息 （拍摄日期、 停转速度、 暴露时间等） 和有关照相机 （制造商、 型号和等等） 的信息。  
  
### <a name="portable-network-graphics-png"></a>可移植网络图形 (PNG)  
 PNG 格式保留许多 GIF 格式的优点，但还提供除 GIF 之外的功能。 GIF 文件，如 PNG 文件被压缩且不会丢失的信息。 PNG 文件可以存储 8、 24 个，或 48 位 / 像素和灰度与 1、 2、 4、 8 或 16 位 / 像素的颜色。 与此相反，GIF 文件可以使用仅为 1、 2、 4 或 8 位 / 像素。 PNG 文件还可以存储每个像素，指定该像素的颜色混合使用背景色的程度的 alpha 值。  
  
 PNG 优于 GIF 渐进式内显示图像的能力 （即，因为它显示的图像的更好并更好地近似值到达通过网络连接）。 PNG 文件可以包含伽玛校正和颜色更正信息，因此，可以显示设备的各种上精确地呈现图像。  
  
### <a name="tag-image-file-format-tiff"></a>Tag 图像文件格式 (TIFF)  
 TIFF 是一种灵活且可扩展的格式，支持通过各种平台和图像处理应用程序。 TIFF 文件可以存储使用任意数目的每像素位数为映像，可以使用各种压缩算法。 多个映像可以存储在单个，多个页的 TIFF 文件。 与映像 （扫描仪制造商、 主机、 压缩、 方向、 每个像素，等的样本的类型） 相关的信息可以存储在文件中，并使用标签来排列。 可以扩展 TIFF 格式，根据需要由批准和添加新标签。  
  
## <a name="see-also"></a>另请参阅  
 <xref:System.Drawing.Image?displayProperty=nameWithType>  
 <xref:System.Drawing.Bitmap?displayProperty=nameWithType>  
 <xref:System.Drawing.Imaging.PixelFormat?displayProperty=nameWithType>  
 [图像、位图和图元文件](../../../../docs/framework/winforms/advanced/images-bitmaps-and-metafiles.md)  
 [使用图像、位图、图标和图元文件](../../../../docs/framework/winforms/advanced/working-with-images-bitmaps-icons-and-metafiles.md)
