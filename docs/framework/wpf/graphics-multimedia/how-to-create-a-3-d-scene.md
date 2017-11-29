---
title: "如何：创建三维场景"
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
- scenes [WPF], 3-D
- 3-D scenes
ms.assetid: adb4a598-71a2-4dd5-b677-ea3fc11b78b2
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: dd84a95bf793b3da9970b605b2f02509e3938ab0
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-create-a-3-d-scene"></a><span data-ttu-id="6fd1e-102">如何：创建三维场景</span><span class="sxs-lookup"><span data-stu-id="6fd1e-102">How to: Create a 3-D Scene</span></span>
<span data-ttu-id="6fd1e-103">此示例演示如何创建看起来像平面纸已转动的一个三维对象。</span><span class="sxs-lookup"><span data-stu-id="6fd1e-103">This example shows how to create a 3-D object that looks like a flat sheet of paper which has been rotated.</span></span> <span data-ttu-id="6fd1e-104">A<xref:System.Windows.Controls.Viewport3D>以下组件以及用于创建此简单的三维场景：</span><span class="sxs-lookup"><span data-stu-id="6fd1e-104">A <xref:System.Windows.Controls.Viewport3D> along with the following components are used to create this simple 3-D scene:</span></span>  
  
-   <span data-ttu-id="6fd1e-105">使用创建相机<xref:System.Windows.Media.Media3D.PerspectiveCamera>。</span><span class="sxs-lookup"><span data-stu-id="6fd1e-105">A camera is created using a <xref:System.Windows.Media.Media3D.PerspectiveCamera>.</span></span> <span data-ttu-id="6fd1e-106">照相机指定三维场景的哪个部分可查看。</span><span class="sxs-lookup"><span data-stu-id="6fd1e-106">The camera specifies what part of the 3-D scene is viewable.</span></span>  
  
-   <span data-ttu-id="6fd1e-107">创建一个网格，以指定的三维对象 （张纸） 使用形状<xref:System.Windows.Media.Media3D.GeometryModel3D.Geometry%2A>属性<xref:System.Windows.Media.Media3D.GeometryModel3D>。</span><span class="sxs-lookup"><span data-stu-id="6fd1e-107">A mesh is created to specify the shape of 3-D object (sheet of paper) using the <xref:System.Windows.Media.Media3D.GeometryModel3D.Geometry%2A> property of <xref:System.Windows.Media.Media3D.GeometryModel3D>.</span></span>  
  
-   <span data-ttu-id="6fd1e-108">材料指定要显示在对象 （线性渐变在此示例中） 使用的图面上<xref:System.Windows.Media.Media3D.GeometryModel3D.Material%2A>属性<xref:System.Windows.Media.Media3D.GeometryModel3D>。</span><span class="sxs-lookup"><span data-stu-id="6fd1e-108">A material is specified to be displayed on the surface of the object (linear gradient in this sample) using the <xref:System.Windows.Media.Media3D.GeometryModel3D.Material%2A> property of <xref:System.Windows.Media.Media3D.GeometryModel3D>.</span></span>  
  
-   <span data-ttu-id="6fd1e-109">Light 创建对象使用表现<xref:System.Windows.Media.Media3D.DirectionalLight>。</span><span class="sxs-lookup"><span data-stu-id="6fd1e-109">A light is created to shine on the object using <xref:System.Windows.Media.Media3D.DirectionalLight>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6fd1e-110">示例</span><span class="sxs-lookup"><span data-stu-id="6fd1e-110">Example</span></span>  
 <span data-ttu-id="6fd1e-111">下面的代码演示如何在 XAML 中创建三维场景。</span><span class="sxs-lookup"><span data-stu-id="6fd1e-111">The code below shows how to create a 3-D scene in XAML.</span></span>  
  
 [!code-xaml[3DGallery_snip#Basic3DShapeExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/Basic3DShapeExample.xaml#basic3dshapeexamplewholepage)]  
  
## <a name="example"></a><span data-ttu-id="6fd1e-112">示例</span><span class="sxs-lookup"><span data-stu-id="6fd1e-112">Example</span></span>  
 <span data-ttu-id="6fd1e-113">下面的代码演示如何在程序代码中创建相同的三维场景。</span><span class="sxs-lookup"><span data-stu-id="6fd1e-113">The code below shows how to create the same 3-D scene in procedural code.</span></span>  
  
 [!code-csharp[3DGallery_procedural_snip#Basic3DShapeCodeExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_procedural_snip/CSharp/Basic3DShapeExample.cs#basic3dshapecodeexamplewholepage)]
 [!code-vb[3DGallery_procedural_snip#Basic3DShapeCodeExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/3DGallery_procedural_snip/visualbasic/basic3dshapeexample.vb#basic3dshapecodeexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="6fd1e-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6fd1e-114">See Also</span></span>  
 [<span data-ttu-id="6fd1e-115">3D 图形概述</span><span class="sxs-lookup"><span data-stu-id="6fd1e-115">3-D Graphics Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/3-d-graphics-overview.md)
