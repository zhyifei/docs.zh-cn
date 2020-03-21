---
title: 如何：使用纯色绘制区域
ms.date: 03/30/2017
helpviewer_keywords:
- solid colors [WPF], painting with
- brushes [WPF], painting with solid colors
- painting [WPF], with solid colors
ms.assetid: 5d27d8a7-4bd7-4063-bdf3-2c5c0f19f9d3
ms.openlocfilehash: be28a0af04c4e43cdf745a5429468aee99e34c40
ms.sourcegitcommit: 515469828d0f040e01bde01df6b8e4eb43630b06
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2020
ms.locfileid: "78849517"
---
# <a name="how-to-paint-an-area-with-a-solid-color"></a><span data-ttu-id="8c35e-102">如何：使用纯色绘制区域</span><span class="sxs-lookup"><span data-stu-id="8c35e-102">How to: Paint an Area with a Solid Color</span></span>
<span data-ttu-id="8c35e-103">要使用<xref:System.Windows.Media.Brushes.Red%2A>纯色绘制区域，可以使用预定义的系统画笔（如 或<xref:System.Windows.Media.Brushes.Blue%2A>，）或者可以使用 Alpha、红色、绿色和<xref:System.Windows.Media.SolidColorBrush>蓝色值创建新<xref:System.Windows.Media.SolidColorBrush.Color%2A>区域并描述其区域。</span><span class="sxs-lookup"><span data-stu-id="8c35e-103">To paint an area with a solid color, you can use a predefined system brush, such as <xref:System.Windows.Media.Brushes.Red%2A> or <xref:System.Windows.Media.Brushes.Blue%2A>, or you can create a new <xref:System.Windows.Media.SolidColorBrush> and describe its <xref:System.Windows.Media.SolidColorBrush.Color%2A> using alpha, red, green, and blue values.</span></span> <span data-ttu-id="8c35e-104">在 XAML 中，还可以使用十六进制表示法来利用纯色绘制区域。</span><span class="sxs-lookup"><span data-stu-id="8c35e-104">In XAML, you may also paint an area with a solid color by using hexidecimal notation.</span></span>  
  
 <span data-ttu-id="8c35e-105">以下示例使用以下每种技术来绘制<xref:System.Windows.Shapes.Rectangle>蓝色。</span><span class="sxs-lookup"><span data-stu-id="8c35e-105">The following examples uses each of these techniques to paint a <xref:System.Windows.Shapes.Rectangle> blue.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8c35e-106">示例</span><span class="sxs-lookup"><span data-stu-id="8c35e-106">Example</span></span>  
 <span data-ttu-id="8c35e-107">**使用预定义画笔**</span><span class="sxs-lookup"><span data-stu-id="8c35e-107">**Using a Predefined Brush**</span></span>  
  
 <span data-ttu-id="8c35e-108">在下面的示例中，使用预定义的画笔<xref:System.Windows.Media.Brushes.Blue%2A>绘制一个矩形蓝色。</span><span class="sxs-lookup"><span data-stu-id="8c35e-108">In the following example uses the predefined brush <xref:System.Windows.Media.Brushes.Blue%2A> to paint a rectangle blue.</span></span>  
  
 [!code-xaml[brushsamples_snip#_graphicsmm_PredefinedBrush1](~/samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/SolidColorBrushExample.xaml#_graphicsmm_predefinedbrush1)]  
  
 [!code-csharp[brushsamples_procedural_snip#_graphicsmm_PredefinedBrush1](~/samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_procedural_snip/CSharp/SolidColorBrushExample.cs#_graphicsmm_predefinedbrush1)]  
  
 <span data-ttu-id="8c35e-109">**使用十六进制表示法**</span><span class="sxs-lookup"><span data-stu-id="8c35e-109">**Using Hexadecimal Notation**</span></span>  
  
 <span data-ttu-id="8c35e-110">下一个示例使用 8 位十六进制表示法绘制一个蓝色矩形。</span><span class="sxs-lookup"><span data-stu-id="8c35e-110">The next example uses 8-digit hexadecimal notation to paint a rectangle blue.</span></span>  
  
 [!code-xaml[brushsamples_snip#_graphicsmm_HexNotation8Digit1](~/samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/SolidColorBrushExample.xaml#_graphicsmm_hexnotation8digit1)]  
  
 <span data-ttu-id="8c35e-111">**使用 ARGB 值**</span><span class="sxs-lookup"><span data-stu-id="8c35e-111">**Using ARGB Values**</span></span>  
  
 <span data-ttu-id="8c35e-112">下一个示例创建<xref:System.Windows.Media.SolidColorBrush>和<xref:System.Windows.Media.SolidColorBrush.Color%2A>描述其使用颜色为蓝色的 ARGB 值。</span><span class="sxs-lookup"><span data-stu-id="8c35e-112">The next example creates a <xref:System.Windows.Media.SolidColorBrush> and describes its <xref:System.Windows.Media.SolidColorBrush.Color%2A> using the ARGB values for the color blue.</span></span>  
  
 [!code-xaml[brushsamples_snip#_graphicsmm_RgbNotation1](~/samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/SolidColorBrushExample.xaml#_graphicsmm_rgbnotation1)]  
  
 [!code-csharp[brushsamples_procedural_snip#_graphicsmm_RgbNotation1](~/samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_procedural_snip/CSharp/SolidColorBrushExample.cs#_graphicsmm_rgbnotation1)]  
  
 <span data-ttu-id="8c35e-113">有关描述颜色的其他方法，<xref:System.Windows.Media.Color>请参阅结构。</span><span class="sxs-lookup"><span data-stu-id="8c35e-113">For other ways of describing color, see the <xref:System.Windows.Media.Color> structure.</span></span>  
  
 <span data-ttu-id="8c35e-114">**相关主题**</span><span class="sxs-lookup"><span data-stu-id="8c35e-114">**Related Topics**</span></span>  
  
 <span data-ttu-id="8c35e-115">有关相关信息<xref:System.Windows.Media.SolidColorBrush>和其他示例，请参阅["具有纯色和渐变的绘画概述](painting-with-solid-colors-and-gradients-overview.md)"。</span><span class="sxs-lookup"><span data-stu-id="8c35e-115">For more information about <xref:System.Windows.Media.SolidColorBrush> and additional examples, see the [Painting with Solid Colors and Gradients Overview](painting-with-solid-colors-and-gradients-overview.md) overview.</span></span>  
  
 <span data-ttu-id="8c35e-116">此代码示例是为类提供的更大示例的<xref:System.Windows.Media.SolidColorBrush>一部分。</span><span class="sxs-lookup"><span data-stu-id="8c35e-116">This code example is part of a larger example provided for the <xref:System.Windows.Media.SolidColorBrush> class.</span></span> <span data-ttu-id="8c35e-117">有关完整示例，请参阅[画笔示例](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Brushes)。</span><span class="sxs-lookup"><span data-stu-id="8c35e-117">For the complete sample, see the [Brushes Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Brushes).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8c35e-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8c35e-118">See also</span></span>

- <xref:System.Windows.Media.Brushes>
