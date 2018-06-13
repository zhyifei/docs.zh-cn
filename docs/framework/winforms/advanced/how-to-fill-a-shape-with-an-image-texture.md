---
title: 如何：用图像纹理填充形状
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- images [Windows Forms], using with brushes
- bitmaps [Windows Forms], using texture
- shapes [Windows Forms], filling with images
ms.assetid: 508da5a6-2433-4d2b-9680-eaeae4e96e3b
ms.openlocfilehash: c1eb090bebcced125193c1db16087b6165d27ff3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33523285"
---
# <a name="how-to-fill-a-shape-with-an-image-texture"></a><span data-ttu-id="479f6-102">如何：用图像纹理填充形状</span><span class="sxs-lookup"><span data-stu-id="479f6-102">How to: Fill a Shape with an Image Texture</span></span>
<span data-ttu-id="479f6-103">可以通过用纹理填充的闭合的形状<xref:System.Drawing.Image>类和<xref:System.Drawing.TextureBrush>类。</span><span class="sxs-lookup"><span data-stu-id="479f6-103">You can fill a closed shape with a texture by using the <xref:System.Drawing.Image> class and the <xref:System.Drawing.TextureBrush> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="479f6-104">示例</span><span class="sxs-lookup"><span data-stu-id="479f6-104">Example</span></span>  
 <span data-ttu-id="479f6-105">下面的示例填充的映像的椭圆。</span><span class="sxs-lookup"><span data-stu-id="479f6-105">The following example fills an ellipse with an image.</span></span> <span data-ttu-id="479f6-106">代码构造了<xref:System.Drawing.Image>对象，并随后将传递该地址<xref:System.Drawing.Image>对象的自变量作为<xref:System.Drawing.TextureBrush.%23ctor%2A>构造函数。</span><span class="sxs-lookup"><span data-stu-id="479f6-106">The code constructs an <xref:System.Drawing.Image> object, and then passes the address of that <xref:System.Drawing.Image> object as an argument to a <xref:System.Drawing.TextureBrush.%23ctor%2A> constructor.</span></span> <span data-ttu-id="479f6-107">第三个语句缩放图像，并第四个语句填充椭圆使用的缩放图像的重复副本。</span><span class="sxs-lookup"><span data-stu-id="479f6-107">The third statement scales the image, and the fourth statement fills the ellipse with repeated copies of the scaled image.</span></span>  
  
 <span data-ttu-id="479f6-108">在下面的代码中，<xref:System.Drawing.TextureBrush.Transform%2A>属性包含它绘制之前应用于映像的转换。</span><span class="sxs-lookup"><span data-stu-id="479f6-108">In the following code, the <xref:System.Drawing.TextureBrush.Transform%2A> property contains the transformation that is applied to the image before it is drawn.</span></span> <span data-ttu-id="479f6-109">假设原始图像的宽度为 640 像素和 480 像素的高度。</span><span class="sxs-lookup"><span data-stu-id="479f6-109">Assume that the original image has a width of 640 pixels and a height of 480 pixels.</span></span> <span data-ttu-id="479f6-110">转换将图像缩小到 75 × 75 通过设置水平和垂直缩放值。</span><span class="sxs-lookup"><span data-stu-id="479f6-110">The transform shrinks the image to 75×75 by setting the horizontal and vertical scaling values.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="479f6-111">在下面的示例中，图像大小为 75 × 75，和椭圆大小为 150 × 250 个字符。</span><span class="sxs-lookup"><span data-stu-id="479f6-111">In the following example, the image size is 75×75, and the ellipse size is 150×250.</span></span> <span data-ttu-id="479f6-112">由于映像是小于它所填充的椭圆，椭圆平铺与映像。</span><span class="sxs-lookup"><span data-stu-id="479f6-112">Because the image is smaller than the ellipse it is filling, the ellipse is tiled with the image.</span></span> <span data-ttu-id="479f6-113">达到平铺意味着，将重复图像的水平和垂直之前形状的边界。</span><span class="sxs-lookup"><span data-stu-id="479f6-113">Tiling means that the image is repeated horizontally and vertically until the boundary of the shape is reached.</span></span> <span data-ttu-id="479f6-114">有关平铺的详细信息，请参阅[如何： 平铺图像的形状](../../../../docs/framework/winforms/advanced/how-to-tile-a-shape-with-an-image.md)。</span><span class="sxs-lookup"><span data-stu-id="479f6-114">For more information about tiling, see [How to: Tile a Shape with an Image](../../../../docs/framework/winforms/advanced/how-to-tile-a-shape-with-an-image.md).</span></span>  
  
 [!code-csharp[System.Drawing.UsingABrush#21](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingABrush/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.UsingABrush#21](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingABrush/VB/Class1.vb#21)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="479f6-115">编译代码</span><span class="sxs-lookup"><span data-stu-id="479f6-115">Compiling the Code</span></span>  
 <span data-ttu-id="479f6-116">前面的示例专用于 Windows 窗体，它需要 <xref:System.Windows.Forms.PaintEventArgs> `e`，后者是 <xref:System.Windows.Forms.Control.Paint> 事件处理程序的参数。</span><span class="sxs-lookup"><span data-stu-id="479f6-116">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="479f6-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="479f6-117">See Also</span></span>  
 [<span data-ttu-id="479f6-118">使用画笔填充形状</span><span class="sxs-lookup"><span data-stu-id="479f6-118">Using a Brush to Fill Shapes</span></span>](../../../../docs/framework/winforms/advanced/using-a-brush-to-fill-shapes.md)
