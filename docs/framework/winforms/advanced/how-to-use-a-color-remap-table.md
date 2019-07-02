---
title: 如何：使用颜色重新映射表
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- color tables [Windows Forms], remapping colors with
- custom colors [Windows Forms], creating with color remap table
- color remap tables [Windows Forms], using
ms.assetid: 977df1ce-8665-42d4-9fb1-ef7f0ff63419
ms.openlocfilehash: 360ec30563ee5001d784dc7c4ccdb50563867c29
ms.sourcegitcommit: b1cfd260928d464d91e20121f9bdba7611c94d71
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/02/2019
ms.locfileid: "67505760"
---
# <a name="how-to-use-a-color-remap-table"></a><span data-ttu-id="3957c-102">如何：使用颜色重新映射表</span><span class="sxs-lookup"><span data-stu-id="3957c-102">How to: Use a Color Remap Table</span></span>
<span data-ttu-id="3957c-103">重新映射是转换颜色重新映射表根据图像中的颜色的过程。</span><span class="sxs-lookup"><span data-stu-id="3957c-103">Remapping is the process of converting the colors in an image according to a color remap table.</span></span> <span data-ttu-id="3957c-104">颜色重新映射表是一个数组<xref:System.Drawing.Imaging.ColorMap>对象。</span><span class="sxs-lookup"><span data-stu-id="3957c-104">The color remap table is an array of <xref:System.Drawing.Imaging.ColorMap> objects.</span></span> <span data-ttu-id="3957c-105">每个<xref:System.Drawing.Imaging.ColorMap>数组中的对象具有<xref:System.Drawing.Imaging.ColorMap.OldColor%2A>属性和一个<xref:System.Drawing.Imaging.ColorMap.NewColor%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="3957c-105">Each <xref:System.Drawing.Imaging.ColorMap> object in the array has an <xref:System.Drawing.Imaging.ColorMap.OldColor%2A> property and a <xref:System.Drawing.Imaging.ColorMap.NewColor%2A> property.</span></span>  
  
 <span data-ttu-id="3957c-106">当 GDI + 绘制一个图像时，会将每个像素的图像的与旧颜色数组进行比较。</span><span class="sxs-lookup"><span data-stu-id="3957c-106">When GDI+ draws an image, each pixel of the image is compared to the array of old colors.</span></span> <span data-ttu-id="3957c-107">如果像素的颜色与旧的颜色相匹配，其颜色更改为相应的新颜色。</span><span class="sxs-lookup"><span data-stu-id="3957c-107">If a pixel's color matches an old color, its color is changed to the corresponding new color.</span></span> <span data-ttu-id="3957c-108">仅对呈现更改的颜色，图像本身的颜色值 (存储在<xref:System.Drawing.Image>或<xref:System.Drawing.Bitmap>对象) 将不会更改。</span><span class="sxs-lookup"><span data-stu-id="3957c-108">The colors are changed only for rendering — the color values of the image itself (stored in an <xref:System.Drawing.Image> or <xref:System.Drawing.Bitmap> object) are not changed.</span></span>  
  
 <span data-ttu-id="3957c-109">若要绘制重新映射的图像，初始化数组的<xref:System.Drawing.Imaging.ColorMap>对象。</span><span class="sxs-lookup"><span data-stu-id="3957c-109">To draw a remapped image, initialize an array of <xref:System.Drawing.Imaging.ColorMap> objects.</span></span> <span data-ttu-id="3957c-110">传递到该数组<xref:System.Drawing.Imaging.ImageAttributes.SetRemapTable%2A>方法<xref:System.Drawing.Imaging.ImageAttributes>对象，并将传递<xref:System.Drawing.Imaging.ImageAttributes>对象传递给<xref:System.Drawing.Graphics.DrawImage%2A>方法<xref:System.Drawing.Graphics>对象。</span><span class="sxs-lookup"><span data-stu-id="3957c-110">Pass that array to the <xref:System.Drawing.Imaging.ImageAttributes.SetRemapTable%2A> method of an <xref:System.Drawing.Imaging.ImageAttributes> object, and then pass the <xref:System.Drawing.Imaging.ImageAttributes> object to the <xref:System.Drawing.Graphics.DrawImage%2A> method of a <xref:System.Drawing.Graphics> object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3957c-111">示例</span><span class="sxs-lookup"><span data-stu-id="3957c-111">Example</span></span>  
 <span data-ttu-id="3957c-112">下面的示例创建<xref:System.Drawing.Image>RemapInput.bmp 文件中的对象。</span><span class="sxs-lookup"><span data-stu-id="3957c-112">The following example creates an <xref:System.Drawing.Image> object from the file RemapInput.bmp.</span></span> <span data-ttu-id="3957c-113">代码将创建包含单个颜色重新映射表<xref:System.Drawing.Imaging.ColorMap>对象。</span><span class="sxs-lookup"><span data-stu-id="3957c-113">The code creates a color remap table that consists of a single <xref:System.Drawing.Imaging.ColorMap> object.</span></span> <span data-ttu-id="3957c-114"><xref:System.Drawing.Imaging.ColorMap.OldColor%2A>的属性`ColorRemap`对象为红色，和<xref:System.Drawing.Imaging.ColorMap.NewColor%2A>属性显示为蓝色。</span><span class="sxs-lookup"><span data-stu-id="3957c-114">The <xref:System.Drawing.Imaging.ColorMap.OldColor%2A> property of the `ColorRemap` object is red, and the <xref:System.Drawing.Imaging.ColorMap.NewColor%2A> property is blue.</span></span> <span data-ttu-id="3957c-115">映像是在不重新映射的情况下绘制一次，一次用于重新映射。</span><span class="sxs-lookup"><span data-stu-id="3957c-115">The image is drawn once without remapping and once with remapping.</span></span> <span data-ttu-id="3957c-116">重新映射过程会更改所有红色的像素为蓝色。</span><span class="sxs-lookup"><span data-stu-id="3957c-116">The remapping process changes all the red pixels to blue.</span></span>  
  
 <span data-ttu-id="3957c-117">下图显示在右侧左侧上的原始映像和重新映射的图像。</span><span class="sxs-lookup"><span data-stu-id="3957c-117">The following illustration shows the original image on the left and the remapped image on the right.</span></span>  
  
 ![显示原始图像和重新映射的图像的屏幕截图。](./media/how-to-use-a-color-remap-table/original-image-remap-colors.png)  
  
 [!code-csharp[System.Drawing.RecoloringImages#31](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.RecoloringImages/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.RecoloringImages#31](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.RecoloringImages/VB/Class1.vb#31)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="3957c-119">编译代码</span><span class="sxs-lookup"><span data-stu-id="3957c-119">Compiling the Code</span></span>  
 <span data-ttu-id="3957c-120">前面的示例专用于 Windows 窗体，并且它需要<xref:System.Windows.Forms.PaintEventArgs> `e`，这是一个参数的<xref:System.Windows.Forms.Control.Paint>事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="3957c-120">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3957c-121">请参阅</span><span class="sxs-lookup"><span data-stu-id="3957c-121">See also</span></span>

- [<span data-ttu-id="3957c-122">对图像重新着色</span><span class="sxs-lookup"><span data-stu-id="3957c-122">Recoloring Images</span></span>](recoloring-images.md)
- [<span data-ttu-id="3957c-123">图像、位图和图元文件</span><span class="sxs-lookup"><span data-stu-id="3957c-123">Images, Bitmaps, and Metafiles</span></span>](images-bitmaps-and-metafiles.md)
