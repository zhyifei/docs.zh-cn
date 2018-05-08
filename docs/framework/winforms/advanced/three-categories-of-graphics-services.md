---
title: 图形服务的三个类别
ms.date: 03/30/2017
helpviewer_keywords:
- imaging
- graphics [Windows Forms], categories
- 2-D vector graphics
- vector graphics
- typography
ms.assetid: 068c0ef3-f6ee-4d58-a7b6-eb2531ead408
ms.openlocfilehash: 5621a2c0bba2e922e62006feba9ca0381181c780
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="three-categories-of-graphics-services"></a>图形服务的三个类别
Windows 窗体中的图形产品划分为以下三大类：  
  
-   二维 (2-d) 向量图形  
  
-   映像  
  
-   版式  
  
## <a name="2-d-vector-graphics"></a>二维向量图形  
 二维向量图形是基元;直线、 曲线和图形; 例如指定的坐标系统上的点集。 例如，由其两个终结点，指定一条直线和矩形指定通过提供其左上角和一对数字使其宽度和高度的位置的点。 通过由直线连接的点数组指定简单的路径。 指定由四个控制点的复杂的曲线的贝塞尔样条。  
  
 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] 提供类和存储有关的基元本身的信息的结构、 存储有关如何将绘制基元，信息的类和实际执行绘图的类。 例如，<xref:System.Drawing.Rectangle>结构存储的位置和大小的矩形;<xref:System.Drawing.Pen>类存储线条颜色、 线条宽度和线条样式; 有关的信息和<xref:System.Drawing.Graphics>类具有绘制线条、 矩形、 路径的方法和其他图中。 有几种<xref:System.Drawing.Brush>存储有关如何信息的类封闭图形和路径中将填充颜色或图案。  
  
 你可以在图元文件中记录的图形命令序列矢量图像。 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] 提供<xref:System.Drawing.Imaging.Metafile>类录制、 显示和保存图元文件。 与<xref:System.Drawing.Imaging.MetafileHeader>和<xref:System.Drawing.Imaging.MetaHeader>类，你可以检查图元文件标头中存储的数据。  
  
## <a name="imaging"></a>映像  
 某些种类的图片很难或无法显示使用矢量图形的技术。 例如，在工具栏按钮的图片和以图标形式显示的图片就是难以指定为集合的直线和曲线。 高分辨率数码相片拥挤的棒体育场是创建使用矢量技术变得更加困难。 此类型的图像存储为位图，是表示屏幕上的各个点的颜色的数字的数组。 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] 提供<xref:System.Drawing.Bitmap>用于显示、 操作和保存位图的类。  
  
## <a name="typography"></a>版式  
 版式是文本的在多个字体、 大小和样式的显示。 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] 此复杂的任务提供广泛支持。 中的新功能之一[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]子像素抗锯齿，它可以使文本上呈现 LCD 屏幕模型更流畅的外观。  
  
 此外，Windows 窗体提供的选项，绘制文本[!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)]中的功能其<xref:System.Windows.Forms.TextRenderer>类。  
  
## <a name="see-also"></a>请参阅  
 [图形概述](../../../../docs/framework/winforms/advanced/graphics-overview-windows-forms.md)  
 [关于 GDI+ 托管代码](../../../../docs/framework/winforms/advanced/about-gdi-managed-code.md)  
 [使用托管图形类](../../../../docs/framework/winforms/advanced/using-managed-graphics-classes.md)
