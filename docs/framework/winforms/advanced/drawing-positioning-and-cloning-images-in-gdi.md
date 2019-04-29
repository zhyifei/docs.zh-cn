---
title: 在 GDI+ 中绘制、定位和克隆图像
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- raster images [Windows Forms]
- images [Windows Forms], positioning
- drawing [Windows Forms], images
- drawing [Windows Forms], raster images
- images [Windows Forms], cloning
- images [Windows Forms], drawing
- GDI+, drawing images
- GDI+, cloning images
- GDI+, positioning images
ms.assetid: 09f0c07a-19c0-43b4-90a2-862a10545ce8
ms.openlocfilehash: b5f98e7bdef9ff8ed0a4cd0e040cb92a31f30503
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61756896"
---
# <a name="drawing-positioning-and-cloning-images-in-gdi"></a><span data-ttu-id="65c25-102">在 GDI+ 中绘制、定位和克隆图像</span><span class="sxs-lookup"><span data-stu-id="65c25-102">Drawing, Positioning, and Cloning Images in GDI+</span></span>
<span data-ttu-id="65c25-103">可以使用<xref:System.Drawing.Bitmap>类来加载和显示光栅图像，还可以使用<xref:System.Drawing.Imaging.Metafile>类来加载和显示矢量图像。</span><span class="sxs-lookup"><span data-stu-id="65c25-103">You can use the <xref:System.Drawing.Bitmap> class to load and display raster images, and you can use the <xref:System.Drawing.Imaging.Metafile> class to load and display vector images.</span></span> <span data-ttu-id="65c25-104"><xref:System.Drawing.Bitmap>并<xref:System.Drawing.Imaging.Metafile>类都继承自<xref:System.Drawing.Image>类。</span><span class="sxs-lookup"><span data-stu-id="65c25-104">The <xref:System.Drawing.Bitmap> and <xref:System.Drawing.Imaging.Metafile> classes inherit from the <xref:System.Drawing.Image> class.</span></span> <span data-ttu-id="65c25-105">若要显示矢量图像，您需要的实例<xref:System.Drawing.Graphics>类和一个<xref:System.Drawing.Imaging.Metafile>。</span><span class="sxs-lookup"><span data-stu-id="65c25-105">To display a vector image, you need an instance of the <xref:System.Drawing.Graphics> class and a <xref:System.Drawing.Imaging.Metafile>.</span></span> <span data-ttu-id="65c25-106">若要显示光栅图像，您需要的实例<xref:System.Drawing.Graphics>类和一个<xref:System.Drawing.Bitmap>。</span><span class="sxs-lookup"><span data-stu-id="65c25-106">To display a raster image, you need an instance of the <xref:System.Drawing.Graphics> class and a <xref:System.Drawing.Bitmap>.</span></span> <span data-ttu-id="65c25-107">实例<xref:System.Drawing.Graphics>类提供了<xref:System.Drawing.Graphics.DrawImage%2A>方法，用于接收<xref:System.Drawing.Imaging.Metafile>或<xref:System.Drawing.Bitmap>作为自变量。</span><span class="sxs-lookup"><span data-stu-id="65c25-107">The instance of the <xref:System.Drawing.Graphics> class provides the <xref:System.Drawing.Graphics.DrawImage%2A> method, which receives the <xref:System.Drawing.Imaging.Metafile> or <xref:System.Drawing.Bitmap> as an argument.</span></span>  
  
## <a name="file-types-and-cloning"></a><span data-ttu-id="65c25-108">文件类型和克隆</span><span class="sxs-lookup"><span data-stu-id="65c25-108">File Types and Cloning</span></span>  
 <span data-ttu-id="65c25-109">下面的代码示例演示如何构造<xref:System.Drawing.Bitmap>Climber.jpg 文件中，并显示位图。</span><span class="sxs-lookup"><span data-stu-id="65c25-109">The following code example shows how to construct a <xref:System.Drawing.Bitmap> from the file Climber.jpg and displays the bitmap.</span></span> <span data-ttu-id="65c25-110">图像的左上角的目标点 （10，10） 中的第二个和第三个参数指定。</span><span class="sxs-lookup"><span data-stu-id="65c25-110">The destination point for the upper-left corner of the image, (10, 10), is specified in the second and third parameters.</span></span>  
  
 [!code-csharp[System.Drawing.ImagesBitmapsMetafiles#11](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.ImagesBitmapsMetafiles#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/VB/Class1.vb#11)]  
  
 <span data-ttu-id="65c25-111">下图显示图像。</span><span class="sxs-lookup"><span data-stu-id="65c25-111">The following illustration shows the image.</span></span>  
  
 <span data-ttu-id="65c25-112">![图像示例](./media/aboutgdip03-art04.gif "AboutGdip03_Art04")</span><span class="sxs-lookup"><span data-stu-id="65c25-112">![Image Sample](./media/aboutgdip03-art04.gif "AboutGdip03_Art04")</span></span>  
  
 <span data-ttu-id="65c25-113">您可以构造<xref:System.Drawing.Bitmap>对象使用不同的图形文件格式：BMP、 GIF、 JPEG、 EXIF、 PNG、 TIFF 和图标。</span><span class="sxs-lookup"><span data-stu-id="65c25-113">You can construct <xref:System.Drawing.Bitmap> objects from a variety of graphics file formats: BMP, GIF, JPEG, EXIF, PNG, TIFF, and ICON.</span></span>  
  
 <span data-ttu-id="65c25-114">下面的代码示例演示如何构造<xref:System.Drawing.Bitmap>中不同的文件类型的对象，然后显示位图。</span><span class="sxs-lookup"><span data-stu-id="65c25-114">The following code example shows how to construct <xref:System.Drawing.Bitmap> objects from a variety of file types and then displays the bitmaps.</span></span>  
  
 [!code-csharp[System.Drawing.ImagesBitmapsMetafiles#12](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/CS/Class1.cs#12)]
 [!code-vb[System.Drawing.ImagesBitmapsMetafiles#12](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/VB/Class1.vb#12)]  
  
 <span data-ttu-id="65c25-115"><xref:System.Drawing.Bitmap>类提供了<xref:System.Drawing.Bitmap.Clone%2A>方法可用于制作一份现有<xref:System.Drawing.Bitmap>。</span><span class="sxs-lookup"><span data-stu-id="65c25-115">The <xref:System.Drawing.Bitmap> class provides a <xref:System.Drawing.Bitmap.Clone%2A> method that you can use to make a copy of an existing <xref:System.Drawing.Bitmap>.</span></span> <span data-ttu-id="65c25-116"><xref:System.Drawing.Bitmap.Clone%2A>方法具有可用于指定你想要复制的原始位图的部分的源矩形参数。</span><span class="sxs-lookup"><span data-stu-id="65c25-116">The <xref:System.Drawing.Bitmap.Clone%2A> method has a source rectangle parameter that you can use to specify the portion of the original bitmap that you want to copy.</span></span> <span data-ttu-id="65c25-117">下面的代码示例演示如何创建<xref:System.Drawing.Bitmap>通过克隆现有的上半<xref:System.Drawing.Bitmap>。</span><span class="sxs-lookup"><span data-stu-id="65c25-117">The following code example shows how to create a <xref:System.Drawing.Bitmap> by cloning the top half of an existing <xref:System.Drawing.Bitmap>.</span></span> <span data-ttu-id="65c25-118">然后绘制这两个映像。</span><span class="sxs-lookup"><span data-stu-id="65c25-118">Then both images are drawn.</span></span>  
  
 [!code-csharp[System.Drawing.ImagesBitmapsMetafiles#13](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/CS/Class1.cs#13)]
 [!code-vb[System.Drawing.ImagesBitmapsMetafiles#13](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/VB/Class1.vb#13)]  
  
 <span data-ttu-id="65c25-119">下图显示了两个映像。</span><span class="sxs-lookup"><span data-stu-id="65c25-119">The following illustration shows the two images.</span></span>  
  
 <span data-ttu-id="65c25-120">![Cropping](./media/aboutgdip03-art05.gif "AboutGdip03_Art05")</span><span class="sxs-lookup"><span data-stu-id="65c25-120">![Cropping](./media/aboutgdip03-art05.gif "AboutGdip03_Art05")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="65c25-121">请参阅</span><span class="sxs-lookup"><span data-stu-id="65c25-121">See also</span></span>

- [<span data-ttu-id="65c25-122">图像、位图和图元文件</span><span class="sxs-lookup"><span data-stu-id="65c25-122">Images, Bitmaps, and Metafiles</span></span>](images-bitmaps-and-metafiles.md)
- [<span data-ttu-id="65c25-123">如何：创建用于绘制图形对象</span><span class="sxs-lookup"><span data-stu-id="65c25-123">How to: Create Graphics Objects for Drawing</span></span>](how-to-create-graphics-objects-for-drawing.md)
- [<span data-ttu-id="65c25-124">使用图像、位图、图标和图元文件</span><span class="sxs-lookup"><span data-stu-id="65c25-124">Working with Images, Bitmaps, Icons, and Metafiles</span></span>](working-with-images-bitmaps-icons-and-metafiles.md)
