---
title: 使用渐变画笔填充形状
ms.date: 03/30/2017
helpviewer_keywords:
- brushes [Windows Forms], gradient brushes
- gradient brushes
- examples [Windows Forms], gradient brushes
ms.assetid: 2c6037b9-05bd-44c0-a22a-19584b722524
ms.openlocfilehash: 857a9276a731ae5e69b3caa1a639d1315aba9901
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33525029"
---
# <a name="using-a-gradient-brush-to-fill-shapes"></a>使用渐变画笔填充形状
渐变画笔用于填充形状的渐变的颜色。 例如，水平渐变可用于填充形状的右边缘移动距左边缘的形状时逐渐改变的颜色。 设想这样一个矩形的左边缘为黑色 （0，0，0，则表示由红色、 绿色和蓝色组件） 和右边缘，即红色 （表示 255，0，0）。 如果矩形为 256 像素宽，给定像素的红色组件将一个大于其左侧像素的红色组件。 行中的最左侧像素的颜色分量为 （0，0，0），第二个像素 （1，0，0），第三个像素都有 （2，0，0），依此类推，直到你到达最右边的像素，它具有颜色组件 （255，0，0）。 这些相比内, 插的颜色值构成的颜色渐变。  
  
 线性渐变颜色更改，当您移动水平、 垂直或并行到指定的斜线。 路径渐变更改颜色，随着有关内部和路径的边界。 你可以自定义路径渐变以获得各种效果。  
  
 下图显示使用线性渐变画笔填充的矩形和椭圆填入路径渐变画笔。  
  
 ![渐变](../../../../docs/framework/winforms/advanced/media/gradient2.png "gradient2")  
  
## <a name="in-this-section"></a>本节内容  
 [如何：创建线性渐变](../../../../docs/framework/winforms/advanced/how-to-create-a-linear-gradient.md)  
 演示如何创建线性渐变 using<xref:System.Drawing.Drawing2D.LinearGradientBrush>类。  
  
 [如何：创建路径渐变](../../../../docs/framework/winforms/advanced/how-to-create-a-path-gradient.md)  
 描述如何创建路径渐变 using<xref:System.Drawing.Drawing2D.PathGradientBrush>类。  
  
 [如何：对渐变应用 gamma 矫正](../../../../docs/framework/winforms/advanced/how-to-apply-gamma-correction-to-a-gradient.md)  
 说明如何使用渐变画笔的灰度校正。  
  
## <a name="reference"></a>参考  
 <xref:System.Drawing.Drawing2D.LinearGradientBrush?displayProperty=nameWithType>  
 包含此类的说明，并提供指向其所有成员。  
  
 <xref:System.Drawing.Drawing2D.PathGradientBrush?displayProperty=nameWithType>  
 包含此类的说明，并提供指向其所有成员。
