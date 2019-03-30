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
ms.openlocfilehash: 9255dd4adba19bfef1332e5e3dfa463ee96f43f0
ms.sourcegitcommit: 15ab532fd5e1f8073a4b678922d93b68b521bfa0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/29/2019
ms.locfileid: "58653985"
---
# <a name="using-transformations-to-scale-colors"></a><span data-ttu-id="54d88-102">使用转换来调整颜色</span><span class="sxs-lookup"><span data-stu-id="54d88-102">Using Transformations to Scale Colors</span></span>
<span data-ttu-id="54d88-103">缩放转换将乘以一个或多个数字的四个颜色组件。</span><span class="sxs-lookup"><span data-stu-id="54d88-103">A scaling transformation multiplies one or more of the four color components by a number.</span></span> <span data-ttu-id="54d88-104">下表给出表示缩放颜色矩阵项。</span><span class="sxs-lookup"><span data-stu-id="54d88-104">The color matrix entries that represent scaling are given in the following table.</span></span>  
  
|<span data-ttu-id="54d88-105">若要缩放的组件</span><span class="sxs-lookup"><span data-stu-id="54d88-105">Component to be scaled</span></span>|<span data-ttu-id="54d88-106">矩阵条目</span><span class="sxs-lookup"><span data-stu-id="54d88-106">Matrix entry</span></span>|  
|----------------------------|------------------|  
|<span data-ttu-id="54d88-107">红色</span><span class="sxs-lookup"><span data-stu-id="54d88-107">Red</span></span>|<span data-ttu-id="54d88-108">[0][0]</span><span class="sxs-lookup"><span data-stu-id="54d88-108">[0][0]</span></span>|  
|<span data-ttu-id="54d88-109">绿色</span><span class="sxs-lookup"><span data-stu-id="54d88-109">Green</span></span>|<span data-ttu-id="54d88-110">[1][1]</span><span class="sxs-lookup"><span data-stu-id="54d88-110">[1][1]</span></span>|  
|<span data-ttu-id="54d88-111">蓝色</span><span class="sxs-lookup"><span data-stu-id="54d88-111">Blue</span></span>|<span data-ttu-id="54d88-112">[2][2]</span><span class="sxs-lookup"><span data-stu-id="54d88-112">[2][2]</span></span>|  
|<span data-ttu-id="54d88-113">Alpha</span><span class="sxs-lookup"><span data-stu-id="54d88-113">Alpha</span></span>|<span data-ttu-id="54d88-114">[3][3]</span><span class="sxs-lookup"><span data-stu-id="54d88-114">[3][3]</span></span>|  
  
## <a name="scaling-one-color"></a><span data-ttu-id="54d88-115">缩放的一种颜色</span><span class="sxs-lookup"><span data-stu-id="54d88-115">Scaling One Color</span></span>  
 <span data-ttu-id="54d88-116">下面的示例构造<xref:System.Drawing.Image>ColorBars2.bmp 文件中的对象。</span><span class="sxs-lookup"><span data-stu-id="54d88-116">The following example constructs an <xref:System.Drawing.Image> object from the file ColorBars2.bmp.</span></span> <span data-ttu-id="54d88-117">然后代码会 2 的因素在图中每个像素的蓝色组件。</span><span class="sxs-lookup"><span data-stu-id="54d88-117">Then the code scales the blue component of each pixel in the image by a factor of 2.</span></span> <span data-ttu-id="54d88-118">转换后的图像一起绘制原始图像。</span><span class="sxs-lookup"><span data-stu-id="54d88-118">The original image is drawn alongside the transformed image.</span></span>  
  
 [!code-csharp[System.Drawing.RecoloringImages#41](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.RecoloringImages/CS/Class1.cs#41)]
 [!code-vb[System.Drawing.RecoloringImages#41](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.RecoloringImages/VB/Class1.vb#41)]  
  
 <span data-ttu-id="54d88-119">下图显示在右侧左侧上的原始图像和缩放的图像：</span><span class="sxs-lookup"><span data-stu-id="54d88-119">The following illustration shows the original image on the left and the scaled image on the right:</span></span>  
  
 ![比较原始和缩放颜色的屏幕截图。](./media/using-transformations-to-scale-colors/four-bar-scale-one-color.png)  
  
 <span data-ttu-id="54d88-121">下表列出了四个条形的颜色矢量之前和之后的蓝色缩放。</span><span class="sxs-lookup"><span data-stu-id="54d88-121">The following table lists the color vectors for the four bars before and after the blue scaling.</span></span> <span data-ttu-id="54d88-122">请注意，第四个颜色栏中的蓝色组件发送给 0.6 了从 0.8。</span><span class="sxs-lookup"><span data-stu-id="54d88-122">Note that the blue component in the fourth color bar went from 0.8 to 0.6.</span></span> <span data-ttu-id="54d88-123">这是因为[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]保留仅结果的小数部分。</span><span class="sxs-lookup"><span data-stu-id="54d88-123">That is because [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] retains only the fractional part of the result.</span></span> <span data-ttu-id="54d88-124">例如，(2)(0.8) = 1.6，1.6 的小数部分为 0.6。</span><span class="sxs-lookup"><span data-stu-id="54d88-124">For example, (2)(0.8) = 1.6, and the fractional part of 1.6 is 0.6.</span></span> <span data-ttu-id="54d88-125">保留仅的小数部分，可确保结果始终是中间隔 [0，1]。</span><span class="sxs-lookup"><span data-stu-id="54d88-125">Retaining only the fractional part ensures that the result is always in the interval [0, 1].</span></span>  
  
|<span data-ttu-id="54d88-126">原始</span><span class="sxs-lookup"><span data-stu-id="54d88-126">Original</span></span>|<span data-ttu-id="54d88-127">缩放</span><span class="sxs-lookup"><span data-stu-id="54d88-127">Scaled</span></span>|  
|--------------|------------|  
|<span data-ttu-id="54d88-128">(0.4, 0.4, 0.4, 1)</span><span class="sxs-lookup"><span data-stu-id="54d88-128">(0.4, 0.4, 0.4, 1)</span></span>|<span data-ttu-id="54d88-129">(0.4, 0.4, 0.8, 1)</span><span class="sxs-lookup"><span data-stu-id="54d88-129">(0.4, 0.4, 0.8, 1)</span></span>|  
|<span data-ttu-id="54d88-130">(0.4, 0.2, 0.2, 1)</span><span class="sxs-lookup"><span data-stu-id="54d88-130">(0.4, 0.2, 0.2, 1)</span></span>|<span data-ttu-id="54d88-131">(0.4, 0.2, 0.4, 1)</span><span class="sxs-lookup"><span data-stu-id="54d88-131">(0.4, 0.2, 0.4, 1)</span></span>|  
|<span data-ttu-id="54d88-132">(0.2, 0.4, 0.2, 1)</span><span class="sxs-lookup"><span data-stu-id="54d88-132">(0.2, 0.4, 0.2, 1)</span></span>|<span data-ttu-id="54d88-133">(0.2, 0.4, 0.4, 1)</span><span class="sxs-lookup"><span data-stu-id="54d88-133">(0.2, 0.4, 0.4, 1)</span></span>|  
|<span data-ttu-id="54d88-134">(0.4, 0.4, 0.8, 1)</span><span class="sxs-lookup"><span data-stu-id="54d88-134">(0.4, 0.4, 0.8, 1)</span></span>|<span data-ttu-id="54d88-135">(0.4, 0.4, 0.6, 1)</span><span class="sxs-lookup"><span data-stu-id="54d88-135">(0.4, 0.4, 0.6, 1)</span></span>|  
  
## <a name="scaling-multiple-colors"></a><span data-ttu-id="54d88-136">缩放多个颜色</span><span class="sxs-lookup"><span data-stu-id="54d88-136">Scaling Multiple Colors</span></span>  
 <span data-ttu-id="54d88-137">下面的示例构造<xref:System.Drawing.Image>ColorBars2.bmp 文件中的对象。</span><span class="sxs-lookup"><span data-stu-id="54d88-137">The following example constructs an <xref:System.Drawing.Image> object from the file ColorBars2.bmp.</span></span> <span data-ttu-id="54d88-138">然后，代码会在图像中每个像素的红色、 绿色和蓝色组件。</span><span class="sxs-lookup"><span data-stu-id="54d88-138">Then the code scales the red, green, and blue components of each pixel in the image.</span></span> <span data-ttu-id="54d88-139">红色分量缩小了 25%、 绿色分量缩小了 35%和蓝色分量缩小了 50%。</span><span class="sxs-lookup"><span data-stu-id="54d88-139">The red components are scaled down 25 percent, the green components are scaled down 35 percent, and the blue components are scaled down 50 percent.</span></span>  
  
 [!code-csharp[System.Drawing.RecoloringImages#42](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.RecoloringImages/CS/Class1.cs#42)]
 [!code-vb[System.Drawing.RecoloringImages#42](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.RecoloringImages/VB/Class1.vb#42)]  
  
 <span data-ttu-id="54d88-140">下图显示在右侧左侧上的原始图像和缩放的图像：</span><span class="sxs-lookup"><span data-stu-id="54d88-140">The following illustration shows the original image on the left and the scaled image on the right:</span></span>  
  
 ![比较原始和缩放颜色的屏幕截图。](./media/using-transformations-to-scale-colors/four-bar-scale-multiple-colors.png)  
  
 <span data-ttu-id="54d88-142">下表列出了四个条形的颜色矢量之前和之后的红色、 绿色和蓝色的缩放。</span><span class="sxs-lookup"><span data-stu-id="54d88-142">The following table lists the color vectors for the four bars before and after the red, green and blue scaling.</span></span>  
  
|<span data-ttu-id="54d88-143">原始</span><span class="sxs-lookup"><span data-stu-id="54d88-143">Original</span></span>|<span data-ttu-id="54d88-144">缩放</span><span class="sxs-lookup"><span data-stu-id="54d88-144">Scaled</span></span>|  
|--------------|------------|  
|<span data-ttu-id="54d88-145">(0.6, 0.6, 0.6, 1)</span><span class="sxs-lookup"><span data-stu-id="54d88-145">(0.6, 0.6, 0.6, 1)</span></span>|<span data-ttu-id="54d88-146">(0.45, 0.39, 0.3, 1)</span><span class="sxs-lookup"><span data-stu-id="54d88-146">(0.45, 0.39, 0.3, 1)</span></span>|  
|<span data-ttu-id="54d88-147">(0, 1, 1, 1)</span><span class="sxs-lookup"><span data-stu-id="54d88-147">(0, 1, 1, 1)</span></span>|<span data-ttu-id="54d88-148">(0, 0.65, 0.5, 1)</span><span class="sxs-lookup"><span data-stu-id="54d88-148">(0, 0.65, 0.5, 1)</span></span>|  
|<span data-ttu-id="54d88-149">(1, 1, 0, 1)</span><span class="sxs-lookup"><span data-stu-id="54d88-149">(1, 1, 0, 1)</span></span>|<span data-ttu-id="54d88-150">(0.75, 0.65, 0, 1)</span><span class="sxs-lookup"><span data-stu-id="54d88-150">(0.75, 0.65, 0, 1)</span></span>|  
|<span data-ttu-id="54d88-151">(1, 0, 1, 1)</span><span class="sxs-lookup"><span data-stu-id="54d88-151">(1, 0, 1, 1)</span></span>|<span data-ttu-id="54d88-152">(0.75, 0, 0.5, 1)</span><span class="sxs-lookup"><span data-stu-id="54d88-152">(0.75, 0, 0.5, 1)</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="54d88-153">请参阅</span><span class="sxs-lookup"><span data-stu-id="54d88-153">See also</span></span>
- <xref:System.Drawing.Imaging.ColorMatrix>
- <xref:System.Drawing.Imaging.ImageAttributes>
- [<span data-ttu-id="54d88-154">Windows 窗体中的图形和绘制</span><span class="sxs-lookup"><span data-stu-id="54d88-154">Graphics and Drawing in Windows Forms</span></span>](graphics-and-drawing-in-windows-forms.md)
- [<span data-ttu-id="54d88-155">对图像重新着色</span><span class="sxs-lookup"><span data-stu-id="54d88-155">Recoloring Images</span></span>](recoloring-images.md)
