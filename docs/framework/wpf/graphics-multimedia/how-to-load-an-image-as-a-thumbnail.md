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
ms.openlocfilehash: 0b5435e9b06f37dae7dc762e9035b1eca8156ca6
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/05/2019
ms.locfileid: "57353382"
---
# <a name="how-to-load-an-image-as-a-thumbnail"></a><span data-ttu-id="d9970-102">如何：将图像作为缩略图加载</span><span class="sxs-lookup"><span data-stu-id="d9970-102">How to: Load an Image as a Thumbnail</span></span>
<span data-ttu-id="d9970-103">下面的示例显示如何加载<xref:System.Windows.Controls.Image>作为缩略图以节省应用程序内存。</span><span class="sxs-lookup"><span data-stu-id="d9970-103">The following examples show how to load an <xref:System.Windows.Controls.Image> as a thumbnail to conserve application memory.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d9970-104">示例</span><span class="sxs-lookup"><span data-stu-id="d9970-104">Example</span></span>  
 <span data-ttu-id="d9970-105">下面的示例设置<xref:System.Windows.Media.Imaging.BitmapImage.DecodePixelWidth%2A>的属性<xref:System.Windows.Media.Imaging.BitmapImage>中[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]以减少加载图像所需的内存。</span><span class="sxs-lookup"><span data-stu-id="d9970-105">The following example sets the <xref:System.Windows.Media.Imaging.BitmapImage.DecodePixelWidth%2A> property of a <xref:System.Windows.Media.Imaging.BitmapImage> in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] to reduce the memory required to load the image.</span></span>  
  
 [!code-xaml[ImageElementExample_snip#ImageSimpleExampleInlineMarkup](~/samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample_snip/CSharp/ImageSimpleExample.xaml#imagesimpleexampleinlinemarkup)]  
  
## <a name="example"></a><span data-ttu-id="d9970-106">示例</span><span class="sxs-lookup"><span data-stu-id="d9970-106">Example</span></span>  
 <span data-ttu-id="d9970-107">下面的示例设置<xref:System.Windows.Media.Imaging.BitmapImage.DecodePixelWidth%2A>属性的<xref:System.Windows.Media.Imaging.BitmapImage>代码，以减少加载图像所需的内存中。</span><span class="sxs-lookup"><span data-stu-id="d9970-107">The following example sets the <xref:System.Windows.Media.Imaging.BitmapImage.DecodePixelWidth%2A> property of a <xref:System.Windows.Media.Imaging.BitmapImage> in code to reduce the memory required to load the image.</span></span>  
  
 [!code-csharp[ImageElementExample_snip#ImageSimpleExampleInlineCode1](~/samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample_snip/CSharp/ImageSimpleExample.xaml.cs#imagesimpleexampleinlinecode1)]
 [!code-vb[ImageElementExample_snip#ImageSimpleExampleInlineCode1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImageElementExample_snip/VB/ImageSimpleExample.xaml.vb#imagesimpleexampleinlinecode1)]  
  
## <a name="see-also"></a><span data-ttu-id="d9970-108">请参阅</span><span class="sxs-lookup"><span data-stu-id="d9970-108">See also</span></span>
- [<span data-ttu-id="d9970-109">图像处理概述</span><span class="sxs-lookup"><span data-stu-id="d9970-109">Imaging Overview</span></span>](imaging-overview.md)
