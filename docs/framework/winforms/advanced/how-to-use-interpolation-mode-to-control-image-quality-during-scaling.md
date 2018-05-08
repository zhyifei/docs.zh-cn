---
title: 如何：缩放时使用插值模式控制图像质量
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- interpolation mode [Windows Forms], controlling image quality
- images [Windows Forms], scaling
- images [Windows Forms], controlling quality
ms.assetid: fde9bccf-8aa5-4b0d-ba4b-788740627b02
ms.openlocfilehash: 72a9cb3a19f0d449dcb376a65f1734b79ed61ab9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-use-interpolation-mode-to-control-image-quality-during-scaling"></a>如何：缩放时使用插值模式控制图像质量
内插模式<xref:System.Drawing.Graphics>对象影响方式[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]刻度 （拉伸和收缩） 映像。 <xref:System.Drawing.Drawing2D.InterpolationMode>枚举定义多个内插模式，其中一些都显示在下面的列表：  
  
-   <xref:System.Drawing.Drawing2D.InterpolationMode.NearestNeighbor>  
  
-   <xref:System.Drawing.Drawing2D.InterpolationMode.Bilinear>  
  
-   <xref:System.Drawing.Drawing2D.InterpolationMode.HighQualityBilinear>  
  
-   <xref:System.Drawing.Drawing2D.InterpolationMode.Bicubic>  
  
-   <xref:System.Drawing.Drawing2D.InterpolationMode.HighQualityBicubic>  
  
 拉伸图像，原始映像中的每个像素必须将映射到更大的图像中的像素的组。 若要收缩映像，原始映像中的像素的组必须映射到较小的图像中的单一像素。 执行这些映射的算法的有效性确定缩放图像的质量。 生成更高质量缩放的图像的算法往往需要进行更多的处理时间。 在前面的列表中，<xref:System.Drawing.Drawing2D.InterpolationMode.NearestNeighbor>是最低质量模式和<xref:System.Drawing.Drawing2D.InterpolationMode.HighQualityBicubic>最高质量的方式。  
  
 若要设置的插补模式，分配的成员之一<xref:System.Drawing.Drawing2D.InterpolationMode>枚举<xref:System.Drawing.Graphics.InterpolationMode%2A>属性<xref:System.Drawing.Graphics>对象。  
  
## <a name="example"></a>示例  
 下面的示例绘制图像，然后收缩具有三种不同内插模式的映像。  
  
 下图显示原始图像和三个较小的图像。  
  
 ![具有各种内插设置的图像](../../../../docs/framework/winforms/advanced/media/csgrapes1.png "csgrapes1")  
  
 [!code-csharp[System.Drawing.WorkingWithImages#81](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#81)]
 [!code-vb[System.Drawing.WorkingWithImages#81](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#81)]  
  
## <a name="compiling-the-code"></a>编译代码  
 前面的示例专用于 Windows 窗体，它需要 <xref:System.Windows.Forms.PaintEventArgs> `e`，后者是 <xref:System.Windows.Forms.Control.Paint> 事件处理程序的参数。  
  
## <a name="see-also"></a>请参阅  
 [图像、位图和图元文件](../../../../docs/framework/winforms/advanced/images-bitmaps-and-metafiles.md)  
 [使用图像、位图、图标和图元文件](../../../../docs/framework/winforms/advanced/working-with-images-bitmaps-icons-and-metafiles.md)
