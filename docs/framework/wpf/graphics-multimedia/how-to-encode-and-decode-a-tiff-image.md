---
title: 如何：编码和解码 TIFF 图像
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- TIFF encoding [WPF]
- encoding TIFF images [WPF]
- encoding image formats [WPF]
- decoding TIFF images [WPF]
- decoding image formats [WPF]
- TIFF decoding [WPF]
ms.assetid: 1dfe3209-fc73-40e6-ad1c-71c1c58b3364
ms.openlocfilehash: 0b2b638d3aa81e48a1378794435d59da1b323aa2
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61947545"
---
# <a name="how-to-encode-and-decode-a-tiff-image"></a><span data-ttu-id="4cd8a-102">如何：编码和解码 TIFF 图像</span><span class="sxs-lookup"><span data-stu-id="4cd8a-102">How to: Encode and Decode a TIFF Image</span></span>
<span data-ttu-id="4cd8a-103">以下示例演示如何解码和编码[!INCLUDE[TLA#tla_tiff](../../../../includes/tlasharptla-tiff-md.md)]映像使用特定于<xref:System.Windows.Media.Imaging.TiffBitmapDecoder>和<xref:System.Windows.Media.Imaging.TiffBitmapEncoder>对象。</span><span class="sxs-lookup"><span data-stu-id="4cd8a-103">The following examples show how to decode and encode a [!INCLUDE[TLA#tla_tiff](../../../../includes/tlasharptla-tiff-md.md)] image using the specific <xref:System.Windows.Media.Imaging.TiffBitmapDecoder> and <xref:System.Windows.Media.Imaging.TiffBitmapEncoder> objects.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4cd8a-104">示例</span><span class="sxs-lookup"><span data-stu-id="4cd8a-104">Example</span></span>  
 <span data-ttu-id="4cd8a-105">此示例演示如何进行解码[!INCLUDE[TLA2#tla_tiff](../../../../includes/tla2sharptla-tiff-md.md)]映像使用<xref:System.Windows.Media.Imaging.TiffBitmapDecoder>从<xref:System.Uri>。</span><span class="sxs-lookup"><span data-stu-id="4cd8a-105">This example demonstrates how to decode a [!INCLUDE[TLA2#tla_tiff](../../../../includes/tla2sharptla-tiff-md.md)] image using a <xref:System.Windows.Media.Imaging.TiffBitmapDecoder> from a <xref:System.Uri>.</span></span>  
  
 [!code-cpp[TiffBitmapDecoderEncoder#1](~/samples/snippets/cpp/VS_Snippets_Wpf/TiffBitmapDecoderEncoder/CPP/TiffEncoderDecoder.cpp#1)]
 [!code-csharp[TiffBitmapDecoderEncoder#1](~/samples/snippets/csharp/VS_Snippets_Wpf/TiffBitmapDecoderEncoder/CSharp/TiffEncoderDecoder.cs#1)]
 [!code-vb[TiffBitmapDecoderEncoder#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TiffBitmapDecoderEncoder/VB/TiffEncoderDecoder.vb#1)]  
  
## <a name="example"></a><span data-ttu-id="4cd8a-106">示例</span><span class="sxs-lookup"><span data-stu-id="4cd8a-106">Example</span></span>  
 <span data-ttu-id="4cd8a-107">此示例演示如何进行编码<xref:System.Windows.Media.Imaging.BitmapSource>成[!INCLUDE[TLA2#tla_tiff](../../../../includes/tla2sharptla-tiff-md.md)]图像使用<xref:System.Windows.Media.Imaging.TiffBitmapEncoder>。</span><span class="sxs-lookup"><span data-stu-id="4cd8a-107">This example demonstrates how to encode a <xref:System.Windows.Media.Imaging.BitmapSource> into a [!INCLUDE[TLA2#tla_tiff](../../../../includes/tla2sharptla-tiff-md.md)] image using a <xref:System.Windows.Media.Imaging.TiffBitmapEncoder>.</span></span>  
  
 [!code-cpp[TiffBitmapDecoderEncoder#4](~/samples/snippets/cpp/VS_Snippets_Wpf/TiffBitmapDecoderEncoder/CPP/TiffEncoderDecoder.cpp#4)]
 [!code-csharp[TiffBitmapDecoderEncoder#4](~/samples/snippets/csharp/VS_Snippets_Wpf/TiffBitmapDecoderEncoder/CSharp/TiffEncoderDecoder.cs#4)]
 [!code-vb[TiffBitmapDecoderEncoder#4](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TiffBitmapDecoderEncoder/VB/TiffEncoderDecoder.vb#4)]  
  
## <a name="see-also"></a><span data-ttu-id="4cd8a-108">请参阅</span><span class="sxs-lookup"><span data-stu-id="4cd8a-108">See also</span></span>

- [<span data-ttu-id="4cd8a-109">图像处理概述</span><span class="sxs-lookup"><span data-stu-id="4cd8a-109">Imaging Overview</span></span>](imaging-overview.md)
