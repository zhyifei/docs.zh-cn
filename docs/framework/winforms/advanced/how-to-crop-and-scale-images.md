---
title: 如何：裁剪和缩放图像
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- images [Windows Forms], cropping
- images [Windows Forms], scaling
ms.assetid: 053e3360-bca0-4b25-9afa-0e77a6f17b03
ms.openlocfilehash: 4257431881565f9160f45795111d374cc680dedd
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59189878"
---
# <a name="how-to-crop-and-scale-images"></a><span data-ttu-id="38775-102">如何：裁剪和缩放图像</span><span class="sxs-lookup"><span data-stu-id="38775-102">How to: Crop and Scale Images</span></span>
<span data-ttu-id="38775-103"><xref:System.Drawing.Graphics>类提供了若干<xref:System.Drawing.Graphics.DrawImage%2A>方法，其中一些具有可用于裁剪和缩放图像的源和目标矩形参数。</span><span class="sxs-lookup"><span data-stu-id="38775-103">The <xref:System.Drawing.Graphics> class provides several <xref:System.Drawing.Graphics.DrawImage%2A> methods, some of which have source and destination rectangle parameters that you can use to crop and scale images.</span></span>  
  
## <a name="example"></a><span data-ttu-id="38775-104">示例</span><span class="sxs-lookup"><span data-stu-id="38775-104">Example</span></span>  
 <span data-ttu-id="38775-105">下面的示例构造<xref:System.Drawing.Image>从磁盘文件 Apple.gif 对象。</span><span class="sxs-lookup"><span data-stu-id="38775-105">The following example constructs an <xref:System.Drawing.Image> object from the disk file Apple.gif.</span></span> <span data-ttu-id="38775-106">该代码在其原始大小绘制整个 apple 图像。</span><span class="sxs-lookup"><span data-stu-id="38775-106">The code draws the entire apple image in its original size.</span></span> <span data-ttu-id="38775-107">然后，代码调用<xref:System.Drawing.Graphics.DrawImage%2A>方法的<xref:System.Drawing.Graphics>对象大于原始 apple 映像的目标矩形中绘制 apple 图像的一部分。</span><span class="sxs-lookup"><span data-stu-id="38775-107">The code then calls the <xref:System.Drawing.Graphics.DrawImage%2A> method of a <xref:System.Drawing.Graphics> object to draw a portion of the apple image in a destination rectangle that is larger than the original apple image.</span></span>  
  
 <span data-ttu-id="38775-108"><xref:System.Drawing.Graphics.DrawImage%2A>方法确定 apple 通过查看源矩形，由第三个、 第四，指定第五和第六个参数绘制的哪个部分。</span><span class="sxs-lookup"><span data-stu-id="38775-108">The <xref:System.Drawing.Graphics.DrawImage%2A> method determines which portion of the apple to draw by looking at the source rectangle, which is specified by the third, fourth, fifth, and sixth arguments.</span></span> <span data-ttu-id="38775-109">在这种情况下，在 apple 要裁剪成其宽度的 75%和 75%的窗体的高度。</span><span class="sxs-lookup"><span data-stu-id="38775-109">In this case, the apple is cropped to 75 percent of its width and 75 percent of its height.</span></span>  
  
 <span data-ttu-id="38775-110"><xref:System.Drawing.Graphics.DrawImage%2A>方法确定绘制裁剪后的 apple 的位置和大小以便裁剪后的 apple 通过查看目标矩形，即指定的第二个参数。</span><span class="sxs-lookup"><span data-stu-id="38775-110">The <xref:System.Drawing.Graphics.DrawImage%2A> method determines where to draw the cropped apple and how big to make the cropped apple by looking at the destination rectangle, which is specified by the second argument.</span></span> <span data-ttu-id="38775-111">在这种情况下，目标矩形是更广的 30%，比原始图像高度的 30%。</span><span class="sxs-lookup"><span data-stu-id="38775-111">In this case, the destination rectangle is 30 percent wider and 30 percent taller than the original image.</span></span>  
  
 <span data-ttu-id="38775-112">下图显示了原始 apple 和缩放、 裁剪 apple。</span><span class="sxs-lookup"><span data-stu-id="38775-112">The following illustration shows the original apple and the scaled, cropped apple.</span></span>  
  
 ![原始图像和裁剪的同一映像的屏幕截图。](./media/how-to-crop-and-scale-images/original-image-cropped-image.png)  
  
 [!code-csharp[System.Drawing.WorkingWithImages#11](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.WorkingWithImages#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#11)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="38775-114">编译代码</span><span class="sxs-lookup"><span data-stu-id="38775-114">Compiling the Code</span></span>  
 <span data-ttu-id="38775-115">前面的示例专用于 Windows 窗体，并且它需要<xref:System.Windows.Forms.PaintEventArgs> `e`，这是一个参数的<xref:System.Windows.Forms.Control.Paint>事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="38775-115">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span> <span data-ttu-id="38775-116">请务必替换`Apple.gif`与图像文件名称和在您的系统都有效的路径。</span><span class="sxs-lookup"><span data-stu-id="38775-116">Make sure to replace `Apple.gif` with an image file name and path that are valid on your system.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="38775-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="38775-117">See also</span></span>

- [<span data-ttu-id="38775-118">图像、位图和图元文件</span><span class="sxs-lookup"><span data-stu-id="38775-118">Images, Bitmaps, and Metafiles</span></span>](images-bitmaps-and-metafiles.md)
- [<span data-ttu-id="38775-119">使用图像、位图、图标和图元文件</span><span class="sxs-lookup"><span data-stu-id="38775-119">Working with Images, Bitmaps, Icons, and Metafiles</span></span>](working-with-images-bitmaps-icons-and-metafiles.md)
