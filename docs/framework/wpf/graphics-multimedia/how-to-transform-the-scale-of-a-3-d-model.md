---
title: 如何：转换三维模型的比例
ms.date: 03/30/2017
helpviewer_keywords:
- scaling [WPF], 3-D objects
- 3-D objects [WPF], scaling
ms.assetid: f3fdfe33-f7dc-44b0-84a5-e43b89947f35
ms.openlocfilehash: 6d668de08201d819ce9f8752bedf6c388a6bc718
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59165075"
---
# <a name="how-to-transform-the-scale-of-a-3-d-model"></a><span data-ttu-id="8f1ea-102">如何：转换三维模型的比例</span><span class="sxs-lookup"><span data-stu-id="8f1ea-102">How to: Transform the Scale of a 3-D Model</span></span>
<span data-ttu-id="8f1ea-103">此示例演示如何缩放三维对象。</span><span class="sxs-lookup"><span data-stu-id="8f1ea-103">This example shows how to scale a 3-D object.</span></span> <span data-ttu-id="8f1ea-104">若要缩放三维对象，使用<xref:System.Windows.Media.Media3D.ScaleTransform3D>。</span><span class="sxs-lookup"><span data-stu-id="8f1ea-104">To scale a 3-D object, use a <xref:System.Windows.Media.Media3D.ScaleTransform3D>.</span></span> <span data-ttu-id="8f1ea-105"><xref:System.Windows.Media.Media3D.ScaleTransform3D.ScaleX%2A>， <xref:System.Windows.Media.Media3D.ScaleTransform3D.ScaleY%2A>，和<xref:System.Windows.Media.Media3D.ScaleTransform3D.ScaleZ%2A>属性调整元素大小由指定的系数。</span><span class="sxs-lookup"><span data-stu-id="8f1ea-105">The <xref:System.Windows.Media.Media3D.ScaleTransform3D.ScaleX%2A>, <xref:System.Windows.Media.Media3D.ScaleTransform3D.ScaleY%2A>, and <xref:System.Windows.Media.Media3D.ScaleTransform3D.ScaleZ%2A> properties resize the element by the factor you specify.</span></span> <span data-ttu-id="8f1ea-106">例如，<xref:System.Windows.Media.Media3D.ScaleTransform3D.ScaleX%2A>值为 1.5 会拉伸到其原始宽度的 150%的对象。</span><span class="sxs-lookup"><span data-stu-id="8f1ea-106">For example, a <xref:System.Windows.Media.Media3D.ScaleTransform3D.ScaleX%2A> value of 1.5 stretches an object to 150 percent of its original width.</span></span> <span data-ttu-id="8f1ea-107">一个<xref:System.Windows.Media.Media3D.ScaleTransform3D.ScaleY%2A>值为 0.5 会对象的高度缩小 50%。</span><span class="sxs-lookup"><span data-stu-id="8f1ea-107">A <xref:System.Windows.Media.Media3D.ScaleTransform3D.ScaleY%2A> value of 0.5 shrinks the height of an object by 50 percent.</span></span> <span data-ttu-id="8f1ea-108">下面的代码显示使用<xref:System.Windows.Media.Media3D.ScaleTransform3D>的转换为<xref:System.Windows.Media.Media3D.GeometryModel3D>。</span><span class="sxs-lookup"><span data-stu-id="8f1ea-108">The code below shows using a <xref:System.Windows.Media.Media3D.ScaleTransform3D> as the transform for a <xref:System.Windows.Media.Media3D.GeometryModel3D>.</span></span>  
  
 [!code-xaml[3DGallery_snip#ScaleTransform3DExampleInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/ScaleTransform3DExample.xaml#scaletransform3dexampleinline1)]  
  
## <a name="example"></a><span data-ttu-id="8f1ea-109">示例</span><span class="sxs-lookup"><span data-stu-id="8f1ea-109">Example</span></span>  
 <span data-ttu-id="8f1ea-110">下面的代码演示了整个示例。</span><span class="sxs-lookup"><span data-stu-id="8f1ea-110">The following code shows the entire sample.</span></span>  
  
 [!code-xaml[3DGallery_snip#ScaleTransform3DExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/ScaleTransform3DExample.xaml#scaletransform3dexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="8f1ea-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="8f1ea-111">See also</span></span>

- [<span data-ttu-id="8f1ea-112">对三维转换进行动画处理</span><span class="sxs-lookup"><span data-stu-id="8f1ea-112">Animate 3-D Translations</span></span>](how-to-animate-3-d-translations.md)
- [<span data-ttu-id="8f1ea-113">创建三维场景</span><span class="sxs-lookup"><span data-stu-id="8f1ea-113">Create a 3-D Scene</span></span>](how-to-create-a-3-d-scene.md)
- [<span data-ttu-id="8f1ea-114">三维图形概述</span><span class="sxs-lookup"><span data-stu-id="8f1ea-114">3-D Graphics Overview</span></span>](3-d-graphics-overview.md)
