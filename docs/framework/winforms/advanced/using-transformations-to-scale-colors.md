---
title: "使用转换来调整颜色"
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
- transformations [Windows Forms], for scaling colors
- colors [Windows Forms], scaling
ms.assetid: df23c887-7fd6-4b15-ad94-e30b5bd4b849
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: a4584b74cd7a394f7dd04d0cfba150b907ca7c82
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="using-transformations-to-scale-colors"></a><span data-ttu-id="6dbf7-102">使用转换来调整颜色</span><span class="sxs-lookup"><span data-stu-id="6dbf7-102">Using Transformations to Scale Colors</span></span>
<span data-ttu-id="6dbf7-103">缩放变换乘以一个或多个由大量的四个颜色组件。</span><span class="sxs-lookup"><span data-stu-id="6dbf7-103">A scaling transformation multiplies one or more of the four color components by a number.</span></span> <span data-ttu-id="6dbf7-104">下表给出颜色矩阵条目，用于表示缩放。</span><span class="sxs-lookup"><span data-stu-id="6dbf7-104">The color matrix entries that represent scaling are given in the following table.</span></span>  
  
|<span data-ttu-id="6dbf7-105">组件可按比例</span><span class="sxs-lookup"><span data-stu-id="6dbf7-105">Component to be scaled</span></span>|<span data-ttu-id="6dbf7-106">矩阵条目</span><span class="sxs-lookup"><span data-stu-id="6dbf7-106">Matrix entry</span></span>|  
|----------------------------|------------------|  
|<span data-ttu-id="6dbf7-107">红色</span><span class="sxs-lookup"><span data-stu-id="6dbf7-107">Red</span></span>|<span data-ttu-id="6dbf7-108">[0][0]</span><span class="sxs-lookup"><span data-stu-id="6dbf7-108">[0][0]</span></span>|  
|<span data-ttu-id="6dbf7-109">绿色</span><span class="sxs-lookup"><span data-stu-id="6dbf7-109">Green</span></span>|<span data-ttu-id="6dbf7-110">[1][1]</span><span class="sxs-lookup"><span data-stu-id="6dbf7-110">[1][1]</span></span>|  
|<span data-ttu-id="6dbf7-111">蓝色</span><span class="sxs-lookup"><span data-stu-id="6dbf7-111">Blue</span></span>|<span data-ttu-id="6dbf7-112">[2][2]</span><span class="sxs-lookup"><span data-stu-id="6dbf7-112">[2][2]</span></span>|  
|<span data-ttu-id="6dbf7-113">Alpha</span><span class="sxs-lookup"><span data-stu-id="6dbf7-113">Alpha</span></span>|<span data-ttu-id="6dbf7-114">[3][3]</span><span class="sxs-lookup"><span data-stu-id="6dbf7-114">[3][3]</span></span>|  
  
## <a name="scaling-one-color"></a><span data-ttu-id="6dbf7-115">缩放的一种颜色</span><span class="sxs-lookup"><span data-stu-id="6dbf7-115">Scaling One Color</span></span>  
 <span data-ttu-id="6dbf7-116">下面的示例构造<xref:System.Drawing.Image>从文件 ColorBars2.bmp 的对象。</span><span class="sxs-lookup"><span data-stu-id="6dbf7-116">The following example constructs an <xref:System.Drawing.Image> object from the file ColorBars2.bmp.</span></span> <span data-ttu-id="6dbf7-117">然后代码蓝色分量每个像素的图像中的 2 倍。</span><span class="sxs-lookup"><span data-stu-id="6dbf7-117">Then the code scales the blue component of each pixel in the image by a factor of 2.</span></span> <span data-ttu-id="6dbf7-118">转换后的图像旁边绘制原始图像。</span><span class="sxs-lookup"><span data-stu-id="6dbf7-118">The original image is drawn alongside the transformed image.</span></span>  
  
 [!code-csharp[System.Drawing.RecoloringImages#41](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.RecoloringImages/CS/Class1.cs#41)]
 [!code-vb[System.Drawing.RecoloringImages#41](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.RecoloringImages/VB/Class1.vb#41)]  
  
 <span data-ttu-id="6dbf7-119">下图右侧显示在左侧的原始映像和缩放的图像。</span><span class="sxs-lookup"><span data-stu-id="6dbf7-119">The following illustration shows the original image on the left and the scaled image on the right.</span></span>  
  
 <span data-ttu-id="6dbf7-120">![调整颜色](../../../../docs/framework/winforms/advanced/media/colortrans3.png "colortrans3")</span><span class="sxs-lookup"><span data-stu-id="6dbf7-120">![Scale Colors](../../../../docs/framework/winforms/advanced/media/colortrans3.png "colortrans3")</span></span>  
  
 <span data-ttu-id="6dbf7-121">下表列出的四个栏的颜色矢量之前和之后的蓝色缩放。</span><span class="sxs-lookup"><span data-stu-id="6dbf7-121">The following table lists the color vectors for the four bars before and after the blue scaling.</span></span> <span data-ttu-id="6dbf7-122">请注意，第四个颜色栏中的蓝色组件发送给 0.6 了从 0.8。</span><span class="sxs-lookup"><span data-stu-id="6dbf7-122">Note that the blue component in the fourth color bar went from 0.8 to 0.6.</span></span> <span data-ttu-id="6dbf7-123">这是因为[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]保留仅结果的小数部分。</span><span class="sxs-lookup"><span data-stu-id="6dbf7-123">That is because [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] retains only the fractional part of the result.</span></span> <span data-ttu-id="6dbf7-124">例如，(2)(0.8) = 1.6 版和 1.6 的小数部分为 0.6。</span><span class="sxs-lookup"><span data-stu-id="6dbf7-124">For example, (2)(0.8) = 1.6, and the fractional part of 1.6 is 0.6.</span></span> <span data-ttu-id="6dbf7-125">保留仅的小数部分可确保结果也始终在间隔 [0，1]。</span><span class="sxs-lookup"><span data-stu-id="6dbf7-125">Retaining only the fractional part ensures that the result is always in the interval [0, 1].</span></span>  
  
|<span data-ttu-id="6dbf7-126">原始</span><span class="sxs-lookup"><span data-stu-id="6dbf7-126">Original</span></span>|<span data-ttu-id="6dbf7-127">缩放</span><span class="sxs-lookup"><span data-stu-id="6dbf7-127">Scaled</span></span>|  
|--------------|------------|  
|<span data-ttu-id="6dbf7-128">(0.4, 0.4, 0.4, 1)</span><span class="sxs-lookup"><span data-stu-id="6dbf7-128">(0.4, 0.4, 0.4, 1)</span></span>|<span data-ttu-id="6dbf7-129">(0.4, 0.4, 0.8, 1)</span><span class="sxs-lookup"><span data-stu-id="6dbf7-129">(0.4, 0.4, 0.8, 1)</span></span>|  
|<span data-ttu-id="6dbf7-130">(0.4, 0.2, 0.2, 1)</span><span class="sxs-lookup"><span data-stu-id="6dbf7-130">(0.4, 0.2, 0.2, 1)</span></span>|<span data-ttu-id="6dbf7-131">(0.4, 0.2, 0.4, 1)</span><span class="sxs-lookup"><span data-stu-id="6dbf7-131">(0.4, 0.2, 0.4, 1)</span></span>|  
|<span data-ttu-id="6dbf7-132">(0.2, 0.4, 0.2, 1)</span><span class="sxs-lookup"><span data-stu-id="6dbf7-132">(0.2, 0.4, 0.2, 1)</span></span>|<span data-ttu-id="6dbf7-133">(0.2, 0.4, 0.4, 1)</span><span class="sxs-lookup"><span data-stu-id="6dbf7-133">(0.2, 0.4, 0.4, 1)</span></span>|  
|<span data-ttu-id="6dbf7-134">(0.4, 0.4, 0.8, 1)</span><span class="sxs-lookup"><span data-stu-id="6dbf7-134">(0.4, 0.4, 0.8, 1)</span></span>|<span data-ttu-id="6dbf7-135">(0.4, 0.4, 0.6, 1)</span><span class="sxs-lookup"><span data-stu-id="6dbf7-135">(0.4, 0.4, 0.6, 1)</span></span>|  
  
## <a name="scaling-multiple-colors"></a><span data-ttu-id="6dbf7-136">缩放多个颜色</span><span class="sxs-lookup"><span data-stu-id="6dbf7-136">Scaling Multiple Colors</span></span>  
 <span data-ttu-id="6dbf7-137">下面的示例构造<xref:System.Drawing.Image>从文件 ColorBars2.bmp 的对象。</span><span class="sxs-lookup"><span data-stu-id="6dbf7-137">The following example constructs an <xref:System.Drawing.Image> object from the file ColorBars2.bmp.</span></span> <span data-ttu-id="6dbf7-138">然后，该代码缩放图像中的每个像素的红色、 绿色和蓝色组件。</span><span class="sxs-lookup"><span data-stu-id="6dbf7-138">Then the code scales the red, green, and blue components of each pixel in the image.</span></span> <span data-ttu-id="6dbf7-139">红色的组件按比例缩小 25%、 绿色组件按比例缩小 35%和蓝色分量缩小了 50%。</span><span class="sxs-lookup"><span data-stu-id="6dbf7-139">The red components are scaled down 25 percent, the green components are scaled down 35 percent, and the blue components are scaled down 50 percent.</span></span>  
  
 [!code-csharp[System.Drawing.RecoloringImages#42](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.RecoloringImages/CS/Class1.cs#42)]
 [!code-vb[System.Drawing.RecoloringImages#42](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.RecoloringImages/VB/Class1.vb#42)]  
  
 <span data-ttu-id="6dbf7-140">下图右侧显示在左侧的原始映像和缩放的图像。</span><span class="sxs-lookup"><span data-stu-id="6dbf7-140">The following illustration shows the original image on the left and the scaled image on the right.</span></span>  
  
 <span data-ttu-id="6dbf7-141">![调整颜色](../../../../docs/framework/winforms/advanced/media/colortrans4.png "colortrans4")</span><span class="sxs-lookup"><span data-stu-id="6dbf7-141">![Scale Colors](../../../../docs/framework/winforms/advanced/media/colortrans4.png "colortrans4")</span></span>  
  
 <span data-ttu-id="6dbf7-142">下表列出的四个栏的颜色矢量之前和之后的红色、 绿色和蓝色的缩放。</span><span class="sxs-lookup"><span data-stu-id="6dbf7-142">The following table lists the color vectors for the four bars before and after the red, green and blue scaling.</span></span>  
  
|<span data-ttu-id="6dbf7-143">原始</span><span class="sxs-lookup"><span data-stu-id="6dbf7-143">Original</span></span>|<span data-ttu-id="6dbf7-144">缩放</span><span class="sxs-lookup"><span data-stu-id="6dbf7-144">Scaled</span></span>|  
|--------------|------------|  
|<span data-ttu-id="6dbf7-145">(0.6, 0.6, 0.6, 1)</span><span class="sxs-lookup"><span data-stu-id="6dbf7-145">(0.6, 0.6, 0.6, 1)</span></span>|<span data-ttu-id="6dbf7-146">(0.45, 0.39, 0.3, 1)</span><span class="sxs-lookup"><span data-stu-id="6dbf7-146">(0.45, 0.39, 0.3, 1)</span></span>|  
|<span data-ttu-id="6dbf7-147">(0, 1, 1, 1)</span><span class="sxs-lookup"><span data-stu-id="6dbf7-147">(0, 1, 1, 1)</span></span>|<span data-ttu-id="6dbf7-148">(0, 0.65, 0.5, 1)</span><span class="sxs-lookup"><span data-stu-id="6dbf7-148">(0, 0.65, 0.5, 1)</span></span>|  
|<span data-ttu-id="6dbf7-149">(1, 1, 0, 1)</span><span class="sxs-lookup"><span data-stu-id="6dbf7-149">(1, 1, 0, 1)</span></span>|<span data-ttu-id="6dbf7-150">(0.75, 0.65, 0, 1)</span><span class="sxs-lookup"><span data-stu-id="6dbf7-150">(0.75, 0.65, 0, 1)</span></span>|  
|<span data-ttu-id="6dbf7-151">(1, 0, 1, 1)</span><span class="sxs-lookup"><span data-stu-id="6dbf7-151">(1, 0, 1, 1)</span></span>|<span data-ttu-id="6dbf7-152">(0.75, 0, 0.5, 1)</span><span class="sxs-lookup"><span data-stu-id="6dbf7-152">(0.75, 0, 0.5, 1)</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="6dbf7-153">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6dbf7-153">See Also</span></span>  
 <xref:System.Drawing.Imaging.ColorMatrix>  
 <xref:System.Drawing.Imaging.ImageAttributes>  
 [<span data-ttu-id="6dbf7-154">Windows 窗体中的图形和绘制</span><span class="sxs-lookup"><span data-stu-id="6dbf7-154">Graphics and Drawing in Windows Forms</span></span>](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)  
 [<span data-ttu-id="6dbf7-155">对图像重新着色</span><span class="sxs-lookup"><span data-stu-id="6dbf7-155">Recoloring Images</span></span>](../../../../docs/framework/winforms/advanced/recoloring-images.md)
