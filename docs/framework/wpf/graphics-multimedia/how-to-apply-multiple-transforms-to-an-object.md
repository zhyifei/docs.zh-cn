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
ms.openlocfilehash: 0700a7ae3f18f745b0d479ace3acbf2d7fbd9722
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/08/2018
ms.locfileid: "44212056"
---
# <a name="how-to-apply-multiple-transforms-to-an-object"></a><span data-ttu-id="063cb-102">如何：向对象应用多个变换</span><span class="sxs-lookup"><span data-stu-id="063cb-102">How to: Apply Multiple Transforms to an Object</span></span>
<span data-ttu-id="063cb-103">此示例演示如何使用<xref:System.Windows.Media.TransformGroup>到两个或多个组<xref:System.Windows.Media.Transform>合并为一个复合对象<xref:System.Windows.Media.Transform>。</span><span class="sxs-lookup"><span data-stu-id="063cb-103">This example shows how to use a <xref:System.Windows.Media.TransformGroup> to group two or more <xref:System.Windows.Media.Transform> objects into a single composite <xref:System.Windows.Media.Transform>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="063cb-104">示例</span><span class="sxs-lookup"><span data-stu-id="063cb-104">Example</span></span>  
 <span data-ttu-id="063cb-105">下面的示例使用<xref:System.Windows.Media.TransformGroup>以应用<xref:System.Windows.Media.ScaleTransform>和一个<xref:System.Windows.Media.RotateTransform>到<xref:System.Windows.Controls.Button>。</span><span class="sxs-lookup"><span data-stu-id="063cb-105">The following example uses a <xref:System.Windows.Media.TransformGroup> to apply a <xref:System.Windows.Media.ScaleTransform> and a <xref:System.Windows.Media.RotateTransform> to a <xref:System.Windows.Controls.Button>.</span></span>  
  
 [!code-xaml[Transforms_snip#MultipleTransformExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/MultipleTransformExample.xaml#multipletransformexamplewholepage)]  
  
 [!code-csharp[Transforms_Procedural_snip#MultipleTransformsCodeExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Transforms_Procedural_snip/CSharp/MultipleTransformsExample.cs#multipletransformscodeexamplewholepage)]
 [!code-vb[Transforms_Procedural_snip#MultipleTransformsCodeExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Transforms_Procedural_snip/VisualBasic/MultipleTransformsExample.vb#multipletransformscodeexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="063cb-106">请参阅</span><span class="sxs-lookup"><span data-stu-id="063cb-106">See Also</span></span>  
 <xref:System.Windows.UIElement.RenderTransform%2A>  
 <xref:System.Windows.Media.TransformGroup>  
 [<span data-ttu-id="063cb-107">转换概述</span><span class="sxs-lookup"><span data-stu-id="063cb-107">Transforms Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/transforms-overview.md)  
 [<span data-ttu-id="063cb-108">2D 转换示例</span><span class="sxs-lookup"><span data-stu-id="063cb-108">2-D Transforms Sample</span></span>](https://go.microsoft.com/fwlink/?LinkID=158252)
