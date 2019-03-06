---
title: 如何：将几何图形用作参数的命中测试
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hit tests [WPF], on visual objects using Geometry objects [WPF]
- visual objects [WPF], hit tests on
- Geometry objects [WPF], hit tests on visual objects [WPF]
ms.assetid: 6c8bdbf2-19e0-4fbb-bf89-c1252b2ebc61
ms.openlocfilehash: 15a33d05cb3ca4fd40f04170bd1756e466631275
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/05/2019
ms.locfileid: "57366356"
---
# <a name="how-to-hit-test-using-geometry-as-a-parameter"></a><span data-ttu-id="78e4e-102">如何：将几何图形用作参数的命中测试</span><span class="sxs-lookup"><span data-stu-id="78e4e-102">How to: Hit Test Using Geometry as a Parameter</span></span>
<span data-ttu-id="78e4e-103">此示例演示如何对视觉对象使用执行命中的测试<xref:System.Windows.Media.Geometry>作为命中测试参数。</span><span class="sxs-lookup"><span data-stu-id="78e4e-103">This example shows how to perform a hit test on a visual object using a <xref:System.Windows.Media.Geometry> as a hit test parameter.</span></span>  
  
## <a name="example"></a><span data-ttu-id="78e4e-104">示例</span><span class="sxs-lookup"><span data-stu-id="78e4e-104">Example</span></span>  
 <span data-ttu-id="78e4e-105">下面的示例演示如何设置命中的测试使用<xref:System.Windows.Media.GeometryHitTestParameters>为<xref:System.Windows.Media.VisualTreeHelper.HitTest%2A>方法。</span><span class="sxs-lookup"><span data-stu-id="78e4e-105">The following example shows how to set up a hit test using <xref:System.Windows.Media.GeometryHitTestParameters> for the <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A> method.</span></span> <span data-ttu-id="78e4e-106"><xref:System.Windows.Point>值传递给`OnMouseDown`方法用于创建<xref:System.Windows.Media.Geometry>对象以扩展命中测试的范围。</span><span class="sxs-lookup"><span data-stu-id="78e4e-106">The <xref:System.Windows.Point> value that is passed to the `OnMouseDown` method is used to create a <xref:System.Windows.Media.Geometry> object in order to expand the range of the hit test.</span></span>  
  
 [!code-csharp[HitTestingOverview#HitTestingOverviewSnippet10](~/samples/snippets/csharp/VS_Snippets_Wpf/HitTestingOverview/CSharp/GeometryHitTest.cs#hittestingoverviewsnippet10)]
 [!code-vb[HitTestingOverview#HitTestingOverviewSnippet10](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HitTestingOverview/visualbasic/geometryhittest.vb#hittestingoverviewsnippet10)]  
  
 <span data-ttu-id="78e4e-107"><xref:System.Windows.Media.GeometryHitTestResult.IntersectionDetail%2A>的属性<xref:System.Windows.Media.GeometryHitTestResult>提供了有关使用的命中测试结果信息<xref:System.Windows.Media.Geometry>作为命中测试参数。</span><span class="sxs-lookup"><span data-stu-id="78e4e-107">The <xref:System.Windows.Media.GeometryHitTestResult.IntersectionDetail%2A> property of <xref:System.Windows.Media.GeometryHitTestResult> provides information about the results of a hit test that uses a <xref:System.Windows.Media.Geometry> as a hit test parameter.</span></span> <span data-ttu-id="78e4e-108">下图演示了命中测试几何图形（蓝色圆圈）与目标视觉对象（红色正方形）的呈现内容之间的关系。</span><span class="sxs-lookup"><span data-stu-id="78e4e-108">The following illustration shows the relationship between the hit test geometry (the blue circle) and the rendered content of the target visual object (the red square).</span></span>  
  
 <span data-ttu-id="78e4e-109">![中使用的 IntersectionDetail 的关系图进行命中测试](./media/intersectiondetail01.png "IntersectionDetail01")</span><span class="sxs-lookup"><span data-stu-id="78e4e-109">![Diagram of IntersectionDetail used in hit testing](./media/intersectiondetail01.png "IntersectionDetail01")</span></span>  
<span data-ttu-id="78e4e-110">命中测试几何图形与目标视觉对象之间的交集</span><span class="sxs-lookup"><span data-stu-id="78e4e-110">Intersection between hit test geometry and target visual object</span></span>  
  
 <span data-ttu-id="78e4e-111">下面的示例演示如何实现命中的测试回叫时<xref:System.Windows.Media.Geometry>用作命中的测试参数。</span><span class="sxs-lookup"><span data-stu-id="78e4e-111">The following example shows how to implement a hit test callback when a <xref:System.Windows.Media.Geometry> is used as a hit test parameter.</span></span> <span data-ttu-id="78e4e-112">`result`参数强制转换为<xref:System.Windows.Media.GeometryHitTestResult>以便检索的值<xref:System.Windows.Media.GeometryHitTestResult.IntersectionDetail%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="78e4e-112">The `result` parameter is cast to a <xref:System.Windows.Media.GeometryHitTestResult> in order to retrieve the value of the <xref:System.Windows.Media.GeometryHitTestResult.IntersectionDetail%2A> property.</span></span> <span data-ttu-id="78e4e-113">属性值可以确定如果<xref:System.Windows.Media.Geometry>命中的测试参数完全或部分包含在命中的测试目标的呈现内容。</span><span class="sxs-lookup"><span data-stu-id="78e4e-113">The property value allows you to determine if the <xref:System.Windows.Media.Geometry> hit test parameter is fully or partially contained within the rendered content of the hit test target.</span></span> <span data-ttu-id="78e4e-114">在本示例中，示例代码仅将命中测试结果添加到完全包含在目标边界中的视觉对象的列表中。</span><span class="sxs-lookup"><span data-stu-id="78e4e-114">In this case, the sample code is only adding hit test results to the list for visuals that are fully contained within the target boundary.</span></span>  
  
 [!code-csharp[HitTestingOverview#HitTestingOverviewSnippet11](~/samples/snippets/csharp/VS_Snippets_Wpf/HitTestingOverview/CSharp/GeometryHitTest.cs#hittestingoverviewsnippet11)]
 [!code-vb[HitTestingOverview#HitTestingOverviewSnippet11](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HitTestingOverview/visualbasic/geometryhittest.vb#hittestingoverviewsnippet11)]  
  
> [!NOTE]
>  <span data-ttu-id="78e4e-115"><xref:System.Windows.Media.HitTestResult>交集详细信息时，不应调用回调<xref:System.Windows.Media.IntersectionDetail.Empty>。</span><span class="sxs-lookup"><span data-stu-id="78e4e-115">The <xref:System.Windows.Media.HitTestResult> callback should not be called when the intersection detail is <xref:System.Windows.Media.IntersectionDetail.Empty>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="78e4e-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="78e4e-116">See also</span></span>
- [<span data-ttu-id="78e4e-117">可视化层中的命中测试</span><span class="sxs-lookup"><span data-stu-id="78e4e-117">Hit Testing in the Visual Layer</span></span>](hit-testing-in-the-visual-layer.md)
- [<span data-ttu-id="78e4e-118">对视觉对象中的几何图形进行命中测试</span><span class="sxs-lookup"><span data-stu-id="78e4e-118">Hit Test Geometry in a Visual</span></span>](how-to-hit-test-geometry-in-a-visual.md)
