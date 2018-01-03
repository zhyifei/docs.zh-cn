---
title: "实现 UI 自动化 Table 控件模式"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-bcl
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- UI Automation, Table control pattern
- control patterns, Table
- TableControl pattern
ms.assetid: 880cd85c-aa8c-4fb5-9369-45491d34bb78
caps.latest.revision: "19"
author: Xansky
ms.author: mhopkins
manager: markl
ms.workload: dotnet
ms.openlocfilehash: 1e0b3c09948b53363888ae133cd0c4d9f9ae8f05
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="implementing-the-ui-automation-table-control-pattern"></a><span data-ttu-id="81c5b-102">实现 UI 自动化 Table 控件模式</span><span class="sxs-lookup"><span data-stu-id="81c5b-102">Implementing the UI Automation Table Control Pattern</span></span>
> [!NOTE]
>  <span data-ttu-id="81c5b-103">本文档适用于想要使用 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 命名空间中定义的托管 <xref:System.Windows.Automation> 类的 .NET Framework 开发人员。</span><span class="sxs-lookup"><span data-stu-id="81c5b-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="81c5b-104">有关 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]的最新信息，请参阅 [Windows 自动化 API：UI 自动化](http://go.microsoft.com/fwlink/?LinkID=156746)。</span><span class="sxs-lookup"><span data-stu-id="81c5b-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](http://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="81c5b-105">本主题介绍实现 <xref:System.Windows.Automation.Provider.ITableProvider> 的准则和约定，包括有关属性、方法和事件的信息。</span><span class="sxs-lookup"><span data-stu-id="81c5b-105">This topic introduces guidelines and conventions for implementing <xref:System.Windows.Automation.Provider.ITableProvider>, including information about properties, methods, and events.</span></span> <span data-ttu-id="81c5b-106">本概述的结尾列出了指向其他参考资料的链接。</span><span class="sxs-lookup"><span data-stu-id="81c5b-106">Links to additional references are listed at the end of the overview.</span></span>  
  
 <span data-ttu-id="81c5b-107"><xref:System.Windows.Automation.TablePattern>控件模式用于支持充当子元素的集合的容器的控件。</span><span class="sxs-lookup"><span data-stu-id="81c5b-107">The <xref:System.Windows.Automation.TablePattern> control pattern is used to support controls that act as containers for a collection of child elements.</span></span> <span data-ttu-id="81c5b-108">此元素的子级必须实现<xref:System.Windows.Automation.Provider.ITableItemProvider>并且可以按行和列进行遍历的二维逻辑坐标系统中进行组织。</span><span class="sxs-lookup"><span data-stu-id="81c5b-108">The children of this element must implement <xref:System.Windows.Automation.Provider.ITableItemProvider> and be organized in a two-dimensional logical coordinate system that can be traversed by row and column.</span></span> <span data-ttu-id="81c5b-109">此控件模式相当于<xref:System.Windows.Automation.Provider.IGridProvider>，任何控件实现区别<xref:System.Windows.Automation.Provider.ITableProvider>还必须公开每个子元素的列和/或行标头关系。</span><span class="sxs-lookup"><span data-stu-id="81c5b-109">This control pattern is analogous to <xref:System.Windows.Automation.Provider.IGridProvider>, with the distinction that any control implementing <xref:System.Windows.Automation.Provider.ITableProvider> must also expose a column and/or row header relationship for each child element.</span></span> <span data-ttu-id="81c5b-110">有关实现此控件模式的控件示例，请参阅 [Control Pattern Mapping for UI Automation Clients](../../../docs/framework/ui-automation/control-pattern-mapping-for-ui-automation-clients.md)。</span><span class="sxs-lookup"><span data-stu-id="81c5b-110">For examples of controls that implement this control pattern, see [Control Pattern Mapping for UI Automation Clients](../../../docs/framework/ui-automation/control-pattern-mapping-for-ui-automation-clients.md).</span></span>  
  
<a name="Implementation_Guidelines_and_Conventions"></a>   
## <a name="implementation-guidelines-and-conventions"></a><span data-ttu-id="81c5b-111">实现准则和约定</span><span class="sxs-lookup"><span data-stu-id="81c5b-111">Implementation Guidelines and Conventions</span></span>  
 <span data-ttu-id="81c5b-112">在实现 Table 控件模式时，请注意以下准则和约定：</span><span class="sxs-lookup"><span data-stu-id="81c5b-112">When implementing the Table control pattern, note the following guidelines and conventions:</span></span>  
  
-   <span data-ttu-id="81c5b-113">对各个单元格的内容的访问是通过二维逻辑坐标系统或数组的所需的并发实现提供<xref:System.Windows.Automation.Provider.IGridProvider>。</span><span class="sxs-lookup"><span data-stu-id="81c5b-113">Access to the content of individual cells is through a two-dimensional logical coordinate system or array provided by the required concurrent implementation of <xref:System.Windows.Automation.Provider.IGridProvider>.</span></span>  
  
-   <span data-ttu-id="81c5b-114">列或行标头可包含在表对象中或可以为与表对象相关联的单独标头对象。</span><span class="sxs-lookup"><span data-stu-id="81c5b-114">A column or row header can be contained within a table object or be a separate header object that is associated with a table object.</span></span>  
  
-   <span data-ttu-id="81c5b-115">列和行标头可能包含主标头以及任何支持的标头。</span><span class="sxs-lookup"><span data-stu-id="81c5b-115">Column and row headers may include both a primary header as well as any supporting headers.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="81c5b-116">这一概念变得显而易见中[!INCLUDE[TLA#tla_xl](../../../includes/tlasharptla-xl-md.md)]电子表格，其中用户已定义的"名字"列。</span><span class="sxs-lookup"><span data-stu-id="81c5b-116">This concept becomes evident in a [!INCLUDE[TLA#tla_xl](../../../includes/tlasharptla-xl-md.md)] spreadsheet where a user has defined a "First name" column.</span></span> <span data-ttu-id="81c5b-117">此列现在有两个标头 — 用户定义的“名字”标头和应用程序分配的该列的字母数字名称。</span><span class="sxs-lookup"><span data-stu-id="81c5b-117">This column now has two headers—the "First name" header defined by the user and the alphanumeric designation for that column assigned by the application.</span></span>  
  
-   <span data-ttu-id="81c5b-118">请参阅[实现 UI 自动化 Grid 控件模式](../../../docs/framework/ui-automation/implementing-the-ui-automation-grid-control-pattern.md)相关的网格功能。</span><span class="sxs-lookup"><span data-stu-id="81c5b-118">See [Implementing the UI Automation Grid Control Pattern](../../../docs/framework/ui-automation/implementing-the-ui-automation-grid-control-pattern.md) for related grid functionality.</span></span>  
  
 <span data-ttu-id="81c5b-119">![具有复杂标题项的表。] (../../../docs/framework/ui-automation/media/uia-tablepattern-complex-column-headers.PNG "UIA_TablePattern_Complex_Column_Headers")</span><span class="sxs-lookup"><span data-stu-id="81c5b-119">![Table with complex header items.](../../../docs/framework/ui-automation/media/uia-tablepattern-complex-column-headers.PNG "UIA_TablePattern_Complex_Column_Headers")</span></span>  
<span data-ttu-id="81c5b-120">具有复杂列标头的表示例</span><span class="sxs-lookup"><span data-stu-id="81c5b-120">Example of a Table with Complex Column Headers</span></span>  
  
 <span data-ttu-id="81c5b-121">![具有不明确的 RowOrColumnMajor 属性表。] (../../../docs/framework/ui-automation/media/uia-tablepattern-roworcolumnmajorproperty.PNG "UIA_TablePattern_RowOrColumnMajorProperty")</span><span class="sxs-lookup"><span data-stu-id="81c5b-121">![Table with ambiguous RowOrColumnMajor property.](../../../docs/framework/ui-automation/media/uia-tablepattern-roworcolumnmajorproperty.PNG "UIA_TablePattern_RowOrColumnMajorProperty")</span></span>  
<span data-ttu-id="81c5b-122">具有不明确的 RowOrColumnMajor 属性的表示例。</span><span class="sxs-lookup"><span data-stu-id="81c5b-122">Example of a Table with Ambiguous RowOrColumnMajor Property</span></span>  
  
<a name="Required_Members_for_ITableProvider"></a>   
## <a name="required-members-for-itableprovider"></a><span data-ttu-id="81c5b-123">ITableProvider 必需的成员</span><span class="sxs-lookup"><span data-stu-id="81c5b-123">Required Members for ITableProvider</span></span>  
 <span data-ttu-id="81c5b-124">ITableProvider 接口需要以下属性和方法。</span><span class="sxs-lookup"><span data-stu-id="81c5b-124">The following properties and methods are required for the ITableProvider interface.</span></span>  
  
|<span data-ttu-id="81c5b-125">必需的成员</span><span class="sxs-lookup"><span data-stu-id="81c5b-125">Required members</span></span>|<span data-ttu-id="81c5b-126">成员类型</span><span class="sxs-lookup"><span data-stu-id="81c5b-126">Member type</span></span>|<span data-ttu-id="81c5b-127">备注</span><span class="sxs-lookup"><span data-stu-id="81c5b-127">Notes</span></span>|  
|----------------------|-----------------|-----------|  
|<xref:System.Windows.Automation.Provider.ITableProvider.RowOrColumnMajor%2A>|<span data-ttu-id="81c5b-128">属性</span><span class="sxs-lookup"><span data-stu-id="81c5b-128">Property</span></span>|<span data-ttu-id="81c5b-129">无</span><span class="sxs-lookup"><span data-stu-id="81c5b-129">None</span></span>|  
|<xref:System.Windows.Automation.Provider.ITableProvider.GetColumnHeaders%2A>|<span data-ttu-id="81c5b-130">方法</span><span class="sxs-lookup"><span data-stu-id="81c5b-130">Method</span></span>|<span data-ttu-id="81c5b-131">无</span><span class="sxs-lookup"><span data-stu-id="81c5b-131">None</span></span>|  
|<xref:System.Windows.Automation.Provider.ITableProvider.GetRowHeaders%2A>|<span data-ttu-id="81c5b-132">方法</span><span class="sxs-lookup"><span data-stu-id="81c5b-132">Method</span></span>|<span data-ttu-id="81c5b-133">无</span><span class="sxs-lookup"><span data-stu-id="81c5b-133">None</span></span>|  
  
 <span data-ttu-id="81c5b-134">没有与此控件模式关联的事件。</span><span class="sxs-lookup"><span data-stu-id="81c5b-134">This control pattern has no associated events.</span></span>  
  
<a name="Exceptions"></a>   
## <a name="exceptions"></a><span data-ttu-id="81c5b-135">异常</span><span class="sxs-lookup"><span data-stu-id="81c5b-135">Exceptions</span></span>  
 <span data-ttu-id="81c5b-136">没有与此控件模式关联的异常。</span><span class="sxs-lookup"><span data-stu-id="81c5b-136">This control pattern has no associated exceptions.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="81c5b-137">请参阅</span><span class="sxs-lookup"><span data-stu-id="81c5b-137">See Also</span></span>  
 [<span data-ttu-id="81c5b-138">UI 自动化控件模式概述</span><span class="sxs-lookup"><span data-stu-id="81c5b-138">UI Automation Control Patterns Overview</span></span>](../../../docs/framework/ui-automation/ui-automation-control-patterns-overview.md)  
 [<span data-ttu-id="81c5b-139">在 UI 自动化提供程序中支持控件模式</span><span class="sxs-lookup"><span data-stu-id="81c5b-139">Support Control Patterns in a UI Automation Provider</span></span>](../../../docs/framework/ui-automation/support-control-patterns-in-a-ui-automation-provider.md)  
 [<span data-ttu-id="81c5b-140">客户端的 UI 自动化控件模式</span><span class="sxs-lookup"><span data-stu-id="81c5b-140">UI Automation Control Patterns for Clients</span></span>](../../../docs/framework/ui-automation/ui-automation-control-patterns-for-clients.md)  
 [<span data-ttu-id="81c5b-141">实现 UI 自动化 TableItem 控件模式</span><span class="sxs-lookup"><span data-stu-id="81c5b-141">Implementing the UI Automation TableItem Control Pattern</span></span>](../../../docs/framework/ui-automation/implementing-the-ui-automation-tableitem-control-pattern.md)  
 [<span data-ttu-id="81c5b-142">实现 UI 自动化 Grid 控件模式</span><span class="sxs-lookup"><span data-stu-id="81c5b-142">Implementing the UI Automation Grid Control Pattern</span></span>](../../../docs/framework/ui-automation/implementing-the-ui-automation-grid-control-pattern.md)  
 [<span data-ttu-id="81c5b-143">UI 自动化树概述</span><span class="sxs-lookup"><span data-stu-id="81c5b-143">UI Automation Tree Overview</span></span>](../../../docs/framework/ui-automation/ui-automation-tree-overview.md)  
 [<span data-ttu-id="81c5b-144">在 UI 自动化中使用缓存</span><span class="sxs-lookup"><span data-stu-id="81c5b-144">Use Caching in UI Automation</span></span>](../../../docs/framework/ui-automation/use-caching-in-ui-automation.md)
