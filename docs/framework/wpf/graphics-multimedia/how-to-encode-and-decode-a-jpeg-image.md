---
title: "如何：编码和解码 JPEG 图像"
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
- encoding image formats [WPF]
- decoding JPEG images [WPF]
- encoding JPEG images [WPF]
- decoding image formats [WPF]
- JPEG decoding [WPF]
- JPEG encoding [WPF]
ms.assetid: b8cfde37-9f68-4911-a05e-51d8d7bdec7b
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 2e982c09a27789bcf4a679fd9d237bf1a2b113f7
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-encode-and-decode-a-jpeg-image"></a><span data-ttu-id="0b53f-102">如何：编码和解码 JPEG 图像</span><span class="sxs-lookup"><span data-stu-id="0b53f-102">How to: Encode and Decode a JPEG Image</span></span>
<span data-ttu-id="0b53f-103">下面的示例演示如何进行解码，并进行编码[!INCLUDE[TLA#tla_jpeg](../../../../includes/tlasharptla-jpeg-md.md)]映像使用特定<xref:System.Windows.Media.Imaging.JpegBitmapDecoder>和<xref:System.Windows.Media.Imaging.JpegBitmapEncoder>对象。</span><span class="sxs-lookup"><span data-stu-id="0b53f-103">The following examples show how to decode and encode a [!INCLUDE[TLA#tla_jpeg](../../../../includes/tlasharptla-jpeg-md.md)] image using the specific <xref:System.Windows.Media.Imaging.JpegBitmapDecoder> and <xref:System.Windows.Media.Imaging.JpegBitmapEncoder> objects.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0b53f-104">示例</span><span class="sxs-lookup"><span data-stu-id="0b53f-104">Example</span></span>  
 <span data-ttu-id="0b53f-105">此示例演示了如何解码[!INCLUDE[TLA2#tla_jpeg](../../../../includes/tla2sharptla-jpeg-md.md)]映像使用<xref:System.Windows.Media.Imaging.JpegBitmapDecoder>从<xref:System.IO.FileStream>。</span><span class="sxs-lookup"><span data-stu-id="0b53f-105">This example demonstrates how to decode a [!INCLUDE[TLA2#tla_jpeg](../../../../includes/tla2sharptla-jpeg-md.md)] image using a <xref:System.Windows.Media.Imaging.JpegBitmapDecoder> from a <xref:System.IO.FileStream>.</span></span>  
  
 [!code-cpp[JpegBitmapDecoderEncoder#1](../../../../samples/snippets/cpp/VS_Snippets_Wpf/JpegBitmapDecoderEncoder/CPP/jpegencoderdecoder.cpp#1)]
 [!code-csharp[JpegBitmapDecoderEncoder#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/JpegBitmapDecoderEncoder/CSharp/JpegEncoderDecoder.cs#1)]
 [!code-vb[JpegBitmapDecoderEncoder#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/JpegBitmapDecoderEncoder/VB/JpegEncoderDecoder.vb#1)]  
  
## <a name="example"></a><span data-ttu-id="0b53f-106">示例</span><span class="sxs-lookup"><span data-stu-id="0b53f-106">Example</span></span>  
 <span data-ttu-id="0b53f-107">此示例演示如何进行编码<xref:System.Windows.Media.Imaging.BitmapSource>到[!INCLUDE[TLA2#tla_jpeg](../../../../includes/tla2sharptla-jpeg-md.md)]映像使用<xref:System.Windows.Media.Imaging.JpegBitmapEncoder>。</span><span class="sxs-lookup"><span data-stu-id="0b53f-107">This example demonstrates how to encode a <xref:System.Windows.Media.Imaging.BitmapSource> into a [!INCLUDE[TLA2#tla_jpeg](../../../../includes/tla2sharptla-jpeg-md.md)] image using a <xref:System.Windows.Media.Imaging.JpegBitmapEncoder>.</span></span>  
  
 [!code-cpp[JpegBitmapDecoderEncoder#4](../../../../samples/snippets/cpp/VS_Snippets_Wpf/JpegBitmapDecoderEncoder/CPP/jpegencoderdecoder.cpp#4)]
 [!code-csharp[JpegBitmapDecoderEncoder#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/JpegBitmapDecoderEncoder/CSharp/JpegEncoderDecoder.cs#4)]
 [!code-vb[JpegBitmapDecoderEncoder#4](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/JpegBitmapDecoderEncoder/VB/JpegEncoderDecoder.vb#4)]  
  
## <a name="net-framework-security"></a><span data-ttu-id="0b53f-108">.NET Framework 安全性</span><span class="sxs-lookup"><span data-stu-id="0b53f-108">.NET Framework Security</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0b53f-109">请参阅</span><span class="sxs-lookup"><span data-stu-id="0b53f-109">See Also</span></span>  
 [<span data-ttu-id="0b53f-110">图像处理概述</span><span class="sxs-lookup"><span data-stu-id="0b53f-110">Imaging Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/imaging-overview.md)
