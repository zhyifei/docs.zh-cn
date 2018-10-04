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
author: Xansky
ms.author: mhopkins
ms.openlocfilehash: d948ff2f71ff7d4335cacc0fa3815dd75af4ad45
ms.sourcegitcommit: 69229651598b427c550223d3c58aba82e47b3f82
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "48778229"
---
# <a name="get-supported-ui-automation-control-patterns"></a><span data-ttu-id="a274f-102">获取受支持的 UI 自动化控件模式</span><span class="sxs-lookup"><span data-stu-id="a274f-102">Get Supported UI Automation Control Patterns</span></span>
> [!NOTE]
>  <span data-ttu-id="a274f-103">本文档适用于想要使用 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 命名空间中定义的托管 <xref:System.Windows.Automation> 类的 .NET Framework 开发人员。</span><span class="sxs-lookup"><span data-stu-id="a274f-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="a274f-104">有关最新信息[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]，请参阅[Windows 自动化 API: UI 自动化](https://go.microsoft.com/fwlink/?LinkID=156746)。</span><span class="sxs-lookup"><span data-stu-id="a274f-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](https://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="a274f-105">本主题演示如何检索控件模式对象从[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]元素。</span><span class="sxs-lookup"><span data-stu-id="a274f-105">This topic shows how to retrieve control pattern objects from [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] elements.</span></span>  
  
### <a name="obtain-all-control-patterns"></a><span data-ttu-id="a274f-106">获取所有控件模式</span><span class="sxs-lookup"><span data-stu-id="a274f-106">Obtain All Control Patterns</span></span>  
  
1.  <span data-ttu-id="a274f-107">获取<xref:System.Windows.Automation.AutomationElement>您对其控件模式感兴趣。</span><span class="sxs-lookup"><span data-stu-id="a274f-107">Get the <xref:System.Windows.Automation.AutomationElement> whose control patterns you are interested in.</span></span>  
  
2.  <span data-ttu-id="a274f-108">调用<xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A>若要从元素中获取所有控件模式。</span><span class="sxs-lookup"><span data-stu-id="a274f-108">Call <xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A> to get all control patterns from the element.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="a274f-109">强烈建议客户端不使用<xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A>。</span><span class="sxs-lookup"><span data-stu-id="a274f-109">It is strongly recommended that a client not use <xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A>.</span></span> <span data-ttu-id="a274f-110">因为此方法调用，性能会受到严重影响<xref:System.Windows.Automation.AutomationElement.GetCurrentPattern%2A>在内部为每个现有的控件模式。</span><span class="sxs-lookup"><span data-stu-id="a274f-110">Performance can be severely affected as this method calls <xref:System.Windows.Automation.AutomationElement.GetCurrentPattern%2A> internally for each existing control pattern.</span></span> <span data-ttu-id="a274f-111">如果可能，应调用客户端<xref:System.Windows.Automation.AutomationElement.GetCurrentPattern%2A>感兴趣的关键模式。</span><span class="sxs-lookup"><span data-stu-id="a274f-111">If possible, a client should call <xref:System.Windows.Automation.AutomationElement.GetCurrentPattern%2A> for the key patterns of interest.</span></span>  
  
### <a name="obtain-a-specific-control-pattern"></a><span data-ttu-id="a274f-112">获取特定的控件模式</span><span class="sxs-lookup"><span data-stu-id="a274f-112">Obtain a Specific Control Pattern</span></span>  
  
1.  <span data-ttu-id="a274f-113">获取<xref:System.Windows.Automation.AutomationElement>您对其控件模式感兴趣。</span><span class="sxs-lookup"><span data-stu-id="a274f-113">Get the <xref:System.Windows.Automation.AutomationElement> whose control patterns you are interested in.</span></span>  
  
2.  <span data-ttu-id="a274f-114">调用<xref:System.Windows.Automation.AutomationElement.GetCurrentPattern%2A>或<xref:System.Windows.Automation.AutomationElement.TryGetCurrentPattern%2A>特定模式的查询。</span><span class="sxs-lookup"><span data-stu-id="a274f-114">Call <xref:System.Windows.Automation.AutomationElement.GetCurrentPattern%2A> or <xref:System.Windows.Automation.AutomationElement.TryGetCurrentPattern%2A> to query for a specific pattern.</span></span> <span data-ttu-id="a274f-115">这些方法非常相似，但是，如果找不到模式，<xref:System.Windows.Automation.AutomationElement.GetCurrentPattern%2A>引发异常，并<xref:System.Windows.Automation.AutomationElement.TryGetCurrentPattern%2A>返回`false`。</span><span class="sxs-lookup"><span data-stu-id="a274f-115">These methods are similar, but if the pattern is not found, <xref:System.Windows.Automation.AutomationElement.GetCurrentPattern%2A> raises an exception, and <xref:System.Windows.Automation.AutomationElement.TryGetCurrentPattern%2A> returns `false`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a274f-116">示例</span><span class="sxs-lookup"><span data-stu-id="a274f-116">Example</span></span>  
 <span data-ttu-id="a274f-117">下面的示例检索<xref:System.Windows.Automation.AutomationElement>列表项，并获取<xref:System.Windows.Automation.SelectionItemPattern>从该元素。</span><span class="sxs-lookup"><span data-stu-id="a274f-117">The following example retrieves an <xref:System.Windows.Automation.AutomationElement> for a list item and obtains a <xref:System.Windows.Automation.SelectionItemPattern> from that element.</span></span>  
  
 [!code-csharp[UIAClient_snip#103](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAClient_snip/CSharp/ClientForm.cs#103)]
 [!code-vb[UIAClient_snip#103](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAClient_snip/VisualBasic/ClientForm.vb#103)]  
  
## <a name="see-also"></a><span data-ttu-id="a274f-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="a274f-118">See Also</span></span>  
 [<span data-ttu-id="a274f-119">客户端的 UI 自动化控件模式</span><span class="sxs-lookup"><span data-stu-id="a274f-119">UI Automation Control Patterns for Clients</span></span>](../../../docs/framework/ui-automation/ui-automation-control-patterns-for-clients.md)
