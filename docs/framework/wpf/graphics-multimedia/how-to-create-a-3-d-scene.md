---
title: 如何：创建三维场景
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- scenes [WPF], 3-D
- 3-D scenes
ms.assetid: adb4a598-71a2-4dd5-b677-ea3fc11b78b2
ms.openlocfilehash: 8c9aec78bdda4f9f122b6dbefe0956ba649adf22
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/05/2019
ms.locfileid: "57370743"
---
# <a name="how-to-create-a-3-d-scene"></a><span data-ttu-id="22eae-102">如何：创建三维场景</span><span class="sxs-lookup"><span data-stu-id="22eae-102">How to: Create a 3-D Scene</span></span>
<span data-ttu-id="22eae-103">此示例演示如何创建三维对象，如下所示已旋转的纸张的平面表。</span><span class="sxs-lookup"><span data-stu-id="22eae-103">This example shows how to create a 3-D object that looks like a flat sheet of paper which has been rotated.</span></span> <span data-ttu-id="22eae-104">一个<xref:System.Windows.Controls.Viewport3D>以及以下组件用于创建此简单的三维场景：</span><span class="sxs-lookup"><span data-stu-id="22eae-104">A <xref:System.Windows.Controls.Viewport3D> along with the following components are used to create this simple 3-D scene:</span></span>  
  
-   <span data-ttu-id="22eae-105">使用创建照相机<xref:System.Windows.Media.Media3D.PerspectiveCamera>。</span><span class="sxs-lookup"><span data-stu-id="22eae-105">A camera is created using a <xref:System.Windows.Media.Media3D.PerspectiveCamera>.</span></span> <span data-ttu-id="22eae-106">照相机指定可查看三维场景的哪个部分。</span><span class="sxs-lookup"><span data-stu-id="22eae-106">The camera specifies what part of the 3-D scene is viewable.</span></span>  
  
-   <span data-ttu-id="22eae-107">创建一个网格，以指定的三维对象 （张纸的） 使用形状<xref:System.Windows.Media.Media3D.GeometryModel3D.Geometry%2A>属性的<xref:System.Windows.Media.Media3D.GeometryModel3D>。</span><span class="sxs-lookup"><span data-stu-id="22eae-107">A mesh is created to specify the shape of 3-D object (sheet of paper) using the <xref:System.Windows.Media.Media3D.GeometryModel3D.Geometry%2A> property of <xref:System.Windows.Media.Media3D.GeometryModel3D>.</span></span>  
  
-   <span data-ttu-id="22eae-108">材料指定要在对象 （线性渐变在此示例中） 使用的图面上显示<xref:System.Windows.Media.Media3D.GeometryModel3D.Material%2A>属性的<xref:System.Windows.Media.Media3D.GeometryModel3D>。</span><span class="sxs-lookup"><span data-stu-id="22eae-108">A material is specified to be displayed on the surface of the object (linear gradient in this sample) using the <xref:System.Windows.Media.Media3D.GeometryModel3D.Material%2A> property of <xref:System.Windows.Media.Media3D.GeometryModel3D>.</span></span>  
  
-   <span data-ttu-id="22eae-109">创建光照射对象使用<xref:System.Windows.Media.Media3D.DirectionalLight>。</span><span class="sxs-lookup"><span data-stu-id="22eae-109">A light is created to shine on the object using <xref:System.Windows.Media.Media3D.DirectionalLight>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="22eae-110">示例</span><span class="sxs-lookup"><span data-stu-id="22eae-110">Example</span></span>  
 <span data-ttu-id="22eae-111">下面的代码演示如何在 XAML 中创建三维场景。</span><span class="sxs-lookup"><span data-stu-id="22eae-111">The code below shows how to create a 3-D scene in XAML.</span></span>  
  
 [!code-xaml[3DGallery_snip#Basic3DShapeExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/Basic3DShapeExample.xaml#basic3dshapeexamplewholepage)]  
  
## <a name="example"></a><span data-ttu-id="22eae-112">示例</span><span class="sxs-lookup"><span data-stu-id="22eae-112">Example</span></span>  
 <span data-ttu-id="22eae-113">下面的代码演示如何在程序代码中创建相同的三维场景。</span><span class="sxs-lookup"><span data-stu-id="22eae-113">The code below shows how to create the same 3-D scene in procedural code.</span></span>  
  
 [!code-csharp[3DGallery_procedural_snip#Basic3DShapeCodeExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_procedural_snip/CSharp/Basic3DShapeExample.cs#basic3dshapecodeexamplewholepage)]
 [!code-vb[3DGallery_procedural_snip#Basic3DShapeCodeExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/3DGallery_procedural_snip/visualbasic/basic3dshapeexample.vb#basic3dshapecodeexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="22eae-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="22eae-114">See also</span></span>
- [<span data-ttu-id="22eae-115">3D 图形概述</span><span class="sxs-lookup"><span data-stu-id="22eae-115">3-D Graphics Overview</span></span>](3-d-graphics-overview.md)
