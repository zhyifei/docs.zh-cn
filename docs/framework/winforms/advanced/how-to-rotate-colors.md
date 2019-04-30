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
ms.openlocfilehash: 241d2824fc2d87a0505eb6e790c865bfa7d8ef90
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61967326"
---
# <a name="how-to-rotate-colors"></a><span data-ttu-id="011df-102">如何：旋转颜色</span><span class="sxs-lookup"><span data-stu-id="011df-102">How to: Rotate Colors</span></span>
<span data-ttu-id="011df-103">四维颜色空间中的旋转很难直观显示。</span><span class="sxs-lookup"><span data-stu-id="011df-103">Rotation in a four-dimensional color space is difficult to visualize.</span></span> <span data-ttu-id="011df-104">我们可以轻松地实现旋转同意接受保持一个固定的颜色组件的可视化效果。</span><span class="sxs-lookup"><span data-stu-id="011df-104">We can make it easier to visualize rotation by agreeing to keep one of the color components fixed.</span></span> <span data-ttu-id="011df-105">假设我们同意将 alpha 分量固定在 1 （完全不透明）。</span><span class="sxs-lookup"><span data-stu-id="011df-105">Suppose we agree to keep the alpha component fixed at 1 (fully opaque).</span></span> <span data-ttu-id="011df-106">然后我们可以直观显示三维颜色空间具有红色、 绿色和蓝色的轴，如下图中所示。</span><span class="sxs-lookup"><span data-stu-id="011df-106">Then we can visualize a three-dimensional color space with red, green, and blue axes as shown in the following illustration.</span></span>  
  
 ![显示具有红色、 绿色和蓝色轴旋转的图例。](./media/how-to-rotate-colors/rotation-red-green-blue-axes.gif)  
  
 <span data-ttu-id="011df-108">一种颜色可视为在三维空间中点。</span><span class="sxs-lookup"><span data-stu-id="011df-108">A color can be thought of as a point in 3-D space.</span></span> <span data-ttu-id="011df-109">例如，空间中的点 （1，0，0） 表示的颜色为红色，并在空间中的点 （0、 1、 0） 表示绿色。</span><span class="sxs-lookup"><span data-stu-id="011df-109">For example, the point (1, 0, 0) in space represents the color red, and the point (0, 1, 0) in space represents the color green.</span></span>  
  
 <span data-ttu-id="011df-110">下图通过红-绿平面中的 60 度的角度显示旋转的颜色 （1，0，0） 意味着什么。</span><span class="sxs-lookup"><span data-stu-id="011df-110">The following illustration shows what it means to rotate the color (1, 0, 0) through an angle of 60 degrees in the Red-Green plane.</span></span> <span data-ttu-id="011df-111">在平面平行于红-绿平面旋转可以看作围绕蓝色轴的旋转。</span><span class="sxs-lookup"><span data-stu-id="011df-111">Rotation in a plane parallel to the Red-Green plane can be thought of as rotation about the blue axis.</span></span>  
  
 ![显示有关蓝色轴旋转的图例。](./media/how-to-rotate-colors/rotation-about-blue-axis.gif)  
  
 <span data-ttu-id="011df-113">下图显示了如何初始化颜色矩阵执行三个坐标轴 （红色、 绿色、 蓝色） 的每个旋转：</span><span class="sxs-lookup"><span data-stu-id="011df-113">The following illustration shows how to initialize a color matrix to perform rotations about each of the three coordinate axes (red, green, blue):</span></span>  
  
 ![初始化一个颜色矩阵以执行有关三个轴的旋转。](./media/how-to-rotate-colors/rotation-about-three-axes.gif)  
  
## <a name="example"></a><span data-ttu-id="011df-115">示例</span><span class="sxs-lookup"><span data-stu-id="011df-115">Example</span></span>  
 <span data-ttu-id="011df-116">下面的示例将是一种颜色 （1，0，0.6） 和顺蓝色轴旋转 60 度的映像。</span><span class="sxs-lookup"><span data-stu-id="011df-116">The following example takes an image that is all one color (1, 0, 0.6) and applies a 60-degree rotation about the blue axis.</span></span> <span data-ttu-id="011df-117">中对红-绿平面平行的平面上旋转的角度扫出。</span><span class="sxs-lookup"><span data-stu-id="011df-117">The angle of the rotation is swept out in a plane that is parallel to the red-green plane.</span></span>  
  
 <span data-ttu-id="011df-118">下图显示在左侧和右侧的颜色旋转图像的原始图像：</span><span class="sxs-lookup"><span data-stu-id="011df-118">The following illustration shows the original image on the left and the color-rotated image on the right:</span></span>  
  
 ![显示原始图像和颜色旋转图像的图例。](./media/how-to-rotate-colors/original-color-rotated-images.png)  
  
 <span data-ttu-id="011df-120">下图显示了执行下面的代码中的颜色旋转的可视化效果：</span><span class="sxs-lookup"><span data-stu-id="011df-120">The following illustration shows a visualization of the color rotation performed in the following code:</span></span>
  
 ![显示颜色旋转的可视化效果的图例。](./media/how-to-rotate-colors/visualization-color-rotation.gif)  
  
 [!code-csharp[System.Drawing.RotateColors#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.RotateColors/CS/Form1.cs#1)]
 [!code-vb[System.Drawing.RotateColors#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.RotateColors/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="011df-122">编译代码</span><span class="sxs-lookup"><span data-stu-id="011df-122">Compiling the Code</span></span>  
 <span data-ttu-id="011df-123">前面的示例专用于 Windows 窗体，它需要 <xref:System.Windows.Forms.PaintEventArgs>`e`，后者是 <xref:System.Windows.Forms.Control.Paint> 事件处理程序的参数。</span><span class="sxs-lookup"><span data-stu-id="011df-123">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs>`e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span> <span data-ttu-id="011df-124">替换为`RotationInput.bmp`与图像文件名称和你的系统上有效的路径。</span><span class="sxs-lookup"><span data-stu-id="011df-124">Replace `RotationInput.bmp` with an image file name and path valid on your system.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="011df-125">请参阅</span><span class="sxs-lookup"><span data-stu-id="011df-125">See also</span></span>

- <xref:System.Drawing.Imaging.ColorMatrix>
- <xref:System.Drawing.Imaging.ImageAttributes>
- [<span data-ttu-id="011df-126">Windows 窗体中的图形和绘制</span><span class="sxs-lookup"><span data-stu-id="011df-126">Graphics and Drawing in Windows Forms</span></span>](graphics-and-drawing-in-windows-forms.md)
- [<span data-ttu-id="011df-127">对图像重新着色</span><span class="sxs-lookup"><span data-stu-id="011df-127">Recoloring Images</span></span>](recoloring-images.md)
