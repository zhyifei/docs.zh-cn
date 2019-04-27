---
title: 如何：使用纯色绘制区域
ms.date: 03/30/2017
helpviewer_keywords:
- solid colors [WPF], painting with
- brushes [WPF], painting with solid colors
- painting [WPF], with solid colors
ms.assetid: 5d27d8a7-4bd7-4063-bdf3-2c5c0f19f9d3
ms.openlocfilehash: c85ba72c858d155f29875bb944824db1c44ffaab
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61922624"
---
# <a name="how-to-paint-an-area-with-a-solid-color"></a><span data-ttu-id="d7048-102">如何：使用纯色绘制区域</span><span class="sxs-lookup"><span data-stu-id="d7048-102">How to: Paint an Area with a Solid Color</span></span>
<span data-ttu-id="d7048-103">若要绘制使用纯色区域，可以使用预定义的系统画笔，如<xref:System.Windows.Media.Brushes.Red%2A>或<xref:System.Windows.Media.Brushes.Blue%2A>，也可以创建一个新<xref:System.Windows.Media.SolidColorBrush>并描述其<xref:System.Windows.Media.SolidColorBrush.Color%2A>使用 alpha、 红色、 绿色和蓝色值。</span><span class="sxs-lookup"><span data-stu-id="d7048-103">To paint an area with a solid color, you can use a predefined system brush, such as <xref:System.Windows.Media.Brushes.Red%2A> or <xref:System.Windows.Media.Brushes.Blue%2A>, or you can create a new <xref:System.Windows.Media.SolidColorBrush> and describe its <xref:System.Windows.Media.SolidColorBrush.Color%2A> using alpha, red, green, and blue values.</span></span> <span data-ttu-id="d7048-104">在 XAML 中，还可以使用十六进制表示法来利用纯色绘制区域。</span><span class="sxs-lookup"><span data-stu-id="d7048-104">In XAML, you may also paint an area with a solid color by using hexidecimal notation.</span></span>  
  
 <span data-ttu-id="d7048-105">下面的示例使用上述每种方法来绘制<xref:System.Windows.Shapes.Rectangle>蓝色。</span><span class="sxs-lookup"><span data-stu-id="d7048-105">The following examples uses each of these techniques to paint a <xref:System.Windows.Shapes.Rectangle> blue.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d7048-106">示例</span><span class="sxs-lookup"><span data-stu-id="d7048-106">Example</span></span>  
 <span data-ttu-id="d7048-107">**使用预定义画笔**</span><span class="sxs-lookup"><span data-stu-id="d7048-107">**Using a Predefined Brush**</span></span>  
  
 <span data-ttu-id="d7048-108">在下面的示例使用预定义的画笔<xref:System.Windows.Media.Brushes.Blue%2A>来绘制一个蓝色矩形。</span><span class="sxs-lookup"><span data-stu-id="d7048-108">In the following example uses the predefined brush <xref:System.Windows.Media.Brushes.Blue%2A> to paint a rectangle blue.</span></span>  
  
 [!code-xaml[brushsamples_snip#_graphicsmm_PredefinedBrush1](~/samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/SolidColorBrushExample.xaml#_graphicsmm_predefinedbrush1)]  
  
 [!code-csharp[brushsamples_procedural_snip#_graphicsmm_PredefinedBrush1](~/samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_procedural_snip/CSharp/SolidColorBrushExample.cs#_graphicsmm_predefinedbrush1)]  
  
 <span data-ttu-id="d7048-109">**使用十六进制表示法**</span><span class="sxs-lookup"><span data-stu-id="d7048-109">**Using Hexadecimal Notation**</span></span>  
  
 <span data-ttu-id="d7048-110">下一个示例使用 8 位十六进制表示法绘制一个蓝色矩形。</span><span class="sxs-lookup"><span data-stu-id="d7048-110">The next example uses 8-digit hexadecimal notation to paint a rectangle blue.</span></span>  
  
 [!code-xaml[brushsamples_snip#_graphicsmm_HexNotation8Digit1](~/samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/SolidColorBrushExample.xaml#_graphicsmm_hexnotation8digit1)]  
  
 <span data-ttu-id="d7048-111">**使用 ARGB 值**</span><span class="sxs-lookup"><span data-stu-id="d7048-111">**Using ARGB Values**</span></span>  
  
 <span data-ttu-id="d7048-112">下一个示例创建<xref:System.Windows.Media.SolidColorBrush>并介绍了其<xref:System.Windows.Media.SolidColorBrush.Color%2A>使用 ARGB 值为蓝色。</span><span class="sxs-lookup"><span data-stu-id="d7048-112">The next example creates a <xref:System.Windows.Media.SolidColorBrush> and describes its <xref:System.Windows.Media.SolidColorBrush.Color%2A> using the ARGB values for the color blue.</span></span>  
  
 [!code-xaml[brushsamples_snip#_graphicsmm_RgbNotation1](~/samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/SolidColorBrushExample.xaml#_graphicsmm_rgbnotation1)]  
  
 [!code-csharp[brushsamples_procedural_snip#_graphicsmm_RgbNotation1](~/samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_procedural_snip/CSharp/SolidColorBrushExample.cs#_graphicsmm_rgbnotation1)]  
  
 <span data-ttu-id="d7048-113">有关描述颜色的其他方法，请参阅<xref:System.Windows.Media.Color>结构。</span><span class="sxs-lookup"><span data-stu-id="d7048-113">For other ways of describing color, see the <xref:System.Windows.Media.Color> structure.</span></span>  
  
 <span data-ttu-id="d7048-114">**相关主题**</span><span class="sxs-lookup"><span data-stu-id="d7048-114">**Related Topics**</span></span>  
  
 <span data-ttu-id="d7048-115">有关详细信息<xref:System.Windows.Media.SolidColorBrush>和其他示例，请参阅[使用纯色和渐变概述进行绘制](painting-with-solid-colors-and-gradients-overview.md)概述。</span><span class="sxs-lookup"><span data-stu-id="d7048-115">For more information about <xref:System.Windows.Media.SolidColorBrush> and additional examples, see the [Painting with Solid Colors and Gradients Overview](painting-with-solid-colors-and-gradients-overview.md) overview.</span></span>  
  
 <span data-ttu-id="d7048-116">此代码示例是为提供一个更大示例的一部分<xref:System.Windows.Media.SolidColorBrush>类。</span><span class="sxs-lookup"><span data-stu-id="d7048-116">This code example is part of a larger example provided for the <xref:System.Windows.Media.SolidColorBrush> class.</span></span> <span data-ttu-id="d7048-117">有关完整示例，请参阅[画笔示例](https://go.microsoft.com/fwlink/?LinkID=159973)。</span><span class="sxs-lookup"><span data-stu-id="d7048-117">For the complete sample, see the [Brushes Sample](https://go.microsoft.com/fwlink/?LinkID=159973).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d7048-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="d7048-118">See also</span></span>

- <xref:System.Windows.Media.Brushes>
