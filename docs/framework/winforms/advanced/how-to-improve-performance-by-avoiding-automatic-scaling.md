---
title: 如何：通过避免自动缩放来改善性能
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- automatic scaling
- images [Windows Forms], improving performance
- images [Windows Forms], using without automatic scaling
- performance [Windows Forms], improving image
ms.assetid: 5fe2c95d-8653-4d55-bf0d-e5afa28f223b
ms.openlocfilehash: dd1a1545dce33de1ce11938db8495ebf311dadda
ms.sourcegitcommit: b1cfd260928d464d91e20121f9bdba7611c94d71
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/02/2019
ms.locfileid: "67506203"
---
# <a name="how-to-improve-performance-by-avoiding-automatic-scaling"></a><span data-ttu-id="027fc-102">如何：通过避免自动缩放来改善性能</span><span class="sxs-lookup"><span data-stu-id="027fc-102">How to: Improve Performance by Avoiding Automatic Scaling</span></span>
<span data-ttu-id="027fc-103">GDI + 可能会自动将图像缩放在绘制时，这会降低性能。</span><span class="sxs-lookup"><span data-stu-id="027fc-103">GDI+ may automatically scale an image as you draw it, which would decrease performance.</span></span> <span data-ttu-id="027fc-104">或者，可以控制图像缩放通过将传递到目标矩形的尺寸<xref:System.Drawing.Graphics.DrawImage%2A>方法。</span><span class="sxs-lookup"><span data-stu-id="027fc-104">Alternatively, you can control the scaling of the image by passing the dimensions of the destination rectangle to the <xref:System.Drawing.Graphics.DrawImage%2A> method.</span></span>  
  
 <span data-ttu-id="027fc-105">例如，以下调用到<xref:System.Drawing.Graphics.DrawImage%2A>方法指定的左上角 （50，30），但未指定目标矩形。</span><span class="sxs-lookup"><span data-stu-id="027fc-105">For example, the following call to the <xref:System.Drawing.Graphics.DrawImage%2A> method specifies an upper-left corner of (50, 30) but does not specify a destination rectangle.</span></span>  
  
 [!code-csharp[System.Drawing.WorkingWithImages#31](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.WorkingWithImages#31](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#31)]  
  
 <span data-ttu-id="027fc-106">虽然这是最简单版本的<xref:System.Drawing.Graphics.DrawImage%2A>方法所需的参数个数不一定是最有效。</span><span class="sxs-lookup"><span data-stu-id="027fc-106">Although this is the easiest version of the <xref:System.Drawing.Graphics.DrawImage%2A> method in terms of the number of required arguments, it is not necessarily the most efficient.</span></span> <span data-ttu-id="027fc-107">如果使用的 GDI + （通常每英寸 96 点） 的解决方法是不同于存储中的分辨率<xref:System.Drawing.Image>对象，则<xref:System.Drawing.Graphics.DrawImage%2A>方法会将图像缩放。</span><span class="sxs-lookup"><span data-stu-id="027fc-107">If the resolution used by GDI+ (usually 96 dots per inch) is different from the resolution stored in the <xref:System.Drawing.Image> object, then the <xref:System.Drawing.Graphics.DrawImage%2A> method will scale the image.</span></span> <span data-ttu-id="027fc-108">例如，假设<xref:System.Drawing.Image>对象具有宽度为 216 像素和存储的水平分辨率值为 72 以每英寸点数。</span><span class="sxs-lookup"><span data-stu-id="027fc-108">For example, suppose an <xref:System.Drawing.Image> object has a width of 216 pixels and a stored horizontal resolution value of 72 dots per inch.</span></span> <span data-ttu-id="027fc-109">因为 216/72 为 3，<xref:System.Drawing.Graphics.DrawImage%2A>会将图像缩放以使其具有最适宜的分辨率的每英寸 96 点 3 英寸的宽度。</span><span class="sxs-lookup"><span data-stu-id="027fc-109">Because 216/72 is 3, <xref:System.Drawing.Graphics.DrawImage%2A> will scale the image so that it has a width of 3 inches at a resolution of 96 dots per inch.</span></span> <span data-ttu-id="027fc-110">也就是说，<xref:System.Drawing.Graphics.DrawImage%2A>将显示图像的宽度为 96 x 3 = 288 条的像素为单位。</span><span class="sxs-lookup"><span data-stu-id="027fc-110">That is, <xref:System.Drawing.Graphics.DrawImage%2A> will display an image that has a width of 96x3 = 288 pixels.</span></span>  
  
 <span data-ttu-id="027fc-111">即使您的屏幕分辨率每英寸 96 点不同，GDI + 将可能将图像缩放，像屏幕分辨率每英寸 96 点。</span><span class="sxs-lookup"><span data-stu-id="027fc-111">Even if your screen resolution is different from 96 dots per inch, GDI+ will probably scale the image as if the screen resolution were 96 dots per inch.</span></span> <span data-ttu-id="027fc-112">这是因为 GDI +<xref:System.Drawing.Graphics>对象是与设备上下文相关联，当 GDI + 查询屏幕分辨率的设备上下文，结果通常是 96，而不考虑实际屏幕分辨率。</span><span class="sxs-lookup"><span data-stu-id="027fc-112">That is because a GDI+ <xref:System.Drawing.Graphics> object is associated with a device context, and when GDI+ queries the device context for the screen resolution, the result is usually 96, regardless of the actual screen resolution.</span></span> <span data-ttu-id="027fc-113">通过指定目标矩形中的自动缩放，可以避免<xref:System.Drawing.Graphics.DrawImage%2A>方法。</span><span class="sxs-lookup"><span data-stu-id="027fc-113">You can avoid automatic scaling by specifying the destination rectangle in the <xref:System.Drawing.Graphics.DrawImage%2A> method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="027fc-114">示例</span><span class="sxs-lookup"><span data-stu-id="027fc-114">Example</span></span>  
 <span data-ttu-id="027fc-115">下面的示例绘制两次相同的映像。</span><span class="sxs-lookup"><span data-stu-id="027fc-115">The following example draws the same image twice.</span></span> <span data-ttu-id="027fc-116">在第一种情况下，未指定的宽度和高度的目标矩形，并自动缩放图像。</span><span class="sxs-lookup"><span data-stu-id="027fc-116">In the first case, the width and height of the destination rectangle are not specified, and the image is automatically scaled.</span></span> <span data-ttu-id="027fc-117">在第二种情况下，指定的宽度和高度 （以像素为单位） 的目标矩形是相同的宽度和原始图像的高度。</span><span class="sxs-lookup"><span data-stu-id="027fc-117">In the second case, the width and height (measured in pixels) of the destination rectangle are specified to be the same as the width and height of the original image.</span></span> <span data-ttu-id="027fc-118">下图显示了两次呈现的图像：</span><span class="sxs-lookup"><span data-stu-id="027fc-118">The following illustration shows the image rendered twice:</span></span>  
  
 ![显示与缩放后的纹理的图像的屏幕截图。](./media/how-to-improve-performance-by-avoiding-automatic-scaling/two-scaled-texture-images.png)  
  
 [!code-csharp[System.Drawing.WorkingWithImages#32](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#32)]
 [!code-vb[System.Drawing.WorkingWithImages#32](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#32)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="027fc-120">编译代码</span><span class="sxs-lookup"><span data-stu-id="027fc-120">Compiling the Code</span></span>  
 <span data-ttu-id="027fc-121">前面的示例专用于 Windows 窗体，并且它需要<xref:System.Windows.Forms.PaintEventArgs> `e`，这是一个参数的<xref:System.Windows.Forms.Control.Paint>事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="027fc-121">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span> <span data-ttu-id="027fc-122">将映像名称和在您的系统都有效的路径替换为 Texture.jpg。</span><span class="sxs-lookup"><span data-stu-id="027fc-122">Replace Texture.jpg with an image name and path that are valid on your system.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="027fc-123">请参阅</span><span class="sxs-lookup"><span data-stu-id="027fc-123">See also</span></span>

- [<span data-ttu-id="027fc-124">图像、位图和图元文件</span><span class="sxs-lookup"><span data-stu-id="027fc-124">Images, Bitmaps, and Metafiles</span></span>](images-bitmaps-and-metafiles.md)
- [<span data-ttu-id="027fc-125">使用图像、位图、图标和图元文件</span><span class="sxs-lookup"><span data-stu-id="027fc-125">Working with Images, Bitmaps, Icons, and Metafiles</span></span>](working-with-images-bitmaps-icons-and-metafiles.md)
