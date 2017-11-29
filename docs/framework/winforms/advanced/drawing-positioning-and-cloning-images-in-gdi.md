---
title: "在 GDI+ 中绘制、定位和克隆图像"
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
- raster images [Windows Forms]
- images [Windows Forms], positioning
- drawing [Windows Forms], images
- drawing [Windows Forms], raster images
- images [Windows Forms], cloning
- images [Windows Forms], drawing
- GDI+, drawing images
- GDI+, cloning images
- GDI+, positioning images
ms.assetid: 09f0c07a-19c0-43b4-90a2-862a10545ce8
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: a3ba716a36280d2ac08dae907abbdbe05e563dfc
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="drawing-positioning-and-cloning-images-in-gdi"></a>在 GDI+ 中绘制、定位和克隆图像
你可以使用<xref:System.Drawing.Bitmap>类来加载和显示光栅图像，并且你可以使用<xref:System.Drawing.Imaging.Metafile>类来加载和显示矢量图像。 <xref:System.Drawing.Bitmap>和<xref:System.Drawing.Imaging.Metafile>类都继承自<xref:System.Drawing.Image>类。 若要显示矢量图像，你需要的实例<xref:System.Drawing.Graphics>类和一个<xref:System.Drawing.Imaging.Metafile>。 若要显示为光栅图像，你需要的实例<xref:System.Drawing.Graphics>类和一个<xref:System.Drawing.Bitmap>。 实例<xref:System.Drawing.Graphics>类提供<xref:System.Drawing.Graphics.DrawImage%2A>方法，用于接收<xref:System.Drawing.Imaging.Metafile>或<xref:System.Drawing.Bitmap>作为自变量。  
  
## <a name="file-types-and-cloning"></a>文件类型和克隆  
 下面的代码示例显示如何构造<xref:System.Drawing.Bitmap>从文件 Climber.jpg 并显示位图。 图像的左上角的目标点 （10，10），第二个和第三个参数中指定。  
  
 [!code-csharp[System.Drawing.ImagesBitmapsMetafiles#11](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.ImagesBitmapsMetafiles#11](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/VB/Class1.vb#11)]  
  
 下图显示图像。  
  
 ![图像示例](../../../../docs/framework/winforms/advanced/media/aboutgdip03-art04.gif "AboutGdip03_Art04")  
  
 您可以构造<xref:System.Drawing.Bitmap>使用不同的图形对象文件格式： BMP、 GIF、 JPEG、 EXIF、 PNG、 TIFF 和图标。  
  
 下面的代码示例显示如何构造<xref:System.Drawing.Bitmap>来自各种文件类型的对象，然后显示位图。  
  
 [!code-csharp[System.Drawing.ImagesBitmapsMetafiles#12](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/CS/Class1.cs#12)]
 [!code-vb[System.Drawing.ImagesBitmapsMetafiles#12](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/VB/Class1.vb#12)]  
  
 <xref:System.Drawing.Bitmap>类提供<xref:System.Drawing.Bitmap.Clone%2A>可以使用现有的副本的方法<xref:System.Drawing.Bitmap>。 <xref:System.Drawing.Bitmap.Clone%2A>方法有一个可用于指定你想要复制的原始位图的部分的源矩形参数。 下面的代码示例演示如何创建<xref:System.Drawing.Bitmap>通过克隆现有的上半<xref:System.Drawing.Bitmap>。 然后绘制这两个映像。  
  
 [!code-csharp[System.Drawing.ImagesBitmapsMetafiles#13](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/CS/Class1.cs#13)]
 [!code-vb[System.Drawing.ImagesBitmapsMetafiles#13](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/VB/Class1.vb#13)]  
  
 下图显示两个映像。  
  
 ![裁剪](../../../../docs/framework/winforms/advanced/media/aboutgdip03-art05.gif "AboutGdip03_Art05")  
  
## <a name="see-also"></a>另请参阅  
 [图像、位图和图元文件](../../../../docs/framework/winforms/advanced/images-bitmaps-and-metafiles.md)  
 [如何：创建用于绘制的图形对象](../../../../docs/framework/winforms/advanced/how-to-create-graphics-objects-for-drawing.md)  
 [使用图像、位图、图标和图元文件](../../../../docs/framework/winforms/advanced/working-with-images-bitmaps-icons-and-metafiles.md)
