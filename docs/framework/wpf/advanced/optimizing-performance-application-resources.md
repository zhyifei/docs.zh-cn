---
title: 优化性能：应用程序资源
ms.date: 03/30/2017
helpviewer_keywords:
- application resources [WPF], performance
- resources [WPF], performance
- static resources [WPF]
- sharing resources [WPF]
- brushes [WPF], performance
- sharing brushes without copying [WPF]
ms.assetid: 62b88488-c08e-4804-b7de-a1c34fbe929c
ms.openlocfilehash: 362d0f0fd3282365e5e05dcd43c49a9fd2ddc9a7
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59139420"
---
# <a name="optimizing-performance-application-resources"></a><span data-ttu-id="9893c-102">优化性能：应用程序资源</span><span class="sxs-lookup"><span data-stu-id="9893c-102">Optimizing Performance: Application Resources</span></span>
[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <span data-ttu-id="9893c-103">可以共享应用程序资源，以便可以跨类似类型的元素支持一致的外观或行为。</span><span class="sxs-lookup"><span data-stu-id="9893c-103">allows you to share application resources so that you can support a consistent look or behavior across similar-typed elements.</span></span> <span data-ttu-id="9893c-104">本主题提供了一些建议在此区域中可帮助你改进应用程序的性能。</span><span class="sxs-lookup"><span data-stu-id="9893c-104">This topic provides a few recommendations in this area that can help you improve the performance of your applications.</span></span>  
  
 <span data-ttu-id="9893c-105">有关资源的详细信息，请参阅 [XAML 资源](xaml-resources.md)。</span><span class="sxs-lookup"><span data-stu-id="9893c-105">For more information on resources, see [XAML Resources](xaml-resources.md).</span></span>  
  
## <a name="sharing-resources"></a><span data-ttu-id="9893c-106">共享资源</span><span class="sxs-lookup"><span data-stu-id="9893c-106">Sharing resources</span></span>  
 <span data-ttu-id="9893c-107">如果你的应用程序使用自定义控件和定义中的资源<xref:System.Windows.ResourceDictionary>（或 XAML 资源节点），建议，您可以定义在资源<xref:System.Windows.Application>或<xref:System.Windows.Window>对象级别，或定义中的默认主题自定义控件。</span><span class="sxs-lookup"><span data-stu-id="9893c-107">If your application uses custom controls and defines resources in a <xref:System.Windows.ResourceDictionary> (or XAML Resources node), it is recommended that you either define the resources at the <xref:System.Windows.Application> or <xref:System.Windows.Window> object level, or define them in the default theme for the custom controls.</span></span> <span data-ttu-id="9893c-108">定义一个自定义控件中的资源<xref:System.Windows.ResourceDictionary>施加了该控件的每个实例的性能造成影响。</span><span class="sxs-lookup"><span data-stu-id="9893c-108">Defining resources in a custom control's <xref:System.Windows.ResourceDictionary> imposes a performance impact for every instance of that control.</span></span> <span data-ttu-id="9893c-109">例如，如果有需要进行大量性能的画笔操作定义为资源定义的自定义控件的部件和自定义控件的多个实例，则应用程序的工作集将显著增加。</span><span class="sxs-lookup"><span data-stu-id="9893c-109">For example, if you have performance-intensive brush operations defined as part of the resource definition of a custom control and many instances of the custom control, the application's working set will increase significantly.</span></span>  
  
 <span data-ttu-id="9893c-110">若要演示这一点，请考虑以下。</span><span class="sxs-lookup"><span data-stu-id="9893c-110">To illustrate this point, consider the following.</span></span> <span data-ttu-id="9893c-111">假设你正在开发卡游戏 using [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="9893c-111">Let's say you are developing a card game using [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].</span></span> <span data-ttu-id="9893c-112">对于大多数纸牌游戏，需要 52 张牌，52 不同的人脸。</span><span class="sxs-lookup"><span data-stu-id="9893c-112">For most card games, you need 52 cards with 52 different faces.</span></span> <span data-ttu-id="9893c-113">还可以实施一种卡片自定义控件和卡自定义控件的资源中定义 52 画笔 （每个元素表示一种纸牌外观）。</span><span class="sxs-lookup"><span data-stu-id="9893c-113">You decide to implement a card custom control and you define 52 brushes (each representing a card face) in the resources of your card custom control.</span></span> <span data-ttu-id="9893c-114">在主应用程序，最初创建此卡自定义控件 52 个的实例。</span><span class="sxs-lookup"><span data-stu-id="9893c-114">In your main application, you initially create 52 instances of this card custom control.</span></span> <span data-ttu-id="9893c-115">卡自定义控件的每个实例生成的 52 个实例<xref:System.Windows.Media.Brush>对象，这将使您总共 52 \* 52<xref:System.Windows.Media.Brush>你的应用程序中的对象。</span><span class="sxs-lookup"><span data-stu-id="9893c-115">Each instance of the card custom control generates 52 instances of <xref:System.Windows.Media.Brush> objects, which gives you a total of 52 \* 52 <xref:System.Windows.Media.Brush> objects in your application.</span></span> <span data-ttu-id="9893c-116">通过将移动到的卡自定义控件资源超出画笔<xref:System.Windows.Application>或<xref:System.Windows.Window>对象级别，或在自定义控件的默认主题中定义它们你降低该应用程序的工作集，因为现在正在共享 52 画笔52 个实例的卡片控件。</span><span class="sxs-lookup"><span data-stu-id="9893c-116">By moving the brushes out of the card custom control resources to the <xref:System.Windows.Application> or <xref:System.Windows.Window> object level, or defining them in the default theme for the custom control, you reduce the working set of the application, since you are now sharing the 52 brushes among 52 instances of the card control.</span></span>  
  
## <a name="sharing-a-brush-without-copying"></a><span data-ttu-id="9893c-117">不进行复制而共享画笔</span><span class="sxs-lookup"><span data-stu-id="9893c-117">Sharing a Brush without Copying</span></span>  
 <span data-ttu-id="9893c-118">如果您有多个元素使用的相同<xref:System.Windows.Media.Brush>对象，定义为资源的画笔并引用它，而不是定义中的画笔内联[!INCLUDE[TLA#tla_titlexaml](../../../../includes/tlasharptla-titlexaml-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="9893c-118">If you have multiple elements using the same <xref:System.Windows.Media.Brush> object, define the brush as a resource and reference it, rather than defining the brush inline in [!INCLUDE[TLA#tla_titlexaml](../../../../includes/tlasharptla-titlexaml-md.md)].</span></span> <span data-ttu-id="9893c-119">此方法将创建一个实例，并重复使用它，而定义画笔中的以内联方式[!INCLUDE[TLA#tla_titlexaml](../../../../includes/tlasharptla-titlexaml-md.md)]创建的每个元素的新实例。</span><span class="sxs-lookup"><span data-stu-id="9893c-119">This method will create one instance and reuse it, whereas defining brushes inline in [!INCLUDE[TLA#tla_titlexaml](../../../../includes/tlasharptla-titlexaml-md.md)] creates a new instance for each element.</span></span>  
  
 <span data-ttu-id="9893c-120">以下标记示例阐释了这一点：</span><span class="sxs-lookup"><span data-stu-id="9893c-120">The following markup sample illustrates this point:</span></span>  
  
 [!code-xaml[Performance#PerformanceSnippet7](~/samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/BrushResource.xaml#performancesnippet7)]  
  
## <a name="use-static-resources-when-possible"></a><span data-ttu-id="9893c-121">使用静态资源在可能的情况</span><span class="sxs-lookup"><span data-stu-id="9893c-121">Use Static Resources when Possible</span></span>  
 <span data-ttu-id="9893c-122">静态资源通过查找对已定义资源的引用，为任何 XAML 属性提供值。</span><span class="sxs-lookup"><span data-stu-id="9893c-122">A static resource provides a value for any XAML property attribute by looking up a reference to an already defined resource.</span></span> <span data-ttu-id="9893c-123">类似于编译时查找该资源的查找行为。</span><span class="sxs-lookup"><span data-stu-id="9893c-123">Lookup behavior for that resource is analogous to compile-time lookup.</span></span>  
  
 <span data-ttu-id="9893c-124">动态资源，但是，将创建初始编译期间的临时表达式，并因此延迟的资源查找，直到实际需要来构造对象请求的资源值为止。</span><span class="sxs-lookup"><span data-stu-id="9893c-124">A dynamic resource, on the other hand, will create a temporary expression during the initial compilation and thus defer lookup for resources until the requested resource value is actually required in order to construct an object.</span></span> <span data-ttu-id="9893c-125">该资源的查找行为是类似于运行时查找，它会影响性能。</span><span class="sxs-lookup"><span data-stu-id="9893c-125">Lookup behavior for that resource is analogous to run-time lookup, which imposes a performance impact.</span></span> <span data-ttu-id="9893c-126">使用静态资源应尽可能使用动态资源仅在必要时你应用程序中。</span><span class="sxs-lookup"><span data-stu-id="9893c-126">Use static resources whenever possible in your application, using dynamic resources only when necessary.</span></span>  
  
 <span data-ttu-id="9893c-127">以下标记示例演示如何使用这两种类型的资源：</span><span class="sxs-lookup"><span data-stu-id="9893c-127">The following markup sample shows the use of both types of resources:</span></span>  
  
 [!code-xaml[Performance#PerformanceSnippet8](~/samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/DynamicResource.xaml#performancesnippet8)]  
  
## <a name="see-also"></a><span data-ttu-id="9893c-128">请参阅</span><span class="sxs-lookup"><span data-stu-id="9893c-128">See also</span></span>

- [<span data-ttu-id="9893c-129">优化 WPF 应用程序性能</span><span class="sxs-lookup"><span data-stu-id="9893c-129">Optimizing WPF Application Performance</span></span>](optimizing-wpf-application-performance.md)
- [<span data-ttu-id="9893c-130">规划应用程序性能</span><span class="sxs-lookup"><span data-stu-id="9893c-130">Planning for Application Performance</span></span>](planning-for-application-performance.md)
- [<span data-ttu-id="9893c-131">利用硬件</span><span class="sxs-lookup"><span data-stu-id="9893c-131">Taking Advantage of Hardware</span></span>](optimizing-performance-taking-advantage-of-hardware.md)
- [<span data-ttu-id="9893c-132">布局和示例</span><span class="sxs-lookup"><span data-stu-id="9893c-132">Layout and Design</span></span>](optimizing-performance-layout-and-design.md)
- [<span data-ttu-id="9893c-133">2D 图形和图像处理</span><span class="sxs-lookup"><span data-stu-id="9893c-133">2D Graphics and Imaging</span></span>](optimizing-performance-2d-graphics-and-imaging.md)
- [<span data-ttu-id="9893c-134">对象行为</span><span class="sxs-lookup"><span data-stu-id="9893c-134">Object Behavior</span></span>](optimizing-performance-object-behavior.md)
- [<span data-ttu-id="9893c-135">文本</span><span class="sxs-lookup"><span data-stu-id="9893c-135">Text</span></span>](optimizing-performance-text.md)
- [<span data-ttu-id="9893c-136">数据绑定</span><span class="sxs-lookup"><span data-stu-id="9893c-136">Data Binding</span></span>](optimizing-performance-data-binding.md)
- [<span data-ttu-id="9893c-137">其他性能建议</span><span class="sxs-lookup"><span data-stu-id="9893c-137">Other Performance Recommendations</span></span>](optimizing-performance-other-recommendations.md)
