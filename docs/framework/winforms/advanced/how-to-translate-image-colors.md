---
title: 如何：转换图像颜色
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- bitmaps [Windows Forms], changing colors
- images [Windows Forms], changing colors
- image colors [Windows Forms]
ms.assetid: 2106fb9a-4d60-4dcf-9220-9f189a6c4d19
ms.openlocfilehash: 8b2e28cab2d2d04f7c99880f2b35a02ebe80dcd8
ms.sourcegitcommit: 7156c0b9e4ce4ce5ecf48ce3d925403b638b680c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/26/2019
ms.locfileid: "58464458"
---
# <a name="how-to-translate-image-colors"></a><span data-ttu-id="c55bc-102">如何：转换图像颜色</span><span class="sxs-lookup"><span data-stu-id="c55bc-102">How to: Translate Image Colors</span></span>
<span data-ttu-id="c55bc-103">翻译添加到一个或多个四个颜色组件值。</span><span class="sxs-lookup"><span data-stu-id="c55bc-103">A translation adds a value to one or more of the four color components.</span></span> <span data-ttu-id="c55bc-104">下表给出表示翻译颜色矩阵项。</span><span class="sxs-lookup"><span data-stu-id="c55bc-104">The color matrix entries that represent translations are given in the following table.</span></span>  
  
|<span data-ttu-id="c55bc-105">要转换的组件</span><span class="sxs-lookup"><span data-stu-id="c55bc-105">Component to be translated</span></span>|<span data-ttu-id="c55bc-106">矩阵条目</span><span class="sxs-lookup"><span data-stu-id="c55bc-106">Matrix entry</span></span>|  
|--------------------------------|------------------|  
|<span data-ttu-id="c55bc-107">红色</span><span class="sxs-lookup"><span data-stu-id="c55bc-107">Red</span></span>|<span data-ttu-id="c55bc-108">[4][0]</span><span class="sxs-lookup"><span data-stu-id="c55bc-108">[4][0]</span></span>|  
|<span data-ttu-id="c55bc-109">绿色</span><span class="sxs-lookup"><span data-stu-id="c55bc-109">Green</span></span>|<span data-ttu-id="c55bc-110">[4][1]</span><span class="sxs-lookup"><span data-stu-id="c55bc-110">[4][1]</span></span>|  
|<span data-ttu-id="c55bc-111">蓝色</span><span class="sxs-lookup"><span data-stu-id="c55bc-111">Blue</span></span>|<span data-ttu-id="c55bc-112">[4][2]</span><span class="sxs-lookup"><span data-stu-id="c55bc-112">[4][2]</span></span>|  
|<span data-ttu-id="c55bc-113">Alpha</span><span class="sxs-lookup"><span data-stu-id="c55bc-113">Alpha</span></span>|<span data-ttu-id="c55bc-114">[4][3]</span><span class="sxs-lookup"><span data-stu-id="c55bc-114">[4][3]</span></span>|  
  
## <a name="example"></a><span data-ttu-id="c55bc-115">示例</span><span class="sxs-lookup"><span data-stu-id="c55bc-115">Example</span></span>  
 <span data-ttu-id="c55bc-116">下面的示例构造<xref:System.Drawing.Image>ColorBars.bmp 文件中的对象。</span><span class="sxs-lookup"><span data-stu-id="c55bc-116">The following example constructs an <xref:System.Drawing.Image> object from the file ColorBars.bmp.</span></span> <span data-ttu-id="c55bc-117">然后代码将添加到映像中的每个像素的红色组件的 0.75。</span><span class="sxs-lookup"><span data-stu-id="c55bc-117">Then the code adds 0.75 to the red component of each pixel in the image.</span></span> <span data-ttu-id="c55bc-118">转换后的图像一起绘制原始图像。</span><span class="sxs-lookup"><span data-stu-id="c55bc-118">The original image is drawn alongside the transformed image.</span></span>  
  
 <span data-ttu-id="c55bc-119">下图显示在右侧左侧上的原始映像和转换后的图像：</span><span class="sxs-lookup"><span data-stu-id="c55bc-119">The following illustration shows the original image on the left and the transformed image on the right:</span></span>  
  
 ![原始和已转换图像的屏幕截图。](./media/how-to-translate-image-colors/original-image-translate-colors.png)  
  
 <span data-ttu-id="c55bc-121">下表列出了四个条形的颜色矢量之前和之后的红色的转换。</span><span class="sxs-lookup"><span data-stu-id="c55bc-121">The following table lists the color vectors for the four bars before and after the red translation.</span></span> <span data-ttu-id="c55bc-122">请注意，因为颜色组件的最大值为 1，第二行中的红色组件不会更改。</span><span class="sxs-lookup"><span data-stu-id="c55bc-122">Note that because the maximum value for a color component is 1, the red component in the second row does not change.</span></span> <span data-ttu-id="c55bc-123">（同样，颜色组件的最小值为 0。）</span><span class="sxs-lookup"><span data-stu-id="c55bc-123">(Similarly, the minimum value for a color component is 0.)</span></span>  
  
|<span data-ttu-id="c55bc-124">原始</span><span class="sxs-lookup"><span data-stu-id="c55bc-124">Original</span></span>|<span data-ttu-id="c55bc-125">目标语言</span><span class="sxs-lookup"><span data-stu-id="c55bc-125">Translated</span></span>|  
|--------------|----------------|  
|<span data-ttu-id="c55bc-126">黑色 （0，0，0，1）</span><span class="sxs-lookup"><span data-stu-id="c55bc-126">Black (0, 0, 0, 1)</span></span>|<span data-ttu-id="c55bc-127">(0.75, 0, 0, 1)</span><span class="sxs-lookup"><span data-stu-id="c55bc-127">(0.75, 0, 0, 1)</span></span>|  
|<span data-ttu-id="c55bc-128">红色 （1，0，0，1）</span><span class="sxs-lookup"><span data-stu-id="c55bc-128">Red (1, 0, 0, 1)</span></span>|<span data-ttu-id="c55bc-129">(1, 0, 0, 1)</span><span class="sxs-lookup"><span data-stu-id="c55bc-129">(1, 0, 0, 1)</span></span>|  
|<span data-ttu-id="c55bc-130">绿色 （0、 1、 0、 1）</span><span class="sxs-lookup"><span data-stu-id="c55bc-130">Green (0, 1, 0, 1)</span></span>|<span data-ttu-id="c55bc-131">(0.75, 1, 0, 1)</span><span class="sxs-lookup"><span data-stu-id="c55bc-131">(0.75, 1, 0, 1)</span></span>|  
|<span data-ttu-id="c55bc-132">蓝色 （0，0，1，1）</span><span class="sxs-lookup"><span data-stu-id="c55bc-132">Blue (0, 0, 1, 1)</span></span>|<span data-ttu-id="c55bc-133">(0.75, 0, 1, 1)</span><span class="sxs-lookup"><span data-stu-id="c55bc-133">(0.75, 0, 1, 1)</span></span>|  
  
 [!code-csharp[System.Drawing.RecoloringImages#11](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.RecoloringImages/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.RecoloringImages#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.RecoloringImages/VB/Class1.vb#11)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="c55bc-134">编译代码</span><span class="sxs-lookup"><span data-stu-id="c55bc-134">Compiling the Code</span></span>  
 <span data-ttu-id="c55bc-135">前面的示例专用于 Windows 窗体，它需要 <xref:System.Windows.Forms.PaintEventArgs>`e`，后者是 <xref:System.Windows.Forms.Control.Paint> 事件处理程序的参数。</span><span class="sxs-lookup"><span data-stu-id="c55bc-135">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs>`e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span> <span data-ttu-id="c55bc-136">替换为`ColorBars.bmp`与图像文件名称和在您的系统都有效的路径。</span><span class="sxs-lookup"><span data-stu-id="c55bc-136">Replace `ColorBars.bmp` with an image file name and path that are valid on your system.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c55bc-137">请参阅</span><span class="sxs-lookup"><span data-stu-id="c55bc-137">See also</span></span>
- <xref:System.Drawing.Imaging.ColorMatrix>
- <xref:System.Drawing.Imaging.ImageAttributes>
- [<span data-ttu-id="c55bc-138">Windows 窗体中的图形和绘制</span><span class="sxs-lookup"><span data-stu-id="c55bc-138">Graphics and Drawing in Windows Forms</span></span>](graphics-and-drawing-in-windows-forms.md)
- [<span data-ttu-id="c55bc-139">对图像重新着色</span><span class="sxs-lookup"><span data-stu-id="c55bc-139">Recoloring Images</span></span>](recoloring-images.md)
