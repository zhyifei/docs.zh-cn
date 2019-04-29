---
title: 如何：向文本应用转换
ms.date: 03/30/2017
helpviewer_keywords:
- typography [WPF], rotated text
- typography [WPF], scaled text
- skewed text [WPF]
- typography [WPF], translated text
- typography [WPF], shadowed text
- rotated text [WPF]
- translated text [WPF]
- shadowed text [WPF]
- transforms in text [WPF]
- typography [WPF], transforms
- scaled text [WPF]
- typography [WPF], skewed text
ms.assetid: 0d61678a-4185-4f2a-85c6-c1d020f96fa0
ms.openlocfilehash: 46a57364e0c18cc4c9fe7884642cd0b718c20f31
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61776936"
---
# <a name="how-to-apply-transforms-to-text"></a><span data-ttu-id="19f4c-102">如何：向文本应用转换</span><span class="sxs-lookup"><span data-stu-id="19f4c-102">How to: Apply Transforms to Text</span></span>
<span data-ttu-id="19f4c-103">应用变换可以改变应用程序中文本的显示。</span><span class="sxs-lookup"><span data-stu-id="19f4c-103">Transforms can alter the display of text in your application.</span></span> <span data-ttu-id="19f4c-104">下面的示例使用不同类型的呈现变换来影响中文本的显示<xref:System.Windows.Controls.TextBlock>控件。</span><span class="sxs-lookup"><span data-stu-id="19f4c-104">The following examples use different types of rendering transforms to affect the display of text in a <xref:System.Windows.Controls.TextBlock> control.</span></span>  
  
## <a name="example"></a><span data-ttu-id="19f4c-105">示例</span><span class="sxs-lookup"><span data-stu-id="19f4c-105">Example</span></span>  
 <span data-ttu-id="19f4c-106">下面的示例演示了在 x-y 二维平面中文本围绕一个特定点进行旋转。</span><span class="sxs-lookup"><span data-stu-id="19f4c-106">The following example shows text rotated about a specified point in the two-dimensional x-y plane.</span></span>  
  
 ![使用 RotateTransform 旋转的文本](./media/how-to-apply-transforms-to-text/text-rotated-ninety-degrees.jpg)  
  
 <span data-ttu-id="19f4c-108">下面的代码示例使用<xref:System.Windows.Media.RotateTransform>来旋转文本。</span><span class="sxs-lookup"><span data-stu-id="19f4c-108">The following code example uses a <xref:System.Windows.Media.RotateTransform> to rotate text.</span></span> <span data-ttu-id="19f4c-109"><xref:System.Windows.Media.RotateTransform.Angle%2A>值为 90，则元素会顺时针旋转 90 度。</span><span class="sxs-lookup"><span data-stu-id="19f4c-109">An <xref:System.Windows.Media.RotateTransform.Angle%2A> value of 90 rotates the element 90 degrees clockwise.</span></span>  
  
 [!code-xaml[TextTransformSample#TextTransformSample1](~/samples/snippets/csharp/VS_Snippets_Wpf/TextTransformSample/CS/Window1.xaml#texttransformsample1)]  
  
 <span data-ttu-id="19f4c-110">下面的示例演示沿 X 轴放大 150% 得到第二行文本，沿 Y 轴放大 150% 得到第三行文本。</span><span class="sxs-lookup"><span data-stu-id="19f4c-110">The following example shows the second line of text scaled by 150% along the x-axis, and the third line of text scaled by 150% along the y-axis.</span></span>  
  
 ![使用 ScaleTransform 缩放的文本](./media/how-to-apply-transforms-to-text/scaled-text-scaletransform.jpg) 
  
 <span data-ttu-id="19f4c-112">下面的代码示例使用<xref:System.Windows.Media.ScaleTransform>对文本从其原始大小进行缩放。</span><span class="sxs-lookup"><span data-stu-id="19f4c-112">The following code example uses a <xref:System.Windows.Media.ScaleTransform> to scale text from its original size.</span></span>  
  
 [!code-xaml[TextTransformSample#TextTransformSample2](~/samples/snippets/csharp/VS_Snippets_Wpf/TextTransformSample/CS/Window1.xaml#texttransformsample2)]  
  
> [!NOTE]
>  <span data-ttu-id="19f4c-113">放大文本不同于增大文本字号。</span><span class="sxs-lookup"><span data-stu-id="19f4c-113">Scaling text is not the same as increasing the font size of text.</span></span> <span data-ttu-id="19f4c-114">字号的计算相互独立，以便针对不同字号提供最佳分辨率。</span><span class="sxs-lookup"><span data-stu-id="19f4c-114">Font sizes are calculated independently of each other in order to provide the best resolution at different sizes.</span></span> <span data-ttu-id="19f4c-115">而缩放后的文本将按比例保持原始的文本大小。</span><span class="sxs-lookup"><span data-stu-id="19f4c-115">Scaled text, on the other hand, preserves the proportions of the original-sized text.</span></span>  
  
 <span data-ttu-id="19f4c-116">以下示例演示沿 X 轴倾斜的文本。</span><span class="sxs-lookup"><span data-stu-id="19f4c-116">The following example shows text skewed along the x-axis.</span></span>  
  
 ![使用 SkewTransform 扭曲的文本](./media/how-to-apply-transforms-to-text/skewed-transformed-text.jpg)
   
 <span data-ttu-id="19f4c-118">下面的代码示例使用<xref:System.Windows.Media.SkewTransform>来扭曲文本。</span><span class="sxs-lookup"><span data-stu-id="19f4c-118">The following code example uses a <xref:System.Windows.Media.SkewTransform> to skew text.</span></span> <span data-ttu-id="19f4c-119">扭曲（也称为倾斜）是一种以非均匀方式拉伸坐标空间的变换。</span><span class="sxs-lookup"><span data-stu-id="19f4c-119">A skew, also known as a shear, is a transformation that stretches the coordinate space in a non-uniform manner.</span></span> <span data-ttu-id="19f4c-120">在本示例中，两个文本字符串沿 x 坐标扭曲了 -30° 和 30°。</span><span class="sxs-lookup"><span data-stu-id="19f4c-120">In this example, the two text strings are skewed -30° and 30° along the x-coordinate.</span></span>  
  
 [!code-xaml[TextTransformSample#TextTransformSample3](~/samples/snippets/csharp/VS_Snippets_Wpf/TextTransformSample/CS/Window1.xaml#texttransformsample3)]  
  
 <span data-ttu-id="19f4c-121">下面的示例演示沿 x 轴和 y 轴平移或移动的文本。</span><span class="sxs-lookup"><span data-stu-id="19f4c-121">The following example shows text translated, or moved, along the x- and y-axis.</span></span>  
  
 ![使用 TranslateTransform 偏移的文本](./media/how-to-apply-transforms-to-text/transformed-text-x-y-axis.jpg)
  
 <span data-ttu-id="19f4c-123">下面的代码示例使用<xref:System.Windows.Media.TranslateTransform>来偏移文本。</span><span class="sxs-lookup"><span data-stu-id="19f4c-123">The following code example uses a <xref:System.Windows.Media.TranslateTransform> to offset text.</span></span> <span data-ttu-id="19f4c-124">在本示例中，主要文本下方略微偏移的文本副本营造出了阴影效果。</span><span class="sxs-lookup"><span data-stu-id="19f4c-124">In this example, a slightly offset copy of text below the primary text creates a shadow effect.</span></span>  
  
 [!code-xaml[TextTransformSample#TextTransformSample4](~/samples/snippets/csharp/VS_Snippets_Wpf/TextTransformSample/CS/Window1.xaml#texttransformsample4)]  
  
> [!NOTE]
>  <span data-ttu-id="19f4c-125"><xref:System.Windows.Media.Effects.DropShadowBitmapEffect>提供丰富的功能来产生阴影效果。</span><span class="sxs-lookup"><span data-stu-id="19f4c-125">The <xref:System.Windows.Media.Effects.DropShadowBitmapEffect> provides a rich set of features for providing shadow effects.</span></span> <span data-ttu-id="19f4c-126">有关详细信息，请参阅[创建具有阴影的文本](how-to-create-text-with-a-shadow.md)。</span><span class="sxs-lookup"><span data-stu-id="19f4c-126">For more information, see [Create Text with a Shadow](how-to-create-text-with-a-shadow.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="19f4c-127">请参阅</span><span class="sxs-lookup"><span data-stu-id="19f4c-127">See also</span></span>

- [<span data-ttu-id="19f4c-128">向文本应用动画</span><span class="sxs-lookup"><span data-stu-id="19f4c-128">Apply Animations to Text</span></span>](how-to-apply-animations-to-text.md)
