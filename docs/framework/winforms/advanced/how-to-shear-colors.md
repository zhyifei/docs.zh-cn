---
title: 如何：修剪颜色
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- colors [Windows Forms], transforming with color matrices
- colors [Windows Forms], shearing
ms.assetid: 0a424171-5b8b-45c4-afef-e9720a6c3e22
ms.openlocfilehash: 825e5a90ebb0d9df3b894ce7bd353e917b676939
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79142389"
---
# <a name="how-to-shear-colors"></a>如何：修剪颜色
剪切会增加或减少颜色分量，以与另一种颜色分量成正比。 例如，考虑红色分量增加蓝色分量值一半的转换。 在这样的转换下，颜色（0.2，0.5，1）将成为（0.7，0.5，1）。 新的红色分量为 0.2 = （1/2）（1） = 0.7。  
  
## <a name="example"></a>示例  
 下面的示例从文件 ColorBars4.bmp 构造对象<xref:System.Drawing.Image>。 然后，代码将前一段中描述的剪切变换应用于图像中的每个像素。  
  
 下图显示了左侧的原始图像和右侧的谢线图像：
  
 ![两个正方形，带彩色条纹并排显示原始图像和谢线图像。](./media/how-to-shear-colors/original-image-sheared-image.png)  
  
 下表列出了剪切变换前后四个条形的颜色矢量。  
  
|原始|剪切|  
|--------------|-------------|  
|(0, 0, 1, 1)|(0.5, 0, 1, 1)|  
|(0.5, 1, 0.5, 1)|(0.75, 1, 0.5, 1)|  
|(1, 1, 0, 1)|(1, 1, 0, 1)|  
|(0.4, 0.4, 0.4, 1)|(0.6, 0.4, 0.4, 1)|  
  
 [!code-csharp[System.Drawing.Misc3#9](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.Misc3/CS/Form1.cs#9)]
 [!code-vb[System.Drawing.Misc3#9](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.Misc3/VB/Form1.vb#9)]  
  
## <a name="compiling-the-code"></a>编译代码  
 前面的示例设计用于 Windows 窗体，它需要<xref:System.Windows.Forms.PaintEventArgs>`e`，这是事件处理程序的<xref:System.Windows.Forms.Control.Paint>参数。 替换为`ColorBars.bmp`系统上有效的图像名称和路径。  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Drawing.Imaging.ColorMatrix>
- <xref:System.Drawing.Imaging.ImageAttributes>
- [Windows 窗体中的图形和绘制](graphics-and-drawing-in-windows-forms.md)
- [对图像重新着色](recoloring-images.md)
