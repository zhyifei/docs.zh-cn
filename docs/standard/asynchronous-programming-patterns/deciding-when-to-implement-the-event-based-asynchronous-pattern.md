---
title: "确定何时实现基于事件的异步模式"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Event-based Asynchronous Pattern
- ProgressChangedEventArgs class
- BackgroundWorker component
- events [.NET Framework], asynchronous
- AsyncOperationManager class
- threading [.NET Framework], asynchronous features
- AsyncOperation class
- AsyncCompletedEventArgs class
ms.assetid: a00046aa-785d-4f7f-a8e5-d06475ea50da
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 48de1b736c251a61a2ad34975c77bc2bca139626
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="deciding-when-to-implement-the-event-based-asynchronous-pattern"></a><span data-ttu-id="1f027-102">确定何时实现基于事件的异步模式</span><span class="sxs-lookup"><span data-stu-id="1f027-102">Deciding When to Implement the Event-based Asynchronous Pattern</span></span>
<span data-ttu-id="1f027-103">基于事件的异步模式公开异步行为的类提供的模式。</span><span class="sxs-lookup"><span data-stu-id="1f027-103">The Event-based Asynchronous Pattern provides a pattern for exposing the asynchronous behavior of a class.</span></span> <span data-ttu-id="1f027-104">通过此模式中，引入[!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)]定义公开异步行为的两种模式： 基于异步模式<xref:System.IAsyncResult?displayProperty=nameWithType>接口，并且基于事件的模式。</span><span class="sxs-lookup"><span data-stu-id="1f027-104">With the introduction of this pattern, the [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] defines two patterns for exposing asynchronous behavior: the Asynchronous Pattern based on the <xref:System.IAsyncResult?displayProperty=nameWithType> interface, and the event-based pattern.</span></span> <span data-ttu-id="1f027-105">本主题介绍当它适合于你要实现这两种模式。</span><span class="sxs-lookup"><span data-stu-id="1f027-105">This topic describes when it is appropriate for you to implement both patterns.</span></span>  
  
 <span data-ttu-id="1f027-106">有关使用异步编程的详细信息<xref:System.IAsyncResult>接口，请参阅[基于事件的异步模式 (EAP)](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md)。</span><span class="sxs-lookup"><span data-stu-id="1f027-106">For more information about asynchronous programming with the <xref:System.IAsyncResult> interface, see [Event-based Asynchronous Pattern (EAP)](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md).</span></span>  
  
## <a name="general-principles"></a><span data-ttu-id="1f027-107">一般原则</span><span class="sxs-lookup"><span data-stu-id="1f027-107">General Principles</span></span>  
 <span data-ttu-id="1f027-108">一般情况下，应公开使用基于事件的异步模式尽可能的异步功能。</span><span class="sxs-lookup"><span data-stu-id="1f027-108">In general, you should expose asynchronous features using the Event-based Asynchronous Pattern whenever possible.</span></span> <span data-ttu-id="1f027-109">但是，没有基于事件的模式不能满足某些要求。</span><span class="sxs-lookup"><span data-stu-id="1f027-109">However, there are some requirements that the event-based pattern cannot meet.</span></span> <span data-ttu-id="1f027-110">在这些情况下，你可能需要实现<xref:System.IAsyncResult>除了基于事件的模式的模式。</span><span class="sxs-lookup"><span data-stu-id="1f027-110">In those cases, you may need to implement the <xref:System.IAsyncResult> pattern in addition to the event-based pattern.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1f027-111">很少<xref:System.IAsyncResult>模式，以实现没有还实现基于事件的模式。</span><span class="sxs-lookup"><span data-stu-id="1f027-111">It is rare for the <xref:System.IAsyncResult> pattern to be implemented without the event-based pattern also being implemented.</span></span>  
  
## <a name="guidelines"></a><span data-ttu-id="1f027-112">准则</span><span class="sxs-lookup"><span data-stu-id="1f027-112">Guidelines</span></span>  
 <span data-ttu-id="1f027-113">以下列表介绍应在何时实现基于事件的异步模式的准则：</span><span class="sxs-lookup"><span data-stu-id="1f027-113">The following list describes the guidelines for when you should implement Event-based Asynchronous Pattern:</span></span>  
  
-   <span data-ttu-id="1f027-114">使用作为默认 API 基于事件的模式公开异步行为为您的类。</span><span class="sxs-lookup"><span data-stu-id="1f027-114">Use the event-based pattern as the default API to expose asynchronous behavior for your class.</span></span>  
  
-   <span data-ttu-id="1f027-115">不会公开<xref:System.IAsyncResult>模式时你类主要用于在客户端应用程序，例如 Windows 窗体。</span><span class="sxs-lookup"><span data-stu-id="1f027-115">Do not expose the <xref:System.IAsyncResult> pattern when your class is primarily used in a client application, for example Windows Forms.</span></span>  
  
-   <span data-ttu-id="1f027-116">仅公开<xref:System.IAsyncResult>模式时才能满足你的要求。</span><span class="sxs-lookup"><span data-stu-id="1f027-116">Only expose the <xref:System.IAsyncResult> pattern when it is necessary for meeting your requirements.</span></span> <span data-ttu-id="1f027-117">例如，与现有 API 兼容性可能需要公开<xref:System.IAsyncResult>模式。</span><span class="sxs-lookup"><span data-stu-id="1f027-117">For example, compatibility with an existing API may require you to expose the <xref:System.IAsyncResult> pattern.</span></span>  
  
-   <span data-ttu-id="1f027-118">不会公开<xref:System.IAsyncResult>模式而不会还公开基于事件的模式。</span><span class="sxs-lookup"><span data-stu-id="1f027-118">Do not expose the <xref:System.IAsyncResult> pattern without also exposing the event-based pattern.</span></span>  
  
-   <span data-ttu-id="1f027-119">如果必须公开<xref:System.IAsyncResult>模式，应将其作为一个高级选项。</span><span class="sxs-lookup"><span data-stu-id="1f027-119">If you must expose the <xref:System.IAsyncResult> pattern, do so as an advanced option.</span></span> <span data-ttu-id="1f027-120">例如，如果你生成一个代理对象，生成默认情况下，用于生成的选项的基于事件的模式<xref:System.IAsyncResult>模式。</span><span class="sxs-lookup"><span data-stu-id="1f027-120">For example, if you generate a proxy object, generate the event-based pattern by default, with an option to generate the <xref:System.IAsyncResult> pattern.</span></span>  
  
-   <span data-ttu-id="1f027-121">在上生成基于事件的模式实现你<xref:System.IAsyncResult>模式实现。</span><span class="sxs-lookup"><span data-stu-id="1f027-121">Build your event-based pattern implementation on your <xref:System.IAsyncResult> pattern implementation.</span></span>  
  
-   <span data-ttu-id="1f027-122">避免将公开这两个基于事件的模式和<xref:System.IAsyncResult>同一类上的模式。</span><span class="sxs-lookup"><span data-stu-id="1f027-122">Avoid exposing both the event-based pattern and the <xref:System.IAsyncResult> pattern on the same class.</span></span> <span data-ttu-id="1f027-123">公开"更高级别的"类上的基于事件的模式和<xref:System.IAsyncResult>模式上的"降低级别"的类。</span><span class="sxs-lookup"><span data-stu-id="1f027-123">Expose the event-based pattern on "higher level" classes and the <xref:System.IAsyncResult> pattern on "lower level" classes.</span></span> <span data-ttu-id="1f027-124">例如，将基于事件的模式上进行比较<xref:System.Net.WebClient>组件<xref:System.IAsyncResult>模式上<xref:System.Web.HttpRequest>类。</span><span class="sxs-lookup"><span data-stu-id="1f027-124">For example, compare the event-based pattern on the <xref:System.Net.WebClient> component with the <xref:System.IAsyncResult> pattern on the <xref:System.Web.HttpRequest> class.</span></span>  
  
    -   <span data-ttu-id="1f027-125">公开基于事件的模式和<xref:System.IAsyncResult>兼容性需要它时位于同一类上的模式。</span><span class="sxs-lookup"><span data-stu-id="1f027-125">Expose the event-based pattern and the <xref:System.IAsyncResult> pattern on the same class when compatibility requires it.</span></span> <span data-ttu-id="1f027-126">例如，如果你已释放使用的 API<xref:System.IAsyncResult>模式中，你将需要保留<xref:System.IAsyncResult>向后兼容性模式。</span><span class="sxs-lookup"><span data-stu-id="1f027-126">For example, if you have already released an API that uses the <xref:System.IAsyncResult> pattern, you would need to retain the <xref:System.IAsyncResult> pattern for backward compatibility.</span></span>  
  
    -   <span data-ttu-id="1f027-127">公开基于事件的模式和<xref:System.IAsyncResult>模式同一类上，如果生成的对象模型复杂性超过带来的好处的分隔实现。</span><span class="sxs-lookup"><span data-stu-id="1f027-127">Expose the event-based pattern and the <xref:System.IAsyncResult> pattern on the same class if the resulting object model complexity outweighs the benefit of separating the implementations.</span></span> <span data-ttu-id="1f027-128">它是更好的做法公开比避免公开基于事件的模式单个类上的这两种模式。</span><span class="sxs-lookup"><span data-stu-id="1f027-128">It is better to expose both patterns on a single class than to avoid exposing the event-based pattern.</span></span>  
  
    -   <span data-ttu-id="1f027-129">如果你必须公开这两个基于事件的模式和<xref:System.IAsyncResult>上单个类，使用模式<xref:System.ComponentModel.EditorBrowsableAttribute>设置为<xref:System.ComponentModel.EditorBrowsableState.Advanced>标记<xref:System.IAsyncResult>模式实现作为一项高级功能。</span><span class="sxs-lookup"><span data-stu-id="1f027-129">If you must expose both the event-based pattern and <xref:System.IAsyncResult> pattern on a single class, use <xref:System.ComponentModel.EditorBrowsableAttribute> set to <xref:System.ComponentModel.EditorBrowsableState.Advanced> to mark the <xref:System.IAsyncResult> pattern implementation as an advanced feature.</span></span> <span data-ttu-id="1f027-130">这将指示设计环境中，如[!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)]IntelliSense，不希望显示<xref:System.IAsyncResult>属性和方法。</span><span class="sxs-lookup"><span data-stu-id="1f027-130">This indicates to design environments, such as [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] IntelliSense, not to display the <xref:System.IAsyncResult> properties and methods.</span></span> <span data-ttu-id="1f027-131">这些属性和方法仍将完全不可用，但通过 IntelliSense 工作的开发人员可以更加清晰的视图的 api。</span><span class="sxs-lookup"><span data-stu-id="1f027-131">These properties and methods are still fully usable, but the developer working through IntelliSense has a clearer view of the API.</span></span>  
  
## <a name="criteria-for-exposing-the-iasyncresult-pattern-in-addition-to-the-event-based-pattern"></a><span data-ttu-id="1f027-132">用于公开 IAsyncResult 模式除了基于事件的模式的条件</span><span class="sxs-lookup"><span data-stu-id="1f027-132">Criteria for Exposing the IAsyncResult Pattern in Addition to the Event-based Pattern</span></span>  
 <span data-ttu-id="1f027-133">虽然基于事件的异步模式有许多好处，前面所述的情况下，它具有某些缺点，你应注意如果性能是您最重要的要求。</span><span class="sxs-lookup"><span data-stu-id="1f027-133">While the Event-based Asynchronous Pattern has many benefits under the previously mentioned scenarios, it does have some drawbacks, which you should be aware of if performance is your most important requirement.</span></span>  
  
 <span data-ttu-id="1f027-134">有三种基于事件的模式不能解决的方案以及<xref:System.IAsyncResult>模式：</span><span class="sxs-lookup"><span data-stu-id="1f027-134">There are three scenarios that the event-based pattern does not address as well as the <xref:System.IAsyncResult> pattern:</span></span>  
  
-   <span data-ttu-id="1f027-135">阻止，正在等待上一个<xref:System.IAsyncResult></span><span class="sxs-lookup"><span data-stu-id="1f027-135">Blocking wait on one <xref:System.IAsyncResult></span></span>  
  
-   <span data-ttu-id="1f027-136">阻止正在等待多个<xref:System.IAsyncResult>对象</span><span class="sxs-lookup"><span data-stu-id="1f027-136">Blocking wait on many <xref:System.IAsyncResult> objects</span></span>  
  
-   <span data-ttu-id="1f027-137">轮询上完成<xref:System.IAsyncResult></span><span class="sxs-lookup"><span data-stu-id="1f027-137">Polling for completion on the <xref:System.IAsyncResult></span></span>  
  
 <span data-ttu-id="1f027-138">你可以通过使用基于事件的模式，来满足这些方案，但这种比较麻烦比使用<xref:System.IAsyncResult>模式。</span><span class="sxs-lookup"><span data-stu-id="1f027-138">You can address these scenarios by using the event-based pattern, but doing so is more cumbersome than using the <xref:System.IAsyncResult> pattern.</span></span>  
  
 <span data-ttu-id="1f027-139">开发人员通常使用<xref:System.IAsyncResult>对于通常具有非常高的性能要求的服务的模式。</span><span class="sxs-lookup"><span data-stu-id="1f027-139">Developers often use the <xref:System.IAsyncResult> pattern for services that typically have very high performance requirements.</span></span> <span data-ttu-id="1f027-140">例如，对完成情形轮询是高性能服务器技术。</span><span class="sxs-lookup"><span data-stu-id="1f027-140">For example, the polling for completion scenario is a high-performance server technique.</span></span>  
  
 <span data-ttu-id="1f027-141">此外，基于事件的模式是效率低于<xref:System.IAsyncResult>模式，因为它会创建更多的对象，尤其是<xref:System.EventArgs>，而是因为它将同步的线程。</span><span class="sxs-lookup"><span data-stu-id="1f027-141">Additionally, the event-based pattern is less efficient than the <xref:System.IAsyncResult> pattern because it creates more objects, especially <xref:System.EventArgs>, and because it synchronizes across threads.</span></span>  
  
 <span data-ttu-id="1f027-142">以下列表显示了一些建议，如果你决定使用，请按照<xref:System.IAsyncResult>模式：</span><span class="sxs-lookup"><span data-stu-id="1f027-142">The following list shows some recommendations to follow if you decide to use the <xref:System.IAsyncResult> pattern:</span></span>  
  
-   <span data-ttu-id="1f027-143">仅公开<xref:System.IAsyncResult>模式时特别需要支持<xref:System.Threading.WaitHandle>或<xref:System.IAsyncResult>对象。</span><span class="sxs-lookup"><span data-stu-id="1f027-143">Only expose the <xref:System.IAsyncResult> pattern when you specifically require support for <xref:System.Threading.WaitHandle> or <xref:System.IAsyncResult> objects.</span></span>  
  
-   <span data-ttu-id="1f027-144">仅公开<xref:System.IAsyncResult>模式时必须使用的现有 API<xref:System.IAsyncResult>模式。</span><span class="sxs-lookup"><span data-stu-id="1f027-144">Only expose the <xref:System.IAsyncResult> pattern when you have an existing API that uses the <xref:System.IAsyncResult> pattern.</span></span>  
  
-   <span data-ttu-id="1f027-145">如果你有现有 API 基于<xref:System.IAsyncResult>模式，请考虑也公开在下一个版本中的基于事件的模式。</span><span class="sxs-lookup"><span data-stu-id="1f027-145">If you have an existing API based on the <xref:System.IAsyncResult> pattern, consider also exposing the event-based pattern in your next release.</span></span>  
  
-   <span data-ttu-id="1f027-146">仅公开<xref:System.IAsyncResult>如果你有高性能要求的已验证的模式不满足由基于事件的模式，但它可以通过满足<xref:System.IAsyncResult>模式。</span><span class="sxs-lookup"><span data-stu-id="1f027-146">Only expose <xref:System.IAsyncResult> pattern if you have high performance requirements which you have verified cannot be met by the event-based pattern but can be met by the <xref:System.IAsyncResult> pattern.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1f027-147">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1f027-147">See Also</span></span>  
 [<span data-ttu-id="1f027-148">演练：实现支持基于事件的异步模式的组件</span><span class="sxs-lookup"><span data-stu-id="1f027-148">Walkthrough: Implementing a Component That Supports the Event-based Asynchronous Pattern</span></span>](../../../docs/standard/asynchronous-programming-patterns/component-that-supports-the-event-based-asynchronous-pattern.md)  
 [<span data-ttu-id="1f027-149">基于事件的异步模式 (EAP)</span><span class="sxs-lookup"><span data-stu-id="1f027-149">Event-based Asynchronous Pattern (EAP)</span></span>](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md)  
 [<span data-ttu-id="1f027-150">使用基于事件的异步模式进行多线程编程</span><span class="sxs-lookup"><span data-stu-id="1f027-150">Multithreaded Programming with the Event-based Asynchronous Pattern</span></span>](../../../docs/standard/asynchronous-programming-patterns/multithreaded-programming-with-the-event-based-asynchronous-pattern.md)  
 [<span data-ttu-id="1f027-151">实现基于事件的异步模式</span><span class="sxs-lookup"><span data-stu-id="1f027-151">Implementing the Event-based Asynchronous Pattern</span></span>](../../../docs/standard/asynchronous-programming-patterns/implementing-the-event-based-asynchronous-pattern.md)  
 [<span data-ttu-id="1f027-152">实现基于事件的异步模式的最佳做法</span><span class="sxs-lookup"><span data-stu-id="1f027-152">Best Practices for Implementing the Event-based Asynchronous Pattern</span></span>](../../../docs/standard/asynchronous-programming-patterns/best-practices-for-implementing-the-event-based-asynchronous-pattern.md)  
 [<span data-ttu-id="1f027-153">基于事件的异步模式概述</span><span class="sxs-lookup"><span data-stu-id="1f027-153">Event-based Asynchronous Pattern Overview</span></span>](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md)
