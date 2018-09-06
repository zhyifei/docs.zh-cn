---
title: 实现 UI 自动化 GridItem 控件模式
ms.date: 03/30/2017
helpviewer_keywords:
- control patterns, GridItem
- UI Automation GridItem control pattern
- GridItem control pattern
ms.assetid: bffbae08-fe2a-42fd-ab84-f37187518916
author: Xansky
ms.author: mhopkins
manager: markl
ms.openlocfilehash: bfe2e62e98dd206d85e87d8885a1c58786a420fc
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/06/2018
ms.locfileid: "43855460"
---
# <a name="implementing-the-ui-automation-griditem-control-pattern"></a><span data-ttu-id="8dfff-102">实现 UI 自动化 GridItem 控件模式</span><span class="sxs-lookup"><span data-stu-id="8dfff-102">Implementing the UI Automation GridItem Control Pattern</span></span>
> [!NOTE]
>  <span data-ttu-id="8dfff-103">本文档适用于想要使用 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 命名空间中定义的托管 <xref:System.Windows.Automation> 类的 .NET Framework 开发人员。</span><span class="sxs-lookup"><span data-stu-id="8dfff-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="8dfff-104">有关最新信息[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]，请参阅[Windows 自动化 API: UI 自动化](https://go.microsoft.com/fwlink/?LinkID=156746)。</span><span class="sxs-lookup"><span data-stu-id="8dfff-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](https://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="8dfff-105">本主题介绍的实现准则和约定<xref:System.Windows.Automation.Provider.IGridItemProvider>，包括有关属性的信息。</span><span class="sxs-lookup"><span data-stu-id="8dfff-105">This topic introduces guidelines and conventions for implementing <xref:System.Windows.Automation.Provider.IGridItemProvider>, including information about properties.</span></span> <span data-ttu-id="8dfff-106">本概述的结尾列出了指向其他参考资料的链接。</span><span class="sxs-lookup"><span data-stu-id="8dfff-106">Links to additional references are listed at the end of the overview.</span></span>  
  
 <span data-ttu-id="8dfff-107"><xref:System.Windows.Automation.GridItemPattern>控件模式用于支持实现的容器的各个子控件<xref:System.Windows.Automation.Provider.IGridProvider>。</span><span class="sxs-lookup"><span data-stu-id="8dfff-107">The <xref:System.Windows.Automation.GridItemPattern> control pattern is used to support individual child controls of containers that implement <xref:System.Windows.Automation.Provider.IGridProvider>.</span></span> <span data-ttu-id="8dfff-108">有关实现此控件模式的控件示例，请参阅 [Control Pattern Mapping for UI Automation Clients](../../../docs/framework/ui-automation/control-pattern-mapping-for-ui-automation-clients.md)。</span><span class="sxs-lookup"><span data-stu-id="8dfff-108">For examples of controls that implement this control pattern, see [Control Pattern Mapping for UI Automation Clients](../../../docs/framework/ui-automation/control-pattern-mapping-for-ui-automation-clients.md).</span></span>  
  
<a name="Implementation_Guidelines_and_Conventions"></a>   
## <a name="implementation-guidelines-and-conventions"></a><span data-ttu-id="8dfff-109">实现准则和约定</span><span class="sxs-lookup"><span data-stu-id="8dfff-109">Implementation Guidelines and Conventions</span></span>  
 <span data-ttu-id="8dfff-110">在实现时<xref:System.Windows.Automation.Provider.IGridProvider>，请注意以下准则和约定：</span><span class="sxs-lookup"><span data-stu-id="8dfff-110">When implementing <xref:System.Windows.Automation.Provider.IGridProvider>, note the following guidelines and conventions:</span></span>  
  
-   <span data-ttu-id="8dfff-111">网格坐标从零开始，左上角单元格坐标为 (0, 0)。</span><span class="sxs-lookup"><span data-stu-id="8dfff-111">Grid coordinates are zero-based with the upper left cell having coordinates (0, 0).</span></span>  
  
-   <span data-ttu-id="8dfff-112">合并单元格将报告其<xref:System.Windows.Automation.Provider.IGridItemProvider.Row%2A>和<xref:System.Windows.Automation.Provider.IGridItemProvider.Column%2A>属性基于其基本定位单元格定义的 UI 自动化提供程序。</span><span class="sxs-lookup"><span data-stu-id="8dfff-112">Merged cells will report their <xref:System.Windows.Automation.Provider.IGridItemProvider.Row%2A> and <xref:System.Windows.Automation.Provider.IGridItemProvider.Column%2A> properties based on their underlying anchor cell as defined by the UI Automation provider.</span></span> <span data-ttu-id="8dfff-113">通常，它将是最左上方的行或列。</span><span class="sxs-lookup"><span data-stu-id="8dfff-113">Typically, it will be the topmost and leftmost row or column.</span></span>  
  
-   <span data-ttu-id="8dfff-114"><xref:System.Windows.Automation.Provider.IGridItemProvider> 不提供如合并或拆分单元格网格的活动操作。</span><span class="sxs-lookup"><span data-stu-id="8dfff-114"><xref:System.Windows.Automation.Provider.IGridItemProvider> does not provide for active manipulation of the grid such as merging or splitting cells.</span></span>  
  
-   <span data-ttu-id="8dfff-115">控制实现<xref:System.Windows.Automation.Provider.IGridItemProvider>通常可以遍历 （即，UI 自动化客户端可以移动到相邻控件） 使用键盘。</span><span class="sxs-lookup"><span data-stu-id="8dfff-115">Controls that implement <xref:System.Windows.Automation.Provider.IGridItemProvider> can typically be traversed (that is, a UI Automation client can move to adjacent controls) by using the keyboard.</span></span>  
  
<a name="Required_Members_for_IGridItemProvider"></a>   
## <a name="required-members-for-igriditemprovider"></a><span data-ttu-id="8dfff-116">IGridItemProvider 必需的成员</span><span class="sxs-lookup"><span data-stu-id="8dfff-116">Required Members for IGridItemProvider</span></span>  
 <span data-ttu-id="8dfff-117">实现 <xref:System.Windows.Automation.Provider.IGridItemProvider> 需要以下属性和方法。</span><span class="sxs-lookup"><span data-stu-id="8dfff-117">The following properties and methods are required for implementing <xref:System.Windows.Automation.Provider.IGridItemProvider>.</span></span>  
  
|<span data-ttu-id="8dfff-118">必需的成员</span><span class="sxs-lookup"><span data-stu-id="8dfff-118">Required members</span></span>|<span data-ttu-id="8dfff-119">成员类型</span><span class="sxs-lookup"><span data-stu-id="8dfff-119">Member type</span></span>|<span data-ttu-id="8dfff-120">说明</span><span class="sxs-lookup"><span data-stu-id="8dfff-120">Notes</span></span>|  
|----------------------|-----------------|-----------|  
|<xref:System.Windows.Automation.Provider.IGridItemProvider.Row%2A>|<span data-ttu-id="8dfff-121">属性</span><span class="sxs-lookup"><span data-stu-id="8dfff-121">Property</span></span>|<span data-ttu-id="8dfff-122">无</span><span class="sxs-lookup"><span data-stu-id="8dfff-122">None</span></span>|  
|<xref:System.Windows.Automation.Provider.IGridItemProvider.Column%2A>|<span data-ttu-id="8dfff-123">属性</span><span class="sxs-lookup"><span data-stu-id="8dfff-123">Property</span></span>|<span data-ttu-id="8dfff-124">无</span><span class="sxs-lookup"><span data-stu-id="8dfff-124">None</span></span>|  
|<xref:System.Windows.Automation.Provider.IGridItemProvider.RowSpan%2A>|<span data-ttu-id="8dfff-125">属性</span><span class="sxs-lookup"><span data-stu-id="8dfff-125">Property</span></span>|<span data-ttu-id="8dfff-126">无</span><span class="sxs-lookup"><span data-stu-id="8dfff-126">None</span></span>|  
|<xref:System.Windows.Automation.Provider.IGridItemProvider.ColumnSpan%2A>|<span data-ttu-id="8dfff-127">属性</span><span class="sxs-lookup"><span data-stu-id="8dfff-127">Property</span></span>|<span data-ttu-id="8dfff-128">无</span><span class="sxs-lookup"><span data-stu-id="8dfff-128">None</span></span>|  
|<xref:System.Windows.Automation.Provider.IGridItemProvider.ContainingGrid%2A>|<span data-ttu-id="8dfff-129">属性</span><span class="sxs-lookup"><span data-stu-id="8dfff-129">Property</span></span>|<span data-ttu-id="8dfff-130">无</span><span class="sxs-lookup"><span data-stu-id="8dfff-130">None</span></span>|  
  
 <span data-ttu-id="8dfff-131">没有与此控件模式关联的方法或事件。</span><span class="sxs-lookup"><span data-stu-id="8dfff-131">This control pattern has no associated methods or events.</span></span>  
  
<a name="Exceptions"></a>   
## <a name="exceptions"></a><span data-ttu-id="8dfff-132">异常</span><span class="sxs-lookup"><span data-stu-id="8dfff-132">Exceptions</span></span>  
 <span data-ttu-id="8dfff-133">没有与此控件模式关联的异常。</span><span class="sxs-lookup"><span data-stu-id="8dfff-133">This control pattern has no associated exceptions.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8dfff-134">请参阅</span><span class="sxs-lookup"><span data-stu-id="8dfff-134">See Also</span></span>  
 [<span data-ttu-id="8dfff-135">UI 自动化控件模式概述</span><span class="sxs-lookup"><span data-stu-id="8dfff-135">UI Automation Control Patterns Overview</span></span>](../../../docs/framework/ui-automation/ui-automation-control-patterns-overview.md)  
 [<span data-ttu-id="8dfff-136">在 UI 自动化提供程序中支持控件模式</span><span class="sxs-lookup"><span data-stu-id="8dfff-136">Support Control Patterns in a UI Automation Provider</span></span>](../../../docs/framework/ui-automation/support-control-patterns-in-a-ui-automation-provider.md)  
 [<span data-ttu-id="8dfff-137">客户端的 UI 自动化控件模式</span><span class="sxs-lookup"><span data-stu-id="8dfff-137">UI Automation Control Patterns for Clients</span></span>](../../../docs/framework/ui-automation/ui-automation-control-patterns-for-clients.md)  
 [<span data-ttu-id="8dfff-138">实现 UI 自动化 Grid 控件模式</span><span class="sxs-lookup"><span data-stu-id="8dfff-138">Implementing the UI Automation Grid Control Pattern</span></span>](../../../docs/framework/ui-automation/implementing-the-ui-automation-grid-control-pattern.md)  
 [<span data-ttu-id="8dfff-139">UI 自动化树概述</span><span class="sxs-lookup"><span data-stu-id="8dfff-139">UI Automation Tree Overview</span></span>](../../../docs/framework/ui-automation/ui-automation-tree-overview.md)  
 [<span data-ttu-id="8dfff-140">在 UI 自动化中使用缓存</span><span class="sxs-lookup"><span data-stu-id="8dfff-140">Use Caching in UI Automation</span></span>](../../../docs/framework/ui-automation/use-caching-in-ui-automation.md)
