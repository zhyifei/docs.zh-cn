---
title: "如何：变换三维模型的比例"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- scaling [WPF], 3-D objects
- 3-D objects [WPF], scaling
ms.assetid: f3fdfe33-f7dc-44b0-84a5-e43b89947f35
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: d94086f38169ee31cbee29e034359d573462ffca
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-transform-the-scale-of-a-3-d-model"></a><span data-ttu-id="6fae8-102">如何：变换三维模型的比例</span><span class="sxs-lookup"><span data-stu-id="6fae8-102">How to: Transform the Scale of a 3-D Model</span></span>
<span data-ttu-id="6fae8-103">此示例演示如何缩放三维对象。</span><span class="sxs-lookup"><span data-stu-id="6fae8-103">This example shows how to scale a 3-D object.</span></span> <span data-ttu-id="6fae8-104">若要缩放三维对象，请使用<xref:System.Windows.Media.Media3D.ScaleTransform3D>。</span><span class="sxs-lookup"><span data-stu-id="6fae8-104">To scale a 3-D object, use a <xref:System.Windows.Media.Media3D.ScaleTransform3D>.</span></span> <span data-ttu-id="6fae8-105"><xref:System.Windows.Media.Media3D.ScaleTransform3D.ScaleX%2A>， <xref:System.Windows.Media.Media3D.ScaleTransform3D.ScaleY%2A>，和<xref:System.Windows.Media.Media3D.ScaleTransform3D.ScaleZ%2A>属性调整元素大小按指定的因子。</span><span class="sxs-lookup"><span data-stu-id="6fae8-105">The <xref:System.Windows.Media.Media3D.ScaleTransform3D.ScaleX%2A>, <xref:System.Windows.Media.Media3D.ScaleTransform3D.ScaleY%2A>, and <xref:System.Windows.Media.Media3D.ScaleTransform3D.ScaleZ%2A> properties resize the element by the factor you specify.</span></span> <span data-ttu-id="6fae8-106">例如，<xref:System.Windows.Media.Media3D.ScaleTransform3D.ScaleX%2A>值为 1.5 拉伸到其原始宽度的 150%的对象。</span><span class="sxs-lookup"><span data-stu-id="6fae8-106">For example, a <xref:System.Windows.Media.Media3D.ScaleTransform3D.ScaleX%2A> value of 1.5 stretches an object to 150 percent of its original width.</span></span> <span data-ttu-id="6fae8-107">A<xref:System.Windows.Media.Media3D.ScaleTransform3D.ScaleY%2A>值为 0.5 时，会对象的高度缩小 50%。</span><span class="sxs-lookup"><span data-stu-id="6fae8-107">A <xref:System.Windows.Media.Media3D.ScaleTransform3D.ScaleY%2A> value of 0.5 shrinks the height of an object by 50 percent.</span></span> <span data-ttu-id="6fae8-108">下面的代码演示使用<xref:System.Windows.Media.Media3D.ScaleTransform3D>的转换为<xref:System.Windows.Media.Media3D.GeometryModel3D>。</span><span class="sxs-lookup"><span data-stu-id="6fae8-108">The code below shows using a <xref:System.Windows.Media.Media3D.ScaleTransform3D> as the transform for a <xref:System.Windows.Media.Media3D.GeometryModel3D>.</span></span>  
  
 [!code-xaml[3DGallery_snip#ScaleTransform3DExampleInline1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/ScaleTransform3DExample.xaml#scaletransform3dexampleinline1)]  
  
## <a name="example"></a><span data-ttu-id="6fae8-109">示例</span><span class="sxs-lookup"><span data-stu-id="6fae8-109">Example</span></span>  
 <span data-ttu-id="6fae8-110">下面的代码演示了整个示例。</span><span class="sxs-lookup"><span data-stu-id="6fae8-110">The following code shows the entire sample.</span></span>  
  
 [!code-xaml[3DGallery_snip#ScaleTransform3DExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/ScaleTransform3DExample.xaml#scaletransform3dexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="6fae8-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6fae8-111">See Also</span></span>  
 [<span data-ttu-id="6fae8-112">为 3D 转换设置动画效果</span><span class="sxs-lookup"><span data-stu-id="6fae8-112">Animate 3-D Translations</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-3-d-translations.md)  
 [<span data-ttu-id="6fae8-113">创建 3D 场景</span><span class="sxs-lookup"><span data-stu-id="6fae8-113">Create a 3-D Scene</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-3-d-scene.md)  
 [<span data-ttu-id="6fae8-114">3D 图形概述</span><span class="sxs-lookup"><span data-stu-id="6fae8-114">3-D Graphics Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/3-d-graphics-overview.md)
