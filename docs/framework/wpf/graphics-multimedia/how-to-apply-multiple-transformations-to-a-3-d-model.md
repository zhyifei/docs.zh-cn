---
title: "如何：向三维模型应用多个变换"
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
helpviewer_keywords: 3-D models [WPF], applying multiple transformations to
ms.assetid: cb72245a-5560-4c96-9f58-593c66296992
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 77e9f664ababa32cf0629f513f81b1e24030eac1
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-apply-multiple-transformations-to-a-3-d-model"></a><span data-ttu-id="2bd3e-102">如何：向三维模型应用多个变换</span><span class="sxs-lookup"><span data-stu-id="2bd3e-102">How to: Apply Multiple Transformations to a 3-D Model</span></span>
<span data-ttu-id="2bd3e-103">此示例演示如何使用<xref:System.Windows.Media.Media3D.RotateTransform3D>和<xref:System.Windows.Media.Media3D.ScaleTransform3D>旋转并更改三维模型的小数位数。</span><span class="sxs-lookup"><span data-stu-id="2bd3e-103">This sample shows how to use a <xref:System.Windows.Media.Media3D.RotateTransform3D> and a <xref:System.Windows.Media.Media3D.ScaleTransform3D> to rotate and change the scale of a 3-D model.</span></span> <span data-ttu-id="2bd3e-104">下面的代码演示如何将应用到这些转换<xref:System.Windows.Media.Media3D.Model3D.Transform%2A>属性<xref:System.Windows.Media.Media3D.GeometryModel3D>在 XAML 中。</span><span class="sxs-lookup"><span data-stu-id="2bd3e-104">The code below shows how to apply these transforms to the <xref:System.Windows.Media.Media3D.Model3D.Transform%2A> property of a <xref:System.Windows.Media.Media3D.GeometryModel3D> in XAML.</span></span>  
  
 [!code-xaml[3DGallery_snip#Multiple3DTransformationsExampleInline1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/MultipleTransformationsExample.xaml#multiple3dtransformationsexampleinline1)]  
  
 <span data-ttu-id="2bd3e-105">在代码中：</span><span class="sxs-lookup"><span data-stu-id="2bd3e-105">In code:</span></span>  
  
 [!code-csharp[3DGallery_procedural_snip#Multiple3DTransformationsCodeExampleInline1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_procedural_snip/CSharp/MultipleTransformationsExample.cs#multiple3dtransformationscodeexampleinline1)]
 [!code-vb[3DGallery_procedural_snip#Multiple3DTransformationsCodeExampleInline1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/3DGallery_procedural_snip/visualbasic/multipletransformationsexample.vb#multiple3dtransformationscodeexampleinline1)]  
  
## <a name="example"></a><span data-ttu-id="2bd3e-106">示例</span><span class="sxs-lookup"><span data-stu-id="2bd3e-106">Example</span></span>  
 <span data-ttu-id="2bd3e-107">下面的代码演示了整个示例在 XAML 中。</span><span class="sxs-lookup"><span data-stu-id="2bd3e-107">The following code shows the entire sample in XAML.</span></span>  
  
 [!code-xaml[3DGallery_snip#Multiple3DTransformationsExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/MultipleTransformationsExample.xaml#multiple3dtransformationsexamplewholepage)]  
  
## <a name="example"></a><span data-ttu-id="2bd3e-108">示例</span><span class="sxs-lookup"><span data-stu-id="2bd3e-108">Example</span></span>  
 <span data-ttu-id="2bd3e-109">下面是在代码中的完整示例。</span><span class="sxs-lookup"><span data-stu-id="2bd3e-109">Below is the entire sample in code.</span></span>  
  
 [!code-csharp[3DGallery_procedural_snip#Multiple3DTransformationsCodeExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_procedural_snip/CSharp/MultipleTransformationsExample.cs#multiple3dtransformationscodeexamplewholepage)]
 [!code-vb[3DGallery_procedural_snip#Multiple3DTransformationsCodeExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/3DGallery_procedural_snip/visualbasic/multipletransformationsexample.vb#multiple3dtransformationscodeexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="2bd3e-110">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2bd3e-110">See Also</span></span>  
 [<span data-ttu-id="2bd3e-111">转换 3D 模型的比例</span><span class="sxs-lookup"><span data-stu-id="2bd3e-111">Transform the Scale of a 3-D Model</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-transform-the-scale-of-a-3-d-model.md)
