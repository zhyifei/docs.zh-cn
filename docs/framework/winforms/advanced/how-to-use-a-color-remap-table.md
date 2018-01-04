---
title: "如何：使用颜色重新映射表"
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
- color tables [Windows Forms], remapping colors with
- custom colors [Windows Forms], creating with color remap table
- color remap tables [Windows Forms], using
ms.assetid: 977df1ce-8665-42d4-9fb1-ef7f0ff63419
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 6e208aa9c98c1ca19baee83760cfd0f75972ecfa
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-use-a-color-remap-table"></a>如何：使用颜色重新映射表
重新映射是将转换在映像中颜色重新映射表根据颜色的过程。 颜色重新映射表是一个数组<xref:System.Drawing.Imaging.ColorMap>对象。 每个<xref:System.Drawing.Imaging.ColorMap>数组中的对象具有<xref:System.Drawing.Imaging.ColorMap.OldColor%2A>属性和<xref:System.Drawing.Imaging.ColorMap.NewColor%2A>属性。  
  
 当[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]绘制图像，图像的每个像素相比的旧颜色数组。 如果像素的颜色与旧颜色相匹配，则会将其颜色更改为相应的新颜色。 仅对呈现更改的颜色，图像本身的颜色值 (存储在<xref:System.Drawing.Image>或<xref:System.Drawing.Bitmap>对象) 将不会更改。  
  
 若要绘制变换后的图像，初始化的数组<xref:System.Drawing.Imaging.ColorMap>对象。 传递到该数组<xref:System.Drawing.Imaging.ImageAttributes.SetRemapTable%2A>方法<xref:System.Drawing.Imaging.ImageAttributes>对象，并将然后传递<xref:System.Drawing.Imaging.ImageAttributes>对象传递给<xref:System.Drawing.Graphics.DrawImage%2A>方法<xref:System.Drawing.Graphics>对象。  
  
## <a name="example"></a>示例  
 下面的示例创建<xref:System.Drawing.Image>从文件 RemapInput.bmp 的对象。 该代码创建包含单个颜色重新映射表<xref:System.Drawing.Imaging.ColorMap>对象。 <xref:System.Drawing.Imaging.ColorMap.OldColor%2A>属性`ColorRemap`对象为红色，和<xref:System.Drawing.Imaging.ColorMap.NewColor%2A>属性为蓝色。 该映像已绘制一次，而无需重新映射和一次使用重新映射。 重映射过程更改所有红色的像素为单位，为蓝色。  
  
 下图右侧显示在左侧的原始映像和变换后的图像。  
  
 ![颜色重新映射](../../../../docs/framework/winforms/advanced/media/colortrans7.png "colortrans7")  
  
 [!code-csharp[System.Drawing.RecoloringImages#31](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.RecoloringImages/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.RecoloringImages#31](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.RecoloringImages/VB/Class1.vb#31)]  
  
## <a name="compiling-the-code"></a>编译代码  
 前面的示例专用于 Windows 窗体，并且它需要<xref:System.Windows.Forms.PaintEventArgs> `e`，这是一个参数的<xref:System.Windows.Forms.Control.Paint>事件处理程序。  
  
## <a name="see-also"></a>请参阅  
 [对图像重新着色](../../../../docs/framework/winforms/advanced/recoloring-images.md)  
 [图像、位图和图元文件](../../../../docs/framework/winforms/advanced/images-bitmaps-and-metafiles.md)
