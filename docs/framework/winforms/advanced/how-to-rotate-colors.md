---
title: "如何：旋转颜色"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- colors [Windows Forms], rotating
- examples [Windows Forms], rotating colors
ms.assetid: e2e4c300-159c-4f4a-9b56-103b0f7cbc05
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 81b022011bd5613b8e956aa83482d2836508a4f1
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-rotate-colors"></a><span data-ttu-id="bd49e-102">如何：旋转颜色</span><span class="sxs-lookup"><span data-stu-id="bd49e-102">How to: Rotate Colors</span></span>
<span data-ttu-id="bd49e-103">四维颜色空间中的旋转很难直观显示。</span><span class="sxs-lookup"><span data-stu-id="bd49e-103">Rotation in a four-dimensional color space is difficult to visualize.</span></span> <span data-ttu-id="bd49e-104">我们可以更加轻松地实现旋转同意保持一个固定的颜色组件的可视化效果。</span><span class="sxs-lookup"><span data-stu-id="bd49e-104">We can make it easier to visualize rotation by agreeing to keep one of the color components fixed.</span></span> <span data-ttu-id="bd49e-105">假设我们同意将 alpha 分量固定为 1 （完全不透明）。</span><span class="sxs-lookup"><span data-stu-id="bd49e-105">Suppose we agree to keep the alpha component fixed at 1 (fully opaque).</span></span> <span data-ttu-id="bd49e-106">然后我们可以可视化三维颜色空间红色、 绿色和蓝色轴与下图中所示。</span><span class="sxs-lookup"><span data-stu-id="bd49e-106">Then we can visualize a three-dimensional color space with red, green, and blue axes as shown in the following illustration.</span></span>  
  
 <span data-ttu-id="bd49e-107">![重新着色](../../../../docs/framework/winforms/advanced/media/recoloring03.gif "recoloring03")</span><span class="sxs-lookup"><span data-stu-id="bd49e-107">![Recoloring](../../../../docs/framework/winforms/advanced/media/recoloring03.gif "recoloring03")</span></span>  
  
 <span data-ttu-id="bd49e-108">一种颜色可视为在三维空间中的点。</span><span class="sxs-lookup"><span data-stu-id="bd49e-108">A color can be thought of as a point in 3-D space.</span></span> <span data-ttu-id="bd49e-109">例如，在空间中的点 （1，0，0） 表示的颜色为红色，并在空间中的点 （0、 1、 0） 表示绿色的颜色。</span><span class="sxs-lookup"><span data-stu-id="bd49e-109">For example, the point (1, 0, 0) in space represents the color red, and the point (0, 1, 0) in space represents the color green.</span></span>  
  
 <span data-ttu-id="bd49e-110">下图通过红-绿平面中的 60 度的角度显示要旋转的颜色 （1，0，0） 意味着什么。</span><span class="sxs-lookup"><span data-stu-id="bd49e-110">The following illustration shows what it means to rotate the color (1, 0, 0) through an angle of 60 degrees in the Red-Green plane.</span></span> <span data-ttu-id="bd49e-111">在平面并行于红-绿平面中的旋转可以看作围绕蓝色轴的旋转。</span><span class="sxs-lookup"><span data-stu-id="bd49e-111">Rotation in a plane parallel to the Red-Green plane can be thought of as rotation about the blue axis.</span></span>  
  
 <span data-ttu-id="bd49e-112">![重新着色](../../../../docs/framework/winforms/advanced/media/recoloring04.gif "recoloring04")</span><span class="sxs-lookup"><span data-stu-id="bd49e-112">![Recoloring](../../../../docs/framework/winforms/advanced/media/recoloring04.gif "recoloring04")</span></span>  
  
 <span data-ttu-id="bd49e-113">下图演示如何初始化颜色矩阵对，以执行有关每个 （红色、 绿色、 蓝色） 的三个坐标轴的旋转。</span><span class="sxs-lookup"><span data-stu-id="bd49e-113">The following illustration shows how to initialize a color matrix to perform rotations about each of the three coordinate axes (red, green, blue).</span></span>  
  
 <span data-ttu-id="bd49e-114">![重新着色](../../../../docs/framework/winforms/advanced/media/recoloring05.gif "recoloring05")</span><span class="sxs-lookup"><span data-stu-id="bd49e-114">![Recoloring](../../../../docs/framework/winforms/advanced/media/recoloring05.gif "recoloring05")</span></span>  
  
## <a name="example"></a><span data-ttu-id="bd49e-115">示例</span><span class="sxs-lookup"><span data-stu-id="bd49e-115">Example</span></span>  
 <span data-ttu-id="bd49e-116">下面的示例将一种颜色 （1、 0、 0.6） 和有关蓝色轴旋转 60 度的映像。</span><span class="sxs-lookup"><span data-stu-id="bd49e-116">The following example takes an image that is all one color (1, 0, 0.6) and applies a 60-degree rotation about the blue axis.</span></span> <span data-ttu-id="bd49e-117">在类似于红-绿平面的平面上的旋转角度扫出。</span><span class="sxs-lookup"><span data-stu-id="bd49e-117">The angle of the rotation is swept out in a plane that is parallel to the red-green plane.</span></span>  
  
 <span data-ttu-id="bd49e-118">下图显示在左侧和右侧旋转颜色后的图像的原始图像。</span><span class="sxs-lookup"><span data-stu-id="bd49e-118">The following illustration shows the original image on the left and the color-rotated image on the right.</span></span>  
  
 <span data-ttu-id="bd49e-119">![旋转颜色](../../../../docs/framework/winforms/advanced/media/colortrans5.png "colortrans5")</span><span class="sxs-lookup"><span data-stu-id="bd49e-119">![Rotate Colors](../../../../docs/framework/winforms/advanced/media/colortrans5.png "colortrans5")</span></span>  
  
 <span data-ttu-id="bd49e-120">下图显示在下面的代码中执行的颜色旋转可视化效果。</span><span class="sxs-lookup"><span data-stu-id="bd49e-120">The following illustration shows a visualization of the color rotation performed in the following code.</span></span>  
  
 <span data-ttu-id="bd49e-121">![重新着色](../../../../docs/framework/winforms/advanced/media/recoloring06.gif "recoloring06")</span><span class="sxs-lookup"><span data-stu-id="bd49e-121">![Recoloring](../../../../docs/framework/winforms/advanced/media/recoloring06.gif "recoloring06")</span></span>  
  
 [!code-csharp[System.Drawing.RotateColors#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.RotateColors/CS/Form1.cs#1)]
 [!code-vb[System.Drawing.RotateColors#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.RotateColors/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="bd49e-122">编译代码</span><span class="sxs-lookup"><span data-stu-id="bd49e-122">Compiling the Code</span></span>  
 <span data-ttu-id="bd49e-123">前面的示例专用于 Windows 窗体，并且它需要<xref:System.Windows.Forms.PaintEventArgs> `e`，这是一个参数的<xref:System.Windows.Forms.Control.Paint>事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="bd49e-123">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs>`e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span> <span data-ttu-id="bd49e-124">替换`RotationInput.bmp`用的图像文件名称和你系统上有效的路径。</span><span class="sxs-lookup"><span data-stu-id="bd49e-124">Replace `RotationInput.bmp` with an image file name and path valid on your system.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bd49e-125">请参阅</span><span class="sxs-lookup"><span data-stu-id="bd49e-125">See Also</span></span>  
 <xref:System.Drawing.Imaging.ColorMatrix>  
 <xref:System.Drawing.Imaging.ImageAttributes>  
 [<span data-ttu-id="bd49e-126">Windows 窗体中的图形和绘制</span><span class="sxs-lookup"><span data-stu-id="bd49e-126">Graphics and Drawing in Windows Forms</span></span>](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)  
 [<span data-ttu-id="bd49e-127">对图像重新着色</span><span class="sxs-lookup"><span data-stu-id="bd49e-127">Recoloring Images</span></span>](../../../../docs/framework/winforms/advanced/recoloring-images.md)
