---
title: 如何：对三维转换进行动画处理
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], 3-D translations
- 3-D translations [WPF], animating
ms.assetid: d4eece1f-0cd2-4a2c-8370-293354c380e4
ms.openlocfilehash: 6d7e0b422d6e76d5d0e25ad276550613f264e9bc
ms.sourcegitcommit: d6e27023aeaffc4b5a3cb4b88685018d6284ada4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/09/2019
ms.locfileid: "67661191"
---
# <a name="how-to-animate-3-d-translations"></a><span data-ttu-id="2b4e1-102">如何：对三维转换进行动画处理</span><span class="sxs-lookup"><span data-stu-id="2b4e1-102">How to: Animate 3-D Translations</span></span>
<span data-ttu-id="2b4e1-103">本主题演示如何进行动画处理三维模型上设置的平移转换。</span><span class="sxs-lookup"><span data-stu-id="2b4e1-103">This topic demonstrates how to animate a translation transformation set on a 3-D model.</span></span>  
  
 <span data-ttu-id="2b4e1-104">下面的代码显示的应用程序<xref:System.Windows.Media.Media3D.TranslateTransform3D>对象传递给<xref:System.Windows.Media.Media3D.Model3D.Transform%2A>属性的<xref:System.Windows.Media.Media3D.GeometryModel3D>。</span><span class="sxs-lookup"><span data-stu-id="2b4e1-104">The code below shows the application of a <xref:System.Windows.Media.Media3D.TranslateTransform3D> object to the <xref:System.Windows.Media.Media3D.Model3D.Transform%2A> property of a <xref:System.Windows.Media.Media3D.GeometryModel3D>.</span></span>  
  
 [!code-xaml[Animation3DGallery_snip#Translation3DAnimationInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/Translation3DAnimationExample.xaml#translation3danimationinline1)]  
  
 <span data-ttu-id="2b4e1-105"><xref:System.Windows.Media.Media3D.TranslateTransform3D.OffsetX%2A>属性的<xref:System.Windows.Media.Media3D.TranslateTransform3D>对象进行动画处理，使用下面的代码。</span><span class="sxs-lookup"><span data-stu-id="2b4e1-105">The <xref:System.Windows.Media.Media3D.TranslateTransform3D.OffsetX%2A> property of this <xref:System.Windows.Media.Media3D.TranslateTransform3D> object is animated using the code below.</span></span>  
  
 [!code-xaml[Animation3DGallery_snip#Translation3DAnimationInline2](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/Translation3DAnimationExample.xaml#translation3danimationinline2)]  
  
## <a name="example"></a><span data-ttu-id="2b4e1-106">示例</span><span class="sxs-lookup"><span data-stu-id="2b4e1-106">Example</span></span>  
 <span data-ttu-id="2b4e1-107">下面的代码演示了整个示例。</span><span class="sxs-lookup"><span data-stu-id="2b4e1-107">The following code shows the entire sample.</span></span>  
  
 [!code-xaml[Animation3DGallery_snip#Translation3DAnimationExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/Translation3DAnimationExample.xaml#translation3danimationexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="2b4e1-108">请参阅</span><span class="sxs-lookup"><span data-stu-id="2b4e1-108">See also</span></span>

- [<span data-ttu-id="2b4e1-109">动画概述</span><span class="sxs-lookup"><span data-stu-id="2b4e1-109">Animation Overview</span></span>](animation-overview.md)
- [<span data-ttu-id="2b4e1-110">创建 3D 场景</span><span class="sxs-lookup"><span data-stu-id="2b4e1-110">Create a 3-D Scene</span></span>](how-to-create-a-3-d-scene.md)
- [<span data-ttu-id="2b4e1-111">3D 图形概述</span><span class="sxs-lookup"><span data-stu-id="2b4e1-111">3-D Graphics Overview</span></span>](3-d-graphics-overview.md)
- [<span data-ttu-id="2b4e1-112">转换概述</span><span class="sxs-lookup"><span data-stu-id="2b4e1-112">Transforms Overview</span></span>](transforms-overview.md)
