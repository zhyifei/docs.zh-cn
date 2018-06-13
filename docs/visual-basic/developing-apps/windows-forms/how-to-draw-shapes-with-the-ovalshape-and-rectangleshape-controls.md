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
# <a name="how-to-draw-shapes-with-the-ovalshape-and-rectangleshape-controls-visual-studio"></a><span data-ttu-id="51d46-102">如何：使用 OvalShape 和 RectangleShape 控件绘制形状 (Visual Studio)</span><span class="sxs-lookup"><span data-stu-id="51d46-102">How to: Draw Shapes with the OvalShape and RectangleShape Controls (Visual Studio)</span></span>
<span data-ttu-id="51d46-103">你可使用 <xref:Microsoft.VisualBasic.PowerPacks.OvalShape> 控件在设计时和在运行时在窗体或容器上绘制圆形或椭圆形。</span><span class="sxs-lookup"><span data-stu-id="51d46-103">You can use the <xref:Microsoft.VisualBasic.PowerPacks.OvalShape> control to draw circles or ovals on a form or container, both at design time and at run time.</span></span> <span data-ttu-id="51d46-104">你可使用 <xref:Microsoft.VisualBasic.PowerPacks.RectangleShape> 控件在窗体或容器上绘制正方形、矩形或圆角矩形。</span><span class="sxs-lookup"><span data-stu-id="51d46-104">You can use the <xref:Microsoft.VisualBasic.PowerPacks.RectangleShape> control to draw squares, rectangles, or rectangles with rounded corners on a form or container.</span></span> <span data-ttu-id="51d46-105">你还可使用此控件在设计时和在运行时绘制形状。</span><span class="sxs-lookup"><span data-stu-id="51d46-105">You can also use this control to draw shapes both at design time and at run time.</span></span>  
  
 <span data-ttu-id="51d46-106">你可以通过更改宽度、颜色和边框样式来自定义形状的外观。</span><span class="sxs-lookup"><span data-stu-id="51d46-106">You can customize the appearance of a shape by changing the width, color, and style of the border.</span></span> <span data-ttu-id="51d46-107">形状背景默认为透明；你可以自定义背景以显示纯色、图案、渐变填充（从一种颜色过渡到另一种颜色）或图像。</span><span class="sxs-lookup"><span data-stu-id="51d46-107">The background of a shape is transparent by default; you can customize the background to display a solid color, a pattern, a gradient fill (transitioning from one color to another), or an image.</span></span>  
  
### <a name="to-draw-a-simple-shape-at-design-time"></a><span data-ttu-id="51d46-108">若要在设计时绘制简单形状</span><span class="sxs-lookup"><span data-stu-id="51d46-108">To draw a simple shape at design time</span></span>  
  
1.  <span data-ttu-id="51d46-109">拖动<xref:Microsoft.VisualBasic.PowerPacks.OvalShape>或<xref:Microsoft.VisualBasic.PowerPacks.RectangleShape>控件从**Visual Basic PowerPacks**选项卡 (若要安装，请参阅[Visual Basic Power Packs 控件](../../../visual-basic/developing-apps/windows-forms/power-packs-controls.md)) 中**工具箱**向窗体或容器控件。</span><span class="sxs-lookup"><span data-stu-id="51d46-109">Drag the <xref:Microsoft.VisualBasic.PowerPacks.OvalShape> or <xref:Microsoft.VisualBasic.PowerPacks.RectangleShape> control from the **Visual Basic PowerPacks** tab (to install, see [Visual Basic Power Packs Controls](../../../visual-basic/developing-apps/windows-forms/power-packs-controls.md))in the **Toolbox** to a form or container control.</span></span>  
  
2.  <span data-ttu-id="51d46-110">拖动调整大小并移动图柄来调整形状的大小和对其定位。</span><span class="sxs-lookup"><span data-stu-id="51d46-110">Drag the sizing and move handles to size and position the shape.</span></span>  
  
     <span data-ttu-id="51d46-111">您还可以调整大小和通过更改定位形状`Size`和`Position`中的属性**属性**窗口。</span><span class="sxs-lookup"><span data-stu-id="51d46-111">You can also size and position the shape by changing the `Size` and `Position` properties in the **Properties** window.</span></span>  
  
     <span data-ttu-id="51d46-112">若要创建圆角矩形，选择`CornerRadius`中的属性**属性**窗口并将其设置为大于 0 的值。</span><span class="sxs-lookup"><span data-stu-id="51d46-112">To create a rectangle with rounded corners, select the `CornerRadius` property in the **Properties** window and set it to a value that is greater than 0.</span></span>  
  
3.  <span data-ttu-id="51d46-113">在**属性**窗口中，根据需要设置其他属性来更改形状的外观。</span><span class="sxs-lookup"><span data-stu-id="51d46-113">In the **Properties** window, optionally set additional properties to change the appearance of the shape.</span></span>  
  
### <a name="to-draw-a-simple-shape-at-run-time"></a><span data-ttu-id="51d46-114">若要在运行时绘制简单形状</span><span class="sxs-lookup"><span data-stu-id="51d46-114">To draw a simple shape at run time</span></span>  
  
1.  <span data-ttu-id="51d46-115">在“项目”菜单上，单击“添加引用”。</span><span class="sxs-lookup"><span data-stu-id="51d46-115">On the **Project** menu, click **Add Reference**.</span></span>  
  
2.  <span data-ttu-id="51d46-116">在**添加引用**对话框中，选择**Microsoft.VisualBasic.PowerPacks.VS**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="51d46-116">In the **Add Reference** dialog box, select **Microsoft.VisualBasic.PowerPacks.VS**, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="51d46-117">在**代码编辑器**，添加`Imports`或`using`语句模块的顶部：</span><span class="sxs-lookup"><span data-stu-id="51d46-117">In the **Code Editor**, add an `Imports` or `using` statement at the top of the module:</span></span>  
  
```vb  
Imports Microsoft.VisualBasic.PowerPacks  
```  
  
```csharp  
using Microsoft.VisualBasic.PowerPacks;  
```  
  
4.  <span data-ttu-id="51d46-118">在 `Event` 过程中添加以下代码：</span><span class="sxs-lookup"><span data-stu-id="51d46-118">Add the following code in an `Event` procedure:</span></span>  
  
     [!code-csharp[VbPowerpacksShape#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/how-to-draw-shapes-with-the-ovalshape-and-rectangleshape-controls_1.cs)]
     [!code-vb[VbPowerpacksShape#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/how-to-draw-shapes-with-the-ovalshape-and-rectangleshape-controls_1.vb)]  
  
## <a name="customizing-shapes"></a><span data-ttu-id="51d46-119">正在自定义形状</span><span class="sxs-lookup"><span data-stu-id="51d46-119">Customizing Shapes</span></span>  
 <span data-ttu-id="51d46-120">使用默认设置时，<xref:Microsoft.VisualBasic.PowerPacks.OvalShape> 和 <xref:Microsoft.VisualBasic.PowerPacks.RectangleShape> 控件显示时带有黑色实心边框，且边框宽为一个像素，背景色为透明。</span><span class="sxs-lookup"><span data-stu-id="51d46-120">When you use the default settings, the <xref:Microsoft.VisualBasic.PowerPacks.OvalShape> and <xref:Microsoft.VisualBasic.PowerPacks.RectangleShape> controls are displayed with a solid black border that is one pixel wide and a transparent background.</span></span> <span data-ttu-id="51d46-121">你可以通过设置属性来更改边框宽度、样式和颜色。</span><span class="sxs-lookup"><span data-stu-id="51d46-121">You can change the width, style, and color of the border by setting properties.</span></span> <span data-ttu-id="51d46-122">通过其他属性，你可以将形状的背景更改为纯色、图案、渐变填充或图像。</span><span class="sxs-lookup"><span data-stu-id="51d46-122">Additional properties enable you to change the background of a shape to a solid color, a pattern, a gradient fill, or an image.</span></span>  
  
 <span data-ttu-id="51d46-123">更改形状的背景之前，你应了解几个属性的交互方式。</span><span class="sxs-lookup"><span data-stu-id="51d46-123">Before you change the background of a shape, you should know how several of the properties interact.</span></span>  
  
-   <span data-ttu-id="51d46-124"><xref:Microsoft.VisualBasic.PowerPacks.SimpleShape.BackColor%2A> 属性设置在 <xref:Microsoft.VisualBasic.PowerPacks.SimpleShape.BackStyle%2A> 属性设置为 <xref:Microsoft.VisualBasic.PowerPacks.BackStyle.Opaque> 时才起作用。</span><span class="sxs-lookup"><span data-stu-id="51d46-124">The <xref:Microsoft.VisualBasic.PowerPacks.SimpleShape.BackColor%2A> property setting has no effect unless the <xref:Microsoft.VisualBasic.PowerPacks.SimpleShape.BackStyle%2A> property is set to <xref:Microsoft.VisualBasic.PowerPacks.BackStyle.Opaque>.</span></span>  
  
-   <span data-ttu-id="51d46-125">如果将 <xref:Microsoft.VisualBasic.PowerPacks.SimpleShape.FillStyle%2A> 属性设置为 <xref:Microsoft.VisualBasic.PowerPacks.FillStyle.Solid>，则 <xref:Microsoft.VisualBasic.PowerPacks.SimpleShape.FillColor%2A> 将重写 <xref:Microsoft.VisualBasic.PowerPacks.SimpleShape.BackColor%2A>。</span><span class="sxs-lookup"><span data-stu-id="51d46-125">If the <xref:Microsoft.VisualBasic.PowerPacks.SimpleShape.FillStyle%2A> property is set to <xref:Microsoft.VisualBasic.PowerPacks.FillStyle.Solid>, the <xref:Microsoft.VisualBasic.PowerPacks.SimpleShape.FillColor%2A> overrides the <xref:Microsoft.VisualBasic.PowerPacks.SimpleShape.BackColor%2A>.</span></span>  
  
-   <span data-ttu-id="51d46-126">如果将 <xref:Microsoft.VisualBasic.PowerPacks.SimpleShape.FillStyle%2A> 属性设置为一个模式值（如 <xref:Microsoft.VisualBasic.PowerPacks.FillStyle.Horizontal> 或 <xref:Microsoft.VisualBasic.PowerPacks.FillStyle.Vertical>），则图案将在 <xref:Microsoft.VisualBasic.PowerPacks.SimpleShape.FillColor%2A> 中显示。</span><span class="sxs-lookup"><span data-stu-id="51d46-126">If the <xref:Microsoft.VisualBasic.PowerPacks.SimpleShape.FillStyle%2A> property is set to a pattern value such as <xref:Microsoft.VisualBasic.PowerPacks.FillStyle.Horizontal> or <xref:Microsoft.VisualBasic.PowerPacks.FillStyle.Vertical>, the pattern will be displayed in the <xref:Microsoft.VisualBasic.PowerPacks.SimpleShape.FillColor%2A>.</span></span> <span data-ttu-id="51d46-127">如果将 <xref:Microsoft.VisualBasic.PowerPacks.SimpleShape.BackColor%2A> 属性设置为 <xref:Microsoft.VisualBasic.PowerPacks.SimpleShape.BackStyle%2A>，则背景将在 <xref:Microsoft.VisualBasic.PowerPacks.BackStyle.Opaque> 中显示。</span><span class="sxs-lookup"><span data-stu-id="51d46-127">The background will be displayed in the <xref:Microsoft.VisualBasic.PowerPacks.SimpleShape.BackColor%2A>, provided that the <xref:Microsoft.VisualBasic.PowerPacks.SimpleShape.BackStyle%2A> property is set to <xref:Microsoft.VisualBasic.PowerPacks.BackStyle.Opaque>.</span></span>  
  
-   <span data-ttu-id="51d46-128">为了显示渐变填充，<xref:Microsoft.VisualBasic.PowerPacks.SimpleShape.FillStyle%2A> 属性必须设置为 <xref:Microsoft.VisualBasic.PowerPacks.FillStyle.Solid>且 <xref:Microsoft.VisualBasic.PowerPacks.SimpleShape.FillGradientStyle%2A> 属性必须设置为 <xref:Microsoft.VisualBasic.PowerPacks.FillGradientStyle.None> 之外的值。</span><span class="sxs-lookup"><span data-stu-id="51d46-128">In order to display a gradient fill, the <xref:Microsoft.VisualBasic.PowerPacks.SimpleShape.FillStyle%2A> property must be set to <xref:Microsoft.VisualBasic.PowerPacks.FillStyle.Solid> and the <xref:Microsoft.VisualBasic.PowerPacks.SimpleShape.FillGradientStyle%2A> property must be set to a value other than <xref:Microsoft.VisualBasic.PowerPacks.FillGradientStyle.None>.</span></span>  
  
-   <span data-ttu-id="51d46-129">将 <xref:Microsoft.VisualBasic.PowerPacks.SimpleShape.BackgroundImage%2A> 属性设置为图像会重写所有其他背景设置。</span><span class="sxs-lookup"><span data-stu-id="51d46-129">Setting the <xref:Microsoft.VisualBasic.PowerPacks.SimpleShape.BackgroundImage%2A> property to an image overrides all other background settings.</span></span>  
  
#### <a name="to-draw-a-circle-that-has-a-custom-border"></a><span data-ttu-id="51d46-130">若要绘制一个具有自定义边框的圆形</span><span class="sxs-lookup"><span data-stu-id="51d46-130">To draw a circle that has a custom border</span></span>  
  
1.  <span data-ttu-id="51d46-131">拖动`OvalShape`控件从**Visual Basic PowerPacks**选项卡中**工具箱**到窗体或容器控件。</span><span class="sxs-lookup"><span data-stu-id="51d46-131">Drag the `OvalShape` control from the **Visual Basic PowerPacks** tab in the **Toolbox** to a form or container control.</span></span>  
  
2.  <span data-ttu-id="51d46-132">在**属性**窗口，请在`Size`属性，设置`Height`和`Width`为相等的值。</span><span class="sxs-lookup"><span data-stu-id="51d46-132">In the **Properties** window, in the `Size` property, set `Height` and `Width` to equal values.</span></span>  
  
3.  <span data-ttu-id="51d46-133">将 `BorderColor` 属性设置为希望的颜色。</span><span class="sxs-lookup"><span data-stu-id="51d46-133">Set the `BorderColor` property to the color that you want.</span></span>  
  
4.  <span data-ttu-id="51d46-134">将 `BorderStyle` 属性设置为 `Solid` 之外的任何值。</span><span class="sxs-lookup"><span data-stu-id="51d46-134">Set the `BorderStyle` property to any value other than `Solid`.</span></span>  
  
5.  <span data-ttu-id="51d46-135">将 `BorderWidth` 设置为希望的大小（以像素为单位）。</span><span class="sxs-lookup"><span data-stu-id="51d46-135">Set the `BorderWidth` to the size that you want, in pixels.</span></span>  
  
#### <a name="to-draw-a-circle-that-has-a-solid-fill"></a><span data-ttu-id="51d46-136">若要绘制一个具有纯色填充的圆形</span><span class="sxs-lookup"><span data-stu-id="51d46-136">To draw a circle that has a solid fill</span></span>  
  
1.  <span data-ttu-id="51d46-137">拖动`OvalShape`控件从**Visual Basic PowerPacks**选项卡中**工具箱**到窗体或容器控件。</span><span class="sxs-lookup"><span data-stu-id="51d46-137">Drag the `OvalShape` control from the **Visual Basic PowerPacks** tab in the **Toolbox** to a form or container control.</span></span>  
  
2.  <span data-ttu-id="51d46-138">在**属性**窗口，请在`Size`属性，设置`Height`和`Width`为相等的值。</span><span class="sxs-lookup"><span data-stu-id="51d46-138">In the **Properties** window, in the `Size` property, set `Height` and `Width` to equal values.</span></span>  
  
3.  <span data-ttu-id="51d46-139">将 `BackColor` 属性设置为希望的颜色。</span><span class="sxs-lookup"><span data-stu-id="51d46-139">Set the `BackColor` property to the color that you want.</span></span>  
  
4.  <span data-ttu-id="51d46-140">将 `BackStyle` 属性设置为 `Opaque`。</span><span class="sxs-lookup"><span data-stu-id="51d46-140">Set the `BackStyle` property to `Opaque`.</span></span>  
  
#### <a name="to-draw-a-circle-that-has-a-patterned-fill"></a><span data-ttu-id="51d46-141">若要绘制一个具有图案填充的圆形</span><span class="sxs-lookup"><span data-stu-id="51d46-141">To draw a circle that has a patterned fill</span></span>  
  
1.  <span data-ttu-id="51d46-142">拖动`OvalShape`控件从**Visual Basic PowerPacks**选项卡中**工具箱**到窗体或容器控件。</span><span class="sxs-lookup"><span data-stu-id="51d46-142">Drag the `OvalShape` control from the **Visual Basic PowerPacks** tab in the **Toolbox** to a form or container control.</span></span>  
  
2.  <span data-ttu-id="51d46-143">在**属性**窗口，请在`Size`属性，设置`Height`和`Width`为相等的值。</span><span class="sxs-lookup"><span data-stu-id="51d46-143">In the **Properties** window, in the `Size` property, set `Height` and `Width` to equal values.</span></span>  
  
3.  <span data-ttu-id="51d46-144">将 `BackColor` 属性设置为希望的背景颜色。</span><span class="sxs-lookup"><span data-stu-id="51d46-144">Set the `BackColor` property to the color that you want for the background.</span></span>  
  
4.  <span data-ttu-id="51d46-145">将 `BackStyle` 属性设置为 `Opaque`。</span><span class="sxs-lookup"><span data-stu-id="51d46-145">Set the `BackStyle` property to `Opaque`.</span></span>  
  
5.  <span data-ttu-id="51d46-146">将 `FillColor` 属性设置为希望的图案颜色。</span><span class="sxs-lookup"><span data-stu-id="51d46-146">Set the `FillColor` property to the color that you want for the pattern.</span></span>  
  
6.  <span data-ttu-id="51d46-147">将 `FillStyle` 属性设置为 `Transparent` 或 `Solid` 之外的任何值。</span><span class="sxs-lookup"><span data-stu-id="51d46-147">Set the `FillStyle` property to any value other than `Transparent` or `Solid`.</span></span>  
  
#### <a name="to-draw-a-circle-that-has-a-gradient-fill"></a><span data-ttu-id="51d46-148">若要绘制一个具有渐变填充的圆形</span><span class="sxs-lookup"><span data-stu-id="51d46-148">To draw a circle that has a gradient fill</span></span>  
  
1.  <span data-ttu-id="51d46-149">拖动`OvalShape`控件从**Visual Basic PowerPacks**选项卡中**工具箱**到窗体或容器控件。</span><span class="sxs-lookup"><span data-stu-id="51d46-149">Drag the `OvalShape` control from the **Visual Basic PowerPacks** tab in the **Toolbox** to a form or container control.</span></span>  
  
2.  <span data-ttu-id="51d46-150">在**属性**窗口，请在`Size`属性，设置`Height`和`Width`为相等的值。</span><span class="sxs-lookup"><span data-stu-id="51d46-150">In the **Properties** window, in the `Size` property, set `Height` and `Width` to equal values.</span></span>  
  
3.  <span data-ttu-id="51d46-151">将 `FillColor` 属性设置为希望的起始颜色。</span><span class="sxs-lookup"><span data-stu-id="51d46-151">Set the `FillColor` property to the color that you want for the starting color.</span></span>  
  
4.  <span data-ttu-id="51d46-152">将 `FillGradientColor` 属性设置为希望的结束颜色。</span><span class="sxs-lookup"><span data-stu-id="51d46-152">Set the `FillGradientColor` property to the color that you want for the ending color.</span></span>  
  
5.  <span data-ttu-id="51d46-153">将 `FillGradientStyle` 属性设置为 `None` 之外的任何值。</span><span class="sxs-lookup"><span data-stu-id="51d46-153">Set the `FillGradientStyle` property to a value other than `None`.</span></span>  
  
#### <a name="to-draw-a-circle-that-is-filled-with-an-image"></a><span data-ttu-id="51d46-154">若要绘制图像填充的圆形</span><span class="sxs-lookup"><span data-stu-id="51d46-154">To draw a circle that is filled with an image</span></span>  
  
1.  <span data-ttu-id="51d46-155">拖动`OvalShape`控件从**Visual Basic PowerPacks**选项卡中**工具箱**到窗体或容器控件。</span><span class="sxs-lookup"><span data-stu-id="51d46-155">Drag the `OvalShape` control from the **Visual Basic PowerPacks** tab in the **Toolbox** to a form or container control.</span></span>  
  
2.  <span data-ttu-id="51d46-156">在**属性**窗口，请在`Size`属性，设置`Height`和`Width`为相等的值。</span><span class="sxs-lookup"><span data-stu-id="51d46-156">In the **Properties** window, in the `Size` property, set `Height` and `Width` to equal values.</span></span>  
  
3.  <span data-ttu-id="51d46-157">选择`BackgroundImage`属性，然后单击**省略号**按钮 （…）。</span><span class="sxs-lookup"><span data-stu-id="51d46-157">Select the `BackgroundImage` property and click the **ellipsis** button (...).</span></span>  
  
4.  <span data-ttu-id="51d46-158">在**选择资源**对话框中，选择要显示的图像。</span><span class="sxs-lookup"><span data-stu-id="51d46-158">In the **Select Resource** dialog box, select an image to display.</span></span> <span data-ttu-id="51d46-159">如果未不列出任何图像资源，请单击**导入**以浏览到图像的位置。</span><span class="sxs-lookup"><span data-stu-id="51d46-159">If no image resources are listed, click **Import** to browse to the location of an image.</span></span>  
  
5.  <span data-ttu-id="51d46-160">单击**确定**插入图像。</span><span class="sxs-lookup"><span data-stu-id="51d46-160">Click **OK** to insert the image.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="51d46-161">请参阅</span><span class="sxs-lookup"><span data-stu-id="51d46-161">See Also</span></span>  
 <xref:Microsoft.VisualBasic.PowerPacks.OvalShape>  
 <xref:Microsoft.VisualBasic.PowerPacks.RectangleShape>  
 [<span data-ttu-id="51d46-162">Line 和 Shape 控件简介</span><span class="sxs-lookup"><span data-stu-id="51d46-162">Introduction to the Line and Shape Controls</span></span>](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-line-and-shape-controls-visual-studio.md)  
 [<span data-ttu-id="51d46-163">如何：使用 LineShape 控件绘制直线</span><span class="sxs-lookup"><span data-stu-id="51d46-163">How to: Draw Lines with the LineShape Control</span></span>](../../../visual-basic/developing-apps/windows-forms/how-to-draw-lines-with-the-lineshape-control-visual-studio.md)
