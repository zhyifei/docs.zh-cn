---
title: "如何：转换图像颜色"
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
- bitmaps [Windows Forms], changing colors
- images [Windows Forms], changing colors
- image colors [Windows Forms]
ms.assetid: 2106fb9a-4d60-4dcf-9220-9f189a6c4d19
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 2a2147b9bc86aa7ec03e8455bb0dc51c89a8b282
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-translate-image-colors"></a><span data-ttu-id="98ffe-102">如何：转换图像颜色</span><span class="sxs-lookup"><span data-stu-id="98ffe-102">How to: Translate Image Colors</span></span>
<span data-ttu-id="98ffe-103">转换将值添加到一个或多个四个颜色分量。</span><span class="sxs-lookup"><span data-stu-id="98ffe-103">A translation adds a value to one or more of the four color components.</span></span> <span data-ttu-id="98ffe-104">下表给出颜色矩阵条目，用于表示翻译。</span><span class="sxs-lookup"><span data-stu-id="98ffe-104">The color matrix entries that represent translations are given in the following table.</span></span>  
  
|<span data-ttu-id="98ffe-105">要转换的组件</span><span class="sxs-lookup"><span data-stu-id="98ffe-105">Component to be translated</span></span>|<span data-ttu-id="98ffe-106">矩阵条目</span><span class="sxs-lookup"><span data-stu-id="98ffe-106">Matrix entry</span></span>|  
|--------------------------------|------------------|  
|<span data-ttu-id="98ffe-107">红色</span><span class="sxs-lookup"><span data-stu-id="98ffe-107">Red</span></span>|<span data-ttu-id="98ffe-108">[4][0]</span><span class="sxs-lookup"><span data-stu-id="98ffe-108">[4][0]</span></span>|  
|<span data-ttu-id="98ffe-109">绿色</span><span class="sxs-lookup"><span data-stu-id="98ffe-109">Green</span></span>|<span data-ttu-id="98ffe-110">[4][1]</span><span class="sxs-lookup"><span data-stu-id="98ffe-110">[4][1]</span></span>|  
|<span data-ttu-id="98ffe-111">蓝色</span><span class="sxs-lookup"><span data-stu-id="98ffe-111">Blue</span></span>|<span data-ttu-id="98ffe-112">[4][2]</span><span class="sxs-lookup"><span data-stu-id="98ffe-112">[4][2]</span></span>|  
|<span data-ttu-id="98ffe-113">Alpha</span><span class="sxs-lookup"><span data-stu-id="98ffe-113">Alpha</span></span>|<span data-ttu-id="98ffe-114">[4][3]</span><span class="sxs-lookup"><span data-stu-id="98ffe-114">[4][3]</span></span>|  
  
## <a name="example"></a><span data-ttu-id="98ffe-115">示例</span><span class="sxs-lookup"><span data-stu-id="98ffe-115">Example</span></span>  
 <span data-ttu-id="98ffe-116">下面的示例构造<xref:System.Drawing.Image>从文件 ColorBars.bmp 的对象。</span><span class="sxs-lookup"><span data-stu-id="98ffe-116">The following example constructs an <xref:System.Drawing.Image> object from the file ColorBars.bmp.</span></span> <span data-ttu-id="98ffe-117">然后代码将添加到图像中的每个像素的红色组件的 0.75。</span><span class="sxs-lookup"><span data-stu-id="98ffe-117">Then the code adds 0.75 to the red component of each pixel in the image.</span></span> <span data-ttu-id="98ffe-118">转换后的图像旁边绘制原始图像。</span><span class="sxs-lookup"><span data-stu-id="98ffe-118">The original image is drawn alongside the transformed image.</span></span>  
  
 <span data-ttu-id="98ffe-119">下图右侧显示在左侧的原始映像和变换后的图像。</span><span class="sxs-lookup"><span data-stu-id="98ffe-119">The following illustration shows the original image on the left and the transformed image on the right.</span></span>  
  
 <span data-ttu-id="98ffe-120">![转换颜色](../../../../docs/framework/winforms/advanced/media/colortrans2.png "colortrans2")</span><span class="sxs-lookup"><span data-stu-id="98ffe-120">![Translate Colors](../../../../docs/framework/winforms/advanced/media/colortrans2.png "colortrans2")</span></span>  
  
 <span data-ttu-id="98ffe-121">下表列出的四个栏的颜色矢量之前和之后的红色的转换。</span><span class="sxs-lookup"><span data-stu-id="98ffe-121">The following table lists the color vectors for the four bars before and after the red translation.</span></span> <span data-ttu-id="98ffe-122">请注意，因为颜色组件的最大值是 1，第二行中的红色组件不会更改。</span><span class="sxs-lookup"><span data-stu-id="98ffe-122">Note that because the maximum value for a color component is 1, the red component in the second row does not change.</span></span> <span data-ttu-id="98ffe-123">（同样，颜色组件的最小值为 0。）</span><span class="sxs-lookup"><span data-stu-id="98ffe-123">(Similarly, the minimum value for a color component is 0.)</span></span>  
  
|<span data-ttu-id="98ffe-124">原始</span><span class="sxs-lookup"><span data-stu-id="98ffe-124">Original</span></span>|<span data-ttu-id="98ffe-125">目标语言</span><span class="sxs-lookup"><span data-stu-id="98ffe-125">Translated</span></span>|  
|--------------|----------------|  
|<span data-ttu-id="98ffe-126">黑色 （0，0，0，1）</span><span class="sxs-lookup"><span data-stu-id="98ffe-126">Black (0, 0, 0, 1)</span></span>|<span data-ttu-id="98ffe-127">(0.75, 0, 0, 1)</span><span class="sxs-lookup"><span data-stu-id="98ffe-127">(0.75, 0, 0, 1)</span></span>|  
|<span data-ttu-id="98ffe-128">红色 （1，0，0，1）</span><span class="sxs-lookup"><span data-stu-id="98ffe-128">Red (1, 0, 0, 1)</span></span>|<span data-ttu-id="98ffe-129">(1, 0, 0, 1)</span><span class="sxs-lookup"><span data-stu-id="98ffe-129">(1, 0, 0, 1)</span></span>|  
|<span data-ttu-id="98ffe-130">绿色 （0、 1、 0、 1）</span><span class="sxs-lookup"><span data-stu-id="98ffe-130">Green (0, 1, 0, 1)</span></span>|<span data-ttu-id="98ffe-131">(0.75, 1, 0, 1)</span><span class="sxs-lookup"><span data-stu-id="98ffe-131">(0.75, 1, 0, 1)</span></span>|  
|<span data-ttu-id="98ffe-132">蓝色 （0、 0、 1、 1）</span><span class="sxs-lookup"><span data-stu-id="98ffe-132">Blue (0, 0, 1, 1)</span></span>|<span data-ttu-id="98ffe-133">(0.75, 0, 1, 1)</span><span class="sxs-lookup"><span data-stu-id="98ffe-133">(0.75, 0, 1, 1)</span></span>|  
  
 [!code-csharp[System.Drawing.RecoloringImages#11](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.RecoloringImages/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.RecoloringImages#11](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.RecoloringImages/VB/Class1.vb#11)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="98ffe-134">编译代码</span><span class="sxs-lookup"><span data-stu-id="98ffe-134">Compiling the Code</span></span>  
 <span data-ttu-id="98ffe-135">前面的示例专用于 Windows 窗体，并且它需要<xref:System.Windows.Forms.PaintEventArgs> `e`，这是一个参数的<xref:System.Windows.Forms.Control.Paint>事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="98ffe-135">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs>`e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span> <span data-ttu-id="98ffe-136">替换`ColorBars.bmp`用的图像文件名称和你系统有效的路径。</span><span class="sxs-lookup"><span data-stu-id="98ffe-136">Replace `ColorBars.bmp` with an image file name and path that are valid on your system.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="98ffe-137">请参阅</span><span class="sxs-lookup"><span data-stu-id="98ffe-137">See Also</span></span>  
 <xref:System.Drawing.Imaging.ColorMatrix>  
 <xref:System.Drawing.Imaging.ImageAttributes>  
 [<span data-ttu-id="98ffe-138">Windows 窗体中的图形和绘制</span><span class="sxs-lookup"><span data-stu-id="98ffe-138">Graphics and Drawing in Windows Forms</span></span>](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)  
 [<span data-ttu-id="98ffe-139">对图像重新着色</span><span class="sxs-lookup"><span data-stu-id="98ffe-139">Recoloring Images</span></span>](../../../../docs/framework/winforms/advanced/recoloring-images.md)
