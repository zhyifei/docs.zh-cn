---
title: 如何：向绘图应用 GuidelineSet
ms.date: 03/30/2017
helpviewer_keywords:
- GuidelineSet property [WPF], applying to drawings
- graphics [WPF], GuidelineSet property
ms.assetid: 45f3e0b4-8820-45a7-b865-b8ea5b17b0c8
ms.openlocfilehash: 88c44cadce916c2ce10165a586e813ecaaaec672
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/05/2019
ms.locfileid: "57362989"
---
# <a name="how-to-apply-a-guidelineset-to-a-drawing"></a><span data-ttu-id="440c8-102">如何：向绘图应用 GuidelineSet</span><span class="sxs-lookup"><span data-stu-id="440c8-102">How to: Apply a GuidelineSet to a Drawing</span></span>
<span data-ttu-id="440c8-103">此示例演示如何将应用<xref:System.Windows.Media.GuidelineSet>到<xref:System.Windows.Media.DrawingGroup>。</span><span class="sxs-lookup"><span data-stu-id="440c8-103">This example shows how to apply a <xref:System.Windows.Media.GuidelineSet> to a <xref:System.Windows.Media.DrawingGroup>.</span></span>  
  
 <span data-ttu-id="440c8-104"><xref:System.Windows.Media.DrawingGroup>类是唯一的类型<xref:System.Windows.Media.Drawing>具有<xref:System.Windows.Media.DrawingGroup.GuidelineSet%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="440c8-104">The <xref:System.Windows.Media.DrawingGroup> class is the only type of <xref:System.Windows.Media.Drawing> that has a <xref:System.Windows.Media.DrawingGroup.GuidelineSet%2A> property.</span></span> <span data-ttu-id="440c8-105">若要将应用<xref:System.Windows.Media.GuidelineSet>为另一种<xref:System.Windows.Media.Drawing>，将其添加到<xref:System.Windows.Media.DrawingGroup>，然后应用<xref:System.Windows.Media.GuidelineSet>到你<xref:System.Windows.Media.DrawingGroup>。</span><span class="sxs-lookup"><span data-stu-id="440c8-105">To apply a <xref:System.Windows.Media.GuidelineSet> to another type of <xref:System.Windows.Media.Drawing>, add it to a <xref:System.Windows.Media.DrawingGroup> and then apply the <xref:System.Windows.Media.GuidelineSet> to your <xref:System.Windows.Media.DrawingGroup>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="440c8-106">示例</span><span class="sxs-lookup"><span data-stu-id="440c8-106">Example</span></span>  
 <span data-ttu-id="440c8-107">下面的示例创建两个<xref:System.Windows.Media.DrawingGroup>对象的几乎完全相同; 唯一的区别是： 第二个<xref:System.Windows.Media.DrawingGroup>具有<xref:System.Windows.Media.GuidelineSet>和第一个却没有。</span><span class="sxs-lookup"><span data-stu-id="440c8-107">The following example creates two <xref:System.Windows.Media.DrawingGroup> objects that are almost identical; the only difference is: the second <xref:System.Windows.Media.DrawingGroup> has a <xref:System.Windows.Media.GuidelineSet> and the first does not.</span></span>  
  
 <span data-ttu-id="440c8-108">下图显示该示例的输出。</span><span class="sxs-lookup"><span data-stu-id="440c8-108">The following illustration shows the output from the example.</span></span> <span data-ttu-id="440c8-109">因为之间的两个的呈现差别<xref:System.Windows.Media.DrawingGroup>对象很小，因此放大绘图的各个部分。</span><span class="sxs-lookup"><span data-stu-id="440c8-109">Because the rendering difference between the two <xref:System.Windows.Media.DrawingGroup> objects is so subtle, portions of the drawings are enlarged.</span></span>  
  
 <span data-ttu-id="440c8-110">![具有和没有 GuidelineSet 的 DrawingGroup](./media/graphicsmm-drawinggroup-guidelineset.png "graphicsmm_drawinggroup_guidelineset")</span><span class="sxs-lookup"><span data-stu-id="440c8-110">![A DrawingGroup with and without a GuidelineSet](./media/graphicsmm-drawinggroup-guidelineset.png "graphicsmm_drawinggroup_guidelineset")</span></span>  
  
 [!code-csharp[DrawingMiscSnippets_snip#GraphicsMMDrawingGroupGuidelineSetExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/DrawingGroupGuidelineSetExample.cs#graphicsmmdrawinggroupguidelinesetexamplewholepage)]
 [!code-xaml[DrawingMiscSnippets_snip#GraphicsMMDrawingGroupGuidelineSetExampleWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/DrawingGroupGuidelineSetExample.xaml#graphicsmmdrawinggroupguidelinesetexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="440c8-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="440c8-111">See also</span></span>
- <xref:System.Windows.Media.DrawingGroup>
- <xref:System.Windows.Media.GuidelineSet>
- [<span data-ttu-id="440c8-112">Drawing 对象概述</span><span class="sxs-lookup"><span data-stu-id="440c8-112">Drawing Objects Overview</span></span>](drawing-objects-overview.md)
