---
title: 实现 UI 自动化 TableItem 控件模式
ms.date: 03/30/2017
helpviewer_keywords:
- control patterns, Table Item
- UI Automation, Table Item control pattern
- TableItem control pattern
ms.assetid: ac178408-1485-436f-8d3e-eee3bf80cb24
author: Xansky
ms.author: mhopkins
ms.openlocfilehash: e5d5e82c5c2cfc48c98559bd6ce14519bdfaa522
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/25/2018
ms.locfileid: "47085913"
---
# <a name="implementing-the-ui-automation-tableitem-control-pattern"></a><span data-ttu-id="33e74-102">实现 UI 自动化 TableItem 控件模式</span><span class="sxs-lookup"><span data-stu-id="33e74-102">Implementing the UI Automation TableItem Control Pattern</span></span>
> [!NOTE]
>  <span data-ttu-id="33e74-103">本文档适用于想要使用 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 命名空间中定义的托管 <xref:System.Windows.Automation> 类的 .NET Framework 开发人员。</span><span class="sxs-lookup"><span data-stu-id="33e74-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="33e74-104">有关最新信息[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]，请参阅[Windows 自动化 API: UI 自动化](https://go.microsoft.com/fwlink/?LinkID=156746)。</span><span class="sxs-lookup"><span data-stu-id="33e74-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](https://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="33e74-105">本主题介绍的实现准则和约定<xref:System.Windows.Automation.Provider.ITableItemProvider>，包括有关事件和属性的信息。</span><span class="sxs-lookup"><span data-stu-id="33e74-105">This topic introduces guidelines and conventions for implementing <xref:System.Windows.Automation.Provider.ITableItemProvider>, including information about events and properties.</span></span> <span data-ttu-id="33e74-106">本概述的结尾列出了指向其他参考资料的链接。</span><span class="sxs-lookup"><span data-stu-id="33e74-106">Links to additional references are listed at the end of the overview.</span></span>  
  
 <span data-ttu-id="33e74-107"><xref:System.Windows.Automation.TableItemPattern>控件模式用于支持实现的容器的子控件<xref:System.Windows.Automation.Provider.ITableProvider>。</span><span class="sxs-lookup"><span data-stu-id="33e74-107">The <xref:System.Windows.Automation.TableItemPattern> control pattern is used to support child controls of containers that implement <xref:System.Windows.Automation.Provider.ITableProvider>.</span></span> <span data-ttu-id="33e74-108">对个别单元格功能的访问必需的并发实现提供<xref:System.Windows.Automation.Provider.IGridItemProvider>。</span><span class="sxs-lookup"><span data-stu-id="33e74-108">Access to individual cell functionality is provided by the required concurrent implementation of <xref:System.Windows.Automation.Provider.IGridItemProvider>.</span></span> <span data-ttu-id="33e74-109">此控件模式是类似于<xref:System.Windows.Automation.Provider.IGridItemProvider>与任何控件实现的区别<xref:System.Windows.Automation.Provider.ITableItemProvider>必须以编程方式公开各个单元格与其行和列信息之间的关系。</span><span class="sxs-lookup"><span data-stu-id="33e74-109">This control pattern is analogous to <xref:System.Windows.Automation.Provider.IGridItemProvider> with the distinction that any control implementing <xref:System.Windows.Automation.Provider.ITableItemProvider> must programmatically expose the relationship between the individual cell and its row and column information.</span></span> <span data-ttu-id="33e74-110">有关实现此控件模式的控件示例，请参阅 [Control Pattern Mapping for UI Automation Clients](../../../docs/framework/ui-automation/control-pattern-mapping-for-ui-automation-clients.md)。</span><span class="sxs-lookup"><span data-stu-id="33e74-110">For examples of controls that implement this control pattern, see [Control Pattern Mapping for UI Automation Clients](../../../docs/framework/ui-automation/control-pattern-mapping-for-ui-automation-clients.md).</span></span>  
  
<a name="Implementation_Guidelines_and_Conventions"></a>   
## <a name="implementation-guidelines-and-conventions"></a><span data-ttu-id="33e74-111">实现准则和约定</span><span class="sxs-lookup"><span data-stu-id="33e74-111">Implementation Guidelines and Conventions</span></span>  
  
-   <span data-ttu-id="33e74-112">有关相关的网格项功能，请参阅[实现 UI 自动化 GridItem 控件模式](../../../docs/framework/ui-automation/implementing-the-ui-automation-griditem-control-pattern.md)。</span><span class="sxs-lookup"><span data-stu-id="33e74-112">For related grid item functionality, see [Implementing the UI Automation GridItem Control Pattern](../../../docs/framework/ui-automation/implementing-the-ui-automation-griditem-control-pattern.md).</span></span>  
  
<a name="Required_Members_for_ITableItemProvider"></a>   
## <a name="required-members-for-itableitemprovider"></a><span data-ttu-id="33e74-113">ITableItemProvider 必需的成员</span><span class="sxs-lookup"><span data-stu-id="33e74-113">Required Members for ITableItemProvider</span></span>  
  
|<span data-ttu-id="33e74-114">必需的成员</span><span class="sxs-lookup"><span data-stu-id="33e74-114">Required member</span></span>|<span data-ttu-id="33e74-115">成员类型</span><span class="sxs-lookup"><span data-stu-id="33e74-115">Member type</span></span>|<span data-ttu-id="33e74-116">说明</span><span class="sxs-lookup"><span data-stu-id="33e74-116">Notes</span></span>|  
|---------------------|-----------------|-----------|  
|<xref:System.Windows.Automation.Provider.ITableItemProvider.GetColumnHeaderItems%2A>|<span data-ttu-id="33e74-117">方法</span><span class="sxs-lookup"><span data-stu-id="33e74-117">Method</span></span>|<span data-ttu-id="33e74-118">无</span><span class="sxs-lookup"><span data-stu-id="33e74-118">None</span></span>|  
|<xref:System.Windows.Automation.Provider.ITableItemProvider.GetRowHeaderItems%2A>|<span data-ttu-id="33e74-119">方法</span><span class="sxs-lookup"><span data-stu-id="33e74-119">Method</span></span>|<span data-ttu-id="33e74-120">无</span><span class="sxs-lookup"><span data-stu-id="33e74-120">None</span></span>|  
  
 <span data-ttu-id="33e74-121">没有与此控件模式关联的属性或事件。</span><span class="sxs-lookup"><span data-stu-id="33e74-121">This control pattern has no associated properties or events.</span></span>  
  
<a name="Exceptions"></a>   
## <a name="exceptions"></a><span data-ttu-id="33e74-122">异常</span><span class="sxs-lookup"><span data-stu-id="33e74-122">Exceptions</span></span>  
 <span data-ttu-id="33e74-123">没有与此控件模式关联的异常。</span><span class="sxs-lookup"><span data-stu-id="33e74-123">This control pattern has no associated exceptions.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="33e74-124">请参阅</span><span class="sxs-lookup"><span data-stu-id="33e74-124">See Also</span></span>  
 [<span data-ttu-id="33e74-125">UI 自动化控件模式概述</span><span class="sxs-lookup"><span data-stu-id="33e74-125">UI Automation Control Patterns Overview</span></span>](../../../docs/framework/ui-automation/ui-automation-control-patterns-overview.md)  
 [<span data-ttu-id="33e74-126">在 UI 自动化提供程序中支持控件模式</span><span class="sxs-lookup"><span data-stu-id="33e74-126">Support Control Patterns in a UI Automation Provider</span></span>](../../../docs/framework/ui-automation/support-control-patterns-in-a-ui-automation-provider.md)  
 [<span data-ttu-id="33e74-127">客户端的 UI 自动化控件模式</span><span class="sxs-lookup"><span data-stu-id="33e74-127">UI Automation Control Patterns for Clients</span></span>](../../../docs/framework/ui-automation/ui-automation-control-patterns-for-clients.md)  
 [<span data-ttu-id="33e74-128">实现 UI 自动化 Table 控件模式</span><span class="sxs-lookup"><span data-stu-id="33e74-128">Implementing the UI Automation Table Control Pattern</span></span>](../../../docs/framework/ui-automation/implementing-the-ui-automation-table-control-pattern.md)  
 [<span data-ttu-id="33e74-129">实现 UI 自动化 GridItem 控件模式</span><span class="sxs-lookup"><span data-stu-id="33e74-129">Implementing the UI Automation GridItem Control Pattern</span></span>](../../../docs/framework/ui-automation/implementing-the-ui-automation-griditem-control-pattern.md)  
 [<span data-ttu-id="33e74-130">UI 自动化树概述</span><span class="sxs-lookup"><span data-stu-id="33e74-130">UI Automation Tree Overview</span></span>](../../../docs/framework/ui-automation/ui-automation-tree-overview.md)  
 [<span data-ttu-id="33e74-131">在 UI 自动化中使用缓存</span><span class="sxs-lookup"><span data-stu-id="33e74-131">Use Caching in UI Automation</span></span>](../../../docs/framework/ui-automation/use-caching-in-ui-automation.md)
