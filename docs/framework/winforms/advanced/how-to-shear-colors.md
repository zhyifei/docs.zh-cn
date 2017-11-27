---
title: "如何：修剪颜色"
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
- colors [Windows Forms], transforming with color matrices
- colors [Windows Forms], shearing
ms.assetid: 0a424171-5b8b-45c4-afef-e9720a6c3e22
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 35f89bb5d87ef58c5ecda7be4cb9fb41da08e8a8
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-shear-colors"></a><span data-ttu-id="2ac4f-102">如何：修剪颜色</span><span class="sxs-lookup"><span data-stu-id="2ac4f-102">How to: Shear Colors</span></span>
<span data-ttu-id="2ac4f-103">剪切增加或减少量将另一个颜色组件一定比例的颜色组件。</span><span class="sxs-lookup"><span data-stu-id="2ac4f-103">Shearing increases or decreases a color component by an amount proportional to another color component.</span></span> <span data-ttu-id="2ac4f-104">例如，考虑其中红色组件增加了一个半个蓝色分量的值的转换。</span><span class="sxs-lookup"><span data-stu-id="2ac4f-104">For example, consider the transformation where the red component is increased by one half the value of the blue component.</span></span> <span data-ttu-id="2ac4f-105">在此类转换，（0.2、 0.5，1） 的颜色将变为 （0.7、 0.5，1）。</span><span class="sxs-lookup"><span data-stu-id="2ac4f-105">Under such a transformation, the color (0.2, 0.5, 1) would become (0.7, 0.5, 1).</span></span> <span data-ttu-id="2ac4f-106">新的红色组件是 0.2 + (1/2)(1) = 0.7。</span><span class="sxs-lookup"><span data-stu-id="2ac4f-106">The new red component is 0.2 + (1/2)(1) = 0.7.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2ac4f-107">示例</span><span class="sxs-lookup"><span data-stu-id="2ac4f-107">Example</span></span>  
 <span data-ttu-id="2ac4f-108">下面的示例构造<xref:System.Drawing.Image>从文件 ColorBars4.bmp 的对象。</span><span class="sxs-lookup"><span data-stu-id="2ac4f-108">The following example constructs an <xref:System.Drawing.Image> object from the file ColorBars4.bmp.</span></span> <span data-ttu-id="2ac4f-109">然后该代码将应用到图像中的每个像素上一段中所述的倾斜转换。</span><span class="sxs-lookup"><span data-stu-id="2ac4f-109">Then the code applies the shearing transformation described in the preceding paragraph to each pixel in the image.</span></span>  
  
 <span data-ttu-id="2ac4f-110">下图右侧显示在左侧的原始映像和剪切后的图像。</span><span class="sxs-lookup"><span data-stu-id="2ac4f-110">The following illustration shows the original image on the left and the sheared image on the right.</span></span>  
  
 <span data-ttu-id="2ac4f-111">![切变颜色](../../../../docs/framework/winforms/advanced/media/colortrans6.png "colortrans6")</span><span class="sxs-lookup"><span data-stu-id="2ac4f-111">![Shear Colors](../../../../docs/framework/winforms/advanced/media/colortrans6.png "colortrans6")</span></span>  
  
 <span data-ttu-id="2ac4f-112">下表列出的四个栏的颜色矢量之前和之后的倾斜转换。</span><span class="sxs-lookup"><span data-stu-id="2ac4f-112">The following table lists the color vectors for the four bars before and after the shearing transformation.</span></span>  
  
|<span data-ttu-id="2ac4f-113">原始</span><span class="sxs-lookup"><span data-stu-id="2ac4f-113">Original</span></span>|<span data-ttu-id="2ac4f-114">剪切</span><span class="sxs-lookup"><span data-stu-id="2ac4f-114">Sheared</span></span>|  
|--------------|-------------|  
|<span data-ttu-id="2ac4f-115">(0, 0, 1, 1)</span><span class="sxs-lookup"><span data-stu-id="2ac4f-115">(0, 0, 1, 1)</span></span>|<span data-ttu-id="2ac4f-116">(0.5, 0, 1, 1)</span><span class="sxs-lookup"><span data-stu-id="2ac4f-116">(0.5, 0, 1, 1)</span></span>|  
|<span data-ttu-id="2ac4f-117">(0.5, 1, 0.5, 1)</span><span class="sxs-lookup"><span data-stu-id="2ac4f-117">(0.5, 1, 0.5, 1)</span></span>|<span data-ttu-id="2ac4f-118">(0.75, 1, 0.5, 1)</span><span class="sxs-lookup"><span data-stu-id="2ac4f-118">(0.75, 1, 0.5, 1)</span></span>|  
|<span data-ttu-id="2ac4f-119">(1, 1, 0, 1)</span><span class="sxs-lookup"><span data-stu-id="2ac4f-119">(1, 1, 0, 1)</span></span>|<span data-ttu-id="2ac4f-120">(1, 1, 0, 1)</span><span class="sxs-lookup"><span data-stu-id="2ac4f-120">(1, 1, 0, 1)</span></span>|  
|<span data-ttu-id="2ac4f-121">(0.4, 0.4, 0.4, 1)</span><span class="sxs-lookup"><span data-stu-id="2ac4f-121">(0.4, 0.4, 0.4, 1)</span></span>|<span data-ttu-id="2ac4f-122">(0.6, 0.4, 0.4, 1)</span><span class="sxs-lookup"><span data-stu-id="2ac4f-122">(0.6, 0.4, 0.4, 1)</span></span>|  
  
 [!code-csharp[System.Drawing.Misc3#9](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.Misc3/CS/Form1.cs#9)]
 [!code-vb[System.Drawing.Misc3#9](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.Misc3/VB/Form1.vb#9)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="2ac4f-123">编译代码</span><span class="sxs-lookup"><span data-stu-id="2ac4f-123">Compiling the Code</span></span>  
 <span data-ttu-id="2ac4f-124">前面的示例专用于 Windows 窗体，它需要 <xref:System.Windows.Forms.PaintEventArgs>`e`，后者是 <xref:System.Windows.Forms.Control.Paint> 事件处理程序的参数。</span><span class="sxs-lookup"><span data-stu-id="2ac4f-124">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs>`e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span> <span data-ttu-id="2ac4f-125">替换`ColorBars.bmp`用的映像名称和你系统上有效的路径。</span><span class="sxs-lookup"><span data-stu-id="2ac4f-125">Replace `ColorBars.bmp` with an image name and path valid on your system.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2ac4f-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2ac4f-126">See Also</span></span>  
 <xref:System.Drawing.Imaging.ColorMatrix>  
 <xref:System.Drawing.Imaging.ImageAttributes>  
 [<span data-ttu-id="2ac4f-127">Windows 窗体中的图形和绘制</span><span class="sxs-lookup"><span data-stu-id="2ac4f-127">Graphics and Drawing in Windows Forms</span></span>](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)  
 [<span data-ttu-id="2ac4f-128">对图像重新着色</span><span class="sxs-lookup"><span data-stu-id="2ac4f-128">Recoloring Images</span></span>](../../../../docs/framework/winforms/advanced/recoloring-images.md)
