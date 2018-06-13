---
title: 如何：对三维平移进行动画处理
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], 3-D translations
- 3-D translations [WPF], animating
ms.assetid: d4eece1f-0cd2-4a2c-8370-293354c380e4
ms.openlocfilehash: b9307e1c9ca13b465acd76091f364c538416a5b3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33556765"
---
# <a name="how-to-animate-3-d-translations"></a><span data-ttu-id="25f6d-102">如何：对三维平移进行动画处理</span><span class="sxs-lookup"><span data-stu-id="25f6d-102">How to: Animate 3-D Translations</span></span>
<span data-ttu-id="25f6d-103">本主题演示如何进行动画处理上设置的转换转换[!INCLUDE[TLA#tla_3d](../../../../includes/tlasharptla-3d-md.md)]模型。</span><span class="sxs-lookup"><span data-stu-id="25f6d-103">This topic demonstrates how to animate a translation transformation set on a [!INCLUDE[TLA#tla_3d](../../../../includes/tlasharptla-3d-md.md)] model.</span></span>  
  
 <span data-ttu-id="25f6d-104">下面的代码演示的应用程序<xref:System.Windows.Media.Media3D.TranslateTransform3D>对象传递给<xref:System.Windows.Media.Media3D.Model3D.Transform%2A>属性<xref:System.Windows.Media.Media3D.GeometryModel3D>。</span><span class="sxs-lookup"><span data-stu-id="25f6d-104">The code below shows the application of a <xref:System.Windows.Media.Media3D.TranslateTransform3D> object to the <xref:System.Windows.Media.Media3D.Model3D.Transform%2A> property of a <xref:System.Windows.Media.Media3D.GeometryModel3D>.</span></span>  
  
 [!code-xaml[Animation3DGallery_snip#Translation3DAnimationInline1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/Translation3DAnimationExample.xaml#translation3danimationinline1)]  
  
 <span data-ttu-id="25f6d-105"><xref:System.Windows.Media.Media3D.TranslateTransform3D.OffsetX%2A>此属性<xref:System.Windows.Media.Media3D.TranslateTransform3D>对象进行动画处理，使用下面的代码。</span><span class="sxs-lookup"><span data-stu-id="25f6d-105">The <xref:System.Windows.Media.Media3D.TranslateTransform3D.OffsetX%2A> property of this <xref:System.Windows.Media.Media3D.TranslateTransform3D> object is animated using the code below.</span></span>  
  
 [!code-xaml[Animation3DGallery_snip#Translation3DAnimationInline2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/Translation3DAnimationExample.xaml#translation3danimationinline2)]  
  
## <a name="example"></a><span data-ttu-id="25f6d-106">示例</span><span class="sxs-lookup"><span data-stu-id="25f6d-106">Example</span></span>  
 <span data-ttu-id="25f6d-107">下面的代码演示了整个示例。</span><span class="sxs-lookup"><span data-stu-id="25f6d-107">The following code shows the entire sample.</span></span>  
  
 [!code-xaml[Animation3DGallery_snip#Translation3DAnimationExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/Translation3DAnimationExample.xaml#translation3danimationexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="25f6d-108">请参阅</span><span class="sxs-lookup"><span data-stu-id="25f6d-108">See Also</span></span>  
 [<span data-ttu-id="25f6d-109">动画概述</span><span class="sxs-lookup"><span data-stu-id="25f6d-109">Animation Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [<span data-ttu-id="25f6d-110">创建 3D 场景</span><span class="sxs-lookup"><span data-stu-id="25f6d-110">Create a 3-D Scene</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-3-d-scene.md)  
 [<span data-ttu-id="25f6d-111">3D 图形概述</span><span class="sxs-lookup"><span data-stu-id="25f6d-111">3-D Graphics Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/3-d-graphics-overview.md)  
 [<span data-ttu-id="25f6d-112">转换概述</span><span class="sxs-lookup"><span data-stu-id="25f6d-112">Transforms Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/transforms-overview.md)
