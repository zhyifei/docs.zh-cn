---
title: 如何：向三维对象应用放射材质
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- EmissiveMaterial [WPF], applying to 3-D objects
- 3-D objects [WPF], applying EmissiveMaterial
ms.assetid: fd442cc2-5adc-487a-ba70-e45ed54bb3b4
ms.openlocfilehash: 90a4903310ff7a8778296866f39f685aefee3ffb
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54645036"
---
# <a name="how-to-apply-emissive-material-to-a-3-d-object"></a><span data-ttu-id="c737c-102">如何：向三维对象应用放射材质</span><span class="sxs-lookup"><span data-stu-id="c737c-102">How to: Apply Emissive Material to a 3-D Object</span></span>
<span data-ttu-id="c737c-103">下面的示例演示如何使用<xref:System.Windows.Media.Media3D.EmissiveMaterial>将颜色添加到现有材料等于 EmissiveMaterial 的画笔的颜色。</span><span class="sxs-lookup"><span data-stu-id="c737c-103">The following example shows how to use <xref:System.Windows.Media.Media3D.EmissiveMaterial> to add color to an existing Material equal to the color of the EmissiveMaterial's brush.</span></span> <span data-ttu-id="c737c-104">下面的代码显示<xref:System.Windows.Media.Media3D.DiffuseMaterial>和<xref:System.Windows.Media.Media3D.EmissiveMaterial>应用中进行组合，以将蓝色添加到 DiffuseMaterial 的外观。</span><span class="sxs-lookup"><span data-stu-id="c737c-104">The code below shows <xref:System.Windows.Media.Media3D.DiffuseMaterial> and <xref:System.Windows.Media.Media3D.EmissiveMaterial> applied in combination to add blue to the DiffuseMaterial's appearance.</span></span>  
  
 [!code-xaml[3DGallery_snip#EmmisiveMaterialAnimationExampleInline1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/EmissiveMaterialExample.xaml#emmisivematerialanimationexampleinline1)]  
  
 <span data-ttu-id="c737c-105">在程序代码中：</span><span class="sxs-lookup"><span data-stu-id="c737c-105">In procedural code:</span></span>  
  
 [!code-csharp[3DGallery_procedural_snip#EmissiveMaterialCodeExampleInline1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_procedural_snip/CSharp/EmissiveMaterialExample.cs#emissivematerialcodeexampleinline1)]
 [!code-vb[3DGallery_procedural_snip#EmissiveMaterialCodeExampleInline1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/3DGallery_procedural_snip/visualbasic/emissivematerialexample.vb#emissivematerialcodeexampleinline1)]  
  
## <a name="example"></a><span data-ttu-id="c737c-106">示例</span><span class="sxs-lookup"><span data-stu-id="c737c-106">Example</span></span>  
 <span data-ttu-id="c737c-107">下面的代码演示在 XAML 中的整个示例。</span><span class="sxs-lookup"><span data-stu-id="c737c-107">The following code shows the entire sample in XAML.</span></span>  
  
 [!code-xaml[3DGallery_snip#EmissiveMaterialExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/EmissiveMaterialExample.xaml#emissivematerialexamplewholepage)]  
  
## <a name="example"></a><span data-ttu-id="c737c-108">示例</span><span class="sxs-lookup"><span data-stu-id="c737c-108">Example</span></span>  
 <span data-ttu-id="c737c-109">下面是在程序代码中的整个示例。</span><span class="sxs-lookup"><span data-stu-id="c737c-109">Below is the entire sample in procedural code.</span></span>  
  
 [!code-csharp[3DGallery_procedural_snip#EmissiveMaterialCodeExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_procedural_snip/CSharp/EmissiveMaterialExample.cs#emissivematerialcodeexamplewholepage)]
 [!code-vb[3DGallery_procedural_snip#EmissiveMaterialCodeExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/3DGallery_procedural_snip/visualbasic/emissivematerialexample.vb#emissivematerialcodeexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="c737c-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="c737c-110">See also</span></span>
- [<span data-ttu-id="c737c-111">创建 3D 场景</span><span class="sxs-lookup"><span data-stu-id="c737c-111">Create a 3-D Scene</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-3-d-scene.md)
- [<span data-ttu-id="c737c-112">3D 图形概述</span><span class="sxs-lookup"><span data-stu-id="c737c-112">3-D Graphics Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/3-d-graphics-overview.md)
- [<span data-ttu-id="c737c-113">在 3D 场景中为材料属性设置动画效果</span><span class="sxs-lookup"><span data-stu-id="c737c-113">Animate Material Properties in a 3-D Scene</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-material-properties-in-a-3-d-scene.md)
- [<span data-ttu-id="c737c-114">向 3D 对象的正面和背面应用材料</span><span class="sxs-lookup"><span data-stu-id="c737c-114">Apply Material to the Front and Back of a 3-D Object</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-apply-material-to-the-front-and-back-of-a-3-d-object.md)
