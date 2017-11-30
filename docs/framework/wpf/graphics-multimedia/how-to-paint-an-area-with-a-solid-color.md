---
title: "如何：使用纯色绘制区域"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- solid colors [WPF], painting with
- brushes [WPF], painting with solid colors
- painting [WPF], with solid colors
ms.assetid: 5d27d8a7-4bd7-4063-bdf3-2c5c0f19f9d3
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: cde7f7df5089806ffb3235393eacc855d137ee51
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-paint-an-area-with-a-solid-color"></a><span data-ttu-id="90ba5-102">如何：使用纯色绘制区域</span><span class="sxs-lookup"><span data-stu-id="90ba5-102">How to: Paint an Area with a Solid Color</span></span>
<span data-ttu-id="90ba5-103">若要绘制带有纯色的区域，可以使用预定义的系统画笔，如<xref:System.Windows.Media.Brushes.Red%2A>或<xref:System.Windows.Media.Brushes.Blue%2A>，也可以创建一个新<xref:System.Windows.Media.SolidColorBrush>并描述其<xref:System.Windows.Media.SolidColorBrush.Color%2A>使用 alpha、 红色、 绿色和蓝色值。</span><span class="sxs-lookup"><span data-stu-id="90ba5-103">To paint an area with a solid color, you can use a predefined system brush, such as <xref:System.Windows.Media.Brushes.Red%2A> or <xref:System.Windows.Media.Brushes.Blue%2A>, or you can create a new <xref:System.Windows.Media.SolidColorBrush> and describe its <xref:System.Windows.Media.SolidColorBrush.Color%2A> using alpha, red, green, and blue values.</span></span> <span data-ttu-id="90ba5-104">在 XAML 中，还可以使用十六进制表示法来利用纯色绘制区域。</span><span class="sxs-lookup"><span data-stu-id="90ba5-104">In XAML, you may also paint an area with a solid color by using hexidecimal notation.</span></span>  
  
 <span data-ttu-id="90ba5-105">下面的示例使用上述每种方法来绘制<xref:System.Windows.Shapes.Rectangle>蓝色。</span><span class="sxs-lookup"><span data-stu-id="90ba5-105">The following examples uses each of these techniques to paint a <xref:System.Windows.Shapes.Rectangle> blue.</span></span>  
  
## <a name="example"></a><span data-ttu-id="90ba5-106">示例</span><span class="sxs-lookup"><span data-stu-id="90ba5-106">Example</span></span>  
 <span data-ttu-id="90ba5-107">**使用预定义画笔**</span><span class="sxs-lookup"><span data-stu-id="90ba5-107">**Using a Predefined Brush**</span></span>  
  
 <span data-ttu-id="90ba5-108">在下面的示例使用预定义的画笔<xref:System.Windows.Media.Brushes.Blue%2A>来绘制的矩形蓝色。</span><span class="sxs-lookup"><span data-stu-id="90ba5-108">In the following example uses the predefined brush <xref:System.Windows.Media.Brushes.Blue%2A> to paint a rectangle blue.</span></span>  
  
 [!code-xaml[brushsamples_snip#_graphicsmm_PredefinedBrush1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/SolidColorBrushExample.xaml#_graphicsmm_predefinedbrush1)]  
  
 [!code-csharp[brushsamples_procedural_snip#_graphicsmm_PredefinedBrush1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_procedural_snip/CSharp/SolidColorBrushExample.cs#_graphicsmm_predefinedbrush1)]  
  
 <span data-ttu-id="90ba5-109">**使用十六进制表示法**</span><span class="sxs-lookup"><span data-stu-id="90ba5-109">**Using Hexadecimal Notation**</span></span>  
  
 <span data-ttu-id="90ba5-110">下一个示例使用 8 位十六进制表示法绘制一个蓝色矩形。</span><span class="sxs-lookup"><span data-stu-id="90ba5-110">The next example uses 8-digit hexadecimal notation to paint a rectangle blue.</span></span>  
  
 [!code-xaml[brushsamples_snip#_graphicsmm_HexNotation8Digit1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/SolidColorBrushExample.xaml#_graphicsmm_hexnotation8digit1)]  
  
 <span data-ttu-id="90ba5-111">**使用 ARGB 值**</span><span class="sxs-lookup"><span data-stu-id="90ba5-111">**Using ARGB Values**</span></span>  
  
 <span data-ttu-id="90ba5-112">下一个示例创建<xref:System.Windows.Media.SolidColorBrush>并描述其<xref:System.Windows.Media.SolidColorBrush.Color%2A>使用 ARGB 的蓝色值。</span><span class="sxs-lookup"><span data-stu-id="90ba5-112">The next example creates a <xref:System.Windows.Media.SolidColorBrush> and describes its <xref:System.Windows.Media.SolidColorBrush.Color%2A> using the ARGB values for the color blue.</span></span>  
  
 [!code-xaml[brushsamples_snip#_graphicsmm_RgbNotation1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/SolidColorBrushExample.xaml#_graphicsmm_rgbnotation1)]  
  
 [!code-csharp[brushsamples_procedural_snip#_graphicsmm_RgbNotation1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_procedural_snip/CSharp/SolidColorBrushExample.cs#_graphicsmm_rgbnotation1)]  
  
 <span data-ttu-id="90ba5-113">有关描述颜色的其他方法，请参阅<xref:System.Windows.Media.Color>结构。</span><span class="sxs-lookup"><span data-stu-id="90ba5-113">For other ways of describing color, see the <xref:System.Windows.Media.Color> structure.</span></span>  
  
 <span data-ttu-id="90ba5-114">**相关主题**</span><span class="sxs-lookup"><span data-stu-id="90ba5-114">**Related Topics**</span></span>  
  
 <span data-ttu-id="90ba5-115">有关详细信息<xref:System.Windows.Media.SolidColorBrush>和其他示例，请参阅[使用纯色和渐变概述绘制](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md)概述。</span><span class="sxs-lookup"><span data-stu-id="90ba5-115">For more information about <xref:System.Windows.Media.SolidColorBrush> and additional examples, see the [Painting with Solid Colors and Gradients Overview](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md) overview.</span></span>  
  
 <span data-ttu-id="90ba5-116">此代码示例摘自更大的示例为提供<xref:System.Windows.Media.SolidColorBrush>类。</span><span class="sxs-lookup"><span data-stu-id="90ba5-116">This code example is part of a larger example provided for the <xref:System.Windows.Media.SolidColorBrush> class.</span></span> <span data-ttu-id="90ba5-117">有关完整示例，请参阅[画笔示例](http://go.microsoft.com/fwlink/?LinkID=159973)。</span><span class="sxs-lookup"><span data-stu-id="90ba5-117">For the complete sample, see the [Brushes Sample](http://go.microsoft.com/fwlink/?LinkID=159973).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="90ba5-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="90ba5-118">See Also</span></span>  
 <xref:System.Windows.Media.Brushes>
