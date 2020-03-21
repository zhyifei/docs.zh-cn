---
title: 如何：缩放元素
ms.date: 03/30/2017
helpviewer_keywords:
- scaling [WPF], elements
- graphics [WPF], scaling elements
ms.assetid: 18158d94-bbe7-4f6a-814e-84d27fa748bf
ms.openlocfilehash: 34d954f68747be9eedc0ef71634e0c18b411d260
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/21/2020
ms.locfileid: "80112045"
---
# <a name="how-to-scale-an-element"></a><span data-ttu-id="843e2-102">如何：缩放元素</span><span class="sxs-lookup"><span data-stu-id="843e2-102">How to: Scale an Element</span></span>
<span data-ttu-id="843e2-103">此示例演示如何使用<xref:System.Windows.Media.ScaleTransform>缩放元素。</span><span class="sxs-lookup"><span data-stu-id="843e2-103">This example shows how to use a <xref:System.Windows.Media.ScaleTransform> to scale an element.</span></span>  
  
 <span data-ttu-id="843e2-104">使用<xref:System.Windows.Media.ScaleTransform.ScaleX%2A>和<xref:System.Windows.Media.ScaleTransform.ScaleY%2A>属性按指定的因子调整元素的大小。</span><span class="sxs-lookup"><span data-stu-id="843e2-104">Use the <xref:System.Windows.Media.ScaleTransform.ScaleX%2A> and <xref:System.Windows.Media.ScaleTransform.ScaleY%2A> properties to resize the element by the factor you specify.</span></span> <span data-ttu-id="843e2-105">例如，<xref:System.Windows.Media.ScaleTransform.ScaleX%2A>值 1.5 将元素拉伸到其原始宽度的 150%。</span><span class="sxs-lookup"><span data-stu-id="843e2-105">For example, a <xref:System.Windows.Media.ScaleTransform.ScaleX%2A> value of 1.5 stretches the element to 150 percent of its original width.</span></span> <span data-ttu-id="843e2-106">值<xref:System.Windows.Media.ScaleTransform.ScaleY%2A>0.5 将元素的高度缩小 50%。</span><span class="sxs-lookup"><span data-stu-id="843e2-106">A <xref:System.Windows.Media.ScaleTransform.ScaleY%2A> value of 0.5 shrinks the height of an element by 50 percent.</span></span>  
  
 <span data-ttu-id="843e2-107">使用<xref:System.Windows.Media.ScaleTransform.CenterX%2A>和<xref:System.Windows.Media.ScaleTransform.CenterY%2A>属性指定是比例操作中心的点。</span><span class="sxs-lookup"><span data-stu-id="843e2-107">Use the <xref:System.Windows.Media.ScaleTransform.CenterX%2A> and <xref:System.Windows.Media.ScaleTransform.CenterY%2A> properties to specify the point that is the center of the scale operation.</span></span> <span data-ttu-id="843e2-108">默认情况下，a<xref:System.Windows.Media.ScaleTransform>居中居于与矩形左上角相对应的点 （0，0）。</span><span class="sxs-lookup"><span data-stu-id="843e2-108">By default, a <xref:System.Windows.Media.ScaleTransform> is centered at the point (0,0), which corresponds to the upper-left corner of the rectangle.</span></span> <span data-ttu-id="843e2-109">这具有移动元素的效果，并且也使元素看起来更大，因为当您应用 时<xref:System.Windows.Media.Transform>，您将更改对象所在的坐标空间。</span><span class="sxs-lookup"><span data-stu-id="843e2-109">This has the effect of moving the element and also of making it appear larger, because when you apply a <xref:System.Windows.Media.Transform>, you change the coordinate space in which the object resides.</span></span>  
  
 <span data-ttu-id="843e2-110">下面的示例使用 将<xref:System.Windows.Media.ScaleTransform>50 乘 50<xref:System.Windows.Shapes.Rectangle>的大小加倍。</span><span class="sxs-lookup"><span data-stu-id="843e2-110">The following example uses a <xref:System.Windows.Media.ScaleTransform> to double the size of a 50-by-50 <xref:System.Windows.Shapes.Rectangle>.</span></span> <span data-ttu-id="843e2-111">和<xref:System.Windows.Media.ScaleTransform>的值为 0（默认值）。 <xref:System.Windows.Media.ScaleTransform.CenterX%2A> <xref:System.Windows.Media.ScaleTransform.CenterY%2A></span><span class="sxs-lookup"><span data-stu-id="843e2-111">The <xref:System.Windows.Media.ScaleTransform> has a value of 0 (the default) for both <xref:System.Windows.Media.ScaleTransform.CenterX%2A> and <xref:System.Windows.Media.ScaleTransform.CenterY%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="843e2-112">示例</span><span class="sxs-lookup"><span data-stu-id="843e2-112">Example</span></span>  
 [!code-xaml[transformsSample#21](~/samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/ScaleTransformExample.xaml#21)]  
  
 <span data-ttu-id="843e2-113">通常，您设置<xref:System.Windows.Media.ScaleTransform.CenterX%2A>并<xref:System.Windows.Media.ScaleTransform.CenterY%2A>设置为缩放的对象的中心：（/2，/2）。<xref:System.Windows.FrameworkElement.Width%2A> <xref:System.Windows.FrameworkElement.Height%2A></span><span class="sxs-lookup"><span data-stu-id="843e2-113">Typically, you set <xref:System.Windows.Media.ScaleTransform.CenterX%2A> and <xref:System.Windows.Media.ScaleTransform.CenterY%2A> to the center of the object that is scaled: (<xref:System.Windows.FrameworkElement.Width%2A>/2, <xref:System.Windows.FrameworkElement.Height%2A>/2).</span></span>  
  
 <span data-ttu-id="843e2-114">下面的示例显示了另一<xref:System.Windows.Shapes.Rectangle>个大小加倍的，但是，这<xref:System.Windows.Media.ScaleTransform>两个 值为<xref:System.Windows.Media.ScaleTransform.CenterX%2A>25，<xref:System.Windows.Media.ScaleTransform.CenterY%2A>对应于矩形的中心。</span><span class="sxs-lookup"><span data-stu-id="843e2-114">The following example shows another <xref:System.Windows.Shapes.Rectangle> that is doubled in size; however, this <xref:System.Windows.Media.ScaleTransform> has a value of 25 for both <xref:System.Windows.Media.ScaleTransform.CenterX%2A> and <xref:System.Windows.Media.ScaleTransform.CenterY%2A>, which corresponds to the center of the rectangle.</span></span>  
  
 [!code-xaml[transformsSample#22](~/samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/ScaleTransformExample.xaml#22)]  
  
 <span data-ttu-id="843e2-115">下图显示了两<xref:System.Windows.Media.ScaleTransform>个操作之间的差异。</span><span class="sxs-lookup"><span data-stu-id="843e2-115">The following illustration shows the difference between the two <xref:System.Windows.Media.ScaleTransform> operations.</span></span> <span data-ttu-id="843e2-116">虚线显示的是矩形在缩放之前的大小和位置。</span><span class="sxs-lookup"><span data-stu-id="843e2-116">The dotted line shows the size and position of the rectangle before scaling.</span></span>  
  
 <span data-ttu-id="843e2-117">![以不同中心点进行的 2 倍缩放](./media/wcpsdk-graphicsmm-scalecenter.gif "wcpsdk_graphicsmm_scalecenter")</span><span class="sxs-lookup"><span data-stu-id="843e2-117">![2x scales with different center points](./media/wcpsdk-graphicsmm-scalecenter.gif "wcpsdk_graphicsmm_scalecenter")</span></span>  
<span data-ttu-id="843e2-118">两个具有相同 ScaleX 和 ScaleY 值但中心不同的 ScaleTransform 操作</span><span class="sxs-lookup"><span data-stu-id="843e2-118">Two ScaleTransform operations with identical ScaleX and ScaleY values but different centers</span></span>  
  
 <span data-ttu-id="843e2-119">有关完整示例，请参阅[2D 变换示例](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/2DTransforms)。</span><span class="sxs-lookup"><span data-stu-id="843e2-119">For the complete sample, see [2D Transforms Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/2DTransforms).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="843e2-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="843e2-120">See also</span></span>

- <xref:System.Windows.Media.Transform>
- <xref:System.Windows.Media.ScaleTransform>
- [<span data-ttu-id="843e2-121">转换概述</span><span class="sxs-lookup"><span data-stu-id="843e2-121">Transforms Overview</span></span>](transforms-overview.md)
- [<span data-ttu-id="843e2-122">如何使用主题</span><span class="sxs-lookup"><span data-stu-id="843e2-122">How-to Topics</span></span>](transformations-how-to-topics.md)
