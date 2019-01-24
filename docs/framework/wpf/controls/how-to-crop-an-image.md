---
title: 如何：裁剪图像
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- images [WPF], cropping
- cropping images [WPF]
ms.assetid: c6bba109-c6e7-4cf8-bfe6-9cf8d01bb4fc
ms.openlocfilehash: fbd15ea6c5c47aa090829754402cc3a6926654d8
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54663961"
---
# <a name="how-to-crop-an-image"></a><span data-ttu-id="fac9d-102">如何：裁剪图像</span><span class="sxs-lookup"><span data-stu-id="fac9d-102">How to: Crop an Image</span></span>
<span data-ttu-id="fac9d-103">此示例演示如何裁剪图像使用<xref:System.Windows.Media.Imaging.CroppedBitmap>。</span><span class="sxs-lookup"><span data-stu-id="fac9d-103">This example shows how to crop an image using <xref:System.Windows.Media.Imaging.CroppedBitmap>.</span></span>  
  
 <span data-ttu-id="fac9d-104"><xref:System.Windows.Media.Imaging.CroppedBitmap> 主要用于裁剪后的映像版本进行编码时将查看保存到文件。</span><span class="sxs-lookup"><span data-stu-id="fac9d-104"><xref:System.Windows.Media.Imaging.CroppedBitmap> is primarily used when encoding a cropped version of an image to save out to a file.</span></span> <span data-ttu-id="fac9d-105">若要裁剪图像用于显示目的，请参阅[创建剪辑区域](https://msdn.microsoft.com/library/56e4bed6-78d7-4292-b917-d72d0b3e4376)主题。</span><span class="sxs-lookup"><span data-stu-id="fac9d-105">To crop an image for display purposes see the [Create a Clip Region](https://msdn.microsoft.com/library/56e4bed6-78d7-4292-b917-d72d0b3e4376) topic.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fac9d-106">示例</span><span class="sxs-lookup"><span data-stu-id="fac9d-106">Example</span></span>  
 <span data-ttu-id="fac9d-107">以下[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]定义下面的示例中使用的资源。</span><span class="sxs-lookup"><span data-stu-id="fac9d-107">The following [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] defines resources used within the samples below.</span></span>  
  
 [!code-xaml[imageelementexample#CroppedXAML1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample/CSharp/CroppedImageExample.xaml#croppedxaml1)]  
  
 <span data-ttu-id="fac9d-108">下面的示例创建映像使用<xref:System.Windows.Media.Imaging.CroppedBitmap>作为其源。</span><span class="sxs-lookup"><span data-stu-id="fac9d-108">The following example creates an image using a <xref:System.Windows.Media.Imaging.CroppedBitmap> as its source.</span></span>  
  
 [!code-xaml[imageelementexample#CroppedXAML2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample/CSharp/CroppedImageExample.xaml#croppedxaml2)]  
  
 [!code-csharp[imageelementexample#CroppedCSharp1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample/CSharp/CroppedImageExample.xaml.cs#croppedcsharp1)]
 [!code-vb[imageelementexample#CroppedCSharp1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ImageElementExample/VB/CroppedImageExample.xaml.vb#croppedcsharp1)]  
  
 <span data-ttu-id="fac9d-109"><xref:System.Windows.Media.Imaging.CroppedBitmap>还可以用作另一个源<xref:System.Windows.Media.Imaging.CroppedBitmap>，链接裁剪。</span><span class="sxs-lookup"><span data-stu-id="fac9d-109">The <xref:System.Windows.Media.Imaging.CroppedBitmap> can also be used as the source of another <xref:System.Windows.Media.Imaging.CroppedBitmap>, chaining the cropping.</span></span> <span data-ttu-id="fac9d-110">请注意，<xref:System.Windows.Media.Imaging.CroppedBitmap.SourceRect%2A>使用相对于裁剪位图并不是初始的图像的源的值。</span><span class="sxs-lookup"><span data-stu-id="fac9d-110">Note that the <xref:System.Windows.Media.Imaging.CroppedBitmap.SourceRect%2A> uses values that are relative to the source cropped bitmap and not the initial image.</span></span>  
  
 [!code-xaml[imageelementexample#CroppedXAML3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample/CSharp/CroppedImageExample.xaml#croppedxaml3)]  
  
 [!code-csharp[imageelementexample#CroppedCSharp2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample/CSharp/CroppedImageExample.xaml.cs#croppedcsharp2)]
 [!code-vb[imageelementexample#CroppedCSharp2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ImageElementExample/VB/CroppedImageExample.xaml.vb#croppedcsharp2)]  
  
## <a name="see-also"></a><span data-ttu-id="fac9d-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="fac9d-111">See also</span></span>
- [<span data-ttu-id="fac9d-112">创建剪辑区域</span><span class="sxs-lookup"><span data-stu-id="fac9d-112">Create a Clip Region</span></span>](https://msdn.microsoft.com/library/56e4bed6-78d7-4292-b917-d72d0b3e4376)
