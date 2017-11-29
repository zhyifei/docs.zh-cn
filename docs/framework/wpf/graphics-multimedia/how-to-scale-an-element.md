---
title: "如何：缩放元素"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- scaling [WPF], elements
- graphics [WPF], scaling elements
ms.assetid: 18158d94-bbe7-4f6a-814e-84d27fa748bf
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 23b3086452526e804bfdbe50bb0c134f33158f5d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-scale-an-element"></a><span data-ttu-id="d26d7-102">如何：缩放元素</span><span class="sxs-lookup"><span data-stu-id="d26d7-102">How to: Scale an Element</span></span>
<span data-ttu-id="d26d7-103">此示例演示如何使用<xref:System.Windows.Media.ScaleTransform>来缩放元素。</span><span class="sxs-lookup"><span data-stu-id="d26d7-103">This example shows how to use a <xref:System.Windows.Media.ScaleTransform> to scale an element.</span></span>  
  
 <span data-ttu-id="d26d7-104">使用<xref:System.Windows.Media.ScaleTransform.ScaleX%2A>和<xref:System.Windows.Media.ScaleTransform.ScaleY%2A>属性，以调整元素大小按指定的因子。</span><span class="sxs-lookup"><span data-stu-id="d26d7-104">Use the <xref:System.Windows.Media.ScaleTransform.ScaleX%2A> and <xref:System.Windows.Media.ScaleTransform.ScaleY%2A> properties to resize the element by the factor you specify.</span></span> <span data-ttu-id="d26d7-105">例如，<xref:System.Windows.Media.ScaleTransform.ScaleX%2A>值为 1.5 拉伸到其原始宽度的 150%的元素。</span><span class="sxs-lookup"><span data-stu-id="d26d7-105">For example, a <xref:System.Windows.Media.ScaleTransform.ScaleX%2A> value of 1.5 stretches the element to 150 percent of its original width.</span></span> <span data-ttu-id="d26d7-106">A<xref:System.Windows.Media.ScaleTransform.ScaleY%2A>值为 0.5 时，会元素的高度缩小 50%。</span><span class="sxs-lookup"><span data-stu-id="d26d7-106">A <xref:System.Windows.Media.ScaleTransform.ScaleY%2A> value of 0.5 shrinks the height of an element by 50 percent.</span></span>  
  
 <span data-ttu-id="d26d7-107">使用<xref:System.Windows.Media.ScaleTransform.CenterX%2A>和<xref:System.Windows.Media.ScaleTransform.CenterY%2A>属性以指定的点的缩放操作的中心。</span><span class="sxs-lookup"><span data-stu-id="d26d7-107">Use the <xref:System.Windows.Media.ScaleTransform.CenterX%2A> and <xref:System.Windows.Media.ScaleTransform.CenterY%2A> properties to specify the point that is the center of the scale operation.</span></span> <span data-ttu-id="d26d7-108">默认情况下，<xref:System.Windows.Media.ScaleTransform>以对应的矩形的左上角的点 (0，0)，为中心。</span><span class="sxs-lookup"><span data-stu-id="d26d7-108">By default, a <xref:System.Windows.Media.ScaleTransform> is centered at the point (0,0), which corresponds to the upper-left corner of the rectangle.</span></span> <span data-ttu-id="d26d7-109">此操作将该元素移动以及使其看上去更大，因为当你将<xref:System.Windows.Media.Transform>，更改对象驻留在其中的坐标空间。</span><span class="sxs-lookup"><span data-stu-id="d26d7-109">This has the effect of moving the element and also of making it appear larger, because when you apply a <xref:System.Windows.Media.Transform>, you change the coordinate space in which the object resides.</span></span>  
  
 <span data-ttu-id="d26d7-110">下面的示例使用<xref:System.Windows.Media.ScaleTransform>为双精度，大小为 50 的 50 <xref:System.Windows.Shapes.Rectangle>。</span><span class="sxs-lookup"><span data-stu-id="d26d7-110">The following example uses a <xref:System.Windows.Media.ScaleTransform> to double the size of a 50-by-50 <xref:System.Windows.Shapes.Rectangle>.</span></span> <span data-ttu-id="d26d7-111"><xref:System.Windows.Media.ScaleTransform>两个具有值为 0 （默认值）<xref:System.Windows.Media.ScaleTransform.CenterX%2A>和<xref:System.Windows.Media.ScaleTransform.CenterY%2A>。</span><span class="sxs-lookup"><span data-stu-id="d26d7-111">The <xref:System.Windows.Media.ScaleTransform> has a value of 0 (the default) for both <xref:System.Windows.Media.ScaleTransform.CenterX%2A> and <xref:System.Windows.Media.ScaleTransform.CenterY%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d26d7-112">示例</span><span class="sxs-lookup"><span data-stu-id="d26d7-112">Example</span></span>  
 [!code-xaml[transformsSample#21](../../../../samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/ScaleTransformExample.xaml#21)]  
  
 <span data-ttu-id="d26d7-113">通常情况下，设置<xref:System.Windows.Media.ScaleTransform.CenterX%2A>和<xref:System.Windows.Media.ScaleTransform.CenterY%2A>到中心进行缩放后的对象: (<xref:System.Windows.FrameworkElement.Width%2A>/月 2 日，  <xref:System.Windows.FrameworkElement.Height%2A> /2)。</span><span class="sxs-lookup"><span data-stu-id="d26d7-113">Typically, you set <xref:System.Windows.Media.ScaleTransform.CenterX%2A> and <xref:System.Windows.Media.ScaleTransform.CenterY%2A> to the center of the object that is scaled: (<xref:System.Windows.FrameworkElement.Width%2A>/2, <xref:System.Windows.FrameworkElement.Height%2A>/2).</span></span>  
  
 <span data-ttu-id="d26d7-114">下面的示例显示另一种<xref:System.Windows.Shapes.Rectangle>，加倍大小; 但是，这<xref:System.Windows.Media.ScaleTransform>两个具有值为 25<xref:System.Windows.Media.ScaleTransform.CenterX%2A>和<xref:System.Windows.Media.ScaleTransform.CenterY%2A>，这对应于矩形的中心。</span><span class="sxs-lookup"><span data-stu-id="d26d7-114">The following example shows another <xref:System.Windows.Shapes.Rectangle> that is doubled in size; however, this <xref:System.Windows.Media.ScaleTransform> has a value of 25 for both <xref:System.Windows.Media.ScaleTransform.CenterX%2A> and <xref:System.Windows.Media.ScaleTransform.CenterY%2A>, which corresponds to the center of the rectangle.</span></span>  
  
 [!code-xaml[transformsSample#22](../../../../samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/ScaleTransformExample.xaml#22)]  
  
 <span data-ttu-id="d26d7-115">下图显示这两者之间的差异<xref:System.Windows.Media.ScaleTransform>操作。</span><span class="sxs-lookup"><span data-stu-id="d26d7-115">The following illustration shows the difference between the two <xref:System.Windows.Media.ScaleTransform> operations.</span></span> <span data-ttu-id="d26d7-116">虚线显示的是矩形在缩放之前的大小和位置。</span><span class="sxs-lookup"><span data-stu-id="d26d7-116">The dotted line shows the size and position of the rectangle before scaling.</span></span>  
  
 <span data-ttu-id="d26d7-117">![以不同中心点进行的 2x 缩放](../../../../docs/framework/wpf/graphics-multimedia/media/wcpsdk-graphicsmm-scalecenter.gif "wcpsdk_graphicsmm_scalecenter")</span><span class="sxs-lookup"><span data-stu-id="d26d7-117">![2x scales with different center points](../../../../docs/framework/wpf/graphics-multimedia/media/wcpsdk-graphicsmm-scalecenter.gif "wcpsdk_graphicsmm_scalecenter")</span></span>  
<span data-ttu-id="d26d7-118">两个具有相同 ScaleX 和 ScaleY 值但中心不同的 ScaleTransform 操作</span><span class="sxs-lookup"><span data-stu-id="d26d7-118">Two ScaleTransform operations with identical ScaleX and ScaleY values but different centers</span></span>  
  
 <span data-ttu-id="d26d7-119">有关完整示例，请参阅 [2D 转换示例](http://go.microsoft.com/fwlink/?LinkID=158252)。</span><span class="sxs-lookup"><span data-stu-id="d26d7-119">For the complete sample, see [2-D Transforms Sample](http://go.microsoft.com/fwlink/?LinkID=158252).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d26d7-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d26d7-120">See Also</span></span>  
 <xref:System.Windows.Media.Transform>  
 <xref:System.Windows.Media.ScaleTransform>  
 [<span data-ttu-id="d26d7-121">转换概述</span><span class="sxs-lookup"><span data-stu-id="d26d7-121">Transforms Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/transforms-overview.md)  
 [<span data-ttu-id="d26d7-122">操作说明主题</span><span class="sxs-lookup"><span data-stu-id="d26d7-122">How-to Topics</span></span>](../../../../docs/framework/wpf/graphics-multimedia/transformations-how-to-topics.md)
