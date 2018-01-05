---
title: "如何：编码和解码 BMP 图像"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: c2a6f5b67d4e8bb0653b7f472296d86a770ccbf8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-encode-and-decode-a-bmp-image"></a><span data-ttu-id="d3af8-102">如何：编码和解码 BMP 图像</span><span class="sxs-lookup"><span data-stu-id="d3af8-102">How to: Encode and Decode a BMP Image</span></span>
<span data-ttu-id="d3af8-103">下面的示例演示如何进行解码，并进行编码[!INCLUDE[TLA#tla_bmp](../../../../includes/tlasharptla-bmp-md.md)]映像使用特定<xref:System.Windows.Media.Imaging.BmpBitmapDecoder>和<xref:System.Windows.Media.Imaging.BmpBitmapEncoder>对象。</span><span class="sxs-lookup"><span data-stu-id="d3af8-103">The following examples show how to decode and encode a [!INCLUDE[TLA#tla_bmp](../../../../includes/tlasharptla-bmp-md.md)] image using the specific <xref:System.Windows.Media.Imaging.BmpBitmapDecoder> and <xref:System.Windows.Media.Imaging.BmpBitmapEncoder> objects.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d3af8-104">示例</span><span class="sxs-lookup"><span data-stu-id="d3af8-104">Example</span></span>  
 <span data-ttu-id="d3af8-105">此示例演示了如何解码[!INCLUDE[TLA2#tla_bmp](../../../../includes/tla2sharptla-bmp-md.md)]映像使用<xref:System.Windows.Media.Imaging.BmpBitmapDecoder>从<xref:System.Uri>。</span><span class="sxs-lookup"><span data-stu-id="d3af8-105">This example demonstrates how to decode a [!INCLUDE[TLA2#tla_bmp](../../../../includes/tla2sharptla-bmp-md.md)] image using a <xref:System.Windows.Media.Imaging.BmpBitmapDecoder> from a <xref:System.Uri>.</span></span>  
  
 [!code-cpp[BmpBitmapDecoderEncoder#5](../../../../samples/snippets/cpp/VS_Snippets_Wpf/BmpBitmapDecoderEncoder/CPP/anotherfile.cpp#5)]
 [!code-csharp[BmpBitmapDecoderEncoder#5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BmpBitmapDecoderEncoder/CSharp/BitmapFrame.cs#5)]
 [!code-vb[BmpBitmapDecoderEncoder#5](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BmpBitmapDecoderEncoder/VB/BitmapFrame.vb#5)]  
  
## <a name="example"></a><span data-ttu-id="d3af8-106">示例</span><span class="sxs-lookup"><span data-stu-id="d3af8-106">Example</span></span>  
 <span data-ttu-id="d3af8-107">此示例演示如何进行编码<xref:System.Windows.Media.Imaging.BitmapSource>到[!INCLUDE[TLA2#tla_bmp](../../../../includes/tla2sharptla-bmp-md.md)]映像使用<xref:System.Windows.Media.Imaging.BmpBitmapEncoder>。</span><span class="sxs-lookup"><span data-stu-id="d3af8-107">This example demonstrates how to encode a <xref:System.Windows.Media.Imaging.BitmapSource> into a [!INCLUDE[TLA2#tla_bmp](../../../../includes/tla2sharptla-bmp-md.md)] image using a <xref:System.Windows.Media.Imaging.BmpBitmapEncoder>.</span></span>  
  
 [!code-cpp[BmpBitmapDecoderEncoder#4](../../../../samples/snippets/cpp/VS_Snippets_Wpf/BmpBitmapDecoderEncoder/CPP/anotherfile.cpp#4)]
 [!code-csharp[BmpBitmapDecoderEncoder#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BmpBitmapDecoderEncoder/CSharp/BitmapFrame.cs#4)]
 [!code-vb[BmpBitmapDecoderEncoder#4](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BmpBitmapDecoderEncoder/VB/BitmapFrame.vb#4)]  
  
## <a name="see-also"></a><span data-ttu-id="d3af8-108">请参阅</span><span class="sxs-lookup"><span data-stu-id="d3af8-108">See Also</span></span>  
 [<span data-ttu-id="d3af8-109">图像处理概述</span><span class="sxs-lookup"><span data-stu-id="d3af8-109">Imaging Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/imaging-overview.md)
