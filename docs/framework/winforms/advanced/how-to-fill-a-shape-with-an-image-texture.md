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
ms.openlocfilehash: 89ebad6773b076514f5a745db653e0e0a18d4b48
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/09/2019
ms.locfileid: "57708439"
---
# <a name="how-to-fill-a-shape-with-an-image-texture"></a><span data-ttu-id="de9d5-102">如何：用图像纹理填充形状</span><span class="sxs-lookup"><span data-stu-id="de9d5-102">How to: Fill a Shape with an Image Texture</span></span>
<span data-ttu-id="de9d5-103">可以通过用纹理填充闭合的形状<xref:System.Drawing.Image>类和<xref:System.Drawing.TextureBrush>类。</span><span class="sxs-lookup"><span data-stu-id="de9d5-103">You can fill a closed shape with a texture by using the <xref:System.Drawing.Image> class and the <xref:System.Drawing.TextureBrush> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="de9d5-104">示例</span><span class="sxs-lookup"><span data-stu-id="de9d5-104">Example</span></span>  
 <span data-ttu-id="de9d5-105">下面的示例填充椭圆的映像。</span><span class="sxs-lookup"><span data-stu-id="de9d5-105">The following example fills an ellipse with an image.</span></span> <span data-ttu-id="de9d5-106">该代码构造<xref:System.Drawing.Image>对象，并随后将传递该地址<xref:System.Drawing.Image>对象的参数作为<xref:System.Drawing.TextureBrush.%23ctor%2A>构造函数。</span><span class="sxs-lookup"><span data-stu-id="de9d5-106">The code constructs an <xref:System.Drawing.Image> object, and then passes the address of that <xref:System.Drawing.Image> object as an argument to a <xref:System.Drawing.TextureBrush.%23ctor%2A> constructor.</span></span> <span data-ttu-id="de9d5-107">第三个语句缩放图像，并第四个语句填充椭圆的缩放的图像的重复副本。</span><span class="sxs-lookup"><span data-stu-id="de9d5-107">The third statement scales the image, and the fourth statement fills the ellipse with repeated copies of the scaled image.</span></span>  
  
 <span data-ttu-id="de9d5-108">在下面的代码，<xref:System.Drawing.TextureBrush.Transform%2A>属性包含的转换，以应用于映像。</span><span class="sxs-lookup"><span data-stu-id="de9d5-108">In the following code, the <xref:System.Drawing.TextureBrush.Transform%2A> property contains the transformation that is applied to the image before it is drawn.</span></span> <span data-ttu-id="de9d5-109">假设原始图像的宽度为 640 像素，高度为 480 像素。</span><span class="sxs-lookup"><span data-stu-id="de9d5-109">Assume that the original image has a width of 640 pixels and a height of 480 pixels.</span></span> <span data-ttu-id="de9d5-110">转换将图像缩小到 75 × 75 设置了水平和垂直缩放值。</span><span class="sxs-lookup"><span data-stu-id="de9d5-110">The transform shrinks the image to 75×75 by setting the horizontal and vertical scaling values.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="de9d5-111">在以下示例中，映像大小为 75 × 75，和椭圆大小为 150 × 250 个字符。</span><span class="sxs-lookup"><span data-stu-id="de9d5-111">In the following example, the image size is 75×75, and the ellipse size is 150×250.</span></span> <span data-ttu-id="de9d5-112">由于映像是小于它所填充的椭圆，椭圆与图像平铺。</span><span class="sxs-lookup"><span data-stu-id="de9d5-112">Because the image is smaller than the ellipse it is filling, the ellipse is tiled with the image.</span></span> <span data-ttu-id="de9d5-113">达到了平铺意味着，重复图像水平和垂直直到形状的边界。</span><span class="sxs-lookup"><span data-stu-id="de9d5-113">Tiling means that the image is repeated horizontally and vertically until the boundary of the shape is reached.</span></span> <span data-ttu-id="de9d5-114">有关平铺的详细信息，请参阅[如何：使用图像形状中平铺](how-to-tile-a-shape-with-an-image.md)。</span><span class="sxs-lookup"><span data-stu-id="de9d5-114">For more information about tiling, see [How to: Tile a Shape with an Image](how-to-tile-a-shape-with-an-image.md).</span></span>  
  
 [!code-csharp[System.Drawing.UsingABrush#21](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingABrush/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.UsingABrush#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingABrush/VB/Class1.vb#21)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="de9d5-115">编译代码</span><span class="sxs-lookup"><span data-stu-id="de9d5-115">Compiling the Code</span></span>  
 <span data-ttu-id="de9d5-116">前面的示例专用于 Windows 窗体，它需要 <xref:System.Windows.Forms.PaintEventArgs> `e`，后者是 <xref:System.Windows.Forms.Control.Paint> 事件处理程序的参数。</span><span class="sxs-lookup"><span data-stu-id="de9d5-116">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="de9d5-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="de9d5-117">See also</span></span>
- [<span data-ttu-id="de9d5-118">使用画笔填充形状</span><span class="sxs-lookup"><span data-stu-id="de9d5-118">Using a Brush to Fill Shapes</span></span>](using-a-brush-to-fill-shapes.md)
