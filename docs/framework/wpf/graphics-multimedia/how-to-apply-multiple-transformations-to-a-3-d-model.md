---
title: 如何：将多个转换应用于 3D 模型
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- 3D models [WPF], applying multiple transformations to
ms.assetid: cb72245a-5560-4c96-9f58-593c66296992
ms.openlocfilehash: 6400d224fb51b93c76c5e9798b4bcc68ff3b9de6
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/21/2020
ms.locfileid: "80112123"
---
# <a name="how-to-apply-multiple-transformations-to-a-3d-model"></a><span data-ttu-id="eff85-102">如何：将多个转换应用于 3D 模型</span><span class="sxs-lookup"><span data-stu-id="eff85-102">How to: Apply Multiple Transformations to a 3D Model</span></span>
<span data-ttu-id="eff85-103">此示例演示如何使用<xref:System.Windows.Media.Media3D.RotateTransform3D>和 a<xref:System.Windows.Media.Media3D.ScaleTransform3D>旋转和更改 3D 模型的比例。</span><span class="sxs-lookup"><span data-stu-id="eff85-103">This sample shows how to use a <xref:System.Windows.Media.Media3D.RotateTransform3D> and a <xref:System.Windows.Media.Media3D.ScaleTransform3D> to rotate and change the scale of a 3D model.</span></span> <span data-ttu-id="eff85-104">下面的代码演示如何将这些转换应用于<xref:System.Windows.Media.Media3D.Model3D.Transform%2A>XAML 中 的属性。 <xref:System.Windows.Media.Media3D.GeometryModel3D></span><span class="sxs-lookup"><span data-stu-id="eff85-104">The code below shows how to apply these transforms to the <xref:System.Windows.Media.Media3D.Model3D.Transform%2A> property of a <xref:System.Windows.Media.Media3D.GeometryModel3D> in XAML.</span></span>  
  
 [!code-xaml[3DGallery_snip#Multiple3DTransformationsExampleInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/MultipleTransformationsExample.xaml#multiple3dtransformationsexampleinline1)]  
  
 <span data-ttu-id="eff85-105">在代码中：</span><span class="sxs-lookup"><span data-stu-id="eff85-105">In code:</span></span>  
  
 [!code-csharp[3DGallery_procedural_snip#Multiple3DTransformationsCodeExampleInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_procedural_snip/CSharp/MultipleTransformationsExample.cs#multiple3dtransformationscodeexampleinline1)]
 [!code-vb[3DGallery_procedural_snip#Multiple3DTransformationsCodeExampleInline1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/3DGallery_procedural_snip/visualbasic/multipletransformationsexample.vb#multiple3dtransformationscodeexampleinline1)]  
  
## <a name="example"></a><span data-ttu-id="eff85-106">示例</span><span class="sxs-lookup"><span data-stu-id="eff85-106">Example</span></span>  
 <span data-ttu-id="eff85-107">以下代码在 XAML 中显示整个示例。</span><span class="sxs-lookup"><span data-stu-id="eff85-107">The following code shows the entire sample in XAML.</span></span>  
  
 [!code-xaml[3DGallery_snip#Multiple3DTransformationsExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/MultipleTransformationsExample.xaml#multiple3dtransformationsexamplewholepage)]  
  
## <a name="example"></a><span data-ttu-id="eff85-108">示例</span><span class="sxs-lookup"><span data-stu-id="eff85-108">Example</span></span>  
 <span data-ttu-id="eff85-109">下面是代码中的全部示例。</span><span class="sxs-lookup"><span data-stu-id="eff85-109">Below is the entire sample in code.</span></span>  
  
 [!code-csharp[3DGallery_procedural_snip#Multiple3DTransformationsCodeExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_procedural_snip/CSharp/MultipleTransformationsExample.cs#multiple3dtransformationscodeexamplewholepage)]
 [!code-vb[3DGallery_procedural_snip#Multiple3DTransformationsCodeExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/3DGallery_procedural_snip/visualbasic/multipletransformationsexample.vb#multiple3dtransformationscodeexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="eff85-110">另请参阅</span><span class="sxs-lookup"><span data-stu-id="eff85-110">See also</span></span>

- [<span data-ttu-id="eff85-111">变换 3D 模型的比例</span><span class="sxs-lookup"><span data-stu-id="eff85-111">Transform the Scale of a 3D Model</span></span>](how-to-transform-the-scale-of-a-3-d-model.md)
