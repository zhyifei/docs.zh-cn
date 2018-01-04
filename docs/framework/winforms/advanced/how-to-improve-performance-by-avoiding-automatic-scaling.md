---
title: "如何：通过避免自动缩放改善性能"
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
- automatic scaling
- images [Windows Forms], improving performance
- images [Windows Forms], using without automatic scaling
- performance [Windows Forms], improving image
ms.assetid: 5fe2c95d-8653-4d55-bf0d-e5afa28f223b
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 1f49fc4b1e59879b9ecc67295610187fa2e5e80d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-improve-performance-by-avoiding-automatic-scaling"></a>如何：通过避免自动缩放改善性能
[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]在绘制时，这会降低性能，可能自动缩放图像。 或者，你可以控制将传递到目标矩形的尺寸缩放图像<xref:System.Drawing.Graphics.DrawImage%2A>方法。  
  
 例如，以下调用<xref:System.Drawing.Graphics.DrawImage%2A>方法指定的左上角 （50、 30），但未指定目标矩形。  
  
 [!code-csharp[System.Drawing.WorkingWithImages#31](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.WorkingWithImages#31](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#31)]  
  
 尽管这是最简单版本<xref:System.Drawing.Graphics.DrawImage%2A>方法按照的所需的参数的数量，它不一定最有效。 如果使用的分辨率[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]（通常每英寸 96 点） 不同于中存储的分辨率<xref:System.Drawing.Image>对象，则<xref:System.Drawing.Graphics.DrawImage%2A>方法将缩放该图像。 例如，假设<xref:System.Drawing.Image>对象还具有为 216 像素宽度和存储的水平分辨率值的每英寸点数为 72。 因为 216/72 为 3，<xref:System.Drawing.Graphics.DrawImage%2A>将图像缩放，使其宽度为 3 英寸分辨率为每英寸 96 点。 也就是说，<xref:System.Drawing.Graphics.DrawImage%2A>将显示的宽度为 96 x 3 = 288 图像像素。  
  
 即使您的屏幕分辨率是不同的每英寸 96 点[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]将可能缩放该图像的屏幕分辨率好像每英寸 96 点。 这是因为[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]<xref:System.Drawing.Graphics>对象所关联的设备上下文，以及何时[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]屏幕分辨率，结果的设备上下文通常为 96，而不考虑实际屏幕分辨率的查询。 你可以避免通过指定目标矩形中的自动缩放<xref:System.Drawing.Graphics.DrawImage%2A>方法。  
  
## <a name="example"></a>示例  
 下面的示例绘制两次相同的映像。 在第一种情况下，未指定的宽度和目标矩形的高度，并将图像进行自动缩放。 在第二个情况下，指定的宽度和高度 （以像素为单位） 的目标矩形的宽度和高度的原始图像是相同。 下图显示两次呈现的图像。  
  
 ![缩放纹理](../../../../docs/framework/winforms/advanced/media/csscaledtexture1.png "csscaledtexture1")  
  
 [!code-csharp[System.Drawing.WorkingWithImages#32](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#32)]
 [!code-vb[System.Drawing.WorkingWithImages#32](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#32)]  
  
## <a name="compiling-the-code"></a>编译代码  
 前面的示例专用于 Windows 窗体，它需要 <xref:System.Windows.Forms.PaintEventArgs> `e`，后者是 <xref:System.Windows.Forms.Control.Paint> 事件处理程序的参数。 Texture.jpg 替换的映像名称和你系统有效的路径。  
  
## <a name="see-also"></a>请参阅  
 [图像、位图和图元文件](../../../../docs/framework/winforms/advanced/images-bitmaps-and-metafiles.md)  
 [使用图像、位图、图标和图元文件](../../../../docs/framework/winforms/advanced/working-with-images-bitmaps-icons-and-metafiles.md)
