---
title: 如何：修剪颜色
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- colors [Windows Forms], transforming with color matrices
- colors [Windows Forms], shearing
ms.assetid: 0a424171-5b8b-45c4-afef-e9720a6c3e22
ms.openlocfilehash: 825e5a90ebb0d9df3b894ce7bd353e917b676939
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79142389"
---
# <a name="how-to-shear-colors"></a><span data-ttu-id="5a1a6-102">如何：修剪颜色</span><span class="sxs-lookup"><span data-stu-id="5a1a6-102">How to: Shear Colors</span></span>
<span data-ttu-id="5a1a6-103">剪切会增加或减少颜色分量，以与另一种颜色分量成正比。</span><span class="sxs-lookup"><span data-stu-id="5a1a6-103">Shearing increases or decreases a color component by an amount proportional to another color component.</span></span> <span data-ttu-id="5a1a6-104">例如，考虑红色分量增加蓝色分量值一半的转换。</span><span class="sxs-lookup"><span data-stu-id="5a1a6-104">For example, consider the transformation where the red component is increased by one half the value of the blue component.</span></span> <span data-ttu-id="5a1a6-105">在这样的转换下，颜色（0.2，0.5，1）将成为（0.7，0.5，1）。</span><span class="sxs-lookup"><span data-stu-id="5a1a6-105">Under such a transformation, the color (0.2, 0.5, 1) would become (0.7, 0.5, 1).</span></span> <span data-ttu-id="5a1a6-106">新的红色分量为 0.2 = （1/2）（1） = 0.7。</span><span class="sxs-lookup"><span data-stu-id="5a1a6-106">The new red component is 0.2 + (1/2)(1) = 0.7.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5a1a6-107">示例</span><span class="sxs-lookup"><span data-stu-id="5a1a6-107">Example</span></span>  
 <span data-ttu-id="5a1a6-108">下面的示例从文件 ColorBars4.bmp 构造对象<xref:System.Drawing.Image>。</span><span class="sxs-lookup"><span data-stu-id="5a1a6-108">The following example constructs an <xref:System.Drawing.Image> object from the file ColorBars4.bmp.</span></span> <span data-ttu-id="5a1a6-109">然后，代码将前一段中描述的剪切变换应用于图像中的每个像素。</span><span class="sxs-lookup"><span data-stu-id="5a1a6-109">Then the code applies the shearing transformation described in the preceding paragraph to each pixel in the image.</span></span>  
  
 <span data-ttu-id="5a1a6-110">下图显示了左侧的原始图像和右侧的谢线图像：</span><span class="sxs-lookup"><span data-stu-id="5a1a6-110">The following illustration shows the original image on the left and the sheared image on the right:</span></span>
  
 ![两个正方形，带彩色条纹并排显示原始图像和谢线图像。](./media/how-to-shear-colors/original-image-sheared-image.png)  
  
 <span data-ttu-id="5a1a6-112">下表列出了剪切变换前后四个条形的颜色矢量。</span><span class="sxs-lookup"><span data-stu-id="5a1a6-112">The following table lists the color vectors for the four bars before and after the shearing transformation.</span></span>  
  
|<span data-ttu-id="5a1a6-113">原始</span><span class="sxs-lookup"><span data-stu-id="5a1a6-113">Original</span></span>|<span data-ttu-id="5a1a6-114">剪切</span><span class="sxs-lookup"><span data-stu-id="5a1a6-114">Sheared</span></span>|  
|--------------|-------------|  
|<span data-ttu-id="5a1a6-115">(0, 0, 1, 1)</span><span class="sxs-lookup"><span data-stu-id="5a1a6-115">(0, 0, 1, 1)</span></span>|<span data-ttu-id="5a1a6-116">(0.5, 0, 1, 1)</span><span class="sxs-lookup"><span data-stu-id="5a1a6-116">(0.5, 0, 1, 1)</span></span>|  
|<span data-ttu-id="5a1a6-117">(0.5, 1, 0.5, 1)</span><span class="sxs-lookup"><span data-stu-id="5a1a6-117">(0.5, 1, 0.5, 1)</span></span>|<span data-ttu-id="5a1a6-118">(0.75, 1, 0.5, 1)</span><span class="sxs-lookup"><span data-stu-id="5a1a6-118">(0.75, 1, 0.5, 1)</span></span>|  
|<span data-ttu-id="5a1a6-119">(1, 1, 0, 1)</span><span class="sxs-lookup"><span data-stu-id="5a1a6-119">(1, 1, 0, 1)</span></span>|<span data-ttu-id="5a1a6-120">(1, 1, 0, 1)</span><span class="sxs-lookup"><span data-stu-id="5a1a6-120">(1, 1, 0, 1)</span></span>|  
|<span data-ttu-id="5a1a6-121">(0.4, 0.4, 0.4, 1)</span><span class="sxs-lookup"><span data-stu-id="5a1a6-121">(0.4, 0.4, 0.4, 1)</span></span>|<span data-ttu-id="5a1a6-122">(0.6, 0.4, 0.4, 1)</span><span class="sxs-lookup"><span data-stu-id="5a1a6-122">(0.6, 0.4, 0.4, 1)</span></span>|  
  
 [!code-csharp[System.Drawing.Misc3#9](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.Misc3/CS/Form1.cs#9)]
 [!code-vb[System.Drawing.Misc3#9](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.Misc3/VB/Form1.vb#9)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="5a1a6-123">编译代码</span><span class="sxs-lookup"><span data-stu-id="5a1a6-123">Compiling the Code</span></span>  
 <span data-ttu-id="5a1a6-124">前面的示例设计用于 Windows 窗体，它需要<xref:System.Windows.Forms.PaintEventArgs>`e`，这是事件处理程序的<xref:System.Windows.Forms.Control.Paint>参数。</span><span class="sxs-lookup"><span data-stu-id="5a1a6-124">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span> <span data-ttu-id="5a1a6-125">替换为`ColorBars.bmp`系统上有效的图像名称和路径。</span><span class="sxs-lookup"><span data-stu-id="5a1a6-125">Replace `ColorBars.bmp` with an image name and path valid on your system.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5a1a6-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5a1a6-126">See also</span></span>

- <xref:System.Drawing.Imaging.ColorMatrix>
- <xref:System.Drawing.Imaging.ImageAttributes>
- [<span data-ttu-id="5a1a6-127">Windows 窗体中的图形和绘制</span><span class="sxs-lookup"><span data-stu-id="5a1a6-127">Graphics and Drawing in Windows Forms</span></span>](graphics-and-drawing-in-windows-forms.md)
- [<span data-ttu-id="5a1a6-128">对图像重新着色</span><span class="sxs-lookup"><span data-stu-id="5a1a6-128">Recoloring Images</span></span>](recoloring-images.md)
