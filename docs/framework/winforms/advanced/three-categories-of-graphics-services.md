---
title: 图形服务的三个类别
ms.date: 03/30/2017
helpviewer_keywords:
- imaging
- graphics [Windows Forms], categories
- 2D vector graphics
- vector graphics
- typography
ms.assetid: 068c0ef3-f6ee-4d58-a7b6-eb2531ead408
ms.openlocfilehash: b0f2ad8293daf6ad53899a0f8be82985c24ff50d
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/21/2020
ms.locfileid: "80111200"
---
# <a name="three-categories-of-graphics-services"></a>图形服务的三个类别
Windows 窗体中的图形产品分为以下三大类：  
  
- 二维 （二-D） 矢量图形  
  
- 映像  
  
- 版式  
  
## <a name="2d-vector-graphics"></a>2D 矢量图形  
 二维矢量图形是基元图形;如直线、曲线和图形;由坐标系上的点集指定。 例如，直线由其两个端点指定，矩形由一个点指定，该点给出其左上角的位置，以及一对表示其宽度和高度的数字。 简单路径由由直线连接的点数组指定。 贝塞尔样条线是由四个控制点指定的复杂曲线。  
  
 GDI+ 提供类和结构，这些类和结构存储有关基元本身的信息、存储有关基元绘制方式的信息的类以及实际执行绘图的类。 例如，结构存储<xref:System.Drawing.Rectangle>矩形的位置和大小;例如，该结构存储矩形的位置和大小。类<xref:System.Drawing.Pen>存储有关线颜色、线宽和线样式的信息;<xref:System.Drawing.Graphics>类具有绘制线条、矩形、路径和其他图形的方法。 还有几个<xref:System.Drawing.Brush>类存储有关如何用颜色或图案填充闭合的数字和路径的信息。  
  
 您可以在元文件中记录矢量图像（即图形命令序列）。 GDI+ 提供<xref:System.Drawing.Imaging.Metafile>用于录制、显示和保存元文件的类。 使用<xref:System.Drawing.Imaging.MetafileHeader>和<xref:System.Drawing.Imaging.MetaHeader>类，可以检查存储在元文件标头中的数据。  
  
## <a name="imaging"></a>映像  
 使用矢量图形技术很难或不可能显示某些类型的图片。 例如，工具栏按钮上的图片和显示为图标的图片很难指定为线条和曲线的集合。 使用矢量技术，制作拥挤的棒球场的高分辨率数字照片就更加困难了。 此类型的图像存储为位图，即表示屏幕上单个点颜色的数字数组。 GDI+ 提供<xref:System.Drawing.Bitmap>用于显示、操作和保存位图的类。  
  
## <a name="typography"></a>版式  
 排版是文本以各种字体、大小和样式显示的。 GDI+ 为这一复杂任务提供了广泛的支持。 GDI+ 中的新功能之一是子像素抗锯齿，它使在 LCD 屏幕上呈现的文本外观更平滑。  
  
 此外，Windows 窗体还提供使用类<xref:System.Windows.Forms.TextRenderer>中的 GDI 功能绘制文本的选项。  
  
## <a name="see-also"></a>另请参阅

- [图形概述](graphics-overview-windows-forms.md)
- [关于 GDI+ 托管代码](about-gdi-managed-code.md)
- [使用托管图形类](using-managed-graphics-classes.md)
