---
title: 如何：编码和解码 GIF 图像
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- encoding GIF images [WPF]
- encoding image formats [WPF]
- decoding GIF images [WPF]
- decoding image formats [WPF]
- GIF decoding [WPF]
- GIF encoding [WPF]
ms.assetid: 9cdd9ec7-71eb-444b-b9e3-991958461163
ms.openlocfilehash: 9b13ac8021b6f2d25209a89ff2ff9b4bb7531ad3
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54562461"
---
# <a name="how-to-encode-and-decode-a-gif-image"></a><span data-ttu-id="8d99a-102">如何：编码和解码 GIF 图像</span><span class="sxs-lookup"><span data-stu-id="8d99a-102">How to: Encode and Decode a GIF Image</span></span>
<span data-ttu-id="8d99a-103">以下示例演示如何解码和编码[!INCLUDE[TLA#tla_gif](../../../../includes/tlasharptla-gif-md.md)]映像使用特定于<xref:System.Windows.Media.Imaging.GifBitmapDecoder>和<xref:System.Windows.Media.Imaging.GifBitmapEncoder>对象。</span><span class="sxs-lookup"><span data-stu-id="8d99a-103">The following examples show how to decode and encode a [!INCLUDE[TLA#tla_gif](../../../../includes/tlasharptla-gif-md.md)] image using the specific <xref:System.Windows.Media.Imaging.GifBitmapDecoder> and <xref:System.Windows.Media.Imaging.GifBitmapEncoder> objects.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8d99a-104">示例</span><span class="sxs-lookup"><span data-stu-id="8d99a-104">Example</span></span>  
 <span data-ttu-id="8d99a-105">此示例演示如何进行解码[!INCLUDE[TLA2#tla_gif](../../../../includes/tla2sharptla-gif-md.md)]映像使用<xref:System.Windows.Media.Imaging.GifBitmapDecoder>从<xref:System.IO.FileStream>。</span><span class="sxs-lookup"><span data-stu-id="8d99a-105">This example demonstrates how to decode a [!INCLUDE[TLA2#tla_gif](../../../../includes/tla2sharptla-gif-md.md)] image using a <xref:System.Windows.Media.Imaging.GifBitmapDecoder> from a <xref:System.IO.FileStream>.</span></span>  
  
 [!code-cpp[GifBitmapDecoderEncoder#1](../../../../samples/snippets/cpp/VS_Snippets_Wpf/GifBitmapDecoderEncoder/CPP/GifEncoderDecoder.cpp#1)]
 [!code-csharp[GifBitmapDecoderEncoder#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GifBitmapDecoderEncoder/CSharp/GifEncoderDecoder.cs#1)]
 [!code-vb[GifBitmapDecoderEncoder#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/GifBitmapDecoderEncoder/VB/GifEncoderDecoder.vb#1)]  
  
## <a name="example"></a><span data-ttu-id="8d99a-106">示例</span><span class="sxs-lookup"><span data-stu-id="8d99a-106">Example</span></span>  
 <span data-ttu-id="8d99a-107">此示例演示如何进行编码<xref:System.Windows.Media.Imaging.BitmapSource>成[!INCLUDE[TLA2#tla_gif](../../../../includes/tla2sharptla-gif-md.md)]图像使用<xref:System.Windows.Media.Imaging.GifBitmapEncoder>。</span><span class="sxs-lookup"><span data-stu-id="8d99a-107">This example demonstrates how to encode a <xref:System.Windows.Media.Imaging.BitmapSource> into a [!INCLUDE[TLA2#tla_gif](../../../../includes/tla2sharptla-gif-md.md)] image using a <xref:System.Windows.Media.Imaging.GifBitmapEncoder>.</span></span>  
  
 [!code-cpp[GifBitmapDecoderEncoder#4](../../../../samples/snippets/cpp/VS_Snippets_Wpf/GifBitmapDecoderEncoder/CPP/GifEncoderDecoder.cpp#4)]
 [!code-csharp[GifBitmapDecoderEncoder#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GifBitmapDecoderEncoder/CSharp/GifEncoderDecoder.cs#4)]
 [!code-vb[GifBitmapDecoderEncoder#4](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/GifBitmapDecoderEncoder/VB/GifEncoderDecoder.vb#4)]  
  
## <a name="see-also"></a><span data-ttu-id="8d99a-108">请参阅</span><span class="sxs-lookup"><span data-stu-id="8d99a-108">See also</span></span>
- [<span data-ttu-id="8d99a-109">图像处理概述</span><span class="sxs-lookup"><span data-stu-id="8d99a-109">Imaging Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/imaging-overview.md)
