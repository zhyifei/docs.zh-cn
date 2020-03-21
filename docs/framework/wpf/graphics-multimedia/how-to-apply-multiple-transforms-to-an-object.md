---
title: 如何：向对象应用多个变换
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- grouping Transform objects [WPF]
- Transform objects [WPF], grouping
- graphics [WPF], grouping Transform objects
- TransformGroup [WPF]
ms.assetid: 98cd1921-12bc-4bf5-8193-529228fb7402
ms.openlocfilehash: 3ef11104b2a4fc775d29d2a388c9a70a69a3f10f
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/21/2020
ms.locfileid: "80112110"
---
# <a name="how-to-apply-multiple-transforms-to-an-object"></a><span data-ttu-id="eb505-102">如何：向对象应用多个变换</span><span class="sxs-lookup"><span data-stu-id="eb505-102">How to: Apply Multiple Transforms to an Object</span></span>
<span data-ttu-id="eb505-103">此示例演示如何使用<xref:System.Windows.Media.TransformGroup>将两个或多个<xref:System.Windows.Media.Transform>对象分组到单个复合中。 <xref:System.Windows.Media.Transform></span><span class="sxs-lookup"><span data-stu-id="eb505-103">This example shows how to use a <xref:System.Windows.Media.TransformGroup> to group two or more <xref:System.Windows.Media.Transform> objects into a single composite <xref:System.Windows.Media.Transform>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="eb505-104">示例</span><span class="sxs-lookup"><span data-stu-id="eb505-104">Example</span></span>  
 <span data-ttu-id="eb505-105">下面的<xref:System.Windows.Media.TransformGroup>示例使用 将 和<xref:System.Windows.Media.ScaleTransform>a<xref:System.Windows.Media.RotateTransform>应用于<xref:System.Windows.Controls.Button>。</span><span class="sxs-lookup"><span data-stu-id="eb505-105">The following example uses a <xref:System.Windows.Media.TransformGroup> to apply a <xref:System.Windows.Media.ScaleTransform> and a <xref:System.Windows.Media.RotateTransform> to a <xref:System.Windows.Controls.Button>.</span></span>  
  
 [!code-xaml[Transforms_snip#MultipleTransformExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/MultipleTransformExample.xaml#multipletransformexamplewholepage)]  
  
 [!code-csharp[Transforms_Procedural_snip#MultipleTransformsCodeExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_Procedural_snip/CSharp/MultipleTransformsExample.cs#multipletransformscodeexamplewholepage)]
 [!code-vb[Transforms_Procedural_snip#MultipleTransformsCodeExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Transforms_Procedural_snip/VisualBasic/MultipleTransformsExample.vb#multipletransformscodeexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="eb505-106">另请参阅</span><span class="sxs-lookup"><span data-stu-id="eb505-106">See also</span></span>

- <xref:System.Windows.UIElement.RenderTransform%2A>
- <xref:System.Windows.Media.TransformGroup>
- [<span data-ttu-id="eb505-107">转换概述</span><span class="sxs-lookup"><span data-stu-id="eb505-107">Transforms Overview</span></span>](transforms-overview.md)
- [<span data-ttu-id="eb505-108">2D 变换示例</span><span class="sxs-lookup"><span data-stu-id="eb505-108">2D Transforms Sample</span></span>](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/2DTransforms)
