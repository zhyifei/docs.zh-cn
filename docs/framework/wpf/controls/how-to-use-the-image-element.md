---
title: 如何：使用 Image 元素
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [WPF], Image
- Image control [WPF]
- rendering images [WPF]
ms.assetid: 5b92e74b-1b56-4756-ac64-d5e9e08d9854
ms.openlocfilehash: 967159894e25721bdf380f851712e91d76088f87
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59205298"
---
# <a name="how-to-use-the-image-element"></a><span data-ttu-id="5666a-102">如何：使用 Image 元素</span><span class="sxs-lookup"><span data-stu-id="5666a-102">How to: Use the Image Element</span></span>
<span data-ttu-id="5666a-103">此示例演示如何通过使用应用程序中包含图像<xref:System.Windows.Controls.Image>元素。</span><span class="sxs-lookup"><span data-stu-id="5666a-103">This example shows how to include images in an application by using the <xref:System.Windows.Controls.Image> element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5666a-104">示例</span><span class="sxs-lookup"><span data-stu-id="5666a-104">Example</span></span>  
 <span data-ttu-id="5666a-105">下面的示例演示如何呈现宽为 200 像素的图像。</span><span class="sxs-lookup"><span data-stu-id="5666a-105">The following example shows how to render an image 200 pixels wide.</span></span> <span data-ttu-id="5666a-106">在此 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 示例中，同时使用特性语法和属性标记语法来定义图像。</span><span class="sxs-lookup"><span data-stu-id="5666a-106">In this [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] example, both attribute syntax and property tag syntax are used to define the image.</span></span> <span data-ttu-id="5666a-107">有关特性语法和属性语法的详细信息，请参阅[依赖属性概述](../advanced/dependency-properties-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="5666a-107">For more information on attribute syntax and property syntax, see [Dependency Properties Overview](../advanced/dependency-properties-overview.md).</span></span> <span data-ttu-id="5666a-108">一个<xref:System.Windows.Media.Imaging.BitmapImage>用于定义图像的源数据并为属性标记语法示例显式定义。</span><span class="sxs-lookup"><span data-stu-id="5666a-108">A <xref:System.Windows.Media.Imaging.BitmapImage> is used to define the image's source data and is explicitly defined for the property tag syntax example.</span></span> <span data-ttu-id="5666a-109">此外，<xref:System.Windows.Media.Imaging.BitmapImage.DecodePixelWidth%2A>的<xref:System.Windows.Media.Imaging.BitmapImage>设置为宽度相同<xref:System.Windows.FrameworkElement.Width%2A>的<xref:System.Windows.Controls.Image>。</span><span class="sxs-lookup"><span data-stu-id="5666a-109">In addition, the <xref:System.Windows.Media.Imaging.BitmapImage.DecodePixelWidth%2A> of the <xref:System.Windows.Media.Imaging.BitmapImage> is set to the same width as the <xref:System.Windows.FrameworkElement.Width%2A> of the <xref:System.Windows.Controls.Image>.</span></span> <span data-ttu-id="5666a-110">这样做是为了确保呈现图像所使用的内存量最小。</span><span class="sxs-lookup"><span data-stu-id="5666a-110">This is done to ensure that the minimum amount of memory is used rendering the image.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5666a-111">如果你想要指定呈现图像的大小，一般情况下，仅指定<xref:System.Windows.FrameworkElement.Width%2A>或<xref:System.Windows.FrameworkElement.Height%2A>但不可同时使用两者。</span><span class="sxs-lookup"><span data-stu-id="5666a-111">In general, if you want to specify the size of a rendered image, specify only the <xref:System.Windows.FrameworkElement.Width%2A> or the <xref:System.Windows.FrameworkElement.Height%2A> but not both.</span></span> <span data-ttu-id="5666a-112">如果仅指定一个，则会保持图像的纵横比。</span><span class="sxs-lookup"><span data-stu-id="5666a-112">If you only specify one, the image's aspect ratio is preserved.</span></span> <span data-ttu-id="5666a-113">否则，图像可能会出现意外的拉伸或扭曲。</span><span class="sxs-lookup"><span data-stu-id="5666a-113">Otherwise, the image may unexpectedly appear stretched or warped.</span></span> <span data-ttu-id="5666a-114">若要控制图像的拉伸行为，请使用<xref:System.Windows.Controls.Image.Stretch%2A>和<xref:System.Windows.Controls.Image.StretchDirection%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="5666a-114">To control the image's stretching behavior, use the <xref:System.Windows.Controls.Image.Stretch%2A> and <xref:System.Windows.Controls.Image.StretchDirection%2A> properties.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5666a-115">映像的大小指定的<xref:System.Windows.FrameworkElement.Width%2A>或<xref:System.Windows.FrameworkElement.Height%2A>，你还应设置<xref:System.Windows.Media.Imaging.BitmapImage.DecodePixelWidth%2A>或<xref:System.Windows.Media.Imaging.BitmapImage.DecodePixelHeight%2A>的相应大小。</span><span class="sxs-lookup"><span data-stu-id="5666a-115">When you specify the size of an image with either <xref:System.Windows.FrameworkElement.Width%2A> or <xref:System.Windows.FrameworkElement.Height%2A>, you should also set either <xref:System.Windows.Media.Imaging.BitmapImage.DecodePixelWidth%2A> or <xref:System.Windows.Media.Imaging.BitmapImage.DecodePixelHeight%2A> to the same respective size.</span></span>  
  
 <span data-ttu-id="5666a-116"><xref:System.Windows.Controls.Image.Stretch%2A>属性确定如何拉伸图像源来填充图像元素。</span><span class="sxs-lookup"><span data-stu-id="5666a-116">The <xref:System.Windows.Controls.Image.Stretch%2A> property determines how the image source is stretched to fill the image element.</span></span> <span data-ttu-id="5666a-117">有关详细信息，请参见 <xref:System.Windows.Media.Stretch> 枚举。</span><span class="sxs-lookup"><span data-stu-id="5666a-117">For more information, see the <xref:System.Windows.Media.Stretch> enumeration.</span></span>  
  
 [!code-xaml[ImageElementExample_snip#ImageSimpleExampleInlineMarkup](~/samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample_snip/CSharp/ImageSimpleExample.xaml#imagesimpleexampleinlinemarkup)]  
  
## <a name="example"></a><span data-ttu-id="5666a-118">示例</span><span class="sxs-lookup"><span data-stu-id="5666a-118">Example</span></span>  
 <span data-ttu-id="5666a-119">以下示例演示如何使用代码呈现宽度为 200 像素的图像。</span><span class="sxs-lookup"><span data-stu-id="5666a-119">The following example shows how to render an image 200 pixels wide using code.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5666a-120">设置<xref:System.Windows.Media.Imaging.BitmapImage>属性必须在完成<xref:System.Windows.Media.Imaging.BitmapImage.BeginInit%2A>和<xref:System.Windows.Media.Imaging.BitmapImage.EndInit%2A>块。</span><span class="sxs-lookup"><span data-stu-id="5666a-120">Setting <xref:System.Windows.Media.Imaging.BitmapImage> properties must be done within a <xref:System.Windows.Media.Imaging.BitmapImage.BeginInit%2A> and <xref:System.Windows.Media.Imaging.BitmapImage.EndInit%2A> block.</span></span>  
  
 [!code-csharp[ImageElementExample_snip#ImageSimpleExampleInlineCode1](~/samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample_snip/CSharp/ImageSimpleExample.xaml.cs#imagesimpleexampleinlinecode1)]
 [!code-vb[ImageElementExample_snip#ImageSimpleExampleInlineCode1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImageElementExample_snip/VB/ImageSimpleExample.xaml.vb#imagesimpleexampleinlinecode1)]  
  
## <a name="see-also"></a><span data-ttu-id="5666a-121">请参阅</span><span class="sxs-lookup"><span data-stu-id="5666a-121">See also</span></span>

- [<span data-ttu-id="5666a-122">图像处理概述</span><span class="sxs-lookup"><span data-stu-id="5666a-122">Imaging Overview</span></span>](../graphics-multimedia/imaging-overview.md)
