---
title: 实现 UI 自动化 ScrollItem 控件模式
ms.date: 03/30/2017
helpviewer_keywords:
- control patterns, Scroll Item
- UI Automation, Scroll Item control pattern
- Scroll Item control pattern
ms.assetid: 903bab5c-80c1-44d7-bdc2-0a418893b987
author: Xansky
ms.author: mhopkins
manager: markl
ms.openlocfilehash: 0346b70b4400c5f7a8d282d945e029701973dad1
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/09/2018
ms.locfileid: "44251623"
---
# <a name="implementing-the-ui-automation-scrollitem-control-pattern"></a><span data-ttu-id="e8b8d-102">实现 UI 自动化 ScrollItem 控件模式</span><span class="sxs-lookup"><span data-stu-id="e8b8d-102">Implementing the UI Automation ScrollItem Control Pattern</span></span>
> [!NOTE]
>  <span data-ttu-id="e8b8d-103">本文档适用于想要使用 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 命名空间中定义的托管 <xref:System.Windows.Automation> 类的 .NET Framework 开发人员。</span><span class="sxs-lookup"><span data-stu-id="e8b8d-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="e8b8d-104">有关最新信息[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]，请参阅[Windows 自动化 API: UI 自动化](https://go.microsoft.com/fwlink/?LinkID=156746)。</span><span class="sxs-lookup"><span data-stu-id="e8b8d-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](https://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="e8b8d-105">本主题介绍的实现准则和约定<xref:System.Windows.Automation.Provider.IScrollItemProvider>，包括有关属性、 方法和事件的信息。</span><span class="sxs-lookup"><span data-stu-id="e8b8d-105">This topic introduces guidelines and conventions for implementing the <xref:System.Windows.Automation.Provider.IScrollItemProvider>, including information about properties, methods, and events.</span></span> <span data-ttu-id="e8b8d-106">本主题的结尾列出了指向其他参考资料的链接。</span><span class="sxs-lookup"><span data-stu-id="e8b8d-106">Links to additional references are listed at the end of the topic.</span></span>  
  
 <span data-ttu-id="e8b8d-107"><xref:System.Windows.Automation.ScrollItemPattern>控件模式用于支持实现的容器的各个子控件<xref:System.Windows.Automation.Provider.IScrollProvider>。</span><span class="sxs-lookup"><span data-stu-id="e8b8d-107">The <xref:System.Windows.Automation.ScrollItemPattern> control pattern is used to support individual child controls of containers that implement <xref:System.Windows.Automation.Provider.IScrollProvider>.</span></span> <span data-ttu-id="e8b8d-108">此控件模式充当子控件与其容器之间的通信通道，以确保容器可以更改其视区内当前可见的内容（或区域）以显示子控件。</span><span class="sxs-lookup"><span data-stu-id="e8b8d-108">This control pattern acts as a communication channel between a child control and its container to ensure that the container can change the currently visible content (or region) within its viewport to display the child control.</span></span> <span data-ttu-id="e8b8d-109">有关实现此控件模式的控件示例，请参阅 [Control Pattern Mapping for UI Automation Clients](../../../docs/framework/ui-automation/control-pattern-mapping-for-ui-automation-clients.md)。</span><span class="sxs-lookup"><span data-stu-id="e8b8d-109">For examples of controls that implement this control pattern, see [Control Pattern Mapping for UI Automation Clients](../../../docs/framework/ui-automation/control-pattern-mapping-for-ui-automation-clients.md).</span></span>  
  
<a name="Implementation_Guidelines_and_Conventions"></a>   
## <a name="implementation-guidelines-and-conventions"></a><span data-ttu-id="e8b8d-110">实现准则和约定</span><span class="sxs-lookup"><span data-stu-id="e8b8d-110">Implementation Guidelines and Conventions</span></span>  
 <span data-ttu-id="e8b8d-111">在实现“滚动项”控件模式时，请注意以下准则和约定：</span><span class="sxs-lookup"><span data-stu-id="e8b8d-111">When implementing the Scroll Item control pattern, note the following guidelines and conventions:</span></span>  
  
-   <span data-ttu-id="e8b8d-112">包含在 Window 或 Canvas 控件内的项不需要实现 IScrollItemProvider 接口。</span><span class="sxs-lookup"><span data-stu-id="e8b8d-112">Items contained within a Window or Canvas control are not required to implement the IScrollItemProvider interface.</span></span> <span data-ttu-id="e8b8d-113">作为替代方法，但是，它们必须公开的有效位置<xref:System.Windows.Automation.AutomationElementIdentifiers.BoundingRectangleProperty>。</span><span class="sxs-lookup"><span data-stu-id="e8b8d-113">As an alternative, however, they must expose a valid location for the <xref:System.Windows.Automation.AutomationElementIdentifiers.BoundingRectangleProperty>.</span></span> <span data-ttu-id="e8b8d-114">这将允许 UI 自动化客户端应用程序，以使用<xref:System.Windows.Automation.ScrollPattern>控件模式上容器以显示子项目的方法。</span><span class="sxs-lookup"><span data-stu-id="e8b8d-114">This will allow a UI Automation client application to use the <xref:System.Windows.Automation.ScrollPattern> control pattern methods on the container to display the child item.</span></span>  
  
<a name="Required_Members_for_IScrollItemProvider"></a>   
## <a name="required-members-for-iscrollitemprovider"></a><span data-ttu-id="e8b8d-115">IScrollItemProvider 必需的成员</span><span class="sxs-lookup"><span data-stu-id="e8b8d-115">Required Members for IScrollItemProvider</span></span>  
 <span data-ttu-id="e8b8d-116">需要以下方法来实现 IScrollProvider 接口。</span><span class="sxs-lookup"><span data-stu-id="e8b8d-116">The following method is required for implementing the IScrollProvider interface.</span></span>  
  
|<span data-ttu-id="e8b8d-117">必需的成员</span><span class="sxs-lookup"><span data-stu-id="e8b8d-117">Required members</span></span>|<span data-ttu-id="e8b8d-118">成员类型</span><span class="sxs-lookup"><span data-stu-id="e8b8d-118">Member type</span></span>|<span data-ttu-id="e8b8d-119">说明</span><span class="sxs-lookup"><span data-stu-id="e8b8d-119">Notes</span></span>|  
|----------------------|-----------------|-----------|  
|<xref:System.Windows.Automation.Provider.IScrollItemProvider.ScrollIntoView%2A>|<span data-ttu-id="e8b8d-120">-方法</span><span class="sxs-lookup"><span data-stu-id="e8b8d-120">-   Method</span></span>|<span data-ttu-id="e8b8d-121">无</span><span class="sxs-lookup"><span data-stu-id="e8b8d-121">None</span></span>|  
  
 <span data-ttu-id="e8b8d-122">没有与此控件模式关联的属性或事件。</span><span class="sxs-lookup"><span data-stu-id="e8b8d-122">This control pattern has no associated properties or events.</span></span>  
  
<a name="Exceptions"></a>   
## <a name="exceptions"></a><span data-ttu-id="e8b8d-123">异常</span><span class="sxs-lookup"><span data-stu-id="e8b8d-123">Exceptions</span></span>  
 <span data-ttu-id="e8b8d-124">提供程序必须引发以下异常。</span><span class="sxs-lookup"><span data-stu-id="e8b8d-124">Providers must throw the following exceptions.</span></span>  
  
|<span data-ttu-id="e8b8d-125">异常类型</span><span class="sxs-lookup"><span data-stu-id="e8b8d-125">Exception Type</span></span>|<span data-ttu-id="e8b8d-126">条件</span><span class="sxs-lookup"><span data-stu-id="e8b8d-126">Condition</span></span>|  
|--------------------|---------------|  
|<xref:System.InvalidOperationException>|<span data-ttu-id="e8b8d-127">如果项无法滚动到视图：</span><span class="sxs-lookup"><span data-stu-id="e8b8d-127">If an item cannot be scrolled into view:</span></span><br /><br /> -   <xref:System.Windows.Automation.ScrollItemPattern.ScrollIntoView%2A>|  
  
## <a name="see-also"></a><span data-ttu-id="e8b8d-128">请参阅</span><span class="sxs-lookup"><span data-stu-id="e8b8d-128">See Also</span></span>  
 [<span data-ttu-id="e8b8d-129">UI 自动化控件模式概述</span><span class="sxs-lookup"><span data-stu-id="e8b8d-129">UI Automation Control Patterns Overview</span></span>](../../../docs/framework/ui-automation/ui-automation-control-patterns-overview.md)  
 [<span data-ttu-id="e8b8d-130">在 UI 自动化提供程序中支持控件模式</span><span class="sxs-lookup"><span data-stu-id="e8b8d-130">Support Control Patterns in a UI Automation Provider</span></span>](../../../docs/framework/ui-automation/support-control-patterns-in-a-ui-automation-provider.md)  
 [<span data-ttu-id="e8b8d-131">客户端的 UI 自动化控件模式</span><span class="sxs-lookup"><span data-stu-id="e8b8d-131">UI Automation Control Patterns for Clients</span></span>](../../../docs/framework/ui-automation/ui-automation-control-patterns-for-clients.md)  
 [<span data-ttu-id="e8b8d-132">UI 自动化树概述</span><span class="sxs-lookup"><span data-stu-id="e8b8d-132">UI Automation Tree Overview</span></span>](../../../docs/framework/ui-automation/ui-automation-tree-overview.md)  
 [<span data-ttu-id="e8b8d-133">在 UI 自动化中使用缓存</span><span class="sxs-lookup"><span data-stu-id="e8b8d-133">Use Caching in UI Automation</span></span>](../../../docs/framework/ui-automation/use-caching-in-ui-automation.md)
