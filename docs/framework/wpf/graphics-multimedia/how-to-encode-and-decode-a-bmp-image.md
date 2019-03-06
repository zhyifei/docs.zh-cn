---
title: 如何：编码和解码 BMP 图像
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- encoding BMP images [WPF]
- BMP encoding [WPF]
- decoding BMP images [WPF]
- encoding image formats [WPF]
- BMP decoding [WPF]
- decoding image formats [WPF]
ms.assetid: feb5ef27-28ac-40ab-bfc2-e0456990d32c
ms.openlocfilehash: 5aee77ab70c6a24846967b01bbb458ba4cdbe970
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/05/2019
ms.locfileid: "57379622"
---
# <a name="how-to-encode-and-decode-a-bmp-image"></a><span data-ttu-id="a2435-102">如何：编码和解码 BMP 图像</span><span class="sxs-lookup"><span data-stu-id="a2435-102">How to: Encode and Decode a BMP Image</span></span>
<span data-ttu-id="a2435-103">以下示例演示如何解码和编码[!INCLUDE[TLA#tla_bmp](../../../../includes/tlasharptla-bmp-md.md)]映像使用特定于<xref:System.Windows.Media.Imaging.BmpBitmapDecoder>和<xref:System.Windows.Media.Imaging.BmpBitmapEncoder>对象。</span><span class="sxs-lookup"><span data-stu-id="a2435-103">The following examples show how to decode and encode a [!INCLUDE[TLA#tla_bmp](../../../../includes/tlasharptla-bmp-md.md)] image using the specific <xref:System.Windows.Media.Imaging.BmpBitmapDecoder> and <xref:System.Windows.Media.Imaging.BmpBitmapEncoder> objects.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a2435-104">示例</span><span class="sxs-lookup"><span data-stu-id="a2435-104">Example</span></span>  
 <span data-ttu-id="a2435-105">此示例演示如何进行解码[!INCLUDE[TLA2#tla_bmp](../../../../includes/tla2sharptla-bmp-md.md)]映像使用<xref:System.Windows.Media.Imaging.BmpBitmapDecoder>从<xref:System.Uri>。</span><span class="sxs-lookup"><span data-stu-id="a2435-105">This example demonstrates how to decode a [!INCLUDE[TLA2#tla_bmp](../../../../includes/tla2sharptla-bmp-md.md)] image using a <xref:System.Windows.Media.Imaging.BmpBitmapDecoder> from a <xref:System.Uri>.</span></span>  
  
 [!code-cpp[BmpBitmapDecoderEncoder#5](~/samples/snippets/cpp/VS_Snippets_Wpf/BmpBitmapDecoderEncoder/CPP/anotherfile.cpp#5)]
 [!code-csharp[BmpBitmapDecoderEncoder#5](~/samples/snippets/csharp/VS_Snippets_Wpf/BmpBitmapDecoderEncoder/CSharp/BitmapFrame.cs#5)]
 [!code-vb[BmpBitmapDecoderEncoder#5](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BmpBitmapDecoderEncoder/VB/BitmapFrame.vb#5)]  
  
## <a name="example"></a><span data-ttu-id="a2435-106">示例</span><span class="sxs-lookup"><span data-stu-id="a2435-106">Example</span></span>  
 <span data-ttu-id="a2435-107">此示例演示如何进行编码<xref:System.Windows.Media.Imaging.BitmapSource>成[!INCLUDE[TLA2#tla_bmp](../../../../includes/tla2sharptla-bmp-md.md)]图像使用<xref:System.Windows.Media.Imaging.BmpBitmapEncoder>。</span><span class="sxs-lookup"><span data-stu-id="a2435-107">This example demonstrates how to encode a <xref:System.Windows.Media.Imaging.BitmapSource> into a [!INCLUDE[TLA2#tla_bmp](../../../../includes/tla2sharptla-bmp-md.md)] image using a <xref:System.Windows.Media.Imaging.BmpBitmapEncoder>.</span></span>  
  
 [!code-cpp[BmpBitmapDecoderEncoder#4](~/samples/snippets/cpp/VS_Snippets_Wpf/BmpBitmapDecoderEncoder/CPP/anotherfile.cpp#4)]
 [!code-csharp[BmpBitmapDecoderEncoder#4](~/samples/snippets/csharp/VS_Snippets_Wpf/BmpBitmapDecoderEncoder/CSharp/BitmapFrame.cs#4)]
 [!code-vb[BmpBitmapDecoderEncoder#4](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BmpBitmapDecoderEncoder/VB/BitmapFrame.vb#4)]  
  
## <a name="see-also"></a><span data-ttu-id="a2435-108">请参阅</span><span class="sxs-lookup"><span data-stu-id="a2435-108">See also</span></span>
- [<span data-ttu-id="a2435-109">图像处理概述</span><span class="sxs-lookup"><span data-stu-id="a2435-109">Imaging Overview</span></span>](imaging-overview.md)
