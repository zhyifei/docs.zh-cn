---
title: 如何：编码和解码 WDP 图像
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- WDP encoding [WPF]
- WDP decoding [WPF]
- encoding image formats [WPF]
- decoding WDP images [WPF]
- decoding image formats [WPF]
- encoding WDP images [WPF]
ms.assetid: 911777d1-516b-49db-a87b-b54e31b18532
ms.openlocfilehash: 8c5c312c7e58d48a865e493c38c3defd3f5f3d1d
ms.sourcegitcommit: ad800f019ac976cb669e635fb0ea49db740e6890
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/29/2019
ms.locfileid: "73040781"
---
# <a name="how-to-encode-and-decode-a-wdp-image"></a><span data-ttu-id="0866e-102">如何：编码和解码 WDP 图像</span><span class="sxs-lookup"><span data-stu-id="0866e-102">How to: Encode and Decode a WDP Image</span></span>
<span data-ttu-id="0866e-103">下面的示例演示如何使用特定的 <xref:System.Windows.Media.Imaging.WmpBitmapDecoder> 和 <xref:System.Windows.Media.Imaging.WmpBitmapEncoder> 对象对 Microsoft Windows Media 照片图像进行解码和编码。</span><span class="sxs-lookup"><span data-stu-id="0866e-103">The following examples show how to decode and encode a Microsoft Windows Media Photo image using the specific <xref:System.Windows.Media.Imaging.WmpBitmapDecoder> and <xref:System.Windows.Media.Imaging.WmpBitmapEncoder> objects.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0866e-104">示例</span><span class="sxs-lookup"><span data-stu-id="0866e-104">Example</span></span>  
 <span data-ttu-id="0866e-105">此示例演示如何使用 <xref:System.Uri>中的 <xref:System.Windows.Media.Imaging.WmpBitmapDecoder> 对 Windows Media 照片图像进行解码。</span><span class="sxs-lookup"><span data-stu-id="0866e-105">This example demonstrates how to decode a Windows Media Photo image using a <xref:System.Windows.Media.Imaging.WmpBitmapDecoder> from a <xref:System.Uri>.</span></span>  
  
 [!code-cpp[WdpBitmapDecoderEncoder#1](~/samples/snippets/cpp/VS_Snippets_Wpf/WdpBitmapDecoderEncoder/CPP/WDPEncoderDecoder.cpp#1)]
 [!code-csharp[WdpBitmapDecoderEncoder#1](~/samples/snippets/csharp/VS_Snippets_Wpf/WdpBitmapDecoderEncoder/CSharp/WDPEncoderDecoder.cs#1)]
 [!code-vb[WdpBitmapDecoderEncoder#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WdpBitmapDecoderEncoder/VB/WDPEncoderDecoder.vb#1)]  
  
## <a name="example"></a><span data-ttu-id="0866e-106">示例</span><span class="sxs-lookup"><span data-stu-id="0866e-106">Example</span></span>  
 <span data-ttu-id="0866e-107">此示例演示如何使用 <xref:System.Windows.Media.Imaging.WmpBitmapEncoder>将 <xref:System.Windows.Media.Imaging.BitmapSource> 编码为 Windows Media 照片图像。</span><span class="sxs-lookup"><span data-stu-id="0866e-107">This example demonstrates how to encode a <xref:System.Windows.Media.Imaging.BitmapSource> into a Windows Media Photo image using a <xref:System.Windows.Media.Imaging.WmpBitmapEncoder>.</span></span>  
  
 [!code-cpp[WdpBitmapDecoderEncoder#4](~/samples/snippets/cpp/VS_Snippets_Wpf/WdpBitmapDecoderEncoder/CPP/WDPEncoderDecoder.cpp#4)]
 [!code-csharp[WdpBitmapDecoderEncoder#4](~/samples/snippets/csharp/VS_Snippets_Wpf/WdpBitmapDecoderEncoder/CSharp/WDPEncoderDecoder.cs#4)]
 [!code-vb[WdpBitmapDecoderEncoder#4](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WdpBitmapDecoderEncoder/VB/WDPEncoderDecoder.vb#4)]  
  
## <a name="see-also"></a><span data-ttu-id="0866e-108">请参阅</span><span class="sxs-lookup"><span data-stu-id="0866e-108">See also</span></span>

- [<span data-ttu-id="0866e-109">图像处理概述</span><span class="sxs-lookup"><span data-stu-id="0866e-109">Imaging Overview</span></span>](imaging-overview.md)
