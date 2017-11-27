---
title: "如何：用图像纹理填充形状"
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
- images [Windows Forms], using with brushes
- bitmaps [Windows Forms], using texture
- shapes [Windows Forms], filling with images
ms.assetid: 508da5a6-2433-4d2b-9680-eaeae4e96e3b
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: c20562cade6917a3426fe04861a05c4b6b0bd543
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-fill-a-shape-with-an-image-texture"></a>如何：用图像纹理填充形状
可以通过用纹理填充的闭合的形状<xref:System.Drawing.Image>类和<xref:System.Drawing.TextureBrush>类。  
  
## <a name="example"></a>示例  
 下面的示例填充的映像的椭圆。 代码构造了<xref:System.Drawing.Image>对象，并随后将传递该地址<xref:System.Drawing.Image>对象的自变量作为<xref:System.Drawing.TextureBrush.%23ctor%2A>构造函数。 第三个语句缩放图像，并第四个语句填充椭圆使用的缩放图像的重复副本。  
  
 在下面的代码中，<xref:System.Drawing.TextureBrush.Transform%2A>属性包含它绘制之前应用于映像的转换。 假设原始图像的宽度为 640 像素和 480 像素的高度。 转换将图像缩小到 75 × 75 通过设置水平和垂直缩放值。  
  
> [!NOTE]
>  在下面的示例中，图像大小为 75 × 75，和椭圆大小为 150 × 250 个字符。 由于映像是小于它所填充的椭圆，椭圆平铺与映像。 达到平铺意味着，将重复图像的水平和垂直之前形状的边界。 有关平铺的详细信息，请参阅[如何： 平铺图像的形状](../../../../docs/framework/winforms/advanced/how-to-tile-a-shape-with-an-image.md)。  
  
 [!code-csharp[System.Drawing.UsingABrush#21](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingABrush/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.UsingABrush#21](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingABrush/VB/Class1.vb#21)]  
  
## <a name="compiling-the-code"></a>编译代码  
 前面的示例专用于 Windows 窗体，它需要 <xref:System.Windows.Forms.PaintEventArgs> `e`，后者是 <xref:System.Windows.Forms.Control.Paint> 事件处理程序的参数。  
  
## <a name="see-also"></a>另请参阅  
 [使用画笔填充形状](../../../../docs/framework/winforms/advanced/using-a-brush-to-fill-shapes.md)
