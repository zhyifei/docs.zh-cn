---
title: Freezable 对象概述
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Freezable objects [WPF], description
- unfreezing Freezable objects [WPF]
- classes [WPF], Freezable
ms.assetid: 89c71692-4f43-4057-b611-67c6a8a863a2
ms.openlocfilehash: a1006816168e405d0d79786b8430b802f1ec0928
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/14/2018
ms.locfileid: "45615575"
---
# <a name="freezable-objects-overview"></a><span data-ttu-id="740b3-102">Freezable 对象概述</span><span class="sxs-lookup"><span data-stu-id="740b3-102">Freezable Objects Overview</span></span>
<span data-ttu-id="740b3-103">本主题介绍如何有效地使用和创建<xref:System.Windows.Freezable>对象，它们提供特殊功能，可帮助提高应用程序性能。</span><span class="sxs-lookup"><span data-stu-id="740b3-103">This topic describes how to effectively use and create <xref:System.Windows.Freezable> objects, which provide special features that can help improve application performance.</span></span> <span data-ttu-id="740b3-104">Freezable 对象的示例包括画笔、 笔、 转换、 几何和动画。</span><span class="sxs-lookup"><span data-stu-id="740b3-104">Examples of freezable objects include brushes, pens, transformations, geometries, and animations.</span></span>  
  
<a name="whatisafreezable"></a>   
## <a name="what-is-a-freezable"></a><span data-ttu-id="740b3-105">什么是 Freezable？</span><span class="sxs-lookup"><span data-stu-id="740b3-105">What Is a Freezable?</span></span>  
 <span data-ttu-id="740b3-106">一个<xref:System.Windows.Freezable>是一种特殊的对象，它有两种状态： 解冻和冻结。</span><span class="sxs-lookup"><span data-stu-id="740b3-106">A <xref:System.Windows.Freezable> is a special type of object that has two states: unfrozen and frozen.</span></span> <span data-ttu-id="740b3-107">当未冻结，<xref:System.Windows.Freezable>看起来就像任何其他对象的行为。</span><span class="sxs-lookup"><span data-stu-id="740b3-107">When unfrozen, a <xref:System.Windows.Freezable> appears to behave like any other object.</span></span> <span data-ttu-id="740b3-108">当冻结，<xref:System.Windows.Freezable>无法再进行修改。</span><span class="sxs-lookup"><span data-stu-id="740b3-108">When frozen, a <xref:System.Windows.Freezable> can no longer be modified.</span></span>  
  
 <span data-ttu-id="740b3-109">一个<xref:System.Windows.Freezable>提供了<xref:System.Windows.Freezable.Changed>事件，以通知观察者的对对象进行任何修改。</span><span class="sxs-lookup"><span data-stu-id="740b3-109">A <xref:System.Windows.Freezable> provides a <xref:System.Windows.Freezable.Changed> event to notify observers of any modifications to the object.</span></span> <span data-ttu-id="740b3-110">冻结<xref:System.Windows.Freezable>可以提高其性能，因为它不再需要更改通知而消耗资源。</span><span class="sxs-lookup"><span data-stu-id="740b3-110">Freezing a <xref:System.Windows.Freezable> can improve its performance, because it no longer needs to spend resources on change notifications.</span></span> <span data-ttu-id="740b3-111">冻结<xref:System.Windows.Freezable>还可以在时未冻结的线程之间共享<xref:System.Windows.Freezable>不能。</span><span class="sxs-lookup"><span data-stu-id="740b3-111">A frozen <xref:System.Windows.Freezable> can also be shared across threads, while an unfrozen <xref:System.Windows.Freezable> cannot.</span></span>  
  
 <span data-ttu-id="740b3-112">尽管<xref:System.Windows.Freezable>类具有许多应用程序，最<xref:System.Windows.Freezable>中的对象[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]与图形子系统相关。</span><span class="sxs-lookup"><span data-stu-id="740b3-112">Although the <xref:System.Windows.Freezable> class has many applications, most <xref:System.Windows.Freezable> objects in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] are related to the graphics sub-system.</span></span>  
  
 <span data-ttu-id="740b3-113"><xref:System.Windows.Freezable>类可以容易地使用某些图形系统对象，并有助于提高应用程序性能。</span><span class="sxs-lookup"><span data-stu-id="740b3-113">The <xref:System.Windows.Freezable> class makes it easier to use certain graphics system objects and can help improve application performance.</span></span> <span data-ttu-id="740b3-114">继承的类型的示例<xref:System.Windows.Freezable>包括<xref:System.Windows.Media.Brush>， <xref:System.Windows.Media.Transform>，和<xref:System.Windows.Media.Geometry>类。</span><span class="sxs-lookup"><span data-stu-id="740b3-114">Examples of types that inherit from <xref:System.Windows.Freezable> include the <xref:System.Windows.Media.Brush>, <xref:System.Windows.Media.Transform>, and <xref:System.Windows.Media.Geometry> classes.</span></span> <span data-ttu-id="740b3-115">因为它们包含非托管的资源，系统必须监视这些对象的修改，并对原始对象的更改时，然后更新其相应的非托管的资源。</span><span class="sxs-lookup"><span data-stu-id="740b3-115">Because they contain unmanaged resources, the system must monitor these objects for modifications, and then update their corresponding unmanaged resources when there is a change to the original object.</span></span> <span data-ttu-id="740b3-116">即使你实际上无需修改图形系统对象，系统必须仍需花一些资源来监视对象，以防对其进行更改。</span><span class="sxs-lookup"><span data-stu-id="740b3-116">Even if you don't actually modify a graphics system object, the system must still spend some of its resources monitoring the object, in case you do change it.</span></span>  
  
 <span data-ttu-id="740b3-117">例如，假设您创建<xref:System.Windows.Media.SolidColorBrush>画笔，并使用它来绘制按钮的背景。</span><span class="sxs-lookup"><span data-stu-id="740b3-117">For example, suppose you create a <xref:System.Windows.Media.SolidColorBrush> brush and use it to paint the background of a button.</span></span>  
  
 [!code-csharp[freezablesample_procedural#FrozenExamplePart1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#frozenexamplepart1)]
 [!code-vb[freezablesample_procedural#FrozenExamplePart1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#frozenexamplepart1)]  
  
 <span data-ttu-id="740b3-118">当呈现该按钮时，[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]图形子系统使用您提供要绘制的一组像素，若要创建一个按钮的外观的信息。</span><span class="sxs-lookup"><span data-stu-id="740b3-118">When the button is rendered, the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] graphics sub-system uses the information you provided to paint a group of pixels to create the appearance of a button.</span></span> <span data-ttu-id="740b3-119">尽管使用纯色画笔来描述应如何绘制按钮，但纯色画笔实际上不会进行绘制。</span><span class="sxs-lookup"><span data-stu-id="740b3-119">Although you used a solid color brush to describe how the button should be painted, your solid color brush doesn't actually do the painting.</span></span> <span data-ttu-id="740b3-120">图形系统将生成用于按钮和画笔，快速、 低级别对象并且在屏幕实际显示这些对象。</span><span class="sxs-lookup"><span data-stu-id="740b3-120">The graphics system generates fast, low-level objects for the button and the brush, and it is those objects that actually appear on the screen.</span></span>  
  
 <span data-ttu-id="740b3-121">如果您打算修改画笔，这些低级别对象需要重新生成。</span><span class="sxs-lookup"><span data-stu-id="740b3-121">If you were to modify the brush, those low-level objects would have to be regenerated.</span></span> <span data-ttu-id="740b3-122">Freezable 类是什么使画笔能够以查找其相应的生成的低级别对象，并且它发生更改时更新它们。</span><span class="sxs-lookup"><span data-stu-id="740b3-122">The freezable class is what gives a brush the ability to find its corresponding generated, low-level objects and to update them when it changes.</span></span> <span data-ttu-id="740b3-123">画笔时启用此功能，则称其"未冻结。"</span><span class="sxs-lookup"><span data-stu-id="740b3-123">When this ability is enabled, the brush is said to be "unfrozen."</span></span>  
  
 <span data-ttu-id="740b3-124">Freezable 的<xref:System.Windows.Freezable.Freeze%2A>方法使您能够禁用此自我更新功能。</span><span class="sxs-lookup"><span data-stu-id="740b3-124">A freezable's <xref:System.Windows.Freezable.Freeze%2A> method enables you to disable this self-updating ability.</span></span> <span data-ttu-id="740b3-125">此方法可用于使画笔变为"冻结"或变为不可修改。</span><span class="sxs-lookup"><span data-stu-id="740b3-125">You can use this method to make the brush become "frozen," or unmodifiable.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="740b3-126">不是每个 Freezable 对象可以被冻结。</span><span class="sxs-lookup"><span data-stu-id="740b3-126">Not every Freezable object can be frozen.</span></span> <span data-ttu-id="740b3-127">若要避免引发<xref:System.InvalidOperationException>，检查 Freezable 对象的值<xref:System.Windows.Freezable.CanFreeze%2A>属性来确定是否它可以冻结然后再尝试冻结它。</span><span class="sxs-lookup"><span data-stu-id="740b3-127">To avoid throwing an <xref:System.InvalidOperationException>, check the value of the Freezable object's <xref:System.Windows.Freezable.CanFreeze%2A> property to determine whether it can be frozen before attempting to freeze it.</span></span>  
  
 [!code-csharp[freezablesample_procedural#FrozenExamplePart2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#frozenexamplepart2)]
 [!code-vb[freezablesample_procedural#FrozenExamplePart2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#frozenexamplepart2)]  
  
 <span data-ttu-id="740b3-128">当不再需要进行修改的 freezable 时，冻结它提供性能优势。</span><span class="sxs-lookup"><span data-stu-id="740b3-128">When you no longer need to modify a freezable, freezing it provides performance benefits.</span></span> <span data-ttu-id="740b3-129">如果要冻结的画笔在此示例中，图形系统将不再需要监视的更改。</span><span class="sxs-lookup"><span data-stu-id="740b3-129">If you were to freeze the brush in this example, the graphics system would no longer need to monitor it for changes.</span></span> <span data-ttu-id="740b3-130">图形系统还可以进行其他优化，因为它知道画笔不会更改。</span><span class="sxs-lookup"><span data-stu-id="740b3-130">The graphics system can also make other optimizations, because it knows the brush won't change.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="740b3-131">为方便起见，freezable 对象保持未冻结，除非显式冻结。</span><span class="sxs-lookup"><span data-stu-id="740b3-131">For convenience, freezable objects remain unfrozen unless you explicitly freeze them.</span></span>  
  
<a name="frozenfreezables"></a>   
## <a name="using-freezables"></a><span data-ttu-id="740b3-132">使用的可冻结对象</span><span class="sxs-lookup"><span data-stu-id="740b3-132">Using Freezables</span></span>  
 <span data-ttu-id="740b3-133">使用解冻 freezable 就像使用任何其他类型的对象。</span><span class="sxs-lookup"><span data-stu-id="740b3-133">Using an unfrozen freezable is like using any other type of object.</span></span> <span data-ttu-id="740b3-134">在下面的示例中，颜色<xref:System.Windows.Media.SolidColorBrush>从黄色更改为红色后它用于绘制按钮背景。</span><span class="sxs-lookup"><span data-stu-id="740b3-134">In the following example, the color of a <xref:System.Windows.Media.SolidColorBrush> is changed from yellow to red after it's used to paint the background of a button.</span></span> <span data-ttu-id="740b3-135">图形系统来自动更改按钮从黄色为红色的下次刷新屏幕时在后台工作。</span><span class="sxs-lookup"><span data-stu-id="740b3-135">The graphics system works behind the scenes to automatically change the button from yellow to red the next time the screen is refreshed.</span></span>  
  
 [!code-csharp[freezablesample_procedural#UnFrozenExampleShort](../../../../samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#unfrozenexampleshort)]
 [!code-vb[freezablesample_procedural#UnFrozenExampleShort](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#unfrozenexampleshort)]  
  
### <a name="freezing-a-freezable"></a><span data-ttu-id="740b3-136">冻结 Freezable</span><span class="sxs-lookup"><span data-stu-id="740b3-136">Freezing a Freezable</span></span>  
 <span data-ttu-id="740b3-137">若要使<xref:System.Windows.Freezable>变为不可修改，则调用其<xref:System.Windows.Freezable.Freeze%2A>方法。</span><span class="sxs-lookup"><span data-stu-id="740b3-137">To make a <xref:System.Windows.Freezable> unmodifiable, you call its <xref:System.Windows.Freezable.Freeze%2A> method.</span></span> <span data-ttu-id="740b3-138">冻结包含 freezable 对象的对象，这些对象也会冻结起来。</span><span class="sxs-lookup"><span data-stu-id="740b3-138">When you freeze an object that contains freezable objects, those objects are frozen as well.</span></span> <span data-ttu-id="740b3-139">例如，如果冻结<xref:System.Windows.Media.PathGeometry>，数字和其包含的段会被冻结。</span><span class="sxs-lookup"><span data-stu-id="740b3-139">For example, if you freeze a <xref:System.Windows.Media.PathGeometry>, the figures and segments it contains would be frozen too.</span></span>  
  
 <span data-ttu-id="740b3-140">Freezable**不能**被冻结，如果以下任何条件成立：</span><span class="sxs-lookup"><span data-stu-id="740b3-140">A Freezable **can't** be frozen if any of the following are true:</span></span>  
  
-   <span data-ttu-id="740b3-141">它具有经过动画处理或数据绑定属性。</span><span class="sxs-lookup"><span data-stu-id="740b3-141">It has animated or data bound properties.</span></span>  
  
-   <span data-ttu-id="740b3-142">它具有由动态资源设置的属性。</span><span class="sxs-lookup"><span data-stu-id="740b3-142">It has properties set by a dynamic resource.</span></span> <span data-ttu-id="740b3-143">(请参阅[XAML 资源](../../../../docs/framework/wpf/advanced/xaml-resources.md)动态资源有关的详细信息。)</span><span class="sxs-lookup"><span data-stu-id="740b3-143">(See the [XAML Resources](../../../../docs/framework/wpf/advanced/xaml-resources.md) for more information about dynamic resources.)</span></span>  
  
-   <span data-ttu-id="740b3-144">它包含<xref:System.Windows.Freezable>不能冻结的子对象。</span><span class="sxs-lookup"><span data-stu-id="740b3-144">It contains <xref:System.Windows.Freezable> sub-objects that can't be frozen.</span></span>  
  
 <span data-ttu-id="740b3-145">如果这些条件都为 false，并且不打算修改<xref:System.Windows.Freezable>，则应冻结其获得前面所述的性能优势。</span><span class="sxs-lookup"><span data-stu-id="740b3-145">If these conditions are false, and you don't intend to modify the <xref:System.Windows.Freezable>, then you should freeze it to gain the performance benefits described earlier.</span></span>  
  
 <span data-ttu-id="740b3-146">一旦调用 freezable 的<xref:System.Windows.Freezable.Freeze%2A>方法，它无法再进行修改。</span><span class="sxs-lookup"><span data-stu-id="740b3-146">Once you call a freezable's <xref:System.Windows.Freezable.Freeze%2A> method, it can no longer be modified.</span></span> <span data-ttu-id="740b3-147">尝试修改的冻结对象会导致<xref:System.InvalidOperationException>引发。</span><span class="sxs-lookup"><span data-stu-id="740b3-147">Attempting to modify a frozen object causes an <xref:System.InvalidOperationException> to be thrown.</span></span> <span data-ttu-id="740b3-148">下面的代码引发异常，因为我们试图修改画笔后已被冻结。</span><span class="sxs-lookup"><span data-stu-id="740b3-148">The following code throws an exception, because we attempt to modify the brush after it's been frozen.</span></span>  
  
 [!code-csharp[freezablesample_procedural#ExceptionExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#exceptionexample)]
 [!code-vb[freezablesample_procedural#ExceptionExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#exceptionexample)]  
  
 <span data-ttu-id="740b3-149">若要避免此异常，可以使用<xref:System.Windows.Freezable.IsFrozen%2A>方法，以确定是否<xref:System.Windows.Freezable>处于冻结状态。</span><span class="sxs-lookup"><span data-stu-id="740b3-149">To avoid throwing this exception, you can use the <xref:System.Windows.Freezable.IsFrozen%2A> method to determine whether a <xref:System.Windows.Freezable> is frozen.</span></span>  
  
 [!code-csharp[freezablesample_procedural#CheckIsFrozenExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#checkisfrozenexample)]
 [!code-vb[freezablesample_procedural#CheckIsFrozenExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#checkisfrozenexample)]  
  
 <span data-ttu-id="740b3-150">在前面的代码示例中，可修改副本已冻结的对象使用的<xref:System.Windows.Freezable.Clone%2A>方法。</span><span class="sxs-lookup"><span data-stu-id="740b3-150">In the preceding code example, a modifiable copy was made of a frozen object using the <xref:System.Windows.Freezable.Clone%2A> method.</span></span> <span data-ttu-id="740b3-151">下一节讨论了更详细地克隆。</span><span class="sxs-lookup"><span data-stu-id="740b3-151">The next section discusses cloning in more detail.</span></span>  
  
 <span data-ttu-id="740b3-152">**请注意**因为冻结 freezable 不能进行动画处理时，动画系统将自动创建的可修改克隆冻结<xref:System.Windows.Freezable>对象时尝试与它们进行动画处理<xref:System.Windows.Media.Animation.Storyboard>。</span><span class="sxs-lookup"><span data-stu-id="740b3-152">**Note** Because a frozen freezable cannot be animated, the animation system will automatically create modifiable clones of frozen <xref:System.Windows.Freezable> objects when you try to animate them with a <xref:System.Windows.Media.Animation.Storyboard>.</span></span> <span data-ttu-id="740b3-153">若要消除开销引起的克隆的性能，请将解冻如果你想要对其进行动画处理的对象。</span><span class="sxs-lookup"><span data-stu-id="740b3-153">To eliminate the performance overhead caused by cloning, leave an object unfrozen if you intend to animate it.</span></span> <span data-ttu-id="740b3-154">有关使用演示图板进行动画处理的详细信息，请参阅[情节提要概述](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="740b3-154">For more information about animating with storyboards, see the [Storyboards Overview](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md).</span></span>  
  
### <a name="freezing-from-markup"></a><span data-ttu-id="740b3-155">从标记冻结</span><span class="sxs-lookup"><span data-stu-id="740b3-155">Freezing from Markup</span></span>  
 <span data-ttu-id="740b3-156">若要冻结<xref:System.Windows.Freezable>对象声明在标记中，您使用`PresentationOptions:Freeze`属性。</span><span class="sxs-lookup"><span data-stu-id="740b3-156">To freeze a <xref:System.Windows.Freezable> object declared in markup, you use the `PresentationOptions:Freeze` attribute.</span></span> <span data-ttu-id="740b3-157">在以下示例中，<xref:System.Windows.Media.SolidColorBrush>声明为页面资源和冻结。</span><span class="sxs-lookup"><span data-stu-id="740b3-157">In the following example, a <xref:System.Windows.Media.SolidColorBrush> is declared as a page resource and frozen.</span></span> <span data-ttu-id="740b3-158">然后使用来设置按钮的背景。</span><span class="sxs-lookup"><span data-stu-id="740b3-158">It is then used to set the background of a button.</span></span>  
  
 [!code-xaml[FreezableSample#FreezeFromMarkupWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FreezableSample/CS/FreezeFromMarkupExample.xaml#freezefrommarkupwholepage)]  
  
 <span data-ttu-id="740b3-159">若要使用`Freeze`属性，则必须映射到演示文稿选项命名空间： `http://schemas.microsoft.com/winfx/2006/xaml/presentation/options`。</span><span class="sxs-lookup"><span data-stu-id="740b3-159">To use the `Freeze` attribute, you must map to the presentation options namespace: `http://schemas.microsoft.com/winfx/2006/xaml/presentation/options`.</span></span> <span data-ttu-id="740b3-160">`PresentationOptions` 是映射此命名空间的建议的前缀：</span><span class="sxs-lookup"><span data-stu-id="740b3-160">`PresentationOptions` is the recommended prefix for mapping this namespace:</span></span>  
  
```  
xmlns:PresentationOptions="http://schemas.microsoft.com/winfx/2006/xaml/presentation/options"   
```  
  
 <span data-ttu-id="740b3-161">因为并非所有 XAML 读取器都识别此特性，建议你使用[mc: Ignorable 特性](../../../../docs/framework/wpf/advanced/mc-ignorable-attribute.md)标记`Presentation:Freeze`为可忽略属性：</span><span class="sxs-lookup"><span data-stu-id="740b3-161">Because not all XAML readers recognize this attribute, it's recommended that you use the [mc:Ignorable Attribute](../../../../docs/framework/wpf/advanced/mc-ignorable-attribute.md) to mark the `Presentation:Freeze` attribute as ignorable:</span></span>  
  
```  
xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"  
mc:Ignorable="PresentationOptions"  
```  
  
 <span data-ttu-id="740b3-162">有关详细信息，请参阅[mc: Ignorable 特性](../../../../docs/framework/wpf/advanced/mc-ignorable-attribute.md)页。</span><span class="sxs-lookup"><span data-stu-id="740b3-162">For more information, see the [mc:Ignorable Attribute](../../../../docs/framework/wpf/advanced/mc-ignorable-attribute.md) page.</span></span>  
  
### <a name="unfreezing-a-freezable"></a><span data-ttu-id="740b3-163">"解冻"Freezable</span><span class="sxs-lookup"><span data-stu-id="740b3-163">"Unfreezing" a Freezable</span></span>  
 <span data-ttu-id="740b3-164">一次冻结<xref:System.Windows.Freezable>永远不会修改或解冻; 但是，可以创建使用一个未冻结的克隆<xref:System.Windows.Freezable.Clone%2A>或<xref:System.Windows.Freezable.CloneCurrentValue%2A>方法。</span><span class="sxs-lookup"><span data-stu-id="740b3-164">Once frozen, a <xref:System.Windows.Freezable> can never be modified or unfrozen; however, you can create an unfrozen clone using the <xref:System.Windows.Freezable.Clone%2A> or <xref:System.Windows.Freezable.CloneCurrentValue%2A> method.</span></span>  
  
 <span data-ttu-id="740b3-165">在以下示例中，使用一个画笔设置按钮的背景，然后冻结该画笔。</span><span class="sxs-lookup"><span data-stu-id="740b3-165">In the following example, the button's background is set with a brush and that brush is then frozen.</span></span> <span data-ttu-id="740b3-166">冻结的副本组成画笔使用<xref:System.Windows.Freezable.Clone%2A>方法。</span><span class="sxs-lookup"><span data-stu-id="740b3-166">An unfrozen copy is made of the brush using the <xref:System.Windows.Freezable.Clone%2A> method.</span></span> <span data-ttu-id="740b3-167">克隆是修改并用于将按钮的背景由黄色更改为红色。</span><span class="sxs-lookup"><span data-stu-id="740b3-167">The clone is modified and used to change the button's background from yellow to red.</span></span>  
  
 [!code-csharp[freezablesample_procedural#CloneExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#cloneexample)]
 [!code-vb[freezablesample_procedural#CloneExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#cloneexample)]  
  
> [!NOTE]
>  <span data-ttu-id="740b3-168">无论使用哪种克隆方法，动画不会被复制到新<xref:System.Windows.Freezable>。</span><span class="sxs-lookup"><span data-stu-id="740b3-168">Regardless of which clone method you use, animations are never copied to the new <xref:System.Windows.Freezable>.</span></span>  
  
 <span data-ttu-id="740b3-169"><xref:System.Windows.Freezable.Clone%2A>和<xref:System.Windows.Freezable.CloneCurrentValue%2A>方法会生成可冻结的深层副本。</span><span class="sxs-lookup"><span data-stu-id="740b3-169">The <xref:System.Windows.Freezable.Clone%2A> and <xref:System.Windows.Freezable.CloneCurrentValue%2A> methods produce deep copies of the freezable.</span></span> <span data-ttu-id="740b3-170">如果 freezable 包含其他冻结 freezable 对象，它们是克隆，并且进行可修改的。</span><span class="sxs-lookup"><span data-stu-id="740b3-170">If the freezable contains other frozen freezable objects, they are also cloned and made modifiable.</span></span> <span data-ttu-id="740b3-171">例如，如果你克隆的冻结<xref:System.Windows.Media.PathGeometry>使可供修改，数字和其包含的段也复制并进行修改。</span><span class="sxs-lookup"><span data-stu-id="740b3-171">For example, if you clone a frozen <xref:System.Windows.Media.PathGeometry> to make it modifiable, the figures and segments it contains are also copied and made modifiable.</span></span>  
  
<a name="createyourownfreezableclass"></a>   
## <a name="creating-your-own-freezable-class"></a><span data-ttu-id="740b3-172">创建您自己的 Freezable 类</span><span class="sxs-lookup"><span data-stu-id="740b3-172">Creating Your Own Freezable Class</span></span>  
 <span data-ttu-id="740b3-173">从派生的类<xref:System.Windows.Freezable>可以获得以下功能。</span><span class="sxs-lookup"><span data-stu-id="740b3-173">A class that derives from <xref:System.Windows.Freezable> gains the following features.</span></span>  
  
-   <span data-ttu-id="740b3-174">特殊状态： 只读 （冻结） 和可写状态。</span><span class="sxs-lookup"><span data-stu-id="740b3-174">Special states: a read-only (frozen) and a writable state.</span></span>  
  
-   <span data-ttu-id="740b3-175">线程安全： 的冻结<xref:System.Windows.Freezable>可以在线程之间共享。</span><span class="sxs-lookup"><span data-stu-id="740b3-175">Thread safety: a frozen <xref:System.Windows.Freezable> can be shared across threads.</span></span>  
  
-   <span data-ttu-id="740b3-176">详细的更改通知： 与其他不同<xref:System.Windows.DependencyObject>s，对子属性值更改时 Freezable 对象提供更改通知。</span><span class="sxs-lookup"><span data-stu-id="740b3-176">Detailed change notification: Unlike other <xref:System.Windows.DependencyObject>s, Freezable objects provide change notifications when sub-property values change.</span></span>  
  
-   <span data-ttu-id="740b3-177">简单克隆： Freezable 类已经实现生成深层克隆的几种方法。</span><span class="sxs-lookup"><span data-stu-id="740b3-177">Easy cloning: the Freezable class has already implemented several methods that produce deep clones.</span></span>  
  
 <span data-ttu-id="740b3-178">一个<xref:System.Windows.Freezable>是一种<xref:System.Windows.DependencyObject>，因此使用依赖项属性系统。</span><span class="sxs-lookup"><span data-stu-id="740b3-178">A <xref:System.Windows.Freezable> is a type of <xref:System.Windows.DependencyObject>, and therefore uses the dependency property system.</span></span> <span data-ttu-id="740b3-179">类属性不一定要依赖项属性，但使用依赖项属性可以减少需要编写，因为代码量<xref:System.Windows.Freezable>类的设计中考虑的依赖属性了。</span><span class="sxs-lookup"><span data-stu-id="740b3-179">Your class properties don't have to be dependency properties, but using dependency properties will reduce the amount of code you have to write, because the <xref:System.Windows.Freezable> class was designed with dependency properties in mind.</span></span> <span data-ttu-id="740b3-180">有关依赖属性系统的详细信息，请参阅[依赖属性概述](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="740b3-180">For more information about the dependency property system, see the [Dependency Properties Overview](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md).</span></span>  
  
 <span data-ttu-id="740b3-181">每个<xref:System.Windows.Freezable>子类必须重写<xref:System.Windows.Freezable.CreateInstanceCore%2A>方法。</span><span class="sxs-lookup"><span data-stu-id="740b3-181">Every <xref:System.Windows.Freezable> subclass must override the <xref:System.Windows.Freezable.CreateInstanceCore%2A> method.</span></span> <span data-ttu-id="740b3-182">如果您的类的所有数据使用依赖项属性时，您已完成。</span><span class="sxs-lookup"><span data-stu-id="740b3-182">If your class uses dependency properties for all its data, you're finished.</span></span>  
  
 <span data-ttu-id="740b3-183">如果您的类包含非依赖项属性数据成员，还必须重写以下方法：</span><span class="sxs-lookup"><span data-stu-id="740b3-183">If your class contains non-dependency property data members, you must also override the following methods:</span></span>  
  
-   <xref:System.Windows.Freezable.CloneCore%2A>  
  
-   <xref:System.Windows.Freezable.CloneCurrentValueCore%2A>  
  
-   <xref:System.Windows.Freezable.GetAsFrozenCore%2A>  
  
-   <xref:System.Windows.Freezable.GetCurrentValueAsFrozenCore%2A>  
  
-   <xref:System.Windows.Freezable.FreezeCore%2A>  
  
 <span data-ttu-id="740b3-184">此外必须遵守以下规则用于访问和写入不属于依赖项属性的数据成员：</span><span class="sxs-lookup"><span data-stu-id="740b3-184">You must also observe the following rules for accessing and writing to data members that are not dependency properties:</span></span>  
  
-   <span data-ttu-id="740b3-185">在任何开头[!INCLUDE[TLA#tla_api](../../../../includes/tlasharptla-api-md.md)]读取非依赖项属性数据成员，请调用<xref:System.Windows.Freezable.ReadPreamble%2A>方法。</span><span class="sxs-lookup"><span data-stu-id="740b3-185">At the beginning of any [!INCLUDE[TLA#tla_api](../../../../includes/tlasharptla-api-md.md)] that reads non-dependency property data members, call the <xref:System.Windows.Freezable.ReadPreamble%2A> method.</span></span>  
  
-   <span data-ttu-id="740b3-186">在开始任何 API，它将写入非依赖项属性数据成员时，调用<xref:System.Windows.Freezable.WritePreamble%2A>方法。</span><span class="sxs-lookup"><span data-stu-id="740b3-186">At the beginning of any API that writes non-dependency property data members, call the <xref:System.Windows.Freezable.WritePreamble%2A> method.</span></span> <span data-ttu-id="740b3-187">(调用后<xref:System.Windows.Freezable.WritePreamble%2A>中[!INCLUDE[TLA2#tla_api](../../../../includes/tla2sharptla-api-md.md)]，不需要进行额外调用<xref:System.Windows.Freezable.ReadPreamble%2A>如果还读取非依赖项属性数据成员。)</span><span class="sxs-lookup"><span data-stu-id="740b3-187">(Once you've called <xref:System.Windows.Freezable.WritePreamble%2A> in an [!INCLUDE[TLA2#tla_api](../../../../includes/tla2sharptla-api-md.md)], you don't need to make an additional call to <xref:System.Windows.Freezable.ReadPreamble%2A> if you also read non-dependency property data members.)</span></span>  
  
-   <span data-ttu-id="740b3-188">调用<xref:System.Windows.Freezable.WritePostscript%2A>方法，然后再退出写入非依赖项属性数据成员的方法。</span><span class="sxs-lookup"><span data-stu-id="740b3-188">Call the <xref:System.Windows.Freezable.WritePostscript%2A> method before exiting methods that write to non-dependency property data members.</span></span>  
  
 <span data-ttu-id="740b3-189">如果您的类包含的非依赖项属性数据成员<xref:System.Windows.DependencyObject>对象，还必须调用<xref:System.Windows.Freezable.OnFreezablePropertyChanged%2A>方法更改的它们的值，即使将该成员设置为每次`null`。</span><span class="sxs-lookup"><span data-stu-id="740b3-189">If your class contains non-dependency-property data members that are <xref:System.Windows.DependencyObject> objects, you must also call the <xref:System.Windows.Freezable.OnFreezablePropertyChanged%2A> method each time you change on of their values, even if you're setting the member to `null`.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="740b3-190">务必在开始各个<xref:System.Windows.Freezable>方法通过调用基实现重写。</span><span class="sxs-lookup"><span data-stu-id="740b3-190">It's very important that you begin each <xref:System.Windows.Freezable> method you override with a call to the base implementation.</span></span>  
  
 <span data-ttu-id="740b3-191">有关自定义的示例<xref:System.Windows.Freezable>类，请参阅[自定义动画示例](https://go.microsoft.com/fwlink/?LinkID=159981)。</span><span class="sxs-lookup"><span data-stu-id="740b3-191">For an example of a custom <xref:System.Windows.Freezable> class, see the [Custom Animation Sample](https://go.microsoft.com/fwlink/?LinkID=159981).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="740b3-192">请参阅</span><span class="sxs-lookup"><span data-stu-id="740b3-192">See Also</span></span>  
 <xref:System.Windows.Freezable>  
 [<span data-ttu-id="740b3-193">自定义动画示例</span><span class="sxs-lookup"><span data-stu-id="740b3-193">Custom Animation Sample</span></span>](https://go.microsoft.com/fwlink/?LinkID=159981)  
 [<span data-ttu-id="740b3-194">依赖项属性概述</span><span class="sxs-lookup"><span data-stu-id="740b3-194">Dependency Properties Overview</span></span>](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md)  
 [<span data-ttu-id="740b3-195">自定义依赖属性</span><span class="sxs-lookup"><span data-stu-id="740b3-195">Custom Dependency Properties</span></span>](../../../../docs/framework/wpf/advanced/custom-dependency-properties.md)
