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
ms.openlocfilehash: 81aecddb28903649ff2d59e80fc90368df5e2db4
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/09/2019
ms.locfileid: "57703018"
---
# <a name="how-to-translate-image-colors"></a><span data-ttu-id="d2805-102">如何：转换图像颜色</span><span class="sxs-lookup"><span data-stu-id="d2805-102">How to: Translate Image Colors</span></span>
<span data-ttu-id="d2805-103">翻译添加到一个或多个四个颜色组件值。</span><span class="sxs-lookup"><span data-stu-id="d2805-103">A translation adds a value to one or more of the four color components.</span></span> <span data-ttu-id="d2805-104">下表给出表示翻译颜色矩阵项。</span><span class="sxs-lookup"><span data-stu-id="d2805-104">The color matrix entries that represent translations are given in the following table.</span></span>  
  
|<span data-ttu-id="d2805-105">要转换的组件</span><span class="sxs-lookup"><span data-stu-id="d2805-105">Component to be translated</span></span>|<span data-ttu-id="d2805-106">矩阵条目</span><span class="sxs-lookup"><span data-stu-id="d2805-106">Matrix entry</span></span>|  
|--------------------------------|------------------|  
|<span data-ttu-id="d2805-107">红色</span><span class="sxs-lookup"><span data-stu-id="d2805-107">Red</span></span>|<span data-ttu-id="d2805-108">[4][0]</span><span class="sxs-lookup"><span data-stu-id="d2805-108">[4][0]</span></span>|  
|<span data-ttu-id="d2805-109">绿色</span><span class="sxs-lookup"><span data-stu-id="d2805-109">Green</span></span>|<span data-ttu-id="d2805-110">[4][1]</span><span class="sxs-lookup"><span data-stu-id="d2805-110">[4][1]</span></span>|  
|<span data-ttu-id="d2805-111">蓝色</span><span class="sxs-lookup"><span data-stu-id="d2805-111">Blue</span></span>|<span data-ttu-id="d2805-112">[4][2]</span><span class="sxs-lookup"><span data-stu-id="d2805-112">[4][2]</span></span>|  
|<span data-ttu-id="d2805-113">Alpha</span><span class="sxs-lookup"><span data-stu-id="d2805-113">Alpha</span></span>|<span data-ttu-id="d2805-114">[4][3]</span><span class="sxs-lookup"><span data-stu-id="d2805-114">[4][3]</span></span>|  
  
## <a name="example"></a><span data-ttu-id="d2805-115">示例</span><span class="sxs-lookup"><span data-stu-id="d2805-115">Example</span></span>  
 <span data-ttu-id="d2805-116">下面的示例构造<xref:System.Drawing.Image>ColorBars.bmp 文件中的对象。</span><span class="sxs-lookup"><span data-stu-id="d2805-116">The following example constructs an <xref:System.Drawing.Image> object from the file ColorBars.bmp.</span></span> <span data-ttu-id="d2805-117">然后代码将添加到映像中的每个像素的红色组件的 0.75。</span><span class="sxs-lookup"><span data-stu-id="d2805-117">Then the code adds 0.75 to the red component of each pixel in the image.</span></span> <span data-ttu-id="d2805-118">转换后的图像一起绘制原始图像。</span><span class="sxs-lookup"><span data-stu-id="d2805-118">The original image is drawn alongside the transformed image.</span></span>  
  
 <span data-ttu-id="d2805-119">下图显示在右侧左侧上的原始映像和转换后的图像。</span><span class="sxs-lookup"><span data-stu-id="d2805-119">The following illustration shows the original image on the left and the transformed image on the right.</span></span>  
  
 <span data-ttu-id="d2805-120">![转换颜色](./media/colortrans2.png "colortrans2")</span><span class="sxs-lookup"><span data-stu-id="d2805-120">![Translate Colors](./media/colortrans2.png "colortrans2")</span></span>  
  
 <span data-ttu-id="d2805-121">下表列出了四个条形的颜色矢量之前和之后的红色的转换。</span><span class="sxs-lookup"><span data-stu-id="d2805-121">The following table lists the color vectors for the four bars before and after the red translation.</span></span> <span data-ttu-id="d2805-122">请注意，因为颜色组件的最大值为 1，第二行中的红色组件不会更改。</span><span class="sxs-lookup"><span data-stu-id="d2805-122">Note that because the maximum value for a color component is 1, the red component in the second row does not change.</span></span> <span data-ttu-id="d2805-123">（同样，颜色组件的最小值为 0。）</span><span class="sxs-lookup"><span data-stu-id="d2805-123">(Similarly, the minimum value for a color component is 0.)</span></span>  
  
|<span data-ttu-id="d2805-124">原始</span><span class="sxs-lookup"><span data-stu-id="d2805-124">Original</span></span>|<span data-ttu-id="d2805-125">目标语言</span><span class="sxs-lookup"><span data-stu-id="d2805-125">Translated</span></span>|  
|--------------|----------------|  
|<span data-ttu-id="d2805-126">黑色 （0，0，0，1）</span><span class="sxs-lookup"><span data-stu-id="d2805-126">Black (0, 0, 0, 1)</span></span>|<span data-ttu-id="d2805-127">(0.75, 0, 0, 1)</span><span class="sxs-lookup"><span data-stu-id="d2805-127">(0.75, 0, 0, 1)</span></span>|  
|<span data-ttu-id="d2805-128">红色 （1，0，0，1）</span><span class="sxs-lookup"><span data-stu-id="d2805-128">Red (1, 0, 0, 1)</span></span>|<span data-ttu-id="d2805-129">(1, 0, 0, 1)</span><span class="sxs-lookup"><span data-stu-id="d2805-129">(1, 0, 0, 1)</span></span>|  
|<span data-ttu-id="d2805-130">绿色 （0、 1、 0、 1）</span><span class="sxs-lookup"><span data-stu-id="d2805-130">Green (0, 1, 0, 1)</span></span>|<span data-ttu-id="d2805-131">(0.75, 1, 0, 1)</span><span class="sxs-lookup"><span data-stu-id="d2805-131">(0.75, 1, 0, 1)</span></span>|  
|<span data-ttu-id="d2805-132">蓝色 （0，0，1，1）</span><span class="sxs-lookup"><span data-stu-id="d2805-132">Blue (0, 0, 1, 1)</span></span>|<span data-ttu-id="d2805-133">(0.75, 0, 1, 1)</span><span class="sxs-lookup"><span data-stu-id="d2805-133">(0.75, 0, 1, 1)</span></span>|  
  
 [!code-csharp[System.Drawing.RecoloringImages#11](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.RecoloringImages/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.RecoloringImages#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.RecoloringImages/VB/Class1.vb#11)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="d2805-134">编译代码</span><span class="sxs-lookup"><span data-stu-id="d2805-134">Compiling the Code</span></span>  
 <span data-ttu-id="d2805-135">前面的示例专用于 Windows 窗体，它需要 <xref:System.Windows.Forms.PaintEventArgs>`e`，后者是 <xref:System.Windows.Forms.Control.Paint> 事件处理程序的参数。</span><span class="sxs-lookup"><span data-stu-id="d2805-135">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs>`e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span> <span data-ttu-id="d2805-136">替换为`ColorBars.bmp`与图像文件名称和在您的系统都有效的路径。</span><span class="sxs-lookup"><span data-stu-id="d2805-136">Replace `ColorBars.bmp` with an image file name and path that are valid on your system.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d2805-137">请参阅</span><span class="sxs-lookup"><span data-stu-id="d2805-137">See also</span></span>
- <xref:System.Drawing.Imaging.ColorMatrix>
- <xref:System.Drawing.Imaging.ImageAttributes>
- [<span data-ttu-id="d2805-138">Windows 窗体中的图形和绘制</span><span class="sxs-lookup"><span data-stu-id="d2805-138">Graphics and Drawing in Windows Forms</span></span>](graphics-and-drawing-in-windows-forms.md)
- [<span data-ttu-id="d2805-139">对图像重新着色</span><span class="sxs-lookup"><span data-stu-id="d2805-139">Recoloring Images</span></span>](recoloring-images.md)
