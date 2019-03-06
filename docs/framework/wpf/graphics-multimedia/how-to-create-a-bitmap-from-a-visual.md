---
title: 如何：从 Visual 创建位图
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- bitmaps [WPF], rendering from visuals
- visuals [WPF], rendering to bitmaps
ms.assetid: 103fc7f5-7306-4026-9d61-2005e79959f3
ms.openlocfilehash: 429aacc99d8ead5a18e9be7602b19a74773b419a
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/05/2019
ms.locfileid: "57362859"
---
# <a name="how-to-create-a-bitmap-from-a-visual"></a><span data-ttu-id="8a4df-102">如何：从 Visual 创建位图</span><span class="sxs-lookup"><span data-stu-id="8a4df-102">How to: Create a Bitmap from a Visual</span></span>
<span data-ttu-id="8a4df-103">此示例演示如何创建从位图<xref:System.Windows.Media.Visual>。</span><span class="sxs-lookup"><span data-stu-id="8a4df-103">This example shows how you can create a bitmap from a <xref:System.Windows.Media.Visual>.</span></span> <span data-ttu-id="8a4df-104">一个<xref:System.Windows.Media.DrawingVisual>呈现与<xref:System.Windows.Media.FormattedText>。</span><span class="sxs-lookup"><span data-stu-id="8a4df-104">A <xref:System.Windows.Media.DrawingVisual> is rendered with <xref:System.Windows.Media.FormattedText>.</span></span> <span data-ttu-id="8a4df-105"><xref:System.Windows.Media.Visual>将呈现到<xref:System.Windows.Media.Imaging.RenderTargetBitmap>创建给定文本的位图。</span><span class="sxs-lookup"><span data-stu-id="8a4df-105">The <xref:System.Windows.Media.Visual> is then rendered to the <xref:System.Windows.Media.Imaging.RenderTargetBitmap> creating a bitmap of the given text.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8a4df-106">示例</span><span class="sxs-lookup"><span data-stu-id="8a4df-106">Example</span></span>  
 [!code-csharp[ImagingSnippetGallery_procedural_snip#CreateRTBImage](~/samples/snippets/csharp/VS_Snippets_Wpf/ImagingSnippetGallery_procedural_snip/CSharp/RenderTargetBitmapExample.cs#creatertbimage)]
 [!code-vb[ImagingSnippetGallery_procedural_snip#CreateRTBImage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImagingSnippetGallery_procedural_snip/VB/RenderTargetBitmapExample.vb#creatertbimage)]  
  
## <a name="see-also"></a><span data-ttu-id="8a4df-107">请参阅</span><span class="sxs-lookup"><span data-stu-id="8a4df-107">See also</span></span>
- <xref:System.Windows.Media.DrawingContext>
- [<span data-ttu-id="8a4df-108">图像处理概述</span><span class="sxs-lookup"><span data-stu-id="8a4df-108">Imaging Overview</span></span>](imaging-overview.md)
- [<span data-ttu-id="8a4df-109">Drawing 对象概述</span><span class="sxs-lookup"><span data-stu-id="8a4df-109">Drawing Objects Overview</span></span>](drawing-objects-overview.md)
- [<span data-ttu-id="8a4df-110">使用 DrawingVisual 对象</span><span class="sxs-lookup"><span data-stu-id="8a4df-110">Using DrawingVisual Objects</span></span>](using-drawingvisual-objects.md)
