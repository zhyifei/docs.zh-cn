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
ms.workload: dotnet
ms.openlocfilehash: 26832827b0e92813802073adcb4c2db99dff0807
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-apply-multiple-transformations-to-a-3-d-model"></a><span data-ttu-id="cf277-102">如何：向三维模型应用多个变换</span><span class="sxs-lookup"><span data-stu-id="cf277-102">How to: Apply Multiple Transformations to a 3-D Model</span></span>
<span data-ttu-id="cf277-103">此示例演示如何使用<xref:System.Windows.Media.Media3D.RotateTransform3D>和<xref:System.Windows.Media.Media3D.ScaleTransform3D>旋转并更改三维模型的小数位数。</span><span class="sxs-lookup"><span data-stu-id="cf277-103">This sample shows how to use a <xref:System.Windows.Media.Media3D.RotateTransform3D> and a <xref:System.Windows.Media.Media3D.ScaleTransform3D> to rotate and change the scale of a 3-D model.</span></span> <span data-ttu-id="cf277-104">下面的代码演示如何将应用到这些转换<xref:System.Windows.Media.Media3D.Model3D.Transform%2A>属性<xref:System.Windows.Media.Media3D.GeometryModel3D>在 XAML 中。</span><span class="sxs-lookup"><span data-stu-id="cf277-104">The code below shows how to apply these transforms to the <xref:System.Windows.Media.Media3D.Model3D.Transform%2A> property of a <xref:System.Windows.Media.Media3D.GeometryModel3D> in XAML.</span></span>  
  
 [!code-xaml[3DGallery_snip#Multiple3DTransformationsExampleInline1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/MultipleTransformationsExample.xaml#multiple3dtransformationsexampleinline1)]  
  
 <span data-ttu-id="cf277-105">在代码中：</span><span class="sxs-lookup"><span data-stu-id="cf277-105">In code:</span></span>  
  
 [!code-csharp[3DGallery_procedural_snip#Multiple3DTransformationsCodeExampleInline1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_procedural_snip/CSharp/MultipleTransformationsExample.cs#multiple3dtransformationscodeexampleinline1)]
 [!code-vb[3DGallery_procedural_snip#Multiple3DTransformationsCodeExampleInline1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/3DGallery_procedural_snip/visualbasic/multipletransformationsexample.vb#multiple3dtransformationscodeexampleinline1)]  
  
## <a name="example"></a><span data-ttu-id="cf277-106">示例</span><span class="sxs-lookup"><span data-stu-id="cf277-106">Example</span></span>  
 <span data-ttu-id="cf277-107">下面的代码演示了整个示例在 XAML 中。</span><span class="sxs-lookup"><span data-stu-id="cf277-107">The following code shows the entire sample in XAML.</span></span>  
  
 [!code-xaml[3DGallery_snip#Multiple3DTransformationsExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/MultipleTransformationsExample.xaml#multiple3dtransformationsexamplewholepage)]  
  
## <a name="example"></a><span data-ttu-id="cf277-108">示例</span><span class="sxs-lookup"><span data-stu-id="cf277-108">Example</span></span>  
 <span data-ttu-id="cf277-109">下面是在代码中的完整示例。</span><span class="sxs-lookup"><span data-stu-id="cf277-109">Below is the entire sample in code.</span></span>  
  
 [!code-csharp[3DGallery_procedural_snip#Multiple3DTransformationsCodeExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_procedural_snip/CSharp/MultipleTransformationsExample.cs#multiple3dtransformationscodeexamplewholepage)]
 [!code-vb[3DGallery_procedural_snip#Multiple3DTransformationsCodeExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/3DGallery_procedural_snip/visualbasic/multipletransformationsexample.vb#multiple3dtransformationscodeexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="cf277-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="cf277-110">See Also</span></span>  
 [<span data-ttu-id="cf277-111">转换 3D 模型的比例</span><span class="sxs-lookup"><span data-stu-id="cf277-111">Transform the Scale of a 3-D Model</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-transform-the-scale-of-a-3-d-model.md)
