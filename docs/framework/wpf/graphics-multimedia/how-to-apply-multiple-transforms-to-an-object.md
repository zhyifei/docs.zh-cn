---
title: "如何：向对象应用多个变换"
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
- grouping Transform objects [WPF]
- Transform objects [WPF], grouping
- graphics [WPF], grouping Transform objects
- TransformGroup [WPF]
ms.assetid: 98cd1921-12bc-4bf5-8193-529228fb7402
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: cc2611092313ffa85590e18354a1abf371c0718f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-apply-multiple-transforms-to-an-object"></a><span data-ttu-id="23e36-102">如何：向对象应用多个变换</span><span class="sxs-lookup"><span data-stu-id="23e36-102">How to: Apply Multiple Transforms to an Object</span></span>
<span data-ttu-id="23e36-103">此示例演示如何使用<xref:System.Windows.Media.TransformGroup>到两个或多个组<xref:System.Windows.Media.Transform>对象合并为一个合成<xref:System.Windows.Media.Transform>。</span><span class="sxs-lookup"><span data-stu-id="23e36-103">This example shows how to use a <xref:System.Windows.Media.TransformGroup> to group two or more <xref:System.Windows.Media.Transform> objects into a single composite <xref:System.Windows.Media.Transform>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="23e36-104">示例</span><span class="sxs-lookup"><span data-stu-id="23e36-104">Example</span></span>  
 <span data-ttu-id="23e36-105">下面的示例使用<xref:System.Windows.Media.TransformGroup>应用<xref:System.Windows.Media.ScaleTransform>和<xref:System.Windows.Media.RotateTransform>到<xref:System.Windows.Controls.Button>。</span><span class="sxs-lookup"><span data-stu-id="23e36-105">The following example uses a <xref:System.Windows.Media.TransformGroup> to apply a <xref:System.Windows.Media.ScaleTransform> and a <xref:System.Windows.Media.RotateTransform> to a <xref:System.Windows.Controls.Button>.</span></span>  
  
 [!code-xaml[Transforms_snip#MultipleTransformExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/MultipleTransformExample.xaml#multipletransformexamplewholepage)]  
  
 [!code-csharp[Transforms_Procedural_snip#MultipleTransformsCodeExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Transforms_Procedural_snip/CSharp/MultipleTransformsExample.cs#multipletransformscodeexamplewholepage)]
 [!code-vb[Transforms_Procedural_snip#MultipleTransformsCodeExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Transforms_Procedural_snip/VisualBasic/MultipleTransformsExample.vb#multipletransformscodeexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="23e36-106">请参阅</span><span class="sxs-lookup"><span data-stu-id="23e36-106">See Also</span></span>  
 <xref:System.Windows.UIElement.RenderTransform%2A>  
 <xref:System.Windows.Media.TransformGroup>  
 [<span data-ttu-id="23e36-107">转换概述</span><span class="sxs-lookup"><span data-stu-id="23e36-107">Transforms Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/transforms-overview.md)  
 [<span data-ttu-id="23e36-108">2D 转换示例</span><span class="sxs-lookup"><span data-stu-id="23e36-108">2-D Transforms Sample</span></span>](http://go.microsoft.com/fwlink/?LinkID=158252)
