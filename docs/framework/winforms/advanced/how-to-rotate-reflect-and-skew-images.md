---
title: 如何：旋转、反射和倾斜图像
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- images [Windows Forms], reflecting
- images [Windows Forms], rotating
- images [Windows Forms], skewing
ms.assetid: a3bf97eb-63ed-425a-ba07-dcc65efb567c
ms.openlocfilehash: 505028c491228ffdf9c11d0c71dcd5e1afdc5103
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61967142"
---
# <a name="how-to-rotate-reflect-and-skew-images"></a><span data-ttu-id="acfeb-102">如何：旋转、反射和倾斜图像</span><span class="sxs-lookup"><span data-stu-id="acfeb-102">How to: Rotate, Reflect, and Skew Images</span></span>
<span data-ttu-id="acfeb-103">可以旋转、 反射和倾斜图像通过指定的原始图像的左上角、 右上方和左下角的目标点。</span><span class="sxs-lookup"><span data-stu-id="acfeb-103">You can rotate, reflect, and skew an image by specifying destination points for the upper-left, upper-right, and lower-left corners of the original image.</span></span> <span data-ttu-id="acfeb-104">三个目标点确定将原始矩形图像映射到一个平行四边形的仿射转换。</span><span class="sxs-lookup"><span data-stu-id="acfeb-104">The three destination points determine an affine transformation that maps the original rectangular image to a parallelogram.</span></span>  
  
## <a name="example"></a><span data-ttu-id="acfeb-105">示例</span><span class="sxs-lookup"><span data-stu-id="acfeb-105">Example</span></span>  
 <span data-ttu-id="acfeb-106">例如，假设原始图像是一个矩形，左上角位于 （0，0），在右上角 （100，0），并在左下角 （0，50）。</span><span class="sxs-lookup"><span data-stu-id="acfeb-106">For example, suppose the original image is a rectangle with upper-left corner at (0, 0), upper-right corner at (100, 0), and lower-left corner at (0, 50).</span></span> <span data-ttu-id="acfeb-107">现在假设您将它们映射三个指向目标点，如下所示。</span><span class="sxs-lookup"><span data-stu-id="acfeb-107">Now suppose you map those three points to destination points as follows.</span></span>  
  
|<span data-ttu-id="acfeb-108">原始点</span><span class="sxs-lookup"><span data-stu-id="acfeb-108">Original point</span></span>|<span data-ttu-id="acfeb-109">目标点</span><span class="sxs-lookup"><span data-stu-id="acfeb-109">Destination point</span></span>|  
|--------------------|-----------------------|  
|<span data-ttu-id="acfeb-110">左上角 （0，0）</span><span class="sxs-lookup"><span data-stu-id="acfeb-110">Upper-left (0, 0)</span></span>|<span data-ttu-id="acfeb-111">(200, 20)</span><span class="sxs-lookup"><span data-stu-id="acfeb-111">(200, 20)</span></span>|  
|<span data-ttu-id="acfeb-112">右上方 （100，0）</span><span class="sxs-lookup"><span data-stu-id="acfeb-112">Upper-right (100, 0)</span></span>|<span data-ttu-id="acfeb-113">(110, 100)</span><span class="sxs-lookup"><span data-stu-id="acfeb-113">(110, 100)</span></span>|  
|<span data-ttu-id="acfeb-114">左下角 （0，50）</span><span class="sxs-lookup"><span data-stu-id="acfeb-114">Lower-left (0, 50)</span></span>|<span data-ttu-id="acfeb-115">(250, 30)</span><span class="sxs-lookup"><span data-stu-id="acfeb-115">(250, 30)</span></span>|  
  
 <span data-ttu-id="acfeb-116">下图显示了原始映像和映像映射到的平行四边形。</span><span class="sxs-lookup"><span data-stu-id="acfeb-116">The following illustration shows the original image and the image mapped to the parallelogram.</span></span> <span data-ttu-id="acfeb-117">原始图像具有已倾斜、 反映、 旋转、 和转换。</span><span class="sxs-lookup"><span data-stu-id="acfeb-117">The original image has been skewed, reflected, rotated, and translated.</span></span> <span data-ttu-id="acfeb-118">原始图像的上边缘沿 x 轴映射到通过运行的行 （200，20） 和 （110，100）。</span><span class="sxs-lookup"><span data-stu-id="acfeb-118">The x-axis along the top edge of the original image is mapped to the line that runs through (200, 20) and (110, 100).</span></span> <span data-ttu-id="acfeb-119">沿左边缘原始图像的 y 轴映射到通过运行的行 （200，20） 和 （250，30）。</span><span class="sxs-lookup"><span data-stu-id="acfeb-119">The y-axis along the left edge of the original image is mapped to the line that runs through (200, 20) and (250, 30).</span></span>  
  
 ![原始映像，并映射到的平行四边形的图像。](./media/how-to-rotate-reflect-and-skew-images/reflected-skewed-rotated-illustration.gif)  
  
 <span data-ttu-id="acfeb-121">下图显示了类似的转换应用于摄影图像：</span><span class="sxs-lookup"><span data-stu-id="acfeb-121">The following illustration shows a similar transformation applied to a photographic image:</span></span>  
  
 ![Climber 和映射到的平行四边形的图片的图片。](./media/how-to-rotate-reflect-and-skew-images/reflected-skewed-rotated-photo.png)  
  
 <span data-ttu-id="acfeb-123">下图显示了类似的转换应用于图元文件：</span><span class="sxs-lookup"><span data-stu-id="acfeb-123">The following illustration shows a similar transformation applied to a metafile:</span></span>  
  
 ![形状和文本和映射到的平行四边形的示意图。](./media/how-to-rotate-reflect-and-skew-images/reflected-skewed-rotated-metafile.png)  
  
 <span data-ttu-id="acfeb-125">下面的示例生成第一个图例中所显示的图像。</span><span class="sxs-lookup"><span data-stu-id="acfeb-125">The following example produces the images shown in the first illustration.</span></span>  
  
 [!code-csharp[System.Drawing.WorkingWithImages#61](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#61)]
 [!code-vb[System.Drawing.WorkingWithImages#61](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#61)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="acfeb-126">编译代码</span><span class="sxs-lookup"><span data-stu-id="acfeb-126">Compiling the Code</span></span>  
 <span data-ttu-id="acfeb-127">前面的示例专用于 Windows 窗体，它需要 <xref:System.Windows.Forms.PaintEventArgs>`e`，后者是 <xref:System.Windows.Forms.Control.Paint> 事件处理程序的参数。</span><span class="sxs-lookup"><span data-stu-id="acfeb-127">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs>`e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span> <span data-ttu-id="acfeb-128">请务必替换`Stripes.bmp`替换为你的系统上有效的图像的路径。</span><span class="sxs-lookup"><span data-stu-id="acfeb-128">Make sure to replace `Stripes.bmp` with the path to an image that is valid on your system.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="acfeb-129">请参阅</span><span class="sxs-lookup"><span data-stu-id="acfeb-129">See also</span></span>

- [<span data-ttu-id="acfeb-130">使用图像、位图、图标和图元文件</span><span class="sxs-lookup"><span data-stu-id="acfeb-130">Working with Images, Bitmaps, Icons, and Metafiles</span></span>](working-with-images-bitmaps-icons-and-metafiles.md)
