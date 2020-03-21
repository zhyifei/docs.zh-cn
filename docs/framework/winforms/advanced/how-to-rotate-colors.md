---
title: 如何：旋转颜色
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- colors [Windows Forms], rotating
- examples [Windows Forms], rotating colors
ms.assetid: e2e4c300-159c-4f4a-9b56-103b0f7cbc05
ms.openlocfilehash: 8d2717dd7b819e963126072279b361fda02188bc
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/21/2020
ms.locfileid: "80111330"
---
# <a name="how-to-rotate-colors"></a>如何：旋转颜色
四维色彩空间中的旋转很难可视化。 通过同意固定其中一种颜色组件，我们可以更轻松地可视化旋转。 假设我们同意将 Alpha 组件固定为 1（完全不透明）。 然后，我们可以用红色、绿色和蓝色轴可视化三维颜色空间，如下图所示。  
  
 ![显示红色、绿色和蓝色轴旋转的插图。](./media/how-to-rotate-colors/rotation-red-green-blue-axes.gif)  
  
 颜色可以被视为 3D 空间中的点。 例如，空格中的点 （1， 0， 0） 表示红色，空格中的点 （0， 1， 0） 表示绿色。  
  
 下图显示了在红绿平面中通过 60 度角旋转颜色 （1， 0， 0） 的含义。 与红-绿平面平行的平面上的旋转可视为蓝色轴的旋转。  
  
 ![显示蓝色轴旋转的插图。](./media/how-to-rotate-colors/rotation-about-blue-axis.gif)  
  
 下图演示如何初始化颜色矩阵以对三个坐标轴（红色、绿色、蓝色）执行每个坐标轴的旋转：  
  
 ![初始化颜色矩阵以执行大约三个轴的旋转。](./media/how-to-rotate-colors/rotation-about-three-axes.gif)  
  
## <a name="example"></a>示例  
 下面的示例采用一个全部为一种颜色（1，0，0.6）的图像，并应用 60 度旋转蓝色轴。 旋转角度在与红绿色平面平行的平面中扫出。  
  
 下图显示了左侧的原始图像和右侧的颜色旋转图像：  
  
 ![显示原始图像和颜色旋转图像的插图。](./media/how-to-rotate-colors/original-color-rotated-images.png)  
  
 下图显示了以下代码中执行的颜色旋转的可视化效果：
  
 ![显示颜色旋转可视化的插图。](./media/how-to-rotate-colors/visualization-color-rotation.gif)  
  
 [!code-csharp[System.Drawing.RotateColors#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.RotateColors/CS/Form1.cs#1)]
 [!code-vb[System.Drawing.RotateColors#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.RotateColors/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a>编译代码  
 前面的示例设计用于 Windows 窗体，它需要<xref:System.Windows.Forms.PaintEventArgs>`e`，这是事件处理程序的<xref:System.Windows.Forms.Control.Paint>参数。 替换为`RotationInput.bmp`系统上有效的映像文件名和路径。  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Drawing.Imaging.ColorMatrix>
- <xref:System.Drawing.Imaging.ImageAttributes>
- [Windows 窗体中的图形和绘制](graphics-and-drawing-in-windows-forms.md)
- [对图像重新着色](recoloring-images.md)
