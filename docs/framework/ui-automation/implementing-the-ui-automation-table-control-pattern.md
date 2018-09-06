---
title: 实现 UI 自动化 Table 控件模式
ms.date: 03/30/2017
helpviewer_keywords:
- UI Automation, Table control pattern
- control patterns, Table
- TableControl pattern
ms.assetid: 880cd85c-aa8c-4fb5-9369-45491d34bb78
author: Xansky
ms.author: mhopkins
manager: markl
ms.openlocfilehash: 7466a7cc25ac742483e21fc1ee4a631bd43bc5a3
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/05/2018
ms.locfileid: "43798539"
---
# <a name="implementing-the-ui-automation-table-control-pattern"></a><span data-ttu-id="3aa07-102">实现 UI 自动化 Table 控件模式</span><span class="sxs-lookup"><span data-stu-id="3aa07-102">Implementing the UI Automation Table Control Pattern</span></span>
> [!NOTE]
>  <span data-ttu-id="3aa07-103">本文档适用于想要使用 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 命名空间中定义的托管 <xref:System.Windows.Automation> 类的 .NET Framework 开发人员。</span><span class="sxs-lookup"><span data-stu-id="3aa07-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="3aa07-104">有关最新信息[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]，请参阅[Windows 自动化 API: UI 自动化](https://go.microsoft.com/fwlink/?LinkID=156746)。</span><span class="sxs-lookup"><span data-stu-id="3aa07-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](https://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="3aa07-105">本主题介绍实现 <xref:System.Windows.Automation.Provider.ITableProvider> 的准则和约定，包括有关属性、方法和事件的信息。</span><span class="sxs-lookup"><span data-stu-id="3aa07-105">This topic introduces guidelines and conventions for implementing <xref:System.Windows.Automation.Provider.ITableProvider>, including information about properties, methods, and events.</span></span> <span data-ttu-id="3aa07-106">本概述的结尾列出了指向其他参考资料的链接。</span><span class="sxs-lookup"><span data-stu-id="3aa07-106">Links to additional references are listed at the end of the overview.</span></span>  
  
 <span data-ttu-id="3aa07-107"><xref:System.Windows.Automation.TablePattern>控件模式用于支持充当子元素的集合的容器的控件。</span><span class="sxs-lookup"><span data-stu-id="3aa07-107">The <xref:System.Windows.Automation.TablePattern> control pattern is used to support controls that act as containers for a collection of child elements.</span></span> <span data-ttu-id="3aa07-108">此元素的子级必须实现<xref:System.Windows.Automation.Provider.ITableItemProvider>和组织可以按行和列进行遍历的二维逻辑坐标系统中。</span><span class="sxs-lookup"><span data-stu-id="3aa07-108">The children of this element must implement <xref:System.Windows.Automation.Provider.ITableItemProvider> and be organized in a two-dimensional logical coordinate system that can be traversed by row and column.</span></span> <span data-ttu-id="3aa07-109">此控件模式是类似于<xref:System.Windows.Automation.Provider.IGridProvider>，与任何控件实现的区别<xref:System.Windows.Automation.Provider.ITableProvider>还必须公开每个子元素的列和/或行标题关系。</span><span class="sxs-lookup"><span data-stu-id="3aa07-109">This control pattern is analogous to <xref:System.Windows.Automation.Provider.IGridProvider>, with the distinction that any control implementing <xref:System.Windows.Automation.Provider.ITableProvider> must also expose a column and/or row header relationship for each child element.</span></span> <span data-ttu-id="3aa07-110">有关实现此控件模式的控件示例，请参阅 [Control Pattern Mapping for UI Automation Clients](../../../docs/framework/ui-automation/control-pattern-mapping-for-ui-automation-clients.md)。</span><span class="sxs-lookup"><span data-stu-id="3aa07-110">For examples of controls that implement this control pattern, see [Control Pattern Mapping for UI Automation Clients](../../../docs/framework/ui-automation/control-pattern-mapping-for-ui-automation-clients.md).</span></span>  
  
<a name="Implementation_Guidelines_and_Conventions"></a>   
## <a name="implementation-guidelines-and-conventions"></a><span data-ttu-id="3aa07-111">实现准则和约定</span><span class="sxs-lookup"><span data-stu-id="3aa07-111">Implementation Guidelines and Conventions</span></span>  
 <span data-ttu-id="3aa07-112">在实现 Table 控件模式时，请注意以下准则和约定：</span><span class="sxs-lookup"><span data-stu-id="3aa07-112">When implementing the Table control pattern, note the following guidelines and conventions:</span></span>  
  
-   <span data-ttu-id="3aa07-113">对各个单元格的内容的访问是通过二维逻辑坐标系统或数组的所需的并发实现提供<xref:System.Windows.Automation.Provider.IGridProvider>。</span><span class="sxs-lookup"><span data-stu-id="3aa07-113">Access to the content of individual cells is through a two-dimensional logical coordinate system or array provided by the required concurrent implementation of <xref:System.Windows.Automation.Provider.IGridProvider>.</span></span>  
  
-   <span data-ttu-id="3aa07-114">列或行标头可包含在表对象中或可以为与表对象相关联的单独标头对象。</span><span class="sxs-lookup"><span data-stu-id="3aa07-114">A column or row header can be contained within a table object or be a separate header object that is associated with a table object.</span></span>  
  
-   <span data-ttu-id="3aa07-115">列和行标头可能包含主标头以及任何支持的标头。</span><span class="sxs-lookup"><span data-stu-id="3aa07-115">Column and row headers may include both a primary header as well as any supporting headers.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3aa07-116">这一概念将变得显而易见中[!INCLUDE[TLA#tla_xl](../../../includes/tlasharptla-xl-md.md)]电子表格用户定义的"名字"列。</span><span class="sxs-lookup"><span data-stu-id="3aa07-116">This concept becomes evident in a [!INCLUDE[TLA#tla_xl](../../../includes/tlasharptla-xl-md.md)] spreadsheet where a user has defined a "First name" column.</span></span> <span data-ttu-id="3aa07-117">此列现在有两个标头 — 用户定义的“名字”标头和应用程序分配的该列的字母数字名称。</span><span class="sxs-lookup"><span data-stu-id="3aa07-117">This column now has two headers—the "First name" header defined by the user and the alphanumeric designation for that column assigned by the application.</span></span>  
  
-   <span data-ttu-id="3aa07-118">请参阅[实现 UI 自动化 Grid 控件模式](../../../docs/framework/ui-automation/implementing-the-ui-automation-grid-control-pattern.md)相关的网格功能。</span><span class="sxs-lookup"><span data-stu-id="3aa07-118">See [Implementing the UI Automation Grid Control Pattern](../../../docs/framework/ui-automation/implementing-the-ui-automation-grid-control-pattern.md) for related grid functionality.</span></span>  
  
 <span data-ttu-id="3aa07-119">![具有复杂标题项的表。](../../../docs/framework/ui-automation/media/uia-tablepattern-complex-column-headers.PNG "UIA_TablePattern_Complex_Column_Headers")</span><span class="sxs-lookup"><span data-stu-id="3aa07-119">![Table with complex header items.](../../../docs/framework/ui-automation/media/uia-tablepattern-complex-column-headers.PNG "UIA_TablePattern_Complex_Column_Headers")</span></span>  
<span data-ttu-id="3aa07-120">具有复杂列标头的表示例</span><span class="sxs-lookup"><span data-stu-id="3aa07-120">Example of a Table with Complex Column Headers</span></span>  
  
 <span data-ttu-id="3aa07-121">![具有不明确的 RowOrColumnMajor 属性的表。](../../../docs/framework/ui-automation/media/uia-tablepattern-roworcolumnmajorproperty.PNG "UIA_TablePattern_RowOrColumnMajorProperty")</span><span class="sxs-lookup"><span data-stu-id="3aa07-121">![Table with ambiguous RowOrColumnMajor property.](../../../docs/framework/ui-automation/media/uia-tablepattern-roworcolumnmajorproperty.PNG "UIA_TablePattern_RowOrColumnMajorProperty")</span></span>  
<span data-ttu-id="3aa07-122">具有不明确的 RowOrColumnMajor 属性的表示例。</span><span class="sxs-lookup"><span data-stu-id="3aa07-122">Example of a Table with Ambiguous RowOrColumnMajor Property</span></span>  
  
<a name="Required_Members_for_ITableProvider"></a>   
## <a name="required-members-for-itableprovider"></a><span data-ttu-id="3aa07-123">ITableProvider 必需的成员</span><span class="sxs-lookup"><span data-stu-id="3aa07-123">Required Members for ITableProvider</span></span>  
 <span data-ttu-id="3aa07-124">ITableProvider 接口需要以下属性和方法。</span><span class="sxs-lookup"><span data-stu-id="3aa07-124">The following properties and methods are required for the ITableProvider interface.</span></span>  
  
|<span data-ttu-id="3aa07-125">必需的成员</span><span class="sxs-lookup"><span data-stu-id="3aa07-125">Required members</span></span>|<span data-ttu-id="3aa07-126">成员类型</span><span class="sxs-lookup"><span data-stu-id="3aa07-126">Member type</span></span>|<span data-ttu-id="3aa07-127">说明</span><span class="sxs-lookup"><span data-stu-id="3aa07-127">Notes</span></span>|  
|----------------------|-----------------|-----------|  
|<xref:System.Windows.Automation.Provider.ITableProvider.RowOrColumnMajor%2A>|<span data-ttu-id="3aa07-128">属性</span><span class="sxs-lookup"><span data-stu-id="3aa07-128">Property</span></span>|<span data-ttu-id="3aa07-129">无</span><span class="sxs-lookup"><span data-stu-id="3aa07-129">None</span></span>|  
|<xref:System.Windows.Automation.Provider.ITableProvider.GetColumnHeaders%2A>|<span data-ttu-id="3aa07-130">方法</span><span class="sxs-lookup"><span data-stu-id="3aa07-130">Method</span></span>|<span data-ttu-id="3aa07-131">无</span><span class="sxs-lookup"><span data-stu-id="3aa07-131">None</span></span>|  
|<xref:System.Windows.Automation.Provider.ITableProvider.GetRowHeaders%2A>|<span data-ttu-id="3aa07-132">方法</span><span class="sxs-lookup"><span data-stu-id="3aa07-132">Method</span></span>|<span data-ttu-id="3aa07-133">无</span><span class="sxs-lookup"><span data-stu-id="3aa07-133">None</span></span>|  
  
 <span data-ttu-id="3aa07-134">没有与此控件模式关联的事件。</span><span class="sxs-lookup"><span data-stu-id="3aa07-134">This control pattern has no associated events.</span></span>  
  
<a name="Exceptions"></a>   
## <a name="exceptions"></a><span data-ttu-id="3aa07-135">异常</span><span class="sxs-lookup"><span data-stu-id="3aa07-135">Exceptions</span></span>  
 <span data-ttu-id="3aa07-136">没有与此控件模式关联的异常。</span><span class="sxs-lookup"><span data-stu-id="3aa07-136">This control pattern has no associated exceptions.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3aa07-137">请参阅</span><span class="sxs-lookup"><span data-stu-id="3aa07-137">See Also</span></span>  
 [<span data-ttu-id="3aa07-138">UI 自动化控件模式概述</span><span class="sxs-lookup"><span data-stu-id="3aa07-138">UI Automation Control Patterns Overview</span></span>](../../../docs/framework/ui-automation/ui-automation-control-patterns-overview.md)  
 [<span data-ttu-id="3aa07-139">在 UI 自动化提供程序中支持控件模式</span><span class="sxs-lookup"><span data-stu-id="3aa07-139">Support Control Patterns in a UI Automation Provider</span></span>](../../../docs/framework/ui-automation/support-control-patterns-in-a-ui-automation-provider.md)  
 [<span data-ttu-id="3aa07-140">客户端的 UI 自动化控件模式</span><span class="sxs-lookup"><span data-stu-id="3aa07-140">UI Automation Control Patterns for Clients</span></span>](../../../docs/framework/ui-automation/ui-automation-control-patterns-for-clients.md)  
 [<span data-ttu-id="3aa07-141">实现 UI 自动化 TableItem 控件模式</span><span class="sxs-lookup"><span data-stu-id="3aa07-141">Implementing the UI Automation TableItem Control Pattern</span></span>](../../../docs/framework/ui-automation/implementing-the-ui-automation-tableitem-control-pattern.md)  
 [<span data-ttu-id="3aa07-142">实现 UI 自动化 Grid 控件模式</span><span class="sxs-lookup"><span data-stu-id="3aa07-142">Implementing the UI Automation Grid Control Pattern</span></span>](../../../docs/framework/ui-automation/implementing-the-ui-automation-grid-control-pattern.md)  
 [<span data-ttu-id="3aa07-143">UI 自动化树概述</span><span class="sxs-lookup"><span data-stu-id="3aa07-143">UI Automation Tree Overview</span></span>](../../../docs/framework/ui-automation/ui-automation-tree-overview.md)  
 [<span data-ttu-id="3aa07-144">在 UI 自动化中使用缓存</span><span class="sxs-lookup"><span data-stu-id="3aa07-144">Use Caching in UI Automation</span></span>](../../../docs/framework/ui-automation/use-caching-in-ui-automation.md)
