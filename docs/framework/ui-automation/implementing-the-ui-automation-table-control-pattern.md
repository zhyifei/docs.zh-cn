---
title: 实现 UI 自动化 Table 控件模式
ms.date: 03/30/2017
helpviewer_keywords:
- UI Automation, Table control pattern
- control patterns, Table
- TableControl pattern
ms.assetid: 880cd85c-aa8c-4fb5-9369-45491d34bb78
ms.openlocfilehash: 1fec3671f017ae6c6864537805e6c793b5f9046b
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2019
ms.locfileid: "73458141"
---
# <a name="implementing-the-ui-automation-table-control-pattern"></a><span data-ttu-id="3431c-102">实现 UI 自动化 Table 控件模式</span><span class="sxs-lookup"><span data-stu-id="3431c-102">Implementing the UI Automation Table Control Pattern</span></span>
> [!NOTE]
> <span data-ttu-id="3431c-103">本文档适用于想要使用 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 命名空间中定义的托管 <xref:System.Windows.Automation> 类的 .NET Framework 开发人员。</span><span class="sxs-lookup"><span data-stu-id="3431c-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="3431c-104">有关 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]的最新信息，请参阅 [Windows 自动化 API：UI 自动化](https://go.microsoft.com/fwlink/?LinkID=156746)。</span><span class="sxs-lookup"><span data-stu-id="3431c-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](https://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="3431c-105">本主题介绍实现 <xref:System.Windows.Automation.Provider.ITableProvider>的准则和约定，包括有关属性、方法和事件的信息。</span><span class="sxs-lookup"><span data-stu-id="3431c-105">This topic introduces guidelines and conventions for implementing <xref:System.Windows.Automation.Provider.ITableProvider>, including information about properties, methods, and events.</span></span> <span data-ttu-id="3431c-106">本概述的结尾列出了指向其他参考资料的链接。</span><span class="sxs-lookup"><span data-stu-id="3431c-106">Links to additional references are listed at the end of the overview.</span></span>  
  
 <span data-ttu-id="3431c-107"><xref:System.Windows.Automation.TablePattern> 控件模式用于支持作为子元素集合的容器的控件。</span><span class="sxs-lookup"><span data-stu-id="3431c-107">The <xref:System.Windows.Automation.TablePattern> control pattern is used to support controls that act as containers for a collection of child elements.</span></span> <span data-ttu-id="3431c-108">此元素的子元素必须实现 <xref:System.Windows.Automation.Provider.ITableItemProvider> ，并且在可以按行和列进行遍历的二维逻辑坐标系统中进行组织。</span><span class="sxs-lookup"><span data-stu-id="3431c-108">The children of this element must implement <xref:System.Windows.Automation.Provider.ITableItemProvider> and be organized in a two-dimensional logical coordinate system that can be traversed by row and column.</span></span> <span data-ttu-id="3431c-109">此控件模式类似于 <xref:System.Windows.Automation.Provider.IGridProvider>，区别在于任何实现 <xref:System.Windows.Automation.Provider.ITableProvider> 的控件都还必须公开每个子元素的列和/或行标头关系。</span><span class="sxs-lookup"><span data-stu-id="3431c-109">This control pattern is analogous to <xref:System.Windows.Automation.Provider.IGridProvider>, with the distinction that any control implementing <xref:System.Windows.Automation.Provider.ITableProvider> must also expose a column and/or row header relationship for each child element.</span></span> <span data-ttu-id="3431c-110">有关实现此控件模式的控件示例，请参阅 [Control Pattern Mapping for UI Automation Clients](control-pattern-mapping-for-ui-automation-clients.md)。</span><span class="sxs-lookup"><span data-stu-id="3431c-110">For examples of controls that implement this control pattern, see [Control Pattern Mapping for UI Automation Clients](control-pattern-mapping-for-ui-automation-clients.md).</span></span>  
  
<a name="Implementation_Guidelines_and_Conventions"></a>   
## <a name="implementation-guidelines-and-conventions"></a><span data-ttu-id="3431c-111">实现准则和约定</span><span class="sxs-lookup"><span data-stu-id="3431c-111">Implementation Guidelines and Conventions</span></span>  
 <span data-ttu-id="3431c-112">在实现 Table 控件模式时，请注意以下准则和约定：</span><span class="sxs-lookup"><span data-stu-id="3431c-112">When implementing the Table control pattern, note the following guidelines and conventions:</span></span>  
  
- <span data-ttu-id="3431c-113">对个别单元格的内容的访问是通过二维逻辑坐标系统或由所需的 <xref:System.Windows.Automation.Provider.IGridProvider> 的并发实现提供的数组来实现。</span><span class="sxs-lookup"><span data-stu-id="3431c-113">Access to the content of individual cells is through a two-dimensional logical coordinate system or array provided by the required concurrent implementation of <xref:System.Windows.Automation.Provider.IGridProvider>.</span></span>  
  
- <span data-ttu-id="3431c-114">列或行标头可包含在表对象中或可以为与表对象相关联的单独标头对象。</span><span class="sxs-lookup"><span data-stu-id="3431c-114">A column or row header can be contained within a table object or be a separate header object that is associated with a table object.</span></span>  
  
- <span data-ttu-id="3431c-115">列和行标头可能包含主标头以及任何支持的标头。</span><span class="sxs-lookup"><span data-stu-id="3431c-115">Column and row headers may include both a primary header as well as any supporting headers.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="3431c-116">在 Microsoft Excel 电子表格中，此概念在用户定义了 "First name" 列的情况下变得明显。</span><span class="sxs-lookup"><span data-stu-id="3431c-116">This concept becomes evident in a Microsoft Excel spreadsheet where a user has defined a "First name" column.</span></span> <span data-ttu-id="3431c-117">此列现在有两个标头 — 用户定义的“名字”标头和应用程序分配的该列的字母数字名称。</span><span class="sxs-lookup"><span data-stu-id="3431c-117">This column now has two headers—the "First name" header defined by the user and the alphanumeric designation for that column assigned by the application.</span></span>  
  
- <span data-ttu-id="3431c-118">有关相关网格功能，请参阅[实现 UI 自动化网格控件模式](implementing-the-ui-automation-grid-control-pattern.md)。</span><span class="sxs-lookup"><span data-stu-id="3431c-118">See [Implementing the UI Automation Grid Control Pattern](implementing-the-ui-automation-grid-control-pattern.md) for related grid functionality.</span></span>  
  
 <span data-ttu-id="3431c-119">![具有复杂标头项的表。](./media/uia-tablepattern-complex-column-headers.PNG "UIA_TablePattern_Complex_Column_Headers")</span><span class="sxs-lookup"><span data-stu-id="3431c-119">![Table with complex header items.](./media/uia-tablepattern-complex-column-headers.PNG "UIA_TablePattern_Complex_Column_Headers")</span></span>  
<span data-ttu-id="3431c-120">具有复杂列标头的表示例</span><span class="sxs-lookup"><span data-stu-id="3431c-120">Example of a Table with Complex Column Headers</span></span>  
  
 <span data-ttu-id="3431c-121">![具有不明确的 RowOrColumnMajor 属性的表。](./media/uia-tablepattern-roworcolumnmajorproperty.PNG "UIA_TablePattern_RowOrColumnMajorProperty")</span><span class="sxs-lookup"><span data-stu-id="3431c-121">![Table with ambiguous RowOrColumnMajor property.](./media/uia-tablepattern-roworcolumnmajorproperty.PNG "UIA_TablePattern_RowOrColumnMajorProperty")</span></span>  
<span data-ttu-id="3431c-122">具有不明确的 RowOrColumnMajor 属性的表示例。</span><span class="sxs-lookup"><span data-stu-id="3431c-122">Example of a Table with Ambiguous RowOrColumnMajor Property</span></span>  
  
<a name="Required_Members_for_ITableProvider"></a>   
## <a name="required-members-for-itableprovider"></a><span data-ttu-id="3431c-123">ITableProvider 必需的成员</span><span class="sxs-lookup"><span data-stu-id="3431c-123">Required Members for ITableProvider</span></span>  
 <span data-ttu-id="3431c-124">ITableProvider 接口需要以下属性和方法。</span><span class="sxs-lookup"><span data-stu-id="3431c-124">The following properties and methods are required for the ITableProvider interface.</span></span>  
  
|<span data-ttu-id="3431c-125">必需的成员</span><span class="sxs-lookup"><span data-stu-id="3431c-125">Required members</span></span>|<span data-ttu-id="3431c-126">成员类型</span><span class="sxs-lookup"><span data-stu-id="3431c-126">Member type</span></span>|<span data-ttu-id="3431c-127">注意</span><span class="sxs-lookup"><span data-stu-id="3431c-127">Notes</span></span>|  
|----------------------|-----------------|-----------|  
|<xref:System.Windows.Automation.Provider.ITableProvider.RowOrColumnMajor%2A>|<span data-ttu-id="3431c-128">Property</span><span class="sxs-lookup"><span data-stu-id="3431c-128">Property</span></span>|<span data-ttu-id="3431c-129">None</span><span class="sxs-lookup"><span data-stu-id="3431c-129">None</span></span>|  
|<xref:System.Windows.Automation.Provider.ITableProvider.GetColumnHeaders%2A>|<span data-ttu-id="3431c-130">方法</span><span class="sxs-lookup"><span data-stu-id="3431c-130">Method</span></span>|<span data-ttu-id="3431c-131">None</span><span class="sxs-lookup"><span data-stu-id="3431c-131">None</span></span>|  
|<xref:System.Windows.Automation.Provider.ITableProvider.GetRowHeaders%2A>|<span data-ttu-id="3431c-132">方法</span><span class="sxs-lookup"><span data-stu-id="3431c-132">Method</span></span>|<span data-ttu-id="3431c-133">None</span><span class="sxs-lookup"><span data-stu-id="3431c-133">None</span></span>|  
  
 <span data-ttu-id="3431c-134">没有与此控件模式关联的事件。</span><span class="sxs-lookup"><span data-stu-id="3431c-134">This control pattern has no associated events.</span></span>  
  
<a name="Exceptions"></a>   
## <a name="exceptions"></a><span data-ttu-id="3431c-135">异常</span><span class="sxs-lookup"><span data-stu-id="3431c-135">Exceptions</span></span>  
 <span data-ttu-id="3431c-136">没有与此控件模式关联的异常。</span><span class="sxs-lookup"><span data-stu-id="3431c-136">This control pattern has no associated exceptions.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3431c-137">请参阅</span><span class="sxs-lookup"><span data-stu-id="3431c-137">See also</span></span>

- [<span data-ttu-id="3431c-138">UI 自动化控件模式概述</span><span class="sxs-lookup"><span data-stu-id="3431c-138">UI Automation Control Patterns Overview</span></span>](ui-automation-control-patterns-overview.md)
- [<span data-ttu-id="3431c-139">在 UI 自动化提供程序中支持控件模式</span><span class="sxs-lookup"><span data-stu-id="3431c-139">Support Control Patterns in a UI Automation Provider</span></span>](support-control-patterns-in-a-ui-automation-provider.md)
- [<span data-ttu-id="3431c-140">客户端的 UI 自动化控件模式</span><span class="sxs-lookup"><span data-stu-id="3431c-140">UI Automation Control Patterns for Clients</span></span>](ui-automation-control-patterns-for-clients.md)
- [<span data-ttu-id="3431c-141">实现 UI 自动化 TableItem 控件模式</span><span class="sxs-lookup"><span data-stu-id="3431c-141">Implementing the UI Automation TableItem Control Pattern</span></span>](implementing-the-ui-automation-tableitem-control-pattern.md)
- [<span data-ttu-id="3431c-142">实现 UI 自动化 Grid 控件模式</span><span class="sxs-lookup"><span data-stu-id="3431c-142">Implementing the UI Automation Grid Control Pattern</span></span>](implementing-the-ui-automation-grid-control-pattern.md)
- [<span data-ttu-id="3431c-143">UI 自动化树概述</span><span class="sxs-lookup"><span data-stu-id="3431c-143">UI Automation Tree Overview</span></span>](ui-automation-tree-overview.md)
- [<span data-ttu-id="3431c-144">在 UI 自动化中使用缓存</span><span class="sxs-lookup"><span data-stu-id="3431c-144">Use Caching in UI Automation</span></span>](use-caching-in-ui-automation.md)
