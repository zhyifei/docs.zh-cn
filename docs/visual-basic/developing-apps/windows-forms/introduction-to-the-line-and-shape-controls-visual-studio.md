---
title: Line 和 Shape 控件简介 (Visual Studio)
ms.date: 07/20/2015
helpviewer_keywords:
- Line control [Visual Basic], overview
- Shape control [Visual Basic], overview
- lines, drawing
- shapes, drawing
ms.assetid: 5c4e8b1a-0733-4020-af6c-f582f4026728
ms.openlocfilehash: 3ad740f7dd15194830959a5493970b4ba54ce142
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="introduction-to-the-line-and-shape-controls-visual-studio"></a>Line 和 Shape 控件简介 (Visual Studio)
Visual Basic Power Pack Line 和 Shape 控件是一组可用于在窗体和容器上绘制线条和形状的三个图形控件。 <xref:Microsoft.VisualBasic.PowerPacks.LineShape>控件用于绘制水平线、 垂线、 对角线和行。 <xref:Microsoft.VisualBasic.PowerPacks.OvalShape>控件用于绘制圆形和椭圆形，和<xref:Microsoft.VisualBasic.PowerPacks.RectangleShape>控件用于绘制矩形和正方形。  
  
## <a name="line-and-shape-controls"></a>Line 和 Shape 控件  
 Line 和 Shape 控件封装许多中包含的图形方法<xref:System.Drawing>命名空间。 这使您可以在单个步骤中绘制线条和形状，而无需创建图形对象、 钢笔和画笔。 只需通过设置某些属性，可以实现复杂的图形技术，如渐变填充。  
  
 尽管还有可能要通过使用图形方法绘制线条和形状，但有以下几个使用 Line 和 Shape 控件优点：  
  
-   图形方法可以调用仅在运行时。 Line 和 Shape 控件可以在设计时添加到表单。 这使你若要查看它们的外观并将它们放置在完全;它们也可以添加在运行时。  
  
-   Line 和 Shape 控件是可选择在运行时，如提供事件<xref:Microsoft.VisualBasic.PowerPacks.Shape.Click>和<xref:Microsoft.VisualBasic.PowerPacks.Shape.OnDoubleClick%2A>。 图形方法的输出是不可选择的并且不提供事件。  
  
-   Line 和 Shape 控件提供<xref:Microsoft.VisualBasic.PowerPacks.Shape.BringToFront%2A>和<xref:Microsoft.VisualBasic.PowerPacks.Shape.SendToBack%2A>使您可以在设计时和在运行时控制其 z 顺序的方法。 可以仅通过更改其顺序在运行时执行的控制 z 顺序的图形方法。  
  
-   Line 和 Shape 控件是无窗口控件;它们没有窗口句柄，因此使用少的系统资源。  
  
### <a name="object-model"></a>对象模型  
 Line 和 Shape 控件派生自基<xref:Microsoft.VisualBasic.PowerPacks.Shape>定义其共享的属性、 方法和事件的类。  
  
 下图显示 Line 和 Shape 对象层次结构。  
  
 ![Line 和 Shape 对象层次结构关系图](../../../visual-basic/developing-apps/windows-forms/media/lineshapeobject.png "LineShapeObject")  
Line 和 Shape 对象层次结构  
  
 派生<xref:Microsoft.VisualBasic.PowerPacks.LineShape>类包含属性、 方法和事件是唯一的行。 派生<xref:Microsoft.VisualBasic.PowerPacks.SimpleShape>类是适用于基<xref:Microsoft.VisualBasic.PowerPacks.OvalShape>和<xref:Microsoft.VisualBasic.PowerPacks.RectangleShape>; 它包含属性、 方法和事件普遍适用于所有形状。 你还可以从派生<xref:Microsoft.VisualBasic.PowerPacks.SimpleShape>要创建你自己`Shape`控件。  
  
 <xref:Microsoft.VisualBasic.PowerPacks.OvalShape>和<xref:Microsoft.VisualBasic.PowerPacks.RectangleShape>类可以用于绘制圆形、 椭圆、 矩形和圆角矩形。  
  
 线条或形状控件添加到窗体或容器，不可见时<xref:Microsoft.VisualBasic.PowerPacks.ShapeContainer>创建对象。 <xref:Microsoft.VisualBasic.PowerPacks.ShapeContainer>充当用于每个容器控件中的形状的画布; 每个<xref:Microsoft.VisualBasic.PowerPacks.ShapeContainer>都有一个相应<xref:Microsoft.VisualBasic.PowerPacks.ShapeCollection>，可用于循环访问 Line 和 Shape 控件。 你可以形状在一个容器之间移动通过剪切和粘贴或通过拖放。 当从一个容器，删除最后一个形状<xref:Microsoft.VisualBasic.PowerPacks.ShapeContainer>还删除。  
  
> [!NOTE]
>  并非所有的容器控件支持 Line 和 Shape 控件。 你不能在托管线条或形状控件<xref:System.Windows.Forms.TableLayoutPanel>或<xref:System.Windows.Forms.FlowLayoutPanel>。  
  
## <a name="see-also"></a>请参阅  
 <xref:Microsoft.VisualBasic.PowerPacks>  
 [如何：使用 LineShape 控件绘制直线](../../../visual-basic/developing-apps/windows-forms/how-to-draw-lines-with-the-lineshape-control-visual-studio.md)  
 [如何：使用 OvalShape 和 RectangleShape 控件绘制形状](../../../visual-basic/developing-apps/windows-forms/how-to-draw-shapes-with-the-ovalshape-and-rectangleshape-controls.md)  
 [如何：使用 Tab 键在形状之间切换](../../../visual-basic/developing-apps/windows-forms/how-to-enable-tabbing-between-shapes-visual-studio.md)
