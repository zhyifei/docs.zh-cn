---
title: 如何：使用 MatrixTransform 创建自定义转换
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [WPF], custom Transforms
ms.assetid: 919381ca-989f-47cf-86b4-1094060236e4
ms.openlocfilehash: aeccb961db539d4cc6dea75fb487fba06e59d6de
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59182307"
---
# <a name="how-to-use-a-matrixtransform-to-create-custom-transforms"></a><span data-ttu-id="c8799-102">如何：使用 MatrixTransform 创建自定义转换</span><span class="sxs-lookup"><span data-stu-id="c8799-102">How to: Use a MatrixTransform to Create Custom Transforms</span></span>
<span data-ttu-id="c8799-103">此示例演示如何使用<xref:System.Windows.Media.MatrixTransform>平移 （移动） 位置，拉伸和扭曲的<xref:System.Windows.Controls.Button>。</span><span class="sxs-lookup"><span data-stu-id="c8799-103">This example shows how to use a <xref:System.Windows.Media.MatrixTransform> to translate (move) the position, stretch, and skew of a <xref:System.Windows.Controls.Button>.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c8799-104">使用<xref:System.Windows.Media.MatrixTransform>类，以创建不由提供的自定义转换<xref:System.Windows.Media.RotateTransform>， <xref:System.Windows.Media.SkewTransform>， <xref:System.Windows.Media.ScaleTransform>，或<xref:System.Windows.Media.TranslateTransform>类。</span><span class="sxs-lookup"><span data-stu-id="c8799-104">Use the <xref:System.Windows.Media.MatrixTransform> class to create custom transformations that are not provided by the <xref:System.Windows.Media.RotateTransform>, <xref:System.Windows.Media.SkewTransform>, <xref:System.Windows.Media.ScaleTransform>, or <xref:System.Windows.Media.TranslateTransform> classes.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c8799-105">示例</span><span class="sxs-lookup"><span data-stu-id="c8799-105">Example</span></span>  
 [!code-xaml[Transforms_snip#MatrixTransform](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/MatrixTransformExample.xaml#matrixtransform)]  
  
## <a name="see-also"></a><span data-ttu-id="c8799-106">请参阅</span><span class="sxs-lookup"><span data-stu-id="c8799-106">See also</span></span>

- <xref:System.Windows.Media.MatrixTransform>
- <xref:System.Windows.Media.Transform>
- [<span data-ttu-id="c8799-107">变换概述</span><span class="sxs-lookup"><span data-stu-id="c8799-107">Transforms Overview</span></span>](transforms-overview.md)
- [<span data-ttu-id="c8799-108">帮助主题</span><span class="sxs-lookup"><span data-stu-id="c8799-108">How-to Topics</span></span>](transformations-how-to-topics.md)
- [<span data-ttu-id="c8799-109">WPF 中的形状和基本图形概述</span><span class="sxs-lookup"><span data-stu-id="c8799-109">Shapes and Basic Drawing in WPF Overview</span></span>](shapes-and-basic-drawing-in-wpf-overview.md)
