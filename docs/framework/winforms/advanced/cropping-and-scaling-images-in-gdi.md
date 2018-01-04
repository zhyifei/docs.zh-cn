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
# <a name="cropping-and-scaling-images-in-gdi"></a>在 GDI+ 中裁切和缩放图像
你可以使用<xref:System.Drawing.Graphics.DrawImage%2A>方法<xref:System.Drawing.Graphics>类可以绘制和位置矢量图像和光栅图像。 <xref:System.Drawing.Graphics.DrawImage%2A>是重载的方法，因此有几种方法，你可以向其提供自变量。  
  
## <a name="drawimage-variations"></a>DrawImage 变体  
 一个变体<xref:System.Drawing.Graphics.DrawImage%2A>方法接收<xref:System.Drawing.Bitmap>和<xref:System.Drawing.Rectangle>。 矩形指定绘制操作; 的目标也就是说，它指定在其中绘制图像的矩形。 如果目标矩形的大小不同于原始图像的大小，缩放图像以适合目标矩形。 下面的代码示例演示如何将同一图像绘制三次： 一次没有缩放、 使用扩展，一次，并且一次使用压缩：  
  
 [!code-csharp[System.Drawing.ImagesBitmapsMetafiles#31](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.ImagesBitmapsMetafiles#31](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/VB/Class1.vb#31)]  
  
 下图显示三个图片。  
  
 ![缩放](../../../../docs/framework/winforms/advanced/media/aboutgdip03-art06.gif "AboutGdip03_Art06")  
  
 某些变体<xref:System.Drawing.Graphics.DrawImage%2A>方法有源矩形参数，以及目标矩形参数。 源矩形参数指定要绘制的原始图像的部分。 目标矩形指定要在其中绘制图像的该部分的矩形。 如果目标矩形的大小不同于源矩形的大小，图进行缩放以适合目标矩形。  
  
 下面的代码示例显示如何构造<xref:System.Drawing.Bitmap>从 Runner.jpg 的文件。 在无缩放绘制整个图像 （0，0）。 然后两次绘制图像的一小部分： 一次使用压缩，一次使用扩展。  
  
 [!code-csharp[System.Drawing.ImagesBitmapsMetafiles#32](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/CS/Class1.cs#32)]
 [!code-vb[System.Drawing.ImagesBitmapsMetafiles#32](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/VB/Class1.vb#32)]  
  
 下图显示未缩放的图像和压缩和扩展的图像部分。  
  
 ![剪切和缩放](../../../../docs/framework/winforms/advanced/media/aboutgdip03-art07.gif "AboutGdip03_Art07")  
  
## <a name="see-also"></a>请参阅  
 [图像、位图和图元文件](../../../../docs/framework/winforms/advanced/images-bitmaps-and-metafiles.md)  
 [使用图像、位图、图标和图元文件](../../../../docs/framework/winforms/advanced/working-with-images-bitmaps-icons-and-metafiles.md)
