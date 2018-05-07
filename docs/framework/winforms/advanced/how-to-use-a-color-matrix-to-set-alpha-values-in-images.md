---
title: 如何：使用颜色矩阵设置图像中的 Alpha 值
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- images [Windows Forms], using color matrices for semi-transparent
- transparency [Windows Forms], color matrices
- matrices [Windows Forms], alpha values
- bitmaps [Windows Forms], using color matrices for semi-transparent
ms.assetid: a27121e6-f7e9-4c09-84e2-f05aa9d2a1bb
ms.openlocfilehash: ed129cd9487ba1416cd69b2e13f59747856cb598
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-use-a-color-matrix-to-set-alpha-values-in-images"></a>如何：使用颜色矩阵设置图像中的 Alpha 值
<xref:System.Drawing.Bitmap>类 (其继承自<xref:System.Drawing.Image>类) 和<xref:System.Drawing.Imaging.ImageAttributes>类提供用于获取和设置像素值的功能。 你可以使用<xref:System.Drawing.Imaging.ImageAttributes>类来修改 alpha 值整个图像，也可以调用<xref:System.Drawing.Bitmap.SetPixel%2A>方法<xref:System.Drawing.Bitmap>类来修改单个像素的值。  
  
## <a name="example"></a>示例  
 <xref:System.Drawing.Imaging.ImageAttributes>类具有许多可用于在呈现过程中修改映像的属性。 在下面的示例中，<xref:System.Drawing.Imaging.ImageAttributes>对象用于将所有 alpha 值设置为它们的 80%。 这是通过初始化颜色矩阵和设置的 alpha 缩放为 0.8 矩阵中的值。 颜色矩阵的地址传递给<xref:System.Drawing.Imaging.ImageAttributes.SetColorMatrix%2A>方法<xref:System.Drawing.Imaging.ImageAttributes>对象，与<xref:System.Drawing.Imaging.ImageAttributes>对象传递给<xref:System.Drawing.Graphics.DrawString%2A>方法<xref:System.Drawing.Graphics>对象。  
  
 呈现过程中，在位图中的 alpha 值将转换为它们的 80%。 这会导致混合和背景的图像。 如下图所示，位图图像外观透明的;你可以看到通过它黑色实线。  
  
 ![使用矩阵的 alpha 混合](../../../../docs/framework/winforms/advanced/media/image2.png "image2")  
  
 当图像位于白色背景的部分之上，具有已与白色混合映像。 映像相交黑色的行中，图像与黑色混合。  
  
 [!code-csharp[System.Drawing.AlphaBlending#21](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlphaBlending/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.AlphaBlending#21](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlphaBlending/VB/Class1.vb#21)]  
  
## <a name="compiling-the-code"></a>编译代码  
 前面的示例专用于 Windows 窗体，并且它需要<xref:System.Windows.Forms.PaintEventArgs> `e`，这是一个参数的<xref:System.Windows.Forms.PaintEventHandler>。  
  
## <a name="see-also"></a>请参阅  
 [Windows 窗体中的图形和绘制](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)  
 [alpha 值混合处理直线和填充](../../../../docs/framework/winforms/advanced/alpha-blending-lines-and-fills.md)
