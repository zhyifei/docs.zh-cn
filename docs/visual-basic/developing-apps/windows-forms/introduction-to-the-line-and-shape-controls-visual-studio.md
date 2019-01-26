---
title: Line 和 Shape 控件简介 (Visual Studio)
ms.date: 07/20/2015
helpviewer_keywords:
- Line control [Visual Basic], overview
- Shape control [Visual Basic], overview
- lines, drawing
- shapes, drawing
ms.assetid: 5c4e8b1a-0733-4020-af6c-f582f4026728
ms.openlocfilehash: 3623c2363f39150fd4bb202ba61ebd51df383ca8
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54699917"
---
# <a name="introduction-to-the-line-and-shape-controls-visual-studio"></a>Line 和 Shape 控件简介 (Visual Studio)
Visual Basic Power Pack Line 和 Shape 控件是一组三个图形控件，您可以在窗体和容器上绘制线条和形状。 <xref:Microsoft.VisualBasic.PowerPacks.LineShape>控件用于绘制水平、 垂直，和对角线的线条。 <xref:Microsoft.VisualBasic.PowerPacks.OvalShape>控件用于绘制圆形菜单和椭圆和<xref:Microsoft.VisualBasic.PowerPacks.RectangleShape>控件用于绘制矩形和正方形。  
  
## <a name="line-and-shape-controls"></a>Line 和 Shape 控件  
 Line 和 Shape 控件封装的许多图形方法中包含的<xref:System.Drawing>命名空间。 这使您可以在单个步骤中绘制线条和形状，而无需创建图形对象、 笔和画笔。 只需设置某些属性即可进行复杂的图形技术，例如渐变填充。  
  
 尽管也可以使用图形方法绘制线条和形状，但有以下几个使用 Line 和 Shape 控件优点：  
  
-   仅在运行时，可以调用图形方法。 Line 和 Shape 控件可以在设计时添加到窗体。 这使您可以看到它们的外观，并以它们进行精确; 定位它们可以还添加在运行时。  
  
-   Line 和 Shape 控件是可选择在运行时，提供事件，如<xref:Microsoft.VisualBasic.PowerPacks.Shape.Click>和<xref:Microsoft.VisualBasic.PowerPacks.Shape.OnDoubleClick%2A>。 图形方法的输出是不可选择的并不提供事件。  
  
-   Line 和 Shape 控件提供<xref:Microsoft.VisualBasic.PowerPacks.Shape.BringToFront%2A>和<xref:Microsoft.VisualBasic.PowerPacks.Shape.SendToBack%2A>，您可以在设计时和运行时控制其 z 顺序的方法。 只能通过更改其顺序在运行时执行，可以控制 z 顺序的图形方法。  
  
-   Line 和 Shape 控件是无窗口控件;它们没有窗口句柄，因此使用更少的系统资源。  
  
### <a name="object-model"></a>对象模型  
 Line 和 Shape 控件派生自基<xref:Microsoft.VisualBasic.PowerPacks.Shape>定义其共享的属性、 方法和事件的类。  
  
 下图显示 Line 和 Shape 对象层次结构。  
  
 ![Line 和 Shape 对象层次结构的关系图](../../../visual-basic/developing-apps/windows-forms/media/lineshapeobject.png "LineShapeObject")  
Line 和 Shape 对象层次结构  
  
 派生<xref:Microsoft.VisualBasic.PowerPacks.LineShape>类包含属性、 方法和事件是唯一的行。 派生<xref:Microsoft.VisualBasic.PowerPacks.SimpleShape>类是类的基类<xref:Microsoft.VisualBasic.PowerPacks.OvalShape>和<xref:Microsoft.VisualBasic.PowerPacks.RectangleShape>; 它包含属性、 方法和事件普遍适用于所有形状。 也可以派生<xref:Microsoft.VisualBasic.PowerPacks.SimpleShape>要创建你自己`Shape`控件。  
  
 <xref:Microsoft.VisualBasic.PowerPacks.OvalShape>和<xref:Microsoft.VisualBasic.PowerPacks.RectangleShape>类可用于绘制圆、 椭圆、 矩形和圆角矩形。  
  
 线条或形状控件添加到窗体或容器，不可见时<xref:Microsoft.VisualBasic.PowerPacks.ShapeContainer>创建对象。 <xref:Microsoft.VisualBasic.PowerPacks.ShapeContainer>充当用于每个容器控件内的形状的画布; 每个<xref:Microsoft.VisualBasic.PowerPacks.ShapeContainer>有一个相应<xref:Microsoft.VisualBasic.PowerPacks.ShapeCollection>，可用于循环访问 Line 和 Shape 控件。 您可以移动形状从一个容器到另一个使用剪切和粘贴或拖放。 从容器中，删除最后一个形状时<xref:Microsoft.VisualBasic.PowerPacks.ShapeContainer>还删除。  
  
> [!NOTE]
>  并非所有的容器控件支持 Line 和 Shape 控件。 你不能在托管线条或形状控件<xref:System.Windows.Forms.TableLayoutPanel>或<xref:System.Windows.Forms.FlowLayoutPanel>。  
  
## <a name="see-also"></a>请参阅
- <xref:Microsoft.VisualBasic.PowerPacks>
- [如何：使用 LineShape 控件绘制直线](../../../visual-basic/developing-apps/windows-forms/how-to-draw-lines-with-the-lineshape-control-visual-studio.md)
- [如何：使用 OvalShape 和 RectangleShape 控件绘制形状](../../../visual-basic/developing-apps/windows-forms/how-to-draw-shapes-with-the-ovalshape-and-rectangleshape-controls.md)
- [如何：使用 tab 键切换形状之间](../../../visual-basic/developing-apps/windows-forms/how-to-enable-tabbing-between-shapes-visual-studio.md)
