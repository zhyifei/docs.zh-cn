---
title: 如何：使用颜色矩阵在图像中设置 Alpha 值
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- images [Windows Forms], using color matrices for semi-transparent
- transparency [Windows Forms], color matrices
- matrices [Windows Forms], alpha values
- bitmaps [Windows Forms], using color matrices for semi-transparent
ms.assetid: a27121e6-f7e9-4c09-84e2-f05aa9d2a1bb
ms.openlocfilehash: 9e102f51d00953d05ed1d217a345e32178676ffe
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/09/2019
ms.locfileid: "57716322"
---
# <a name="how-to-use-a-color-matrix-to-set-alpha-values-in-images"></a><span data-ttu-id="3c9a2-102">如何：使用颜色矩阵在图像中设置 Alpha 值</span><span class="sxs-lookup"><span data-stu-id="3c9a2-102">How to: Use a Color Matrix to Set Alpha Values in Images</span></span>
<span data-ttu-id="3c9a2-103"><xref:System.Drawing.Bitmap>类 (派生自<xref:System.Drawing.Image>类) 和<xref:System.Drawing.Imaging.ImageAttributes>类提供用于获取和设置像素值的功能。</span><span class="sxs-lookup"><span data-stu-id="3c9a2-103">The <xref:System.Drawing.Bitmap> class (which inherits from the <xref:System.Drawing.Image> class) and the <xref:System.Drawing.Imaging.ImageAttributes> class provide functionality for getting and setting pixel values.</span></span> <span data-ttu-id="3c9a2-104">可以使用<xref:System.Drawing.Imaging.ImageAttributes>类来修改 alpha 值为整个图像，也可以调用<xref:System.Drawing.Bitmap.SetPixel%2A>方法的<xref:System.Drawing.Bitmap>类来修改单个像素的值。</span><span class="sxs-lookup"><span data-stu-id="3c9a2-104">You can use the <xref:System.Drawing.Imaging.ImageAttributes> class to modify the alpha values for an entire image, or you can call the <xref:System.Drawing.Bitmap.SetPixel%2A> method of the <xref:System.Drawing.Bitmap> class to modify individual pixel values.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3c9a2-105">示例</span><span class="sxs-lookup"><span data-stu-id="3c9a2-105">Example</span></span>  
 <span data-ttu-id="3c9a2-106"><xref:System.Drawing.Imaging.ImageAttributes>类具有许多属性，可用于在呈现期间修改映像。</span><span class="sxs-lookup"><span data-stu-id="3c9a2-106">The <xref:System.Drawing.Imaging.ImageAttributes> class has many properties that you can use to modify images during rendering.</span></span> <span data-ttu-id="3c9a2-107">在以下示例中，<xref:System.Drawing.Imaging.ImageAttributes>对象用于将所有 alpha 值设置为它们的 80%。</span><span class="sxs-lookup"><span data-stu-id="3c9a2-107">In the following example, an <xref:System.Drawing.Imaging.ImageAttributes> object is used to set all the alpha values to 80 percent of what they were.</span></span> <span data-ttu-id="3c9a2-108">这是通过初始化颜色矩阵并设置缩放到 0.8 矩阵中的值的 alpha。</span><span class="sxs-lookup"><span data-stu-id="3c9a2-108">This is done by initializing a color matrix and setting the alpha scaling value in the matrix to 0.8.</span></span> <span data-ttu-id="3c9a2-109">颜色矩阵的地址传递给<xref:System.Drawing.Imaging.ImageAttributes.SetColorMatrix%2A>方法<xref:System.Drawing.Imaging.ImageAttributes>对象，并<xref:System.Drawing.Imaging.ImageAttributes>对象传递给<xref:System.Drawing.Graphics.DrawString%2A>方法<xref:System.Drawing.Graphics>对象。</span><span class="sxs-lookup"><span data-stu-id="3c9a2-109">The address of the color matrix is passed to the <xref:System.Drawing.Imaging.ImageAttributes.SetColorMatrix%2A> method of the <xref:System.Drawing.Imaging.ImageAttributes> object, and the <xref:System.Drawing.Imaging.ImageAttributes> object is passed to the <xref:System.Drawing.Graphics.DrawString%2A> method of the <xref:System.Drawing.Graphics> object.</span></span>  
  
 <span data-ttu-id="3c9a2-110">在呈现期间，在位图中的 alpha 值将转换为它们的 80%。</span><span class="sxs-lookup"><span data-stu-id="3c9a2-110">During rendering, the alpha values in the bitmap are converted to 80 percent of what they were.</span></span> <span data-ttu-id="3c9a2-111">这会导致混合和背景的图像。</span><span class="sxs-lookup"><span data-stu-id="3c9a2-111">This results in an image that is blended with the background.</span></span> <span data-ttu-id="3c9a2-112">如下图所示，位图图像看起来透明;您可以看到通过它黑色实线。</span><span class="sxs-lookup"><span data-stu-id="3c9a2-112">As the following illustration shows, the bitmap image looks transparent; you can see the solid black line through it.</span></span>  
  
 <span data-ttu-id="3c9a2-113">![使用矩阵的 alpha 混合](./media/image2.png "image2")</span><span class="sxs-lookup"><span data-stu-id="3c9a2-113">![Alpha Blending Using a Matrix](./media/image2.png "image2")</span></span>  
  
 <span data-ttu-id="3c9a2-114">图像是通过背景的白色部分，其中具有已与白色混合映像。</span><span class="sxs-lookup"><span data-stu-id="3c9a2-114">Where the image is over the white portion of the background, the image has been blended with the color white.</span></span> <span data-ttu-id="3c9a2-115">图像和黑色线条相交的位置与黑色混合映像。</span><span class="sxs-lookup"><span data-stu-id="3c9a2-115">Where the image crosses the black line, the image is blended with the color black.</span></span>  
  
 [!code-csharp[System.Drawing.AlphaBlending#21](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlphaBlending/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.AlphaBlending#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlphaBlending/VB/Class1.vb#21)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="3c9a2-116">编译代码</span><span class="sxs-lookup"><span data-stu-id="3c9a2-116">Compiling the Code</span></span>  
 <span data-ttu-id="3c9a2-117">前面的示例专用于 Windows 窗体，它需要 <xref:System.Windows.Forms.PaintEventArgs>`e`，这是 <xref:System.Windows.Forms.PaintEventHandler> 的参数。</span><span class="sxs-lookup"><span data-stu-id="3c9a2-117">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs>`e`, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3c9a2-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="3c9a2-118">See also</span></span>
- [<span data-ttu-id="3c9a2-119">Windows 窗体中的图形和绘制</span><span class="sxs-lookup"><span data-stu-id="3c9a2-119">Graphics and Drawing in Windows Forms</span></span>](graphics-and-drawing-in-windows-forms.md)
- [<span data-ttu-id="3c9a2-120">alpha 值混合处理直线和填充</span><span class="sxs-lookup"><span data-stu-id="3c9a2-120">Alpha Blending Lines and Fills</span></span>](alpha-blending-lines-and-fills.md)
