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
ms.openlocfilehash: cb3824d8a5a5674b83124301dbfbd5a3ba60effa
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/09/2019
ms.locfileid: "57720613"
---
# <a name="how-to-rotate-colors"></a><span data-ttu-id="f8b1f-102">如何：旋转颜色</span><span class="sxs-lookup"><span data-stu-id="f8b1f-102">How to: Rotate Colors</span></span>
<span data-ttu-id="f8b1f-103">四维颜色空间中的旋转很难直观显示。</span><span class="sxs-lookup"><span data-stu-id="f8b1f-103">Rotation in a four-dimensional color space is difficult to visualize.</span></span> <span data-ttu-id="f8b1f-104">我们可以轻松地实现旋转同意接受保持一个固定的颜色组件的可视化效果。</span><span class="sxs-lookup"><span data-stu-id="f8b1f-104">We can make it easier to visualize rotation by agreeing to keep one of the color components fixed.</span></span> <span data-ttu-id="f8b1f-105">假设我们同意将 alpha 分量固定在 1 （完全不透明）。</span><span class="sxs-lookup"><span data-stu-id="f8b1f-105">Suppose we agree to keep the alpha component fixed at 1 (fully opaque).</span></span> <span data-ttu-id="f8b1f-106">然后我们可以直观显示三维颜色空间具有红色、 绿色和蓝色的轴，如下图中所示。</span><span class="sxs-lookup"><span data-stu-id="f8b1f-106">Then we can visualize a three-dimensional color space with red, green, and blue axes as shown in the following illustration.</span></span>  
  
 <span data-ttu-id="f8b1f-107">![重新着色](./media/recoloring03.gif "recoloring03")</span><span class="sxs-lookup"><span data-stu-id="f8b1f-107">![Recoloring](./media/recoloring03.gif "recoloring03")</span></span>  
  
 <span data-ttu-id="f8b1f-108">一种颜色可视为在三维空间中点。</span><span class="sxs-lookup"><span data-stu-id="f8b1f-108">A color can be thought of as a point in 3-D space.</span></span> <span data-ttu-id="f8b1f-109">例如，空间中的点 （1，0，0） 表示的颜色为红色，并在空间中的点 （0、 1、 0） 表示绿色。</span><span class="sxs-lookup"><span data-stu-id="f8b1f-109">For example, the point (1, 0, 0) in space represents the color red, and the point (0, 1, 0) in space represents the color green.</span></span>  
  
 <span data-ttu-id="f8b1f-110">下图通过红-绿平面中的 60 度的角度显示旋转的颜色 （1，0，0） 意味着什么。</span><span class="sxs-lookup"><span data-stu-id="f8b1f-110">The following illustration shows what it means to rotate the color (1, 0, 0) through an angle of 60 degrees in the Red-Green plane.</span></span> <span data-ttu-id="f8b1f-111">在平面平行于红-绿平面旋转可以看作围绕蓝色轴的旋转。</span><span class="sxs-lookup"><span data-stu-id="f8b1f-111">Rotation in a plane parallel to the Red-Green plane can be thought of as rotation about the blue axis.</span></span>  
  
 <span data-ttu-id="f8b1f-112">![重新着色](./media/recoloring04.gif "recoloring04")</span><span class="sxs-lookup"><span data-stu-id="f8b1f-112">![Recoloring](./media/recoloring04.gif "recoloring04")</span></span>  
  
 <span data-ttu-id="f8b1f-113">下图显示了如何初始化颜色矩阵执行三个坐标轴 （红色、 绿色、 蓝色） 的每个旋转。</span><span class="sxs-lookup"><span data-stu-id="f8b1f-113">The following illustration shows how to initialize a color matrix to perform rotations about each of the three coordinate axes (red, green, blue).</span></span>  
  
 <span data-ttu-id="f8b1f-114">![重新着色](./media/recoloring05.gif "recoloring05")</span><span class="sxs-lookup"><span data-stu-id="f8b1f-114">![Recoloring](./media/recoloring05.gif "recoloring05")</span></span>  
  
## <a name="example"></a><span data-ttu-id="f8b1f-115">示例</span><span class="sxs-lookup"><span data-stu-id="f8b1f-115">Example</span></span>  
 <span data-ttu-id="f8b1f-116">下面的示例将是一种颜色 （1，0，0.6） 和顺蓝色轴旋转 60 度的映像。</span><span class="sxs-lookup"><span data-stu-id="f8b1f-116">The following example takes an image that is all one color (1, 0, 0.6) and applies a 60-degree rotation about the blue axis.</span></span> <span data-ttu-id="f8b1f-117">中对红-绿平面平行的平面上旋转的角度扫出。</span><span class="sxs-lookup"><span data-stu-id="f8b1f-117">The angle of the rotation is swept out in a plane that is parallel to the red-green plane.</span></span>  
  
 <span data-ttu-id="f8b1f-118">下图显示在左侧和右侧的颜色旋转图像的原始图像。</span><span class="sxs-lookup"><span data-stu-id="f8b1f-118">The following illustration shows the original image on the left and the color-rotated image on the right.</span></span>  
  
 <span data-ttu-id="f8b1f-119">![旋转颜色](./media/colortrans5.png "colortrans5")</span><span class="sxs-lookup"><span data-stu-id="f8b1f-119">![Rotate Colors](./media/colortrans5.png "colortrans5")</span></span>  
  
 <span data-ttu-id="f8b1f-120">下图显示了执行下面的代码中的颜色旋转的可视化效果。</span><span class="sxs-lookup"><span data-stu-id="f8b1f-120">The following illustration shows a visualization of the color rotation performed in the following code.</span></span>  
  
 <span data-ttu-id="f8b1f-121">![重新着色](./media/recoloring06.gif "recoloring06")</span><span class="sxs-lookup"><span data-stu-id="f8b1f-121">![Recoloring](./media/recoloring06.gif "recoloring06")</span></span>  
  
 [!code-csharp[System.Drawing.RotateColors#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.RotateColors/CS/Form1.cs#1)]
 [!code-vb[System.Drawing.RotateColors#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.RotateColors/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="f8b1f-122">编译代码</span><span class="sxs-lookup"><span data-stu-id="f8b1f-122">Compiling the Code</span></span>  
 <span data-ttu-id="f8b1f-123">前面的示例专用于 Windows 窗体，它需要 <xref:System.Windows.Forms.PaintEventArgs>`e`，后者是 <xref:System.Windows.Forms.Control.Paint> 事件处理程序的参数。</span><span class="sxs-lookup"><span data-stu-id="f8b1f-123">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs>`e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span> <span data-ttu-id="f8b1f-124">替换为`RotationInput.bmp`与图像文件名称和你的系统上有效的路径。</span><span class="sxs-lookup"><span data-stu-id="f8b1f-124">Replace `RotationInput.bmp` with an image file name and path valid on your system.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f8b1f-125">请参阅</span><span class="sxs-lookup"><span data-stu-id="f8b1f-125">See also</span></span>
- <xref:System.Drawing.Imaging.ColorMatrix>
- <xref:System.Drawing.Imaging.ImageAttributes>
- [<span data-ttu-id="f8b1f-126">Windows 窗体中的图形和绘制</span><span class="sxs-lookup"><span data-stu-id="f8b1f-126">Graphics and Drawing in Windows Forms</span></span>](graphics-and-drawing-in-windows-forms.md)
- [<span data-ttu-id="f8b1f-127">对图像重新着色</span><span class="sxs-lookup"><span data-stu-id="f8b1f-127">Recoloring Images</span></span>](recoloring-images.md)
