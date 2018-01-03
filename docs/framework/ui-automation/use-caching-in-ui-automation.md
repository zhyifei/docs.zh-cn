---
title: "在 UI 自动化中使用缓存"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-bcl
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- caching, UI Automation
- UI Automation, caching
ms.assetid: ec722dff-6009-4279-b86a-e18d3fa94ebf
caps.latest.revision: "14"
author: Xansky
ms.author: mhopkins
manager: markl
ms.workload: dotnet
ms.openlocfilehash: 808ba16cbacfad2cc255ae40e2cbad3178350afc
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="use-caching-in-ui-automation"></a><span data-ttu-id="cff86-102">在 UI 自动化中使用缓存</span><span class="sxs-lookup"><span data-stu-id="cff86-102">Use Caching in UI Automation</span></span>
> [!NOTE]
>  <span data-ttu-id="cff86-103">本文档适用于想要使用 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 命名空间中定义的托管 <xref:System.Windows.Automation> 类的 .NET Framework 开发人员。</span><span class="sxs-lookup"><span data-stu-id="cff86-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="cff86-104">有关 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]的最新信息，请参阅 [Windows 自动化 API：UI 自动化](http://go.microsoft.com/fwlink/?LinkID=156746)。</span><span class="sxs-lookup"><span data-stu-id="cff86-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](http://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="cff86-105">本部分演示如何实现 <xref:System.Windows.Automation.AutomationElement> 属性和控件模式的缓存。</span><span class="sxs-lookup"><span data-stu-id="cff86-105">This section shows how to implement caching of <xref:System.Windows.Automation.AutomationElement> properties and control patterns.</span></span>  
  
### <a name="activate-a-cache-request"></a><span data-ttu-id="cff86-106">激活缓存请求</span><span class="sxs-lookup"><span data-stu-id="cff86-106">Activate a Cache Request</span></span>  
  
1.  <span data-ttu-id="cff86-107">创建 <xref:System.Windows.Automation.CacheRequest>。</span><span class="sxs-lookup"><span data-stu-id="cff86-107">Create a <xref:System.Windows.Automation.CacheRequest>.</span></span>  
  
2.  <span data-ttu-id="cff86-108">使用 <xref:System.Windows.Automation.CacheRequest.Add%2A>指定要缓存的属性和模式。</span><span class="sxs-lookup"><span data-stu-id="cff86-108">Specify properties and patterns to cache by using <xref:System.Windows.Automation.CacheRequest.Add%2A>.</span></span>  
  
3.  <span data-ttu-id="cff86-109">通过设置 <xref:System.Windows.Automation.CacheRequest.TreeScope%2A> 属性来指定缓存的范围。</span><span class="sxs-lookup"><span data-stu-id="cff86-109">Specify the scope of caching by setting the <xref:System.Windows.Automation.CacheRequest.TreeScope%2A> property.</span></span>  
  
4.  <span data-ttu-id="cff86-110">通过设置 <xref:System.Windows.Automation.CacheRequest.TreeFilter%2A> 属性来指定子树视图。</span><span class="sxs-lookup"><span data-stu-id="cff86-110">Specify the view of the subtree by setting the <xref:System.Windows.Automation.CacheRequest.TreeFilter%2A> property.</span></span>  
  
5.  <span data-ttu-id="cff86-111">如果想通过不检索对对象的完全引用来提高效率，请将 <xref:System.Windows.Automation.CacheRequest.AutomationElementMode%2A> 属性设置为 <xref:System.Windows.Automation.AutomationElementMode.None> 。</span><span class="sxs-lookup"><span data-stu-id="cff86-111">Set the <xref:System.Windows.Automation.CacheRequest.AutomationElementMode%2A> property to <xref:System.Windows.Automation.AutomationElementMode.None> if you wish to increase efficiency by not retrieving a full reference to objects.</span></span> <span data-ttu-id="cff86-112">（这将导致无法从那些对象中检索当前值。）</span><span class="sxs-lookup"><span data-stu-id="cff86-112">(This will make it impossible to retrieve current values from those objects.)</span></span>  
  
6.  <span data-ttu-id="cff86-113">使用 <xref:System.Windows.Automation.CacheRequest.Activate%2A> 块（ `using` 中的`Using` ）中的 [!INCLUDE[TLA#tla_visualbnet](../../../includes/tlasharptla-visualbnet-md.md)]激活请求。</span><span class="sxs-lookup"><span data-stu-id="cff86-113">Activate the request by using <xref:System.Windows.Automation.CacheRequest.Activate%2A> within a `using` block (`Using` in [!INCLUDE[TLA#tla_visualbnet](../../../includes/tlasharptla-visualbnet-md.md)]).</span></span>  
  
 <span data-ttu-id="cff86-114">在获得 <xref:System.Windows.Automation.AutomationElement> 对象或订阅事件后，通过使用 <xref:System.Windows.Automation.CacheRequest.Pop%2A> （如果使用了 <xref:System.Windows.Automation.CacheRequest.Push%2A> ）或处理 <xref:System.Windows.Automation.CacheRequest.Activate%2A>创建的对象来禁用请求。</span><span class="sxs-lookup"><span data-stu-id="cff86-114">After obtaining <xref:System.Windows.Automation.AutomationElement> objects or subscribing to events, deactivate the request by using <xref:System.Windows.Automation.CacheRequest.Pop%2A> (if <xref:System.Windows.Automation.CacheRequest.Push%2A> was used) or by disposing the object created by <xref:System.Windows.Automation.CacheRequest.Activate%2A>.</span></span> <span data-ttu-id="cff86-115">使用 <xref:System.Windows.Automation.CacheRequest.Activate%2A> 块（ `using` 中的`Using` ）中的 [!INCLUDE[TLA#tla_visualbnet](../../../includes/tlasharptla-visualbnet-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="cff86-115">(Use <xref:System.Windows.Automation.CacheRequest.Activate%2A> in a `using` block (`Using` in [!INCLUDE[TLA#tla_visualbnet](../../../includes/tlasharptla-visualbnet-md.md)]).</span></span>  
  
### <a name="cache-automationelement-properties"></a><span data-ttu-id="cff86-116">缓存 AutomationElement 属性</span><span class="sxs-lookup"><span data-stu-id="cff86-116">Cache AutomationElement Properties</span></span>  
  
1.  <span data-ttu-id="cff86-117">当 <xref:System.Windows.Automation.CacheRequest> 处于活动状态时，使用 <xref:System.Windows.Automation.AutomationElement> 或 <xref:System.Windows.Automation.AutomationElement.FindFirst%2A> 获取 <xref:System.Windows.Automation.AutomationElement.FindAll%2A>对象，或者获取 <xref:System.Windows.Automation.AutomationElement> 并将其作为 <xref:System.Windows.Automation.CacheRequest> 处于活动状态时注册的事件的源。</span><span class="sxs-lookup"><span data-stu-id="cff86-117">While a <xref:System.Windows.Automation.CacheRequest> is active, obtain <xref:System.Windows.Automation.AutomationElement> objects by using <xref:System.Windows.Automation.AutomationElement.FindFirst%2A> or <xref:System.Windows.Automation.AutomationElement.FindAll%2A>; or obtain an <xref:System.Windows.Automation.AutomationElement> as the source of an event that you registered for when the <xref:System.Windows.Automation.CacheRequest> was active.</span></span> <span data-ttu-id="cff86-118">（也可以通过下面的方法创建缓存：将 <xref:System.Windows.Automation.CacheRequest> 传递给 GetUpdatedCache 或 <xref:System.Windows.Automation.TreeWalker> 方法之一。）</span><span class="sxs-lookup"><span data-stu-id="cff86-118">(You can also create a cache by passing a <xref:System.Windows.Automation.CacheRequest> to GetUpdatedCache or one of the <xref:System.Windows.Automation.TreeWalker> methods.)</span></span>  
  
2.  <span data-ttu-id="cff86-119">使用 <xref:System.Windows.Automation.AutomationElement.GetCachedPropertyValue%2A> 或从 <xref:System.Windows.Automation.AutomationElement.Cached%2A> 的 <xref:System.Windows.Automation.AutomationElement>属性中检索属性。</span><span class="sxs-lookup"><span data-stu-id="cff86-119">Use <xref:System.Windows.Automation.AutomationElement.GetCachedPropertyValue%2A> or retrieve a property from the <xref:System.Windows.Automation.AutomationElement.Cached%2A> property of the <xref:System.Windows.Automation.AutomationElement>.</span></span>  
  
### <a name="obtain-cached-patterns-and-their-properties"></a><span data-ttu-id="cff86-120">获取缓存模式及其属性</span><span class="sxs-lookup"><span data-stu-id="cff86-120">Obtain Cached Patterns and Their Properties</span></span>  
  
1.  <span data-ttu-id="cff86-121">当 <xref:System.Windows.Automation.CacheRequest> 处于活动状态时，使用 <xref:System.Windows.Automation.AutomationElement> 或 <xref:System.Windows.Automation.AutomationElement.FindFirst%2A> 获取 <xref:System.Windows.Automation.AutomationElement.FindAll%2A>对象，或者获取 <xref:System.Windows.Automation.AutomationElement> 并将其作为 <xref:System.Windows.Automation.CacheRequest> 处于活动状态时注册的事件的源。</span><span class="sxs-lookup"><span data-stu-id="cff86-121">While a <xref:System.Windows.Automation.CacheRequest> is active, obtain <xref:System.Windows.Automation.AutomationElement> objects by using <xref:System.Windows.Automation.AutomationElement.FindFirst%2A> or <xref:System.Windows.Automation.AutomationElement.FindAll%2A>; or obtain an <xref:System.Windows.Automation.AutomationElement> as the source of an event that you registered for when the <xref:System.Windows.Automation.CacheRequest> was active.</span></span> <span data-ttu-id="cff86-122">（也可以通过下面的方法创建缓存：将 <xref:System.Windows.Automation.CacheRequest> 传递给 GetUpdatedCache 或 <xref:System.Windows.Automation.TreeWalker> 方法之一。）</span><span class="sxs-lookup"><span data-stu-id="cff86-122">(You can also create a cache by passing a <xref:System.Windows.Automation.CacheRequest> to GetUpdatedCache or one of the <xref:System.Windows.Automation.TreeWalker> methods.)</span></span>  
  
2.  <span data-ttu-id="cff86-123">使用 <xref:System.Windows.Automation.AutomationElement.GetCachedPattern%2A> 或 <xref:System.Windows.Automation.AutomationElement.TryGetCachedPattern%2A> 检索缓存的模式。</span><span class="sxs-lookup"><span data-stu-id="cff86-123">Use <xref:System.Windows.Automation.AutomationElement.GetCachedPattern%2A> or <xref:System.Windows.Automation.AutomationElement.TryGetCachedPattern%2A> to retrieve a cached pattern.</span></span>  
  
3.  <span data-ttu-id="cff86-124">控件模式的 `Cached` 属性中检索属性值。</span><span class="sxs-lookup"><span data-stu-id="cff86-124">Retrieve property values from the `Cached` property of the control pattern.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cff86-125">示例</span><span class="sxs-lookup"><span data-stu-id="cff86-125">Example</span></span>  
 <span data-ttu-id="cff86-126">下面的代码示例使用 <xref:System.Windows.Automation.CacheRequest.Activate%2A> 激活 <xref:System.Windows.Automation.CacheRequest>，演示了缓存的各个方面。</span><span class="sxs-lookup"><span data-stu-id="cff86-126">The following code example shows various aspects of caching, using <xref:System.Windows.Automation.CacheRequest.Activate%2A> to activate the <xref:System.Windows.Automation.CacheRequest>.</span></span>  
  
 [!code-csharp[UIAClient_snip#107](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAClient_snip/CSharp/ClientForm.cs#107)]
 [!code-vb[UIAClient_snip#107](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAClient_snip/VisualBasic/ClientForm.vb#107)]  
  
## <a name="example"></a><span data-ttu-id="cff86-127">示例</span><span class="sxs-lookup"><span data-stu-id="cff86-127">Example</span></span>  
 <span data-ttu-id="cff86-128">下面的代码示例使用 <xref:System.Windows.Automation.CacheRequest.Push%2A> 激活 <xref:System.Windows.Automation.CacheRequest>，演示了缓存的各个方面。</span><span class="sxs-lookup"><span data-stu-id="cff86-128">The following code example shows various aspects of caching, using <xref:System.Windows.Automation.CacheRequest.Push%2A> to activate the <xref:System.Windows.Automation.CacheRequest>.</span></span> <span data-ttu-id="cff86-129">除非希望嵌套缓存请求，否则最好是使用 <xref:System.Windows.Automation.CacheRequest.Activate%2A>。</span><span class="sxs-lookup"><span data-stu-id="cff86-129">Except when you wish to nest cache requests, it is preferable to use <xref:System.Windows.Automation.CacheRequest.Activate%2A>.</span></span>  
  
 [!code-csharp[UIAClient_snip#108](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAClient_snip/CSharp/ClientForm.cs#108)]
 [!code-vb[UIAClient_snip#108](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAClient_snip/VisualBasic/ClientForm.vb#108)]  
  
## <a name="see-also"></a><span data-ttu-id="cff86-130">请参阅</span><span class="sxs-lookup"><span data-stu-id="cff86-130">See Also</span></span>  
 [<span data-ttu-id="cff86-131">在 UI 自动化客户端中缓存</span><span class="sxs-lookup"><span data-stu-id="cff86-131">Caching in UI Automation Clients</span></span>](../../../docs/framework/ui-automation/caching-in-ui-automation-clients.md)
