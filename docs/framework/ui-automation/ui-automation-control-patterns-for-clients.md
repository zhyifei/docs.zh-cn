---
title: "客户端的 UI 自动化控件模式"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-bcl
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- UI Automation, control patterns for clients
- control patterns, UI Automation clients
ms.assetid: 571561d8-5f49-43a9-a054-87735194e013
caps.latest.revision: "24"
author: Xansky
ms.author: mhopkins
manager: markl
ms.workload: dotnet
ms.openlocfilehash: 7de91de7d2b738d92920ffc691133f8f7608e203
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/19/2018
---
# <a name="ui-automation-control-patterns-for-clients"></a><span data-ttu-id="519ae-102">客户端的 UI 自动化控件模式</span><span class="sxs-lookup"><span data-stu-id="519ae-102">UI Automation Control Patterns for Clients</span></span>
> [!NOTE]
>  <span data-ttu-id="519ae-103">本文档适用于想要使用 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 命名空间中定义的托管 <xref:System.Windows.Automation> 类的 .NET Framework 开发人员。</span><span class="sxs-lookup"><span data-stu-id="519ae-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="519ae-104">有关 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]的最新信息，请参阅 [Windows 自动化 API：UI 自动化](http://go.microsoft.com/fwlink/?LinkID=156746)。</span><span class="sxs-lookup"><span data-stu-id="519ae-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](http://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="519ae-105">此概述介绍 UI 自动化客户端的控件模式。</span><span class="sxs-lookup"><span data-stu-id="519ae-105">This overview introduces control patterns for UI Automation clients.</span></span> <span data-ttu-id="519ae-106">它包括有关 UI 自动化客户端如何使用控件模式访问 [!INCLUDE[TLA#tla_ui](../../../includes/tlasharptla-ui-md.md)]相关信息的信息。</span><span class="sxs-lookup"><span data-stu-id="519ae-106">It includes information on how a UI Automation client can use control patterns to access information about the [!INCLUDE[TLA#tla_ui](../../../includes/tlasharptla-ui-md.md)].</span></span>  
  
 <span data-ttu-id="519ae-107">控件模式提供了一种方法，用于独立于控件类型或控件的外观对控件的功能进行分类和公开。</span><span class="sxs-lookup"><span data-stu-id="519ae-107">Control patterns provide a way to categorize and expose a control's functionality independent of the control type or the appearance of the control.</span></span> <span data-ttu-id="519ae-108">UI 自动化客户端可以检查 <xref:System.Windows.Automation.AutomationElement> 以确定哪些控件模式受支持并确保控件的行为。</span><span class="sxs-lookup"><span data-stu-id="519ae-108">UI Automation clients can examine an <xref:System.Windows.Automation.AutomationElement> to determine which control patterns are supported and be assured of the behavior of the control.</span></span>  
  
 <span data-ttu-id="519ae-109">有关控件模式的完整列表，请参阅 [UI Automation Control Patterns Overview](../../../docs/framework/ui-automation/ui-automation-control-patterns-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="519ae-109">For a complete list of control patterns, see [UI Automation Control Patterns Overview](../../../docs/framework/ui-automation/ui-automation-control-patterns-overview.md).</span></span>  
  
<a name="uiautomation_getting_control_patterns"></a>   
## <a name="getting-control-patterns"></a><span data-ttu-id="519ae-110">获取控件模式</span><span class="sxs-lookup"><span data-stu-id="519ae-110">Getting Control Patterns</span></span>  
 <span data-ttu-id="519ae-111">客户端通过调用 <xref:System.Windows.Automation.AutomationElement.GetCachedPattern%2A?displayProperty=nameWithType> 或 <xref:System.Windows.Automation.AutomationElement.GetCurrentPattern%2A?displayProperty=nameWithType> 从 <xref:System.Windows.Automation.AutomationElement> 检索控件模式。</span><span class="sxs-lookup"><span data-stu-id="519ae-111">Clients retrieve a control pattern from an <xref:System.Windows.Automation.AutomationElement> by calling either <xref:System.Windows.Automation.AutomationElement.GetCachedPattern%2A?displayProperty=nameWithType> or <xref:System.Windows.Automation.AutomationElement.GetCurrentPattern%2A?displayProperty=nameWithType>.</span></span>  
  
 <span data-ttu-id="519ae-112">客户端可以使用 <xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A> 方法或单个 `IsPatternAvailable` 属性（例如 <xref:System.Windows.Automation.AutomationElement.IsTextPatternAvailableProperty>）来确定一个模式或一组模式是否在 <xref:System.Windows.Automation.AutomationElement>上受支持。</span><span class="sxs-lookup"><span data-stu-id="519ae-112">Clients can use the <xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A> method or an individual `IsPatternAvailable` property (for example, <xref:System.Windows.Automation.AutomationElement.IsTextPatternAvailableProperty>) to determine if a pattern or group of patterns is supported on the <xref:System.Windows.Automation.AutomationElement>.</span></span> <span data-ttu-id="519ae-113">但是，尝试获取控件模式并针对 `null` 引用进行测试比检查支持的属性并检索控件模式更高效，因为这样进行的跨进程调用更少。</span><span class="sxs-lookup"><span data-stu-id="519ae-113">However, it is more efficient to attempt to get the control pattern and test for a `null` reference than to check the supported properties and retrieve the control pattern since it results in fewer cross-process calls.</span></span>  
  
 <span data-ttu-id="519ae-114">以下示例演示如何从 <xref:System.Windows.Automation.TextPattern> 获取 <xref:System.Windows.Automation.AutomationElement>控件模式。</span><span class="sxs-lookup"><span data-stu-id="519ae-114">The following example demonstrates how to get a <xref:System.Windows.Automation.TextPattern> control pattern from an <xref:System.Windows.Automation.AutomationElement>.</span></span>  
  
 [!code-csharp[UIATextPattern_snip#1037](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIATextPattern_snip/CSharp/SearchWindow.cs#1037)]  
  
<a name="uiautomation_properties_on_control_patterns"></a>   
## <a name="retrieving-properties-on-control-patterns"></a><span data-ttu-id="519ae-115">检索控件模式上的属性</span><span class="sxs-lookup"><span data-stu-id="519ae-115">Retrieving Properties on Control Patterns</span></span>  
 <span data-ttu-id="519ae-116">客户端可以通过调用 <xref:System.Windows.Automation.AutomationElement.GetCachedPropertyValue%2A?displayProperty=nameWithType> 或 <xref:System.Windows.Automation.AutomationElement.GetCurrentPropertyValue%2A?displayProperty=nameWithType> 并将返回的对象强制转换为适当类型，来检索控件模式上的属性值。</span><span class="sxs-lookup"><span data-stu-id="519ae-116">Clients can retrieve the property values on control patterns by calling either <xref:System.Windows.Automation.AutomationElement.GetCachedPropertyValue%2A?displayProperty=nameWithType> or <xref:System.Windows.Automation.AutomationElement.GetCurrentPropertyValue%2A?displayProperty=nameWithType> and casting the object returned to an appropriate type.</span></span> <span data-ttu-id="519ae-117">有关详细信息[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]属性，请参阅[的客户端 UI 自动化属性](../../../docs/framework/ui-automation/ui-automation-properties-for-clients.md)。</span><span class="sxs-lookup"><span data-stu-id="519ae-117">For more information on [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] properties, see [UI Automation Properties for Clients](../../../docs/framework/ui-automation/ui-automation-properties-for-clients.md).</span></span>  
  
 <span data-ttu-id="519ae-118">除了 `GetPropertyValue` 方法之外，还可以通过 [!INCLUDE[TLA#tla_clr](../../../includes/tlasharptla-clr-md.md)] 访问器检索属性值以访问模式上的 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 属性。</span><span class="sxs-lookup"><span data-stu-id="519ae-118">In addition to the `GetPropertyValue` methods, property values can be retrieved through the [!INCLUDE[TLA#tla_clr](../../../includes/tlasharptla-clr-md.md)] accessors to access the [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] properties on a pattern.</span></span>  
  
<a name="uiautomation_with_variable_patterns"></a>   
## <a name="controls-with-variable-patterns"></a><span data-ttu-id="519ae-119">具有可变模式的控件</span><span class="sxs-lookup"><span data-stu-id="519ae-119">Controls with Variable Patterns</span></span>  
 <span data-ttu-id="519ae-120">某些控件类型支持不同的模式，具体取决于它们的状态或使用控件的方式。</span><span class="sxs-lookup"><span data-stu-id="519ae-120">Some control types support different patterns depending on their state or the manner in which the control is being used.</span></span> <span data-ttu-id="519ae-121">可以具有可变模式的控件示例包括列表视图（缩略图、图块、图标、列表、详细信息）、 [!INCLUDE[TLA#tla_xl](../../../includes/tlasharptla-xl-md.md)] 图表（饼图、折线图、条形图、带有公式的单元格值）、 [!INCLUDE[TLA#tla_word](../../../includes/tlasharptla-word-md.md)]的文档区域（正常、Web 版式、大纲、打印布局、打印预览）和 [!INCLUDE[TLA#tla_wmp](../../../includes/tlasharptla-wmp-md.md)] 外观。</span><span class="sxs-lookup"><span data-stu-id="519ae-121">Examples of controls that can have variable patterns are list views (thumbnails, tiles, icons, list, details), [!INCLUDE[TLA#tla_xl](../../../includes/tlasharptla-xl-md.md)] Charts (Pie, Line, Bar, Cell Value with a formula), [!INCLUDE[TLA#tla_word](../../../includes/tlasharptla-word-md.md)]'s document area (Normal, Web Layout, Outline, Print Layout, Print Preview), and [!INCLUDE[TLA#tla_wmp](../../../includes/tlasharptla-wmp-md.md)] skins.</span></span>  
  
 <span data-ttu-id="519ae-122">实现自定义控件类型的控件可以具有表示其功能所需的任何控件模式集。</span><span class="sxs-lookup"><span data-stu-id="519ae-122">Controls implementing custom control types can have any set of control patterns that are needed to represent their functionality.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="519ae-123">请参阅</span><span class="sxs-lookup"><span data-stu-id="519ae-123">See Also</span></span>  
 [<span data-ttu-id="519ae-124">UI 自动化控件模式</span><span class="sxs-lookup"><span data-stu-id="519ae-124">UI Automation Control Patterns</span></span>](../../../docs/framework/ui-automation/ui-automation-control-patterns.md)  
 [<span data-ttu-id="519ae-125">UI 自动化文本模式</span><span class="sxs-lookup"><span data-stu-id="519ae-125">UI Automation Text Pattern</span></span>](../../../docs/framework/ui-automation/ui-automation-text-pattern.md)  
 [<span data-ttu-id="519ae-126">使用 UI 自动化调用控件</span><span class="sxs-lookup"><span data-stu-id="519ae-126">Invoke a Control Using UI Automation</span></span>](../../../docs/framework/ui-automation/invoke-a-control-using-ui-automation.md)  
 [<span data-ttu-id="519ae-127">使用 UI 自动化获取复选框的切换状态</span><span class="sxs-lookup"><span data-stu-id="519ae-127">Get the Toggle State of a Check Box Using UI Automation</span></span>](../../../docs/framework/ui-automation/get-the-toggle-state-of-a-check-box-using-ui-automation.md)  
 [<span data-ttu-id="519ae-128">UI 自动化客户端的控件模式映射</span><span class="sxs-lookup"><span data-stu-id="519ae-128">Control Pattern Mapping for UI Automation Clients</span></span>](../../../docs/framework/ui-automation/control-pattern-mapping-for-ui-automation-clients.md)  
 [<span data-ttu-id="519ae-129">TextPattern 插入文本示例</span><span class="sxs-lookup"><span data-stu-id="519ae-129">TextPattern Insert Text Sample</span></span>](http://msdn.microsoft.com/library/67353f93-7ee2-42f2-ab76-5c078cf6ca16)  
 [<span data-ttu-id="519ae-130">TextPattern 搜索和选择示例</span><span class="sxs-lookup"><span data-stu-id="519ae-130">TextPattern Search and Selection Sample</span></span>](http://msdn.microsoft.com/library/0a3bca57-8b72-489d-a57c-da85b7a22c7f)  
 [<span data-ttu-id="519ae-131">InvokePattern 和 ExpandCollapsePattern 菜单项示例</span><span class="sxs-lookup"><span data-stu-id="519ae-131">InvokePattern and ExpandCollapsePattern Menu Item Sample</span></span>](http://msdn.microsoft.com/library/b7fa141c-e2d1-4da2-a27f-81a7d1172210)
