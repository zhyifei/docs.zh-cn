---
title: 如何：使用 MatrixTransform 创建自定义转换
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [WPF], custom Transforms
ms.assetid: 919381ca-989f-47cf-86b4-1094060236e4
ms.openlocfilehash: 1971d5fe9422c5138f140517e6fd4c9f9b2cf48b
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69913920"
---
# <a name="how-to-use-a-matrixtransform-to-create-custom-transforms"></a><span data-ttu-id="d7b2b-102">如何：使用 MatrixTransform 创建自定义转换</span><span class="sxs-lookup"><span data-stu-id="d7b2b-102">How to: Use a MatrixTransform to Create Custom Transforms</span></span>
<span data-ttu-id="d7b2b-103">此示例演示如何使用<xref:System.Windows.Media.MatrixTransform>转换 (移动) 的位置、拉伸和倾斜。 <xref:System.Windows.Controls.Button></span><span class="sxs-lookup"><span data-stu-id="d7b2b-103">This example shows how to use a <xref:System.Windows.Media.MatrixTransform> to translate (move) the position, stretch, and skew of a <xref:System.Windows.Controls.Button>.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d7b2b-104"><xref:System.Windows.Media.RotateTransform> <xref:System.Windows.Media.SkewTransform> <xref:System.Windows.Media.ScaleTransform>使用类可创建不由、、或<xref:System.Windows.Media.TranslateTransform>类提供的自定义转换。 <xref:System.Windows.Media.MatrixTransform></span><span class="sxs-lookup"><span data-stu-id="d7b2b-104">Use the <xref:System.Windows.Media.MatrixTransform> class to create custom transformations that are not provided by the <xref:System.Windows.Media.RotateTransform>, <xref:System.Windows.Media.SkewTransform>, <xref:System.Windows.Media.ScaleTransform>, or <xref:System.Windows.Media.TranslateTransform> classes.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d7b2b-105">示例</span><span class="sxs-lookup"><span data-stu-id="d7b2b-105">Example</span></span>  
 [!code-xaml[Transforms_snip#MatrixTransform](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/MatrixTransformExample.xaml#matrixtransform)]  
  
## <a name="see-also"></a><span data-ttu-id="d7b2b-106">请参阅</span><span class="sxs-lookup"><span data-stu-id="d7b2b-106">See also</span></span>

- <xref:System.Windows.Media.MatrixTransform>
- <xref:System.Windows.Media.Transform>
- [<span data-ttu-id="d7b2b-107">转换概述</span><span class="sxs-lookup"><span data-stu-id="d7b2b-107">Transforms Overview</span></span>](transforms-overview.md)
- [<span data-ttu-id="d7b2b-108">帮助主题</span><span class="sxs-lookup"><span data-stu-id="d7b2b-108">How-to Topics</span></span>](transformations-how-to-topics.md)
- [<span data-ttu-id="d7b2b-109">WPF 中的形状和基本绘图概述</span><span class="sxs-lookup"><span data-stu-id="d7b2b-109">Shapes and Basic Drawing in WPF Overview</span></span>](shapes-and-basic-drawing-in-wpf-overview.md)
