---
title: 如何：切变颜色
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- colors [Windows Forms], transforming with color matrices
- colors [Windows Forms], shearing
ms.assetid: 0a424171-5b8b-45c4-afef-e9720a6c3e22
ms.openlocfilehash: eff468e5761038723e16eddf84bdcf8849ac30d1
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/09/2019
ms.locfileid: "57720216"
---
# <a name="how-to-shear-colors"></a><span data-ttu-id="03505-102">如何：切变颜色</span><span class="sxs-lookup"><span data-stu-id="03505-102">How to: Shear Colors</span></span>
<span data-ttu-id="03505-103">修剪每增加或减少到另一个颜色组件比例颜色组件。</span><span class="sxs-lookup"><span data-stu-id="03505-103">Shearing increases or decreases a color component by an amount proportional to another color component.</span></span> <span data-ttu-id="03505-104">例如，考虑红色组件加一半的蓝色组件值的转换。</span><span class="sxs-lookup"><span data-stu-id="03505-104">For example, consider the transformation where the red component is increased by one half the value of the blue component.</span></span> <span data-ttu-id="03505-105">在这种转换 （0.2，0.5，1） 的颜色将变为 （0.7，0.5，1）。</span><span class="sxs-lookup"><span data-stu-id="03505-105">Under such a transformation, the color (0.2, 0.5, 1) would become (0.7, 0.5, 1).</span></span> <span data-ttu-id="03505-106">新的红色分量为 0.2 + (1/2)(1) = 0.7。</span><span class="sxs-lookup"><span data-stu-id="03505-106">The new red component is 0.2 + (1/2)(1) = 0.7.</span></span>  
  
## <a name="example"></a><span data-ttu-id="03505-107">示例</span><span class="sxs-lookup"><span data-stu-id="03505-107">Example</span></span>  
 <span data-ttu-id="03505-108">下面的示例构造<xref:System.Drawing.Image>ColorBars4.bmp 文件中的对象。</span><span class="sxs-lookup"><span data-stu-id="03505-108">The following example constructs an <xref:System.Drawing.Image> object from the file ColorBars4.bmp.</span></span> <span data-ttu-id="03505-109">然后该代码将应用到图像中的每个像素上一段中所述的倾斜转换。</span><span class="sxs-lookup"><span data-stu-id="03505-109">Then the code applies the shearing transformation described in the preceding paragraph to each pixel in the image.</span></span>  
  
 <span data-ttu-id="03505-110">下图显示在右侧左侧上的原始映像和剪切后的图像。</span><span class="sxs-lookup"><span data-stu-id="03505-110">The following illustration shows the original image on the left and the sheared image on the right.</span></span>  
  
 <span data-ttu-id="03505-111">![切变颜色](./media/colortrans6.png "colortrans6")</span><span class="sxs-lookup"><span data-stu-id="03505-111">![Shear Colors](./media/colortrans6.png "colortrans6")</span></span>  
  
 <span data-ttu-id="03505-112">下表列出了四个条形的颜色矢量之前和之后的倾斜转换。</span><span class="sxs-lookup"><span data-stu-id="03505-112">The following table lists the color vectors for the four bars before and after the shearing transformation.</span></span>  
  
|<span data-ttu-id="03505-113">原始</span><span class="sxs-lookup"><span data-stu-id="03505-113">Original</span></span>|<span data-ttu-id="03505-114">剪切</span><span class="sxs-lookup"><span data-stu-id="03505-114">Sheared</span></span>|  
|--------------|-------------|  
|<span data-ttu-id="03505-115">(0, 0, 1, 1)</span><span class="sxs-lookup"><span data-stu-id="03505-115">(0, 0, 1, 1)</span></span>|<span data-ttu-id="03505-116">(0.5, 0, 1, 1)</span><span class="sxs-lookup"><span data-stu-id="03505-116">(0.5, 0, 1, 1)</span></span>|  
|<span data-ttu-id="03505-117">(0.5, 1, 0.5, 1)</span><span class="sxs-lookup"><span data-stu-id="03505-117">(0.5, 1, 0.5, 1)</span></span>|<span data-ttu-id="03505-118">(0.75, 1, 0.5, 1)</span><span class="sxs-lookup"><span data-stu-id="03505-118">(0.75, 1, 0.5, 1)</span></span>|  
|<span data-ttu-id="03505-119">(1, 1, 0, 1)</span><span class="sxs-lookup"><span data-stu-id="03505-119">(1, 1, 0, 1)</span></span>|<span data-ttu-id="03505-120">(1, 1, 0, 1)</span><span class="sxs-lookup"><span data-stu-id="03505-120">(1, 1, 0, 1)</span></span>|  
|<span data-ttu-id="03505-121">(0.4, 0.4, 0.4, 1)</span><span class="sxs-lookup"><span data-stu-id="03505-121">(0.4, 0.4, 0.4, 1)</span></span>|<span data-ttu-id="03505-122">(0.6, 0.4, 0.4, 1)</span><span class="sxs-lookup"><span data-stu-id="03505-122">(0.6, 0.4, 0.4, 1)</span></span>|  
  
 [!code-csharp[System.Drawing.Misc3#9](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.Misc3/CS/Form1.cs#9)]
 [!code-vb[System.Drawing.Misc3#9](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.Misc3/VB/Form1.vb#9)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="03505-123">编译代码</span><span class="sxs-lookup"><span data-stu-id="03505-123">Compiling the Code</span></span>  
 <span data-ttu-id="03505-124">前面的示例专用于 Windows 窗体，它需要 <xref:System.Windows.Forms.PaintEventArgs>`e`，后者是 <xref:System.Windows.Forms.Control.Paint> 事件处理程序的参数。</span><span class="sxs-lookup"><span data-stu-id="03505-124">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs>`e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span> <span data-ttu-id="03505-125">替换为`ColorBars.bmp`用的映像名称和路径在您的系统上有效。</span><span class="sxs-lookup"><span data-stu-id="03505-125">Replace `ColorBars.bmp` with an image name and path valid on your system.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="03505-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="03505-126">See also</span></span>
- <xref:System.Drawing.Imaging.ColorMatrix>
- <xref:System.Drawing.Imaging.ImageAttributes>
- [<span data-ttu-id="03505-127">Windows 窗体中的图形和绘制</span><span class="sxs-lookup"><span data-stu-id="03505-127">Graphics and Drawing in Windows Forms</span></span>](graphics-and-drawing-in-windows-forms.md)
- [<span data-ttu-id="03505-128">对图像重新着色</span><span class="sxs-lookup"><span data-stu-id="03505-128">Recoloring Images</span></span>](recoloring-images.md)
