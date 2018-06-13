---
title: 如何：使用 OvalShape 和 RectangleShape 控件绘制形状 (Visual Studio)
ms.date: 07/20/2015
dev_langs:
- csharp
- vb
helpviewer_keywords:
- OvalShape control [Visual Basic]
- shapes, drawing
- RectangleShape control [Visual Basic]
ms.assetid: 0275b4c6-7a13-46c8-90f3-61db308c6b5d
ms.openlocfilehash: f87865ba3aebe5739b87d6ae6bfeaa957af726d8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33592270"
---
# <a name="how-to-draw-shapes-with-the-ovalshape-and-rectangleshape-controls-visual-studio"></a>如何：使用 OvalShape 和 RectangleShape 控件绘制形状 (Visual Studio)
你可使用 <xref:Microsoft.VisualBasic.PowerPacks.OvalShape> 控件在设计时和在运行时在窗体或容器上绘制圆形或椭圆形。 你可使用 <xref:Microsoft.VisualBasic.PowerPacks.RectangleShape> 控件在窗体或容器上绘制正方形、矩形或圆角矩形。 你还可使用此控件在设计时和在运行时绘制形状。  
  
 你可以通过更改宽度、颜色和边框样式来自定义形状的外观。 形状背景默认为透明；你可以自定义背景以显示纯色、图案、渐变填充（从一种颜色过渡到另一种颜色）或图像。  
  
### <a name="to-draw-a-simple-shape-at-design-time"></a>若要在设计时绘制简单形状  
  
1.  拖动<xref:Microsoft.VisualBasic.PowerPacks.OvalShape>或<xref:Microsoft.VisualBasic.PowerPacks.RectangleShape>控件从**Visual Basic PowerPacks**选项卡 (若要安装，请参阅[Visual Basic Power Packs 控件](../../../visual-basic/developing-apps/windows-forms/power-packs-controls.md)) 中**工具箱**向窗体或容器控件。  
  
2.  拖动调整大小并移动图柄来调整形状的大小和对其定位。  
  
     您还可以调整大小和通过更改定位形状`Size`和`Position`中的属性**属性**窗口。  
  
     若要创建圆角矩形，选择`CornerRadius`中的属性**属性**窗口并将其设置为大于 0 的值。  
  
3.  在**属性**窗口中，根据需要设置其他属性来更改形状的外观。  
  
### <a name="to-draw-a-simple-shape-at-run-time"></a>若要在运行时绘制简单形状  
  
1.  在“项目”菜单上，单击“添加引用”。  
  
2.  在**添加引用**对话框中，选择**Microsoft.VisualBasic.PowerPacks.VS**，然后单击**确定**。  
  
3.  在**代码编辑器**，添加`Imports`或`using`语句模块的顶部：  
  
```vb  
Imports Microsoft.VisualBasic.PowerPacks  
```  
  
```csharp  
using Microsoft.VisualBasic.PowerPacks;  
```  
  
4.  在 `Event` 过程中添加以下代码：  
  
     [!code-csharp[VbPowerpacksShape#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/how-to-draw-shapes-with-the-ovalshape-and-rectangleshape-controls_1.cs)]
     [!code-vb[VbPowerpacksShape#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/how-to-draw-shapes-with-the-ovalshape-and-rectangleshape-controls_1.vb)]  
  
## <a name="customizing-shapes"></a>正在自定义形状  
 使用默认设置时，<xref:Microsoft.VisualBasic.PowerPacks.OvalShape> 和 <xref:Microsoft.VisualBasic.PowerPacks.RectangleShape> 控件显示时带有黑色实心边框，且边框宽为一个像素，背景色为透明。 你可以通过设置属性来更改边框宽度、样式和颜色。 通过其他属性，你可以将形状的背景更改为纯色、图案、渐变填充或图像。  
  
 更改形状的背景之前，你应了解几个属性的交互方式。  
  
-   <xref:Microsoft.VisualBasic.PowerPacks.SimpleShape.BackColor%2A> 属性设置在 <xref:Microsoft.VisualBasic.PowerPacks.SimpleShape.BackStyle%2A> 属性设置为 <xref:Microsoft.VisualBasic.PowerPacks.BackStyle.Opaque> 时才起作用。  
  
-   如果将 <xref:Microsoft.VisualBasic.PowerPacks.SimpleShape.FillStyle%2A> 属性设置为 <xref:Microsoft.VisualBasic.PowerPacks.FillStyle.Solid>，则 <xref:Microsoft.VisualBasic.PowerPacks.SimpleShape.FillColor%2A> 将重写 <xref:Microsoft.VisualBasic.PowerPacks.SimpleShape.BackColor%2A>。  
  
-   如果将 <xref:Microsoft.VisualBasic.PowerPacks.SimpleShape.FillStyle%2A> 属性设置为一个模式值（如 <xref:Microsoft.VisualBasic.PowerPacks.FillStyle.Horizontal> 或 <xref:Microsoft.VisualBasic.PowerPacks.FillStyle.Vertical>），则图案将在 <xref:Microsoft.VisualBasic.PowerPacks.SimpleShape.FillColor%2A> 中显示。 如果将 <xref:Microsoft.VisualBasic.PowerPacks.SimpleShape.BackColor%2A> 属性设置为 <xref:Microsoft.VisualBasic.PowerPacks.SimpleShape.BackStyle%2A>，则背景将在 <xref:Microsoft.VisualBasic.PowerPacks.BackStyle.Opaque> 中显示。  
  
-   为了显示渐变填充，<xref:Microsoft.VisualBasic.PowerPacks.SimpleShape.FillStyle%2A> 属性必须设置为 <xref:Microsoft.VisualBasic.PowerPacks.FillStyle.Solid>且 <xref:Microsoft.VisualBasic.PowerPacks.SimpleShape.FillGradientStyle%2A> 属性必须设置为 <xref:Microsoft.VisualBasic.PowerPacks.FillGradientStyle.None> 之外的值。  
  
-   将 <xref:Microsoft.VisualBasic.PowerPacks.SimpleShape.BackgroundImage%2A> 属性设置为图像会重写所有其他背景设置。  
  
#### <a name="to-draw-a-circle-that-has-a-custom-border"></a>若要绘制一个具有自定义边框的圆形  
  
1.  拖动`OvalShape`控件从**Visual Basic PowerPacks**选项卡中**工具箱**到窗体或容器控件。  
  
2.  在**属性**窗口，请在`Size`属性，设置`Height`和`Width`为相等的值。  
  
3.  将 `BorderColor` 属性设置为希望的颜色。  
  
4.  将 `BorderStyle` 属性设置为 `Solid` 之外的任何值。  
  
5.  将 `BorderWidth` 设置为希望的大小（以像素为单位）。  
  
#### <a name="to-draw-a-circle-that-has-a-solid-fill"></a>若要绘制一个具有纯色填充的圆形  
  
1.  拖动`OvalShape`控件从**Visual Basic PowerPacks**选项卡中**工具箱**到窗体或容器控件。  
  
2.  在**属性**窗口，请在`Size`属性，设置`Height`和`Width`为相等的值。  
  
3.  将 `BackColor` 属性设置为希望的颜色。  
  
4.  将 `BackStyle` 属性设置为 `Opaque`。  
  
#### <a name="to-draw-a-circle-that-has-a-patterned-fill"></a>若要绘制一个具有图案填充的圆形  
  
1.  拖动`OvalShape`控件从**Visual Basic PowerPacks**选项卡中**工具箱**到窗体或容器控件。  
  
2.  在**属性**窗口，请在`Size`属性，设置`Height`和`Width`为相等的值。  
  
3.  将 `BackColor` 属性设置为希望的背景颜色。  
  
4.  将 `BackStyle` 属性设置为 `Opaque`。  
  
5.  将 `FillColor` 属性设置为希望的图案颜色。  
  
6.  将 `FillStyle` 属性设置为 `Transparent` 或 `Solid` 之外的任何值。  
  
#### <a name="to-draw-a-circle-that-has-a-gradient-fill"></a>若要绘制一个具有渐变填充的圆形  
  
1.  拖动`OvalShape`控件从**Visual Basic PowerPacks**选项卡中**工具箱**到窗体或容器控件。  
  
2.  在**属性**窗口，请在`Size`属性，设置`Height`和`Width`为相等的值。  
  
3.  将 `FillColor` 属性设置为希望的起始颜色。  
  
4.  将 `FillGradientColor` 属性设置为希望的结束颜色。  
  
5.  将 `FillGradientStyle` 属性设置为 `None` 之外的任何值。  
  
#### <a name="to-draw-a-circle-that-is-filled-with-an-image"></a>若要绘制图像填充的圆形  
  
1.  拖动`OvalShape`控件从**Visual Basic PowerPacks**选项卡中**工具箱**到窗体或容器控件。  
  
2.  在**属性**窗口，请在`Size`属性，设置`Height`和`Width`为相等的值。  
  
3.  选择`BackgroundImage`属性，然后单击**省略号**按钮 （…）。  
  
4.  在**选择资源**对话框中，选择要显示的图像。 如果未不列出任何图像资源，请单击**导入**以浏览到图像的位置。  
  
5.  单击**确定**插入图像。  
  
## <a name="see-also"></a>请参阅  
 <xref:Microsoft.VisualBasic.PowerPacks.OvalShape>  
 <xref:Microsoft.VisualBasic.PowerPacks.RectangleShape>  
 [Line 和 Shape 控件简介](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-line-and-shape-controls-visual-studio.md)  
 [如何：使用 LineShape 控件绘制直线](../../../visual-basic/developing-apps/windows-forms/how-to-draw-lines-with-the-lineshape-control-visual-studio.md)
