---
title: 如何：向三维模型应用多个转换
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- 3-D models [WPF], applying multiple transformations to
ms.assetid: cb72245a-5560-4c96-9f58-593c66296992
ms.openlocfilehash: 7a6a0dd4942eb2430ff79ab5df4a171a4064ac1c
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59186376"
---
# <a name="how-to-apply-multiple-transformations-to-a-3-d-model"></a><span data-ttu-id="e2a9a-102">如何：向三维模型应用多个转换</span><span class="sxs-lookup"><span data-stu-id="e2a9a-102">How to: Apply Multiple Transformations to a 3-D Model</span></span>
<span data-ttu-id="e2a9a-103">此示例演示如何使用<xref:System.Windows.Media.Media3D.RotateTransform3D>和一个<xref:System.Windows.Media.Media3D.ScaleTransform3D>旋转并更改其小数位数的三维模型。</span><span class="sxs-lookup"><span data-stu-id="e2a9a-103">This sample shows how to use a <xref:System.Windows.Media.Media3D.RotateTransform3D> and a <xref:System.Windows.Media.Media3D.ScaleTransform3D> to rotate and change the scale of a 3-D model.</span></span> <span data-ttu-id="e2a9a-104">下面的代码演示如何将应用到这些转换<xref:System.Windows.Media.Media3D.Model3D.Transform%2A>属性的<xref:System.Windows.Media.Media3D.GeometryModel3D>在 XAML 中。</span><span class="sxs-lookup"><span data-stu-id="e2a9a-104">The code below shows how to apply these transforms to the <xref:System.Windows.Media.Media3D.Model3D.Transform%2A> property of a <xref:System.Windows.Media.Media3D.GeometryModel3D> in XAML.</span></span>  
  
 [!code-xaml[3DGallery_snip#Multiple3DTransformationsExampleInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/MultipleTransformationsExample.xaml#multiple3dtransformationsexampleinline1)]  
  
 <span data-ttu-id="e2a9a-105">在代码中：</span><span class="sxs-lookup"><span data-stu-id="e2a9a-105">In code:</span></span>  
  
 [!code-csharp[3DGallery_procedural_snip#Multiple3DTransformationsCodeExampleInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_procedural_snip/CSharp/MultipleTransformationsExample.cs#multiple3dtransformationscodeexampleinline1)]
 [!code-vb[3DGallery_procedural_snip#Multiple3DTransformationsCodeExampleInline1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/3DGallery_procedural_snip/visualbasic/multipletransformationsexample.vb#multiple3dtransformationscodeexampleinline1)]  
  
## <a name="example"></a><span data-ttu-id="e2a9a-106">示例</span><span class="sxs-lookup"><span data-stu-id="e2a9a-106">Example</span></span>  
 <span data-ttu-id="e2a9a-107">下面的代码演示在 XAML 中的整个示例。</span><span class="sxs-lookup"><span data-stu-id="e2a9a-107">The following code shows the entire sample in XAML.</span></span>  
  
 [!code-xaml[3DGallery_snip#Multiple3DTransformationsExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/MultipleTransformationsExample.xaml#multiple3dtransformationsexamplewholepage)]  
  
## <a name="example"></a><span data-ttu-id="e2a9a-108">示例</span><span class="sxs-lookup"><span data-stu-id="e2a9a-108">Example</span></span>  
 <span data-ttu-id="e2a9a-109">下面是在代码中的完整示例。</span><span class="sxs-lookup"><span data-stu-id="e2a9a-109">Below is the entire sample in code.</span></span>  
  
 [!code-csharp[3DGallery_procedural_snip#Multiple3DTransformationsCodeExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_procedural_snip/CSharp/MultipleTransformationsExample.cs#multiple3dtransformationscodeexamplewholepage)]
 [!code-vb[3DGallery_procedural_snip#Multiple3DTransformationsCodeExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/3DGallery_procedural_snip/visualbasic/multipletransformationsexample.vb#multiple3dtransformationscodeexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="e2a9a-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="e2a9a-110">See also</span></span>

- [<span data-ttu-id="e2a9a-111">转换三维模型的比例</span><span class="sxs-lookup"><span data-stu-id="e2a9a-111">Transform the Scale of a 3-D Model</span></span>](how-to-transform-the-scale-of-a-3-d-model.md)
