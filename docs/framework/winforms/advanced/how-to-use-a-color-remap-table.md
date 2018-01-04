---
title: "如何：使用颜色重新映射表"
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
- color tables [Windows Forms], remapping colors with
- custom colors [Windows Forms], creating with color remap table
- color remap tables [Windows Forms], using
ms.assetid: 977df1ce-8665-42d4-9fb1-ef7f0ff63419
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 6e208aa9c98c1ca19baee83760cfd0f75972ecfa
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-use-a-color-remap-table"></a><span data-ttu-id="69bfe-102">如何：使用颜色重新映射表</span><span class="sxs-lookup"><span data-stu-id="69bfe-102">How to: Use a Color Remap Table</span></span>
<span data-ttu-id="69bfe-103">重新映射是将转换在映像中颜色重新映射表根据颜色的过程。</span><span class="sxs-lookup"><span data-stu-id="69bfe-103">Remapping is the process of converting the colors in an image according to a color remap table.</span></span> <span data-ttu-id="69bfe-104">颜色重新映射表是一个数组<xref:System.Drawing.Imaging.ColorMap>对象。</span><span class="sxs-lookup"><span data-stu-id="69bfe-104">The color remap table is an array of <xref:System.Drawing.Imaging.ColorMap> objects.</span></span> <span data-ttu-id="69bfe-105">每个<xref:System.Drawing.Imaging.ColorMap>数组中的对象具有<xref:System.Drawing.Imaging.ColorMap.OldColor%2A>属性和<xref:System.Drawing.Imaging.ColorMap.NewColor%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="69bfe-105">Each <xref:System.Drawing.Imaging.ColorMap> object in the array has an <xref:System.Drawing.Imaging.ColorMap.OldColor%2A> property and a <xref:System.Drawing.Imaging.ColorMap.NewColor%2A> property.</span></span>  
  
 <span data-ttu-id="69bfe-106">当[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]绘制图像，图像的每个像素相比的旧颜色数组。</span><span class="sxs-lookup"><span data-stu-id="69bfe-106">When [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] draws an image, each pixel of the image is compared to the array of old colors.</span></span> <span data-ttu-id="69bfe-107">如果像素的颜色与旧颜色相匹配，则会将其颜色更改为相应的新颜色。</span><span class="sxs-lookup"><span data-stu-id="69bfe-107">If a pixel's color matches an old color, its color is changed to the corresponding new color.</span></span> <span data-ttu-id="69bfe-108">仅对呈现更改的颜色，图像本身的颜色值 (存储在<xref:System.Drawing.Image>或<xref:System.Drawing.Bitmap>对象) 将不会更改。</span><span class="sxs-lookup"><span data-stu-id="69bfe-108">The colors are changed only for rendering — the color values of the image itself (stored in an <xref:System.Drawing.Image> or <xref:System.Drawing.Bitmap> object) are not changed.</span></span>  
  
 <span data-ttu-id="69bfe-109">若要绘制变换后的图像，初始化的数组<xref:System.Drawing.Imaging.ColorMap>对象。</span><span class="sxs-lookup"><span data-stu-id="69bfe-109">To draw a remapped image, initialize an array of <xref:System.Drawing.Imaging.ColorMap> objects.</span></span> <span data-ttu-id="69bfe-110">传递到该数组<xref:System.Drawing.Imaging.ImageAttributes.SetRemapTable%2A>方法<xref:System.Drawing.Imaging.ImageAttributes>对象，并将然后传递<xref:System.Drawing.Imaging.ImageAttributes>对象传递给<xref:System.Drawing.Graphics.DrawImage%2A>方法<xref:System.Drawing.Graphics>对象。</span><span class="sxs-lookup"><span data-stu-id="69bfe-110">Pass that array to the <xref:System.Drawing.Imaging.ImageAttributes.SetRemapTable%2A> method of an <xref:System.Drawing.Imaging.ImageAttributes> object, and then pass the <xref:System.Drawing.Imaging.ImageAttributes> object to the <xref:System.Drawing.Graphics.DrawImage%2A> method of a <xref:System.Drawing.Graphics> object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="69bfe-111">示例</span><span class="sxs-lookup"><span data-stu-id="69bfe-111">Example</span></span>  
 <span data-ttu-id="69bfe-112">下面的示例创建<xref:System.Drawing.Image>从文件 RemapInput.bmp 的对象。</span><span class="sxs-lookup"><span data-stu-id="69bfe-112">The following example creates an <xref:System.Drawing.Image> object from the file RemapInput.bmp.</span></span> <span data-ttu-id="69bfe-113">该代码创建包含单个颜色重新映射表<xref:System.Drawing.Imaging.ColorMap>对象。</span><span class="sxs-lookup"><span data-stu-id="69bfe-113">The code creates a color remap table that consists of a single <xref:System.Drawing.Imaging.ColorMap> object.</span></span> <span data-ttu-id="69bfe-114"><xref:System.Drawing.Imaging.ColorMap.OldColor%2A>属性`ColorRemap`对象为红色，和<xref:System.Drawing.Imaging.ColorMap.NewColor%2A>属性为蓝色。</span><span class="sxs-lookup"><span data-stu-id="69bfe-114">The <xref:System.Drawing.Imaging.ColorMap.OldColor%2A> property of the `ColorRemap` object is red, and the <xref:System.Drawing.Imaging.ColorMap.NewColor%2A> property is blue.</span></span> <span data-ttu-id="69bfe-115">该映像已绘制一次，而无需重新映射和一次使用重新映射。</span><span class="sxs-lookup"><span data-stu-id="69bfe-115">The image is drawn once without remapping and once with remapping.</span></span> <span data-ttu-id="69bfe-116">重映射过程更改所有红色的像素为单位，为蓝色。</span><span class="sxs-lookup"><span data-stu-id="69bfe-116">The remapping process changes all the red pixels to blue.</span></span>  
  
 <span data-ttu-id="69bfe-117">下图右侧显示在左侧的原始映像和变换后的图像。</span><span class="sxs-lookup"><span data-stu-id="69bfe-117">The following illustration shows the original image on the left and the remapped image on the right.</span></span>  
  
 <span data-ttu-id="69bfe-118">![颜色重新映射](../../../../docs/framework/winforms/advanced/media/colortrans7.png "colortrans7")</span><span class="sxs-lookup"><span data-stu-id="69bfe-118">![Color ReMap](../../../../docs/framework/winforms/advanced/media/colortrans7.png "colortrans7")</span></span>  
  
 [!code-csharp[System.Drawing.RecoloringImages#31](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.RecoloringImages/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.RecoloringImages#31](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.RecoloringImages/VB/Class1.vb#31)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="69bfe-119">编译代码</span><span class="sxs-lookup"><span data-stu-id="69bfe-119">Compiling the Code</span></span>  
 <span data-ttu-id="69bfe-120">前面的示例专用于 Windows 窗体，并且它需要<xref:System.Windows.Forms.PaintEventArgs> `e`，这是一个参数的<xref:System.Windows.Forms.Control.Paint>事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="69bfe-120">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs>`e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="69bfe-121">请参阅</span><span class="sxs-lookup"><span data-stu-id="69bfe-121">See Also</span></span>  
 [<span data-ttu-id="69bfe-122">对图像重新着色</span><span class="sxs-lookup"><span data-stu-id="69bfe-122">Recoloring Images</span></span>](../../../../docs/framework/winforms/advanced/recoloring-images.md)  
 [<span data-ttu-id="69bfe-123">图像、位图和图元文件</span><span class="sxs-lookup"><span data-stu-id="69bfe-123">Images, Bitmaps, and Metafiles</span></span>](../../../../docs/framework/winforms/advanced/images-bitmaps-and-metafiles.md)
