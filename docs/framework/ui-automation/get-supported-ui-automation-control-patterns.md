---
title: 获取受支持的 UI 自动化控件模式
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- control patterns, getting
- UI Automation, getting control patterns
- getting, control patterns
ms.assetid: 006c54c9-50bf-48d9-a855-9d62eb95603a
ms.openlocfilehash: 64c5bae738cee5249e6c2406a2f94667ecb2931f
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59337014"
---
# <a name="get-supported-ui-automation-control-patterns"></a><span data-ttu-id="63fa8-102">获取受支持的 UI 自动化控件模式</span><span class="sxs-lookup"><span data-stu-id="63fa8-102">Get Supported UI Automation Control Patterns</span></span>
> [!NOTE]
>  <span data-ttu-id="63fa8-103">本文档适用于想要使用 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 命名空间中定义的托管 <xref:System.Windows.Automation> 类的 .NET Framework 开发人员。</span><span class="sxs-lookup"><span data-stu-id="63fa8-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="63fa8-104">有关最新信息[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]，请参阅[Windows 自动化 API:UI 自动化](https://go.microsoft.com/fwlink/?LinkID=156746)。</span><span class="sxs-lookup"><span data-stu-id="63fa8-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](https://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="63fa8-105">本主题演示如何从 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 元素检索控件模式对象。</span><span class="sxs-lookup"><span data-stu-id="63fa8-105">This topic shows how to retrieve control pattern objects from [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] elements.</span></span>  
  
### <a name="obtain-all-control-patterns"></a><span data-ttu-id="63fa8-106">获取所有控件模式</span><span class="sxs-lookup"><span data-stu-id="63fa8-106">Obtain All Control Patterns</span></span>  
  
1. <span data-ttu-id="63fa8-107">获取你对其控件模式感兴趣的 <xref:System.Windows.Automation.AutomationElement>。</span><span class="sxs-lookup"><span data-stu-id="63fa8-107">Get the <xref:System.Windows.Automation.AutomationElement> whose control patterns you are interested in.</span></span>  
  
2. <span data-ttu-id="63fa8-108">调用 <xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A>，以便从该元素获取所有控件模式。</span><span class="sxs-lookup"><span data-stu-id="63fa8-108">Call <xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A> to get all control patterns from the element.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="63fa8-109">强烈建议客户端不要使用 <xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A>。</span><span class="sxs-lookup"><span data-stu-id="63fa8-109">It is strongly recommended that a client not use <xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A>.</span></span> <span data-ttu-id="63fa8-110">因为此方法针对每个现有的控件模式在内部调用 <xref:System.Windows.Automation.AutomationElement.GetCurrentPattern%2A>，所以性能会受到严重影响。</span><span class="sxs-lookup"><span data-stu-id="63fa8-110">Performance can be severely affected as this method calls <xref:System.Windows.Automation.AutomationElement.GetCurrentPattern%2A> internally for each existing control pattern.</span></span> <span data-ttu-id="63fa8-111">如有可能，客户端应当针对相关的关键模式来调用 <xref:System.Windows.Automation.AutomationElement.GetCurrentPattern%2A>。</span><span class="sxs-lookup"><span data-stu-id="63fa8-111">If possible, a client should call <xref:System.Windows.Automation.AutomationElement.GetCurrentPattern%2A> for the key patterns of interest.</span></span>  
  
### <a name="obtain-a-specific-control-pattern"></a><span data-ttu-id="63fa8-112">获取特定的控件模式</span><span class="sxs-lookup"><span data-stu-id="63fa8-112">Obtain a Specific Control Pattern</span></span>  
  
1. <span data-ttu-id="63fa8-113">获取你对其控件模式感兴趣的 <xref:System.Windows.Automation.AutomationElement>。</span><span class="sxs-lookup"><span data-stu-id="63fa8-113">Get the <xref:System.Windows.Automation.AutomationElement> whose control patterns you are interested in.</span></span>  
  
2. <span data-ttu-id="63fa8-114">调用 <xref:System.Windows.Automation.AutomationElement.GetCurrentPattern%2A> 或 <xref:System.Windows.Automation.AutomationElement.TryGetCurrentPattern%2A> 以查询特定模式。</span><span class="sxs-lookup"><span data-stu-id="63fa8-114">Call <xref:System.Windows.Automation.AutomationElement.GetCurrentPattern%2A> or <xref:System.Windows.Automation.AutomationElement.TryGetCurrentPattern%2A> to query for a specific pattern.</span></span> <span data-ttu-id="63fa8-115">这两种方法非常相似，但是，如果没有找到该模式，<xref:System.Windows.Automation.AutomationElement.GetCurrentPattern%2A> 会引发异常，而 <xref:System.Windows.Automation.AutomationElement.TryGetCurrentPattern%2A> 会返回 `false`。</span><span class="sxs-lookup"><span data-stu-id="63fa8-115">These methods are similar, but if the pattern is not found, <xref:System.Windows.Automation.AutomationElement.GetCurrentPattern%2A> raises an exception, and <xref:System.Windows.Automation.AutomationElement.TryGetCurrentPattern%2A> returns `false`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="63fa8-116">示例</span><span class="sxs-lookup"><span data-stu-id="63fa8-116">Example</span></span>  
 <span data-ttu-id="63fa8-117">下面的示例检索某个列表项的 <xref:System.Windows.Automation.AutomationElement>，并从该元素获取一个 <xref:System.Windows.Automation.SelectionItemPattern>。</span><span class="sxs-lookup"><span data-stu-id="63fa8-117">The following example retrieves an <xref:System.Windows.Automation.AutomationElement> for a list item and obtains a <xref:System.Windows.Automation.SelectionItemPattern> from that element.</span></span>  
  
 [!code-csharp[UIAClient_snip#103](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAClient_snip/CSharp/ClientForm.cs#103)]
 [!code-vb[UIAClient_snip#103](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAClient_snip/VisualBasic/ClientForm.vb#103)]  
  
## <a name="see-also"></a><span data-ttu-id="63fa8-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="63fa8-118">See also</span></span>

- [<span data-ttu-id="63fa8-119">客户端的 UI 自动化控件模式</span><span class="sxs-lookup"><span data-stu-id="63fa8-119">UI Automation Control Patterns for Clients</span></span>](../../../docs/framework/ui-automation/ui-automation-control-patterns-for-clients.md)
