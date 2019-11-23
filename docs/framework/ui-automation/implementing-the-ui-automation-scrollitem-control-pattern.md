---
title: 实现 UI 自动化 ScrollItem 控件模式
ms.date: 03/30/2017
helpviewer_keywords:
- control patterns, Scroll Item
- UI Automation, Scroll Item control pattern
- Scroll Item control pattern
ms.assetid: 903bab5c-80c1-44d7-bdc2-0a418893b987
ms.openlocfilehash: 1e33a64e66bc084e8cc5f75ece2ac2a4d7ea85aa
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74447136"
---
# <a name="implementing-the-ui-automation-scrollitem-control-pattern"></a><span data-ttu-id="2b8c6-102">实现 UI 自动化 ScrollItem 控件模式</span><span class="sxs-lookup"><span data-stu-id="2b8c6-102">Implementing the UI Automation ScrollItem Control Pattern</span></span>
> [!NOTE]
> <span data-ttu-id="2b8c6-103">本文档适用于想要使用 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 命名空间中定义的托管 <xref:System.Windows.Automation> 类的 .NET Framework 开发人员。</span><span class="sxs-lookup"><span data-stu-id="2b8c6-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="2b8c6-104">有关 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]的最新信息，请参阅 [Windows 自动化 API：UI 自动化](/windows/win32/winauto/entry-uiauto-win32)。</span><span class="sxs-lookup"><span data-stu-id="2b8c6-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](/windows/win32/winauto/entry-uiauto-win32).</span></span>  
  
 <span data-ttu-id="2b8c6-105">本主题介绍了实现 <xref:System.Windows.Automation.Provider.IScrollItemProvider> 的准则和约定，包括有关属性、方法和事件的信息。</span><span class="sxs-lookup"><span data-stu-id="2b8c6-105">This topic introduces guidelines and conventions for implementing the <xref:System.Windows.Automation.Provider.IScrollItemProvider>, including information about properties, methods, and events.</span></span> <span data-ttu-id="2b8c6-106">本主题的结尾列出了指向其他参考资料的链接。</span><span class="sxs-lookup"><span data-stu-id="2b8c6-106">Links to additional references are listed at the end of the topic.</span></span>  
  
 <span data-ttu-id="2b8c6-107"><xref:System.Windows.Automation.ScrollItemPattern> 控件模式用于支持实现 <xref:System.Windows.Automation.Provider.IScrollProvider> 的容器的各个子控件。</span><span class="sxs-lookup"><span data-stu-id="2b8c6-107">The <xref:System.Windows.Automation.ScrollItemPattern> control pattern is used to support individual child controls of containers that implement <xref:System.Windows.Automation.Provider.IScrollProvider>.</span></span> <span data-ttu-id="2b8c6-108">此控件模式充当子控件与其容器之间的通信通道，以确保容器可以更改其视区内当前可见的内容（或区域）以显示子控件。</span><span class="sxs-lookup"><span data-stu-id="2b8c6-108">This control pattern acts as a communication channel between a child control and its container to ensure that the container can change the currently visible content (or region) within its viewport to display the child control.</span></span> <span data-ttu-id="2b8c6-109">有关实现此控件模式的控件示例，请参阅 [Control Pattern Mapping for UI Automation Clients](control-pattern-mapping-for-ui-automation-clients.md)。</span><span class="sxs-lookup"><span data-stu-id="2b8c6-109">For examples of controls that implement this control pattern, see [Control Pattern Mapping for UI Automation Clients](control-pattern-mapping-for-ui-automation-clients.md).</span></span>  
  
<a name="Implementation_Guidelines_and_Conventions"></a>   
## <a name="implementation-guidelines-and-conventions"></a><span data-ttu-id="2b8c6-110">实现准则和约定</span><span class="sxs-lookup"><span data-stu-id="2b8c6-110">Implementation Guidelines and Conventions</span></span>  
 <span data-ttu-id="2b8c6-111">在实现“滚动项”控件模式时，请注意以下准则和约定：</span><span class="sxs-lookup"><span data-stu-id="2b8c6-111">When implementing the Scroll Item control pattern, note the following guidelines and conventions:</span></span>  
  
- <span data-ttu-id="2b8c6-112">包含在 Window 或 Canvas 控件内的项不需要实现 IScrollItemProvider 接口。</span><span class="sxs-lookup"><span data-stu-id="2b8c6-112">Items contained within a Window or Canvas control are not required to implement the IScrollItemProvider interface.</span></span> <span data-ttu-id="2b8c6-113">但是作为替代方法，它们必须公开 <xref:System.Windows.Automation.AutomationElementIdentifiers.BoundingRectangleProperty> 的一个有效位置。</span><span class="sxs-lookup"><span data-stu-id="2b8c6-113">As an alternative, however, they must expose a valid location for the <xref:System.Windows.Automation.AutomationElementIdentifiers.BoundingRectangleProperty>.</span></span> <span data-ttu-id="2b8c6-114">这将允许 UI 自动化客户端应用程序使用容器上的 <xref:System.Windows.Automation.ScrollPattern> 控件模式方法，以显示子项。</span><span class="sxs-lookup"><span data-stu-id="2b8c6-114">This will allow a UI Automation client application to use the <xref:System.Windows.Automation.ScrollPattern> control pattern methods on the container to display the child item.</span></span>  
  
<a name="Required_Members_for_IScrollItemProvider"></a>   
## <a name="required-members-for-iscrollitemprovider"></a><span data-ttu-id="2b8c6-115">IScrollItemProvider 必需的成员</span><span class="sxs-lookup"><span data-stu-id="2b8c6-115">Required Members for IScrollItemProvider</span></span>  
 <span data-ttu-id="2b8c6-116">需要以下方法来实现 IScrollProvider 接口。</span><span class="sxs-lookup"><span data-stu-id="2b8c6-116">The following method is required for implementing the IScrollProvider interface.</span></span>  
  
|<span data-ttu-id="2b8c6-117">必需的成员</span><span class="sxs-lookup"><span data-stu-id="2b8c6-117">Required members</span></span>|<span data-ttu-id="2b8c6-118">成员类型</span><span class="sxs-lookup"><span data-stu-id="2b8c6-118">Member type</span></span>|<span data-ttu-id="2b8c6-119">注意</span><span class="sxs-lookup"><span data-stu-id="2b8c6-119">Notes</span></span>|  
|----------------------|-----------------|-----------|  
|<xref:System.Windows.Automation.Provider.IScrollItemProvider.ScrollIntoView%2A>|<span data-ttu-id="2b8c6-120">-   Method</span><span class="sxs-lookup"><span data-stu-id="2b8c6-120">-   Method</span></span>|<span data-ttu-id="2b8c6-121">None</span><span class="sxs-lookup"><span data-stu-id="2b8c6-121">None</span></span>|  
  
 <span data-ttu-id="2b8c6-122">没有与此控件模式关联的属性或事件。</span><span class="sxs-lookup"><span data-stu-id="2b8c6-122">This control pattern has no associated properties or events.</span></span>  
  
<a name="Exceptions"></a>   
## <a name="exceptions"></a><span data-ttu-id="2b8c6-123">异常</span><span class="sxs-lookup"><span data-stu-id="2b8c6-123">Exceptions</span></span>  
 <span data-ttu-id="2b8c6-124">提供程序必须引发以下异常。</span><span class="sxs-lookup"><span data-stu-id="2b8c6-124">Providers must throw the following exceptions.</span></span>  
  
|<span data-ttu-id="2b8c6-125">异常类型</span><span class="sxs-lookup"><span data-stu-id="2b8c6-125">Exception Type</span></span>|<span data-ttu-id="2b8c6-126">条件</span><span class="sxs-lookup"><span data-stu-id="2b8c6-126">Condition</span></span>|  
|--------------------|---------------|  
|<xref:System.InvalidOperationException>|<span data-ttu-id="2b8c6-127">如果项无法滚动到视图：</span><span class="sxs-lookup"><span data-stu-id="2b8c6-127">If an item cannot be scrolled into view:</span></span><br /><br /> -   <xref:System.Windows.Automation.ScrollItemPattern.ScrollIntoView%2A>|  
  
## <a name="see-also"></a><span data-ttu-id="2b8c6-128">请参阅</span><span class="sxs-lookup"><span data-stu-id="2b8c6-128">See also</span></span>

- [<span data-ttu-id="2b8c6-129">UI 自动化控件模式概述</span><span class="sxs-lookup"><span data-stu-id="2b8c6-129">UI Automation Control Patterns Overview</span></span>](ui-automation-control-patterns-overview.md)
- [<span data-ttu-id="2b8c6-130">在 UI 自动化提供程序中支持控件模式</span><span class="sxs-lookup"><span data-stu-id="2b8c6-130">Support Control Patterns in a UI Automation Provider</span></span>](support-control-patterns-in-a-ui-automation-provider.md)
- [<span data-ttu-id="2b8c6-131">客户端的 UI 自动化控件模式</span><span class="sxs-lookup"><span data-stu-id="2b8c6-131">UI Automation Control Patterns for Clients</span></span>](ui-automation-control-patterns-for-clients.md)
- [<span data-ttu-id="2b8c6-132">UI 自动化树概述</span><span class="sxs-lookup"><span data-stu-id="2b8c6-132">UI Automation Tree Overview</span></span>](ui-automation-tree-overview.md)
- [<span data-ttu-id="2b8c6-133">在 UI 自动化中使用缓存</span><span class="sxs-lookup"><span data-stu-id="2b8c6-133">Use Caching in UI Automation</span></span>](use-caching-in-ui-automation.md)
