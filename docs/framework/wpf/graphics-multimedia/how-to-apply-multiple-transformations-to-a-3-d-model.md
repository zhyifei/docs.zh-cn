---
title: 如何：向三维模型应用多个变换
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- 3-D models [WPF], applying multiple transformations to
ms.assetid: cb72245a-5560-4c96-9f58-593c66296992
ms.openlocfilehash: b5a916583e8ae8769eb52dc6c2c70db9b782d7c8
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54574412"
---
# <a name="how-to-apply-multiple-transformations-to-a-3-d-model"></a><span data-ttu-id="3f3d2-102">如何：向三维模型应用多个变换</span><span class="sxs-lookup"><span data-stu-id="3f3d2-102">How to: Apply Multiple Transformations to a 3-D Model</span></span>
<span data-ttu-id="3f3d2-103">此示例演示如何使用<xref:System.Windows.Media.Media3D.RotateTransform3D>和一个<xref:System.Windows.Media.Media3D.ScaleTransform3D>旋转并更改其小数位数的三维模型。</span><span class="sxs-lookup"><span data-stu-id="3f3d2-103">This sample shows how to use a <xref:System.Windows.Media.Media3D.RotateTransform3D> and a <xref:System.Windows.Media.Media3D.ScaleTransform3D> to rotate and change the scale of a 3-D model.</span></span> <span data-ttu-id="3f3d2-104">下面的代码演示如何将应用到这些转换<xref:System.Windows.Media.Media3D.Model3D.Transform%2A>属性的<xref:System.Windows.Media.Media3D.GeometryModel3D>在 XAML 中。</span><span class="sxs-lookup"><span data-stu-id="3f3d2-104">The code below shows how to apply these transforms to the <xref:System.Windows.Media.Media3D.Model3D.Transform%2A> property of a <xref:System.Windows.Media.Media3D.GeometryModel3D> in XAML.</span></span>  
  
 [!code-xaml[3DGallery_snip#Multiple3DTransformationsExampleInline1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/MultipleTransformationsExample.xaml#multiple3dtransformationsexampleinline1)]  
  
 <span data-ttu-id="3f3d2-105">在代码中：</span><span class="sxs-lookup"><span data-stu-id="3f3d2-105">In code:</span></span>  
  
 [!code-csharp[3DGallery_procedural_snip#Multiple3DTransformationsCodeExampleInline1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_procedural_snip/CSharp/MultipleTransformationsExample.cs#multiple3dtransformationscodeexampleinline1)]
 [!code-vb[3DGallery_procedural_snip#Multiple3DTransformationsCodeExampleInline1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/3DGallery_procedural_snip/visualbasic/multipletransformationsexample.vb#multiple3dtransformationscodeexampleinline1)]  
  
## <a name="example"></a><span data-ttu-id="3f3d2-106">示例</span><span class="sxs-lookup"><span data-stu-id="3f3d2-106">Example</span></span>  
 <span data-ttu-id="3f3d2-107">下面的代码演示在 XAML 中的整个示例。</span><span class="sxs-lookup"><span data-stu-id="3f3d2-107">The following code shows the entire sample in XAML.</span></span>  
  
 [!code-xaml[3DGallery_snip#Multiple3DTransformationsExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/MultipleTransformationsExample.xaml#multiple3dtransformationsexamplewholepage)]  
  
## <a name="example"></a><span data-ttu-id="3f3d2-108">示例</span><span class="sxs-lookup"><span data-stu-id="3f3d2-108">Example</span></span>  
 <span data-ttu-id="3f3d2-109">下面是在代码中的完整示例。</span><span class="sxs-lookup"><span data-stu-id="3f3d2-109">Below is the entire sample in code.</span></span>  
  
 [!code-csharp[3DGallery_procedural_snip#Multiple3DTransformationsCodeExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_procedural_snip/CSharp/MultipleTransformationsExample.cs#multiple3dtransformationscodeexamplewholepage)]
 [!code-vb[3DGallery_procedural_snip#Multiple3DTransformationsCodeExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/3DGallery_procedural_snip/visualbasic/multipletransformationsexample.vb#multiple3dtransformationscodeexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="3f3d2-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="3f3d2-110">See also</span></span>
- [<span data-ttu-id="3f3d2-111">转换 3D 模型的比例</span><span class="sxs-lookup"><span data-stu-id="3f3d2-111">Transform the Scale of a 3-D Model</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-transform-the-scale-of-a-3-d-model.md)
