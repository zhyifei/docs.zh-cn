---
title: 如何：将图像作为缩略图加载
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- loading images as thumbnails [WPF]
- images [WPF], loading as thumbnails
- thumbnails [WPF], loading images as
ms.assetid: 02e055a0-54df-499a-b8b6-ab6ff7535cff
ms.openlocfilehash: 349a602a10b89931701e24334bf5ac5536f26400
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33562318"
---
# <a name="how-to-load-an-image-as-a-thumbnail"></a><span data-ttu-id="b0cd2-102">如何：将图像作为缩略图加载</span><span class="sxs-lookup"><span data-stu-id="b0cd2-102">How to: Load an Image as a Thumbnail</span></span>
<span data-ttu-id="b0cd2-103">下面的示例演示如何加载<xref:System.Windows.Controls.Image>作为以节省应用程序内存的缩略图。</span><span class="sxs-lookup"><span data-stu-id="b0cd2-103">The following examples show how to load an <xref:System.Windows.Controls.Image> as a thumbnail to conserve application memory.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b0cd2-104">示例</span><span class="sxs-lookup"><span data-stu-id="b0cd2-104">Example</span></span>  
 <span data-ttu-id="b0cd2-105">下面的示例设置<xref:System.Windows.Media.Imaging.BitmapImage.DecodePixelWidth%2A>属性<xref:System.Windows.Media.Imaging.BitmapImage>中[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]以减少加载图像所需的内存。</span><span class="sxs-lookup"><span data-stu-id="b0cd2-105">The following example sets the <xref:System.Windows.Media.Imaging.BitmapImage.DecodePixelWidth%2A> property of a <xref:System.Windows.Media.Imaging.BitmapImage> in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] to reduce the memory required to load the image.</span></span>  
  
 [!code-xaml[ImageElementExample_snip#ImageSimpleExampleInlineMarkup](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample_snip/CSharp/ImageSimpleExample.xaml#imagesimpleexampleinlinemarkup)]  
  
## <a name="example"></a><span data-ttu-id="b0cd2-106">示例</span><span class="sxs-lookup"><span data-stu-id="b0cd2-106">Example</span></span>  
 <span data-ttu-id="b0cd2-107">下面的示例设置<xref:System.Windows.Media.Imaging.BitmapImage.DecodePixelWidth%2A>属性<xref:System.Windows.Media.Imaging.BitmapImage>代码以减少加载图像所需的内存中。</span><span class="sxs-lookup"><span data-stu-id="b0cd2-107">The following example sets the <xref:System.Windows.Media.Imaging.BitmapImage.DecodePixelWidth%2A> property of a <xref:System.Windows.Media.Imaging.BitmapImage> in code to reduce the memory required to load the image.</span></span>  
  
 [!code-csharp[ImageElementExample_snip#ImageSimpleExampleInlineCode1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample_snip/CSharp/ImageSimpleExample.xaml.cs#imagesimpleexampleinlinecode1)]
 [!code-vb[ImageElementExample_snip#ImageSimpleExampleInlineCode1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ImageElementExample_snip/VB/ImageSimpleExample.xaml.vb#imagesimpleexampleinlinecode1)]  
  
## <a name="see-also"></a><span data-ttu-id="b0cd2-108">请参阅</span><span class="sxs-lookup"><span data-stu-id="b0cd2-108">See Also</span></span>  
 [<span data-ttu-id="b0cd2-109">图像处理概述</span><span class="sxs-lookup"><span data-stu-id="b0cd2-109">Imaging Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/imaging-overview.md)
