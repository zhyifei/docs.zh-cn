---
title: "如何：旋转、反射和扭曲图像"
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
- images [Windows Forms], reflecting
- images [Windows Forms], rotating
- images [Windows Forms], skewing
ms.assetid: a3bf97eb-63ed-425a-ba07-dcc65efb567c
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 163af74d27adcb7ec720a54bfd969bd704f7b1e5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-rotate-reflect-and-skew-images"></a><span data-ttu-id="f94ed-102">如何：旋转、反射和扭曲图像</span><span class="sxs-lookup"><span data-stu-id="f94ed-102">How to: Rotate, Reflect, and Skew Images</span></span>
<span data-ttu-id="f94ed-103">你可以旋转、 反射和扭曲图像通过指定的原始图像的左上角、 右上角和左下角的目标点。</span><span class="sxs-lookup"><span data-stu-id="f94ed-103">You can rotate, reflect, and skew an image by specifying destination points for the upper-left, upper-right, and lower-left corners of the original image.</span></span> <span data-ttu-id="f94ed-104">三个目标点确定映射到一个平行四边形的原始矩形图像仿射转换。</span><span class="sxs-lookup"><span data-stu-id="f94ed-104">The three destination points determine an affine transformation that maps the original rectangular image to a parallelogram.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f94ed-105">示例</span><span class="sxs-lookup"><span data-stu-id="f94ed-105">Example</span></span>  
 <span data-ttu-id="f94ed-106">例如，假设原始图像是一个具有在左上角的矩形 （0，0），在右上角 （100，0），并在左下角 （0，50）。</span><span class="sxs-lookup"><span data-stu-id="f94ed-106">For example, suppose the original image is a rectangle with upper-left corner at (0, 0), upper-right corner at (100, 0), and lower-left corner at (0, 50).</span></span> <span data-ttu-id="f94ed-107">现在假设你将它们映射三个指向目标点，如下所示。</span><span class="sxs-lookup"><span data-stu-id="f94ed-107">Now suppose you map those three points to destination points as follows.</span></span>  
  
|<span data-ttu-id="f94ed-108">原始点</span><span class="sxs-lookup"><span data-stu-id="f94ed-108">Original point</span></span>|<span data-ttu-id="f94ed-109">目标点</span><span class="sxs-lookup"><span data-stu-id="f94ed-109">Destination point</span></span>|  
|--------------------|-----------------------|  
|<span data-ttu-id="f94ed-110">左上角 （0，0）</span><span class="sxs-lookup"><span data-stu-id="f94ed-110">Upper-left (0, 0)</span></span>|<span data-ttu-id="f94ed-111">(200, 20)</span><span class="sxs-lookup"><span data-stu-id="f94ed-111">(200, 20)</span></span>|  
|<span data-ttu-id="f94ed-112">右上角 （100，0）</span><span class="sxs-lookup"><span data-stu-id="f94ed-112">Upper-right (100, 0)</span></span>|<span data-ttu-id="f94ed-113">(110, 100)</span><span class="sxs-lookup"><span data-stu-id="f94ed-113">(110, 100)</span></span>|  
|<span data-ttu-id="f94ed-114">左下方 （0，50）</span><span class="sxs-lookup"><span data-stu-id="f94ed-114">Lower-left (0, 50)</span></span>|<span data-ttu-id="f94ed-115">(250, 30)</span><span class="sxs-lookup"><span data-stu-id="f94ed-115">(250, 30)</span></span>|  
  
 <span data-ttu-id="f94ed-116">下图显示原始的图像和图像映射到的平行四边形。</span><span class="sxs-lookup"><span data-stu-id="f94ed-116">The following illustration shows the original image and the image mapped to the parallelogram.</span></span> <span data-ttu-id="f94ed-117">原始图像已偏差、 反映、 旋转和转换。</span><span class="sxs-lookup"><span data-stu-id="f94ed-117">The original image has been skewed, reflected, rotated, and translated.</span></span> <span data-ttu-id="f94ed-118">原始图像的上边缘沿 x 轴映射到通过运行的行 （200，20） 和 （110，100）。</span><span class="sxs-lookup"><span data-stu-id="f94ed-118">The x-axis along the top edge of the original image is mapped to the line that runs through (200, 20) and (110, 100).</span></span> <span data-ttu-id="f94ed-119">原始图像的左边缘沿 y 轴映射到通过运行的行 （200，20） 和 （250，30）。</span><span class="sxs-lookup"><span data-stu-id="f94ed-119">The y-axis along the left edge of the original image is mapped to the line that runs through (200, 20) and (250, 30).</span></span>  
  
 <span data-ttu-id="f94ed-120">![条带化](../../../../docs/framework/winforms/advanced/media/stripes1.gif "Stripes1")</span><span class="sxs-lookup"><span data-stu-id="f94ed-120">![Stripes](../../../../docs/framework/winforms/advanced/media/stripes1.gif "Stripes1")</span></span>  
  
 <span data-ttu-id="f94ed-121">下图显示应用到照片图像的类似变换。</span><span class="sxs-lookup"><span data-stu-id="f94ed-121">The following illustration shows a similar transformation applied to a photographic image.</span></span>  
  
 <span data-ttu-id="f94ed-122">![转换的 Climber](../../../../docs/framework/winforms/advanced/media/transformedclimber.png "TransformedClimber")</span><span class="sxs-lookup"><span data-stu-id="f94ed-122">![Transformed Climber](../../../../docs/framework/winforms/advanced/media/transformedclimber.png "TransformedClimber")</span></span>  
  
 <span data-ttu-id="f94ed-123">下图显示类似转换应用于图元文件。</span><span class="sxs-lookup"><span data-stu-id="f94ed-123">The following illustration shows a similar transformation applied to a metafile.</span></span>  
  
 <span data-ttu-id="f94ed-124">![转换图元文件](../../../../docs/framework/winforms/advanced/media/transformedmetafile.png "TransformedMetafile")</span><span class="sxs-lookup"><span data-stu-id="f94ed-124">![Transformed Metafile](../../../../docs/framework/winforms/advanced/media/transformedmetafile.png "TransformedMetafile")</span></span>  
  
 <span data-ttu-id="f94ed-125">下面的示例生成第一个图中所显示的图像。</span><span class="sxs-lookup"><span data-stu-id="f94ed-125">The following example produces the images shown in the first illustration.</span></span>  
  
 [!code-csharp[System.Drawing.WorkingWithImages#61](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#61)]
 [!code-vb[System.Drawing.WorkingWithImages#61](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#61)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="f94ed-126">编译代码</span><span class="sxs-lookup"><span data-stu-id="f94ed-126">Compiling the Code</span></span>  
 <span data-ttu-id="f94ed-127">前面的示例专用于 Windows 窗体，并且它需要<xref:System.Windows.Forms.PaintEventArgs> `e`，这是一个参数的<xref:System.Windows.Forms.Control.Paint>事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="f94ed-127">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs>`e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span> <span data-ttu-id="f94ed-128">请确保将`Stripes.bmp`替换为你系统上有效的映像的路径。</span><span class="sxs-lookup"><span data-stu-id="f94ed-128">Make sure to replace `Stripes.bmp` with the path to an image that is valid on your system.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f94ed-129">请参阅</span><span class="sxs-lookup"><span data-stu-id="f94ed-129">See Also</span></span>  
 [<span data-ttu-id="f94ed-130">使用图像、位图、图标和图元文件</span><span class="sxs-lookup"><span data-stu-id="f94ed-130">Working with Images, Bitmaps, Icons, and Metafiles</span></span>](../../../../docs/framework/winforms/advanced/working-with-images-bitmaps-icons-and-metafiles.md)
