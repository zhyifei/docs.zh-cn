---
title: 如何：向文本应用变换
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
ms.openlocfilehash: fd86293c539bf58ac93894e0b879dddb984825e1
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/05/2019
ms.locfileid: "57378937"
---
# <a name="how-to-apply-transforms-to-text"></a><span data-ttu-id="249bd-102">如何：向文本应用变换</span><span class="sxs-lookup"><span data-stu-id="249bd-102">How to: Apply Transforms to Text</span></span>
<span data-ttu-id="249bd-103">应用变换可以改变应用程序中文本的显示。</span><span class="sxs-lookup"><span data-stu-id="249bd-103">Transforms can alter the display of text in your application.</span></span> <span data-ttu-id="249bd-104">下面的示例使用不同类型的呈现变换来影响中文本的显示<xref:System.Windows.Controls.TextBlock>控件。</span><span class="sxs-lookup"><span data-stu-id="249bd-104">The following examples use different types of rendering transforms to affect the display of text in a <xref:System.Windows.Controls.TextBlock> control.</span></span>  
  
## <a name="example"></a><span data-ttu-id="249bd-105">示例</span><span class="sxs-lookup"><span data-stu-id="249bd-105">Example</span></span>  
 <span data-ttu-id="249bd-106">下面的示例演示了在 x-y 二维平面中文本围绕一个特定点进行旋转。</span><span class="sxs-lookup"><span data-stu-id="249bd-106">The following example shows text rotated about a specified point in the two-dimensional x-y plane.</span></span>  
  
 <span data-ttu-id="249bd-107">![使用 RotateTransform 旋转的文本](./media/transformedtext01.jpg "TransformedText01")</span><span class="sxs-lookup"><span data-stu-id="249bd-107">![Text rotated using a RotateTransform](./media/transformedtext01.jpg "TransformedText01")</span></span>  
<span data-ttu-id="249bd-108">文本旋转 90 度的示例</span><span class="sxs-lookup"><span data-stu-id="249bd-108">Example of text rotated 90 degrees</span></span>  
  
 <span data-ttu-id="249bd-109">下面的代码示例使用<xref:System.Windows.Media.RotateTransform>来旋转文本。</span><span class="sxs-lookup"><span data-stu-id="249bd-109">The following code example uses a <xref:System.Windows.Media.RotateTransform> to rotate text.</span></span> <span data-ttu-id="249bd-110"><xref:System.Windows.Media.RotateTransform.Angle%2A>值为 90，则元素会顺时针旋转 90 度。</span><span class="sxs-lookup"><span data-stu-id="249bd-110">An <xref:System.Windows.Media.RotateTransform.Angle%2A> value of 90 rotates the element 90 degrees clockwise.</span></span>  
  
 [!code-xaml[TextTransformSample#TextTransformSample1](~/samples/snippets/csharp/VS_Snippets_Wpf/TextTransformSample/CS/Window1.xaml#texttransformsample1)]  
  
 <span data-ttu-id="249bd-111">下面的示例演示沿 X 轴放大 150% 得到第二行文本，沿 Y 轴放大 150% 得到第三行文本。</span><span class="sxs-lookup"><span data-stu-id="249bd-111">The following example shows the second line of text scaled by 150% along the x-axis, and the third line of text scaled by 150% along the y-axis.</span></span>  
  
 <span data-ttu-id="249bd-112">![使用 ScaleTransform 缩放的文本](./media/transformedtext02.jpg "TransformedText02")</span><span class="sxs-lookup"><span data-stu-id="249bd-112">![Text scaled using a ScaleTransform](./media/transformedtext02.jpg "TransformedText02")</span></span>  
<span data-ttu-id="249bd-113">缩放文本的示例</span><span class="sxs-lookup"><span data-stu-id="249bd-113">Example of scaled text</span></span>  
  
 <span data-ttu-id="249bd-114">下面的代码示例使用<xref:System.Windows.Media.ScaleTransform>对文本从其原始大小进行缩放。</span><span class="sxs-lookup"><span data-stu-id="249bd-114">The following code example uses a <xref:System.Windows.Media.ScaleTransform> to scale text from its original size.</span></span>  
  
 [!code-xaml[TextTransformSample#TextTransformSample2](~/samples/snippets/csharp/VS_Snippets_Wpf/TextTransformSample/CS/Window1.xaml#texttransformsample2)]  
  
> [!NOTE]
>  <span data-ttu-id="249bd-115">放大文本不同于增大文本字号。</span><span class="sxs-lookup"><span data-stu-id="249bd-115">Scaling text is not the same as increasing the font size of text.</span></span> <span data-ttu-id="249bd-116">字号的计算相互独立，以便针对不同字号提供最佳分辨率。</span><span class="sxs-lookup"><span data-stu-id="249bd-116">Font sizes are calculated independently of each other in order to provide the best resolution at different sizes.</span></span> <span data-ttu-id="249bd-117">而缩放后的文本将按比例保持原始的文本大小。</span><span class="sxs-lookup"><span data-stu-id="249bd-117">Scaled text, on the other hand, preserves the proportions of the original-sized text.</span></span>  
  
 <span data-ttu-id="249bd-118">以下示例演示沿 X 轴倾斜的文本。</span><span class="sxs-lookup"><span data-stu-id="249bd-118">The following example shows text skewed along the x-axis.</span></span>  
  
 <span data-ttu-id="249bd-119">![使用 SkewTransform 倾斜的文本](./media/transformedtext03.jpg "TransformedText03")</span><span class="sxs-lookup"><span data-stu-id="249bd-119">![Text skewed using a SkewTransform](./media/transformedtext03.jpg "TransformedText03")</span></span>  
<span data-ttu-id="249bd-120">扭曲文本的示例</span><span class="sxs-lookup"><span data-stu-id="249bd-120">Example of skewed text</span></span>  
  
 <span data-ttu-id="249bd-121">下面的代码示例使用<xref:System.Windows.Media.SkewTransform>来扭曲文本。</span><span class="sxs-lookup"><span data-stu-id="249bd-121">The following code example uses a <xref:System.Windows.Media.SkewTransform> to skew text.</span></span> <span data-ttu-id="249bd-122">扭曲（也称为倾斜）是一种以非均匀方式拉伸坐标空间的变换。</span><span class="sxs-lookup"><span data-stu-id="249bd-122">A skew, also known as a shear, is a transformation that stretches the coordinate space in a non-uniform manner.</span></span> <span data-ttu-id="249bd-123">在本示例中，两个文本字符串沿 x 坐标扭曲了 -30° 和 30°。</span><span class="sxs-lookup"><span data-stu-id="249bd-123">In this example, the two text strings are skewed -30° and 30° along the x-coordinate.</span></span>  
  
 [!code-xaml[TextTransformSample#TextTransformSample3](~/samples/snippets/csharp/VS_Snippets_Wpf/TextTransformSample/CS/Window1.xaml#texttransformsample3)]  
  
 <span data-ttu-id="249bd-124">下面的示例演示沿 x 轴和 y 轴平移或移动的文本。</span><span class="sxs-lookup"><span data-stu-id="249bd-124">The following example shows text translated, or moved, along the x- and y-axis.</span></span>  
  
 <span data-ttu-id="249bd-125">![使用 TranslateTransform 偏移的文本](./media/transformedtext04.jpg "TransformedText04")</span><span class="sxs-lookup"><span data-stu-id="249bd-125">![Text offset using a TranslateTransform](./media/transformedtext04.jpg "TransformedText04")</span></span>  
<span data-ttu-id="249bd-126">平移文本的示例</span><span class="sxs-lookup"><span data-stu-id="249bd-126">Example of translated text</span></span>  
  
 <span data-ttu-id="249bd-127">下面的代码示例使用<xref:System.Windows.Media.TranslateTransform>来偏移文本。</span><span class="sxs-lookup"><span data-stu-id="249bd-127">The following code example uses a <xref:System.Windows.Media.TranslateTransform> to offset text.</span></span> <span data-ttu-id="249bd-128">在本示例中，主要文本下方略微偏移的文本副本营造出了阴影效果。</span><span class="sxs-lookup"><span data-stu-id="249bd-128">In this example, a slightly offset copy of text below the primary text creates a shadow effect.</span></span>  
  
 [!code-xaml[TextTransformSample#TextTransformSample4](~/samples/snippets/csharp/VS_Snippets_Wpf/TextTransformSample/CS/Window1.xaml#texttransformsample4)]  
  
> [!NOTE]
>  <span data-ttu-id="249bd-129"><xref:System.Windows.Media.Effects.DropShadowBitmapEffect>提供丰富的功能来产生阴影效果。</span><span class="sxs-lookup"><span data-stu-id="249bd-129">The <xref:System.Windows.Media.Effects.DropShadowBitmapEffect> provides a rich set of features for providing shadow effects.</span></span> <span data-ttu-id="249bd-130">有关详细信息，请参阅[创建具有阴影的文本](how-to-create-text-with-a-shadow.md)。</span><span class="sxs-lookup"><span data-stu-id="249bd-130">For more information, see [Create Text with a Shadow](how-to-create-text-with-a-shadow.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="249bd-131">请参阅</span><span class="sxs-lookup"><span data-stu-id="249bd-131">See also</span></span>
- [<span data-ttu-id="249bd-132">向文本应用动画</span><span class="sxs-lookup"><span data-stu-id="249bd-132">Apply Animations to Text</span></span>](how-to-apply-animations-to-text.md)
