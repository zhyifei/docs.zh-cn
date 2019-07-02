---
title: 使用转换来调整颜色
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- transformations [Windows Forms], for scaling colors
- colors [Windows Forms], scaling
ms.assetid: df23c887-7fd6-4b15-ad94-e30b5bd4b849
ms.openlocfilehash: 81c0ddf5b937d604559a9eb1a8b598885546c97f
ms.sourcegitcommit: b1cfd260928d464d91e20121f9bdba7611c94d71
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/02/2019
ms.locfileid: "67504961"
---
# <a name="using-transformations-to-scale-colors"></a><span data-ttu-id="2001e-102">使用转换来调整颜色</span><span class="sxs-lookup"><span data-stu-id="2001e-102">Using Transformations to Scale Colors</span></span>
<span data-ttu-id="2001e-103">缩放转换将乘以一个或多个数字的四个颜色组件。</span><span class="sxs-lookup"><span data-stu-id="2001e-103">A scaling transformation multiplies one or more of the four color components by a number.</span></span> <span data-ttu-id="2001e-104">下表给出表示缩放颜色矩阵项。</span><span class="sxs-lookup"><span data-stu-id="2001e-104">The color matrix entries that represent scaling are given in the following table.</span></span>  
  
|<span data-ttu-id="2001e-105">若要缩放的组件</span><span class="sxs-lookup"><span data-stu-id="2001e-105">Component to be scaled</span></span>|<span data-ttu-id="2001e-106">矩阵条目</span><span class="sxs-lookup"><span data-stu-id="2001e-106">Matrix entry</span></span>|  
|----------------------------|------------------|  
|<span data-ttu-id="2001e-107">红色</span><span class="sxs-lookup"><span data-stu-id="2001e-107">Red</span></span>|<span data-ttu-id="2001e-108">[0][0]</span><span class="sxs-lookup"><span data-stu-id="2001e-108">[0][0]</span></span>|  
|<span data-ttu-id="2001e-109">绿色</span><span class="sxs-lookup"><span data-stu-id="2001e-109">Green</span></span>|<span data-ttu-id="2001e-110">[1][1]</span><span class="sxs-lookup"><span data-stu-id="2001e-110">[1][1]</span></span>|  
|<span data-ttu-id="2001e-111">蓝色</span><span class="sxs-lookup"><span data-stu-id="2001e-111">Blue</span></span>|<span data-ttu-id="2001e-112">[2][2]</span><span class="sxs-lookup"><span data-stu-id="2001e-112">[2][2]</span></span>|  
|<span data-ttu-id="2001e-113">Alpha</span><span class="sxs-lookup"><span data-stu-id="2001e-113">Alpha</span></span>|<span data-ttu-id="2001e-114">[3][3]</span><span class="sxs-lookup"><span data-stu-id="2001e-114">[3][3]</span></span>|  
  
## <a name="scaling-one-color"></a><span data-ttu-id="2001e-115">缩放的一种颜色</span><span class="sxs-lookup"><span data-stu-id="2001e-115">Scaling One Color</span></span>  
 <span data-ttu-id="2001e-116">下面的示例构造<xref:System.Drawing.Image>ColorBars2.bmp 文件中的对象。</span><span class="sxs-lookup"><span data-stu-id="2001e-116">The following example constructs an <xref:System.Drawing.Image> object from the file ColorBars2.bmp.</span></span> <span data-ttu-id="2001e-117">然后代码会 2 的因素在图中每个像素的蓝色组件。</span><span class="sxs-lookup"><span data-stu-id="2001e-117">Then the code scales the blue component of each pixel in the image by a factor of 2.</span></span> <span data-ttu-id="2001e-118">转换后的图像一起绘制原始图像。</span><span class="sxs-lookup"><span data-stu-id="2001e-118">The original image is drawn alongside the transformed image.</span></span>  
  
 [!code-csharp[System.Drawing.RecoloringImages#41](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.RecoloringImages/CS/Class1.cs#41)]
 [!code-vb[System.Drawing.RecoloringImages#41](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.RecoloringImages/VB/Class1.vb#41)]  
  
 <span data-ttu-id="2001e-119">下图显示在右侧左侧上的原始图像和缩放的图像：</span><span class="sxs-lookup"><span data-stu-id="2001e-119">The following illustration shows the original image on the left and the scaled image on the right:</span></span>  
  
 ![比较原始和缩放颜色的屏幕截图。](./media/using-transformations-to-scale-colors/four-bar-scale-one-color.png)  
  
 <span data-ttu-id="2001e-121">下表列出了四个条形的颜色矢量之前和之后的蓝色缩放。</span><span class="sxs-lookup"><span data-stu-id="2001e-121">The following table lists the color vectors for the four bars before and after the blue scaling.</span></span> <span data-ttu-id="2001e-122">请注意，第四个颜色栏中的蓝色组件发送给 0.6 了从 0.8。</span><span class="sxs-lookup"><span data-stu-id="2001e-122">Note that the blue component in the fourth color bar went from 0.8 to 0.6.</span></span> <span data-ttu-id="2001e-123">这是因为 GDI + 保留仅结果的小数部分。</span><span class="sxs-lookup"><span data-stu-id="2001e-123">That is because GDI+ retains only the fractional part of the result.</span></span> <span data-ttu-id="2001e-124">例如，(2)(0.8) = 1.6，1.6 的小数部分为 0.6。</span><span class="sxs-lookup"><span data-stu-id="2001e-124">For example, (2)(0.8) = 1.6, and the fractional part of 1.6 is 0.6.</span></span> <span data-ttu-id="2001e-125">保留仅的小数部分，可确保结果始终是中间隔 [0，1]。</span><span class="sxs-lookup"><span data-stu-id="2001e-125">Retaining only the fractional part ensures that the result is always in the interval [0, 1].</span></span>  
  
|<span data-ttu-id="2001e-126">原始</span><span class="sxs-lookup"><span data-stu-id="2001e-126">Original</span></span>|<span data-ttu-id="2001e-127">缩放</span><span class="sxs-lookup"><span data-stu-id="2001e-127">Scaled</span></span>|  
|--------------|------------|  
|<span data-ttu-id="2001e-128">(0.4, 0.4, 0.4, 1)</span><span class="sxs-lookup"><span data-stu-id="2001e-128">(0.4, 0.4, 0.4, 1)</span></span>|<span data-ttu-id="2001e-129">(0.4, 0.4, 0.8, 1)</span><span class="sxs-lookup"><span data-stu-id="2001e-129">(0.4, 0.4, 0.8, 1)</span></span>|  
|<span data-ttu-id="2001e-130">(0.4, 0.2, 0.2, 1)</span><span class="sxs-lookup"><span data-stu-id="2001e-130">(0.4, 0.2, 0.2, 1)</span></span>|<span data-ttu-id="2001e-131">(0.4, 0.2, 0.4, 1)</span><span class="sxs-lookup"><span data-stu-id="2001e-131">(0.4, 0.2, 0.4, 1)</span></span>|  
|<span data-ttu-id="2001e-132">(0.2, 0.4, 0.2, 1)</span><span class="sxs-lookup"><span data-stu-id="2001e-132">(0.2, 0.4, 0.2, 1)</span></span>|<span data-ttu-id="2001e-133">(0.2, 0.4, 0.4, 1)</span><span class="sxs-lookup"><span data-stu-id="2001e-133">(0.2, 0.4, 0.4, 1)</span></span>|  
|<span data-ttu-id="2001e-134">(0.4, 0.4, 0.8, 1)</span><span class="sxs-lookup"><span data-stu-id="2001e-134">(0.4, 0.4, 0.8, 1)</span></span>|<span data-ttu-id="2001e-135">(0.4, 0.4, 0.6, 1)</span><span class="sxs-lookup"><span data-stu-id="2001e-135">(0.4, 0.4, 0.6, 1)</span></span>|  
  
## <a name="scaling-multiple-colors"></a><span data-ttu-id="2001e-136">缩放多个颜色</span><span class="sxs-lookup"><span data-stu-id="2001e-136">Scaling Multiple Colors</span></span>  
 <span data-ttu-id="2001e-137">下面的示例构造<xref:System.Drawing.Image>ColorBars2.bmp 文件中的对象。</span><span class="sxs-lookup"><span data-stu-id="2001e-137">The following example constructs an <xref:System.Drawing.Image> object from the file ColorBars2.bmp.</span></span> <span data-ttu-id="2001e-138">然后，代码会在图像中每个像素的红色、 绿色和蓝色组件。</span><span class="sxs-lookup"><span data-stu-id="2001e-138">Then the code scales the red, green, and blue components of each pixel in the image.</span></span> <span data-ttu-id="2001e-139">红色分量缩小了 25%、 绿色分量缩小了 35%和蓝色分量缩小了 50%。</span><span class="sxs-lookup"><span data-stu-id="2001e-139">The red components are scaled down 25 percent, the green components are scaled down 35 percent, and the blue components are scaled down 50 percent.</span></span>  
  
 [!code-csharp[System.Drawing.RecoloringImages#42](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.RecoloringImages/CS/Class1.cs#42)]
 [!code-vb[System.Drawing.RecoloringImages#42](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.RecoloringImages/VB/Class1.vb#42)]  
  
 <span data-ttu-id="2001e-140">下图显示在右侧左侧上的原始图像和缩放的图像：</span><span class="sxs-lookup"><span data-stu-id="2001e-140">The following illustration shows the original image on the left and the scaled image on the right:</span></span>  
  
 ![比较原始和缩放颜色的屏幕截图。](./media/using-transformations-to-scale-colors/four-bar-scale-multiple-colors.png)  
  
 <span data-ttu-id="2001e-142">下表列出了四个条形的颜色矢量之前和之后的红色、 绿色和蓝色的缩放。</span><span class="sxs-lookup"><span data-stu-id="2001e-142">The following table lists the color vectors for the four bars before and after the red, green and blue scaling.</span></span>  
  
|<span data-ttu-id="2001e-143">原始</span><span class="sxs-lookup"><span data-stu-id="2001e-143">Original</span></span>|<span data-ttu-id="2001e-144">缩放</span><span class="sxs-lookup"><span data-stu-id="2001e-144">Scaled</span></span>|  
|--------------|------------|  
|<span data-ttu-id="2001e-145">(0.6, 0.6, 0.6, 1)</span><span class="sxs-lookup"><span data-stu-id="2001e-145">(0.6, 0.6, 0.6, 1)</span></span>|<span data-ttu-id="2001e-146">(0.45, 0.39, 0.3, 1)</span><span class="sxs-lookup"><span data-stu-id="2001e-146">(0.45, 0.39, 0.3, 1)</span></span>|  
|<span data-ttu-id="2001e-147">(0, 1, 1, 1)</span><span class="sxs-lookup"><span data-stu-id="2001e-147">(0, 1, 1, 1)</span></span>|<span data-ttu-id="2001e-148">(0, 0.65, 0.5, 1)</span><span class="sxs-lookup"><span data-stu-id="2001e-148">(0, 0.65, 0.5, 1)</span></span>|  
|<span data-ttu-id="2001e-149">(1, 1, 0, 1)</span><span class="sxs-lookup"><span data-stu-id="2001e-149">(1, 1, 0, 1)</span></span>|<span data-ttu-id="2001e-150">(0.75, 0.65, 0, 1)</span><span class="sxs-lookup"><span data-stu-id="2001e-150">(0.75, 0.65, 0, 1)</span></span>|  
|<span data-ttu-id="2001e-151">(1, 0, 1, 1)</span><span class="sxs-lookup"><span data-stu-id="2001e-151">(1, 0, 1, 1)</span></span>|<span data-ttu-id="2001e-152">(0.75, 0, 0.5, 1)</span><span class="sxs-lookup"><span data-stu-id="2001e-152">(0.75, 0, 0.5, 1)</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="2001e-153">请参阅</span><span class="sxs-lookup"><span data-stu-id="2001e-153">See also</span></span>

- <xref:System.Drawing.Imaging.ColorMatrix>
- <xref:System.Drawing.Imaging.ImageAttributes>
- [<span data-ttu-id="2001e-154">Windows 窗体中的图形和绘制</span><span class="sxs-lookup"><span data-stu-id="2001e-154">Graphics and Drawing in Windows Forms</span></span>](graphics-and-drawing-in-windows-forms.md)
- [<span data-ttu-id="2001e-155">对图像重新着色</span><span class="sxs-lookup"><span data-stu-id="2001e-155">Recoloring Images</span></span>](recoloring-images.md)
