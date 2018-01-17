---
title: "如何：将 Visual 编码为图像文件"
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
helpviewer_keywords:
- image files [WPF], encoding from visuals
- encoding image formats [WPF]
- visuals [WPF], encoding to an image file
ms.assetid: 2036385b-ea47-4d54-8027-5797f52c8149
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 88a5d93c9c4726d1f6493df28d0a2a559394ef74
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-encode-a-visual-to-an-image-file"></a>如何：将 Visual 编码为图像文件
此示例演示如何进行编码<xref:System.Windows.Media.Visual>对象插入图像文件使用<xref:System.Windows.Media.Imaging.RenderTargetBitmap>和<xref:System.Windows.Media.Imaging.PngBitmapEncoder>。  
  
## <a name="example"></a>示例  
 <xref:System.Windows.Media.DrawingVisual>使用创建<xref:System.Windows.Media.Imaging.BitmapImage>和<xref:System.Windows.Media.FormattedText>呈现到<xref:System.Windows.Media.Imaging.RenderTargetBitmap>。 呈现的位图随后用于创建<xref:System.Windows.Media.Imaging.BitmapFrame>它被添加到<xref:System.Windows.Media.Imaging.PngBitmapEncoder>创建新[!INCLUDE[TLA#tla_png](../../../../includes/tlasharptla-png-md.md)]文件。  
  
 [!code-csharp[ImagingSnippetGallery_procedural_snip#RTBEncodeInline1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImagingSnippetGallery_procedural_snip/CSharp/RenderTargetBitmapExample_Encode.cs#rtbencodeinline1)]
 [!code-vb[ImagingSnippetGallery_procedural_snip#RTBEncodeInline1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ImagingSnippetGallery_procedural_snip/VB/RenderTargetBitmapExample_Encode.vb#rtbencodeinline1)]  
  
 A<xref:System.Windows.Media.Imaging.PngBitmapEncoder>在本示例，但任何派生中使用<xref:System.Windows.Media.Imaging.BitmapEncoder>对象可能已用来创建图像文件。  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Windows.Media.DrawingContext>  
 [图像处理概述](../../../../docs/framework/wpf/graphics-multimedia/imaging-overview.md)  
 [Drawing 对象概述](../../../../docs/framework/wpf/graphics-multimedia/drawing-objects-overview.md)  
 [使用 DrawingVisual 对象](../../../../docs/framework/wpf/graphics-multimedia/using-drawingvisual-objects.md)
