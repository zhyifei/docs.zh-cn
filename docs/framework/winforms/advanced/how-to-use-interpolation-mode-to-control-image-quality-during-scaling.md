---
title: "如何：缩放时使用插值模式控制图像质量"
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
- interpolation mode [Windows Forms], controlling image quality
- images [Windows Forms], scaling
- images [Windows Forms], controlling quality
ms.assetid: fde9bccf-8aa5-4b0d-ba4b-788740627b02
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e8bbc17b8344fca496dcf8f4077a69b6db1453c7
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-use-interpolation-mode-to-control-image-quality-during-scaling"></a><span data-ttu-id="24e1b-102">如何：缩放时使用插值模式控制图像质量</span><span class="sxs-lookup"><span data-stu-id="24e1b-102">How to: Use Interpolation Mode to Control Image Quality During Scaling</span></span>
<span data-ttu-id="24e1b-103">内插模式<xref:System.Drawing.Graphics>对象影响方式[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]刻度 （拉伸和收缩） 映像。</span><span class="sxs-lookup"><span data-stu-id="24e1b-103">The interpolation mode of a <xref:System.Drawing.Graphics> object influences the way [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] scales (stretches and shrinks) images.</span></span> <span data-ttu-id="24e1b-104"><xref:System.Drawing.Drawing2D.InterpolationMode>枚举定义多个内插模式，其中一些都显示在下面的列表：</span><span class="sxs-lookup"><span data-stu-id="24e1b-104">The <xref:System.Drawing.Drawing2D.InterpolationMode> enumeration defines several interpolation modes, some of which are shown in the following list:</span></span>  
  
-   <xref:System.Drawing.Drawing2D.InterpolationMode.NearestNeighbor>  
  
-   <xref:System.Drawing.Drawing2D.InterpolationMode.Bilinear>  
  
-   <xref:System.Drawing.Drawing2D.InterpolationMode.HighQualityBilinear>  
  
-   <xref:System.Drawing.Drawing2D.InterpolationMode.Bicubic>  
  
-   <xref:System.Drawing.Drawing2D.InterpolationMode.HighQualityBicubic>  
  
 <span data-ttu-id="24e1b-105">拉伸图像，原始映像中的每个像素必须将映射到更大的图像中的像素的组。</span><span class="sxs-lookup"><span data-stu-id="24e1b-105">To stretch an image, each pixel in the original image must be mapped to a group of pixels in the larger image.</span></span> <span data-ttu-id="24e1b-106">若要收缩映像，原始映像中的像素的组必须映射到较小的图像中的单一像素。</span><span class="sxs-lookup"><span data-stu-id="24e1b-106">To shrink an image, groups of pixels in the original image must be mapped to single pixels in the smaller image.</span></span> <span data-ttu-id="24e1b-107">执行这些映射的算法的有效性确定缩放图像的质量。</span><span class="sxs-lookup"><span data-stu-id="24e1b-107">The effectiveness of the algorithms that perform these mappings determines the quality of a scaled image.</span></span> <span data-ttu-id="24e1b-108">生成更高质量缩放的图像的算法往往需要进行更多的处理时间。</span><span class="sxs-lookup"><span data-stu-id="24e1b-108">Algorithms that produce higher-quality scaled images tend to require more processing time.</span></span> <span data-ttu-id="24e1b-109">在前面的列表中，<xref:System.Drawing.Drawing2D.InterpolationMode.NearestNeighbor>是最低质量模式和<xref:System.Drawing.Drawing2D.InterpolationMode.HighQualityBicubic>最高质量的方式。</span><span class="sxs-lookup"><span data-stu-id="24e1b-109">In the preceding list, <xref:System.Drawing.Drawing2D.InterpolationMode.NearestNeighbor> is the lowest-quality mode and <xref:System.Drawing.Drawing2D.InterpolationMode.HighQualityBicubic> is the highest-quality mode.</span></span>  
  
 <span data-ttu-id="24e1b-110">若要设置的插补模式，分配的成员之一<xref:System.Drawing.Drawing2D.InterpolationMode>枚举<xref:System.Drawing.Graphics.InterpolationMode%2A>属性<xref:System.Drawing.Graphics>对象。</span><span class="sxs-lookup"><span data-stu-id="24e1b-110">To set the interpolation mode, assign one of the members of the <xref:System.Drawing.Drawing2D.InterpolationMode> enumeration to the <xref:System.Drawing.Graphics.InterpolationMode%2A> property of a <xref:System.Drawing.Graphics> object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="24e1b-111">示例</span><span class="sxs-lookup"><span data-stu-id="24e1b-111">Example</span></span>  
 <span data-ttu-id="24e1b-112">下面的示例绘制图像，然后收缩具有三种不同内插模式的映像。</span><span class="sxs-lookup"><span data-stu-id="24e1b-112">The following example draws an image and then shrinks the image with three different interpolation modes.</span></span>  
  
 <span data-ttu-id="24e1b-113">下图显示原始图像和三个较小的图像。</span><span class="sxs-lookup"><span data-stu-id="24e1b-113">The following illustration shows the original image and the three smaller images.</span></span>  
  
 <span data-ttu-id="24e1b-114">![具有各种内插设置的图像](../../../../docs/framework/winforms/advanced/media/csgrapes1.png "csgrapes1")</span><span class="sxs-lookup"><span data-stu-id="24e1b-114">![Image with Varied Interpolation Settings](../../../../docs/framework/winforms/advanced/media/csgrapes1.png "csgrapes1")</span></span>  
  
 [!code-csharp[System.Drawing.WorkingWithImages#81](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#81)]
 [!code-vb[System.Drawing.WorkingWithImages#81](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#81)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="24e1b-115">编译代码</span><span class="sxs-lookup"><span data-stu-id="24e1b-115">Compiling the Code</span></span>  
 <span data-ttu-id="24e1b-116">前面的示例专用于 Windows 窗体，它需要 <xref:System.Windows.Forms.PaintEventArgs> `e`，后者是 <xref:System.Windows.Forms.Control.Paint> 事件处理程序的参数。</span><span class="sxs-lookup"><span data-stu-id="24e1b-116">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="24e1b-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="24e1b-117">See Also</span></span>  
 [<span data-ttu-id="24e1b-118">图像、位图和图元文件</span><span class="sxs-lookup"><span data-stu-id="24e1b-118">Images, Bitmaps, and Metafiles</span></span>](../../../../docs/framework/winforms/advanced/images-bitmaps-and-metafiles.md)  
 [<span data-ttu-id="24e1b-119">使用图像、位图、图标和图元文件</span><span class="sxs-lookup"><span data-stu-id="24e1b-119">Working with Images, Bitmaps, Icons, and Metafiles</span></span>](../../../../docs/framework/winforms/advanced/working-with-images-bitmaps-icons-and-metafiles.md)
