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
# <a name="how-to-rotate-colors"></a><span data-ttu-id="957a5-102">如何：旋转颜色</span><span class="sxs-lookup"><span data-stu-id="957a5-102">How to: Rotate Colors</span></span>
<span data-ttu-id="957a5-103">四维色彩空间中的旋转很难可视化。</span><span class="sxs-lookup"><span data-stu-id="957a5-103">Rotation in a four-dimensional color space is difficult to visualize.</span></span> <span data-ttu-id="957a5-104">通过同意固定其中一种颜色组件，我们可以更轻松地可视化旋转。</span><span class="sxs-lookup"><span data-stu-id="957a5-104">We can make it easier to visualize rotation by agreeing to keep one of the color components fixed.</span></span> <span data-ttu-id="957a5-105">假设我们同意将 Alpha 组件固定为 1（完全不透明）。</span><span class="sxs-lookup"><span data-stu-id="957a5-105">Suppose we agree to keep the alpha component fixed at 1 (fully opaque).</span></span> <span data-ttu-id="957a5-106">然后，我们可以用红色、绿色和蓝色轴可视化三维颜色空间，如下图所示。</span><span class="sxs-lookup"><span data-stu-id="957a5-106">Then we can visualize a three-dimensional color space with red, green, and blue axes as shown in the following illustration.</span></span>  
  
 ![显示红色、绿色和蓝色轴旋转的插图。](./media/how-to-rotate-colors/rotation-red-green-blue-axes.gif)  
  
 <span data-ttu-id="957a5-108">颜色可以被视为 3D 空间中的点。</span><span class="sxs-lookup"><span data-stu-id="957a5-108">A color can be thought of as a point in 3D space.</span></span> <span data-ttu-id="957a5-109">例如，空格中的点 （1， 0， 0） 表示红色，空格中的点 （0， 1， 0） 表示绿色。</span><span class="sxs-lookup"><span data-stu-id="957a5-109">For example, the point (1, 0, 0) in space represents the color red, and the point (0, 1, 0) in space represents the color green.</span></span>  
  
 <span data-ttu-id="957a5-110">下图显示了在红绿平面中通过 60 度角旋转颜色 （1， 0， 0） 的含义。</span><span class="sxs-lookup"><span data-stu-id="957a5-110">The following illustration shows what it means to rotate the color (1, 0, 0) through an angle of 60 degrees in the Red-Green plane.</span></span> <span data-ttu-id="957a5-111">与红-绿平面平行的平面上的旋转可视为蓝色轴的旋转。</span><span class="sxs-lookup"><span data-stu-id="957a5-111">Rotation in a plane parallel to the Red-Green plane can be thought of as rotation about the blue axis.</span></span>  
  
 ![显示蓝色轴旋转的插图。](./media/how-to-rotate-colors/rotation-about-blue-axis.gif)  
  
 <span data-ttu-id="957a5-113">下图演示如何初始化颜色矩阵以对三个坐标轴（红色、绿色、蓝色）执行每个坐标轴的旋转：</span><span class="sxs-lookup"><span data-stu-id="957a5-113">The following illustration shows how to initialize a color matrix to perform rotations about each of the three coordinate axes (red, green, blue):</span></span>  
  
 ![初始化颜色矩阵以执行大约三个轴的旋转。](./media/how-to-rotate-colors/rotation-about-three-axes.gif)  
  
## <a name="example"></a><span data-ttu-id="957a5-115">示例</span><span class="sxs-lookup"><span data-stu-id="957a5-115">Example</span></span>  
 <span data-ttu-id="957a5-116">下面的示例采用一个全部为一种颜色（1，0，0.6）的图像，并应用 60 度旋转蓝色轴。</span><span class="sxs-lookup"><span data-stu-id="957a5-116">The following example takes an image that is all one color (1, 0, 0.6) and applies a 60-degree rotation about the blue axis.</span></span> <span data-ttu-id="957a5-117">旋转角度在与红绿色平面平行的平面中扫出。</span><span class="sxs-lookup"><span data-stu-id="957a5-117">The angle of the rotation is swept out in a plane that is parallel to the red-green plane.</span></span>  
  
 <span data-ttu-id="957a5-118">下图显示了左侧的原始图像和右侧的颜色旋转图像：</span><span class="sxs-lookup"><span data-stu-id="957a5-118">The following illustration shows the original image on the left and the color-rotated image on the right:</span></span>  
  
 ![显示原始图像和颜色旋转图像的插图。](./media/how-to-rotate-colors/original-color-rotated-images.png)  
  
 <span data-ttu-id="957a5-120">下图显示了以下代码中执行的颜色旋转的可视化效果：</span><span class="sxs-lookup"><span data-stu-id="957a5-120">The following illustration shows a visualization of the color rotation performed in the following code:</span></span>
  
 ![显示颜色旋转可视化的插图。](./media/how-to-rotate-colors/visualization-color-rotation.gif)  
  
 [!code-csharp[System.Drawing.RotateColors#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.RotateColors/CS/Form1.cs#1)]
 [!code-vb[System.Drawing.RotateColors#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.RotateColors/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="957a5-122">编译代码</span><span class="sxs-lookup"><span data-stu-id="957a5-122">Compiling the Code</span></span>  
 <span data-ttu-id="957a5-123">前面的示例设计用于 Windows 窗体，它需要<xref:System.Windows.Forms.PaintEventArgs>`e`，这是事件处理程序的<xref:System.Windows.Forms.Control.Paint>参数。</span><span class="sxs-lookup"><span data-stu-id="957a5-123">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span> <span data-ttu-id="957a5-124">替换为`RotationInput.bmp`系统上有效的映像文件名和路径。</span><span class="sxs-lookup"><span data-stu-id="957a5-124">Replace `RotationInput.bmp` with an image file name and path valid on your system.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="957a5-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="957a5-125">See also</span></span>

- <xref:System.Drawing.Imaging.ColorMatrix>
- <xref:System.Drawing.Imaging.ImageAttributes>
- [<span data-ttu-id="957a5-126">Windows 窗体中的图形和绘制</span><span class="sxs-lookup"><span data-stu-id="957a5-126">Graphics and Drawing in Windows Forms</span></span>](graphics-and-drawing-in-windows-forms.md)
- [<span data-ttu-id="957a5-127">对图像重新着色</span><span class="sxs-lookup"><span data-stu-id="957a5-127">Recoloring Images</span></span>](recoloring-images.md)
