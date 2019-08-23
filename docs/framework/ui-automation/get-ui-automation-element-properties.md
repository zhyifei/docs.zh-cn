---
title: 获取 UI 自动化元素的属性
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- properties, retrieving
- UI Automation, retrieving properties of elements
ms.assetid: 09576b1a-291f-435c-980e-dee32d899ae1
ms.openlocfilehash: e3b3b118c3db95f55c67c2b27149734efc8cbea8
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69968966"
---
# <a name="get-ui-automation-element-properties"></a><span data-ttu-id="078de-102">获取 UI 自动化元素的属性</span><span class="sxs-lookup"><span data-stu-id="078de-102">Get UI Automation Element Properties</span></span>
> [!NOTE]
> <span data-ttu-id="078de-103">本文档适用于想要使用 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 命名空间中定义的托管 <xref:System.Windows.Automation> 类的 .NET Framework 开发人员。</span><span class="sxs-lookup"><span data-stu-id="078de-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="078de-104">有关的最新信息[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], 请[参阅 Windows 自动化 API:UI 自动化](https://go.microsoft.com/fwlink/?LinkID=156746)。</span><span class="sxs-lookup"><span data-stu-id="078de-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](https://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="078de-105">本主题说明如何检索[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]元素的属性。</span><span class="sxs-lookup"><span data-stu-id="078de-105">This topic shows how to retrieve properties of a [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] element.</span></span>  
  
### <a name="get-a-current-property-value"></a><span data-ttu-id="078de-106">获取当前属性值</span><span class="sxs-lookup"><span data-stu-id="078de-106">Get a Current Property Value</span></span>  
  
1. <span data-ttu-id="078de-107">获取要<xref:System.Windows.Automation.AutomationElement>获取其属性的。</span><span class="sxs-lookup"><span data-stu-id="078de-107">Obtain the <xref:System.Windows.Automation.AutomationElement> whose property you wish to get.</span></span>  
  
2. <span data-ttu-id="078de-108">调用<xref:System.Windows.Automation.AutomationElement.GetCurrentPropertyValue%2A>或<xref:System.Windows.Automation.AutomationElement.Current%2A>检索属性结构, 并从其成员之一获取值。</span><span class="sxs-lookup"><span data-stu-id="078de-108">Call <xref:System.Windows.Automation.AutomationElement.GetCurrentPropertyValue%2A>, or retrieve the <xref:System.Windows.Automation.AutomationElement.Current%2A> property structure and get the value from one of its members.</span></span>  
  
### <a name="get-a-cached-property-value"></a><span data-ttu-id="078de-109">获取缓存的属性值</span><span class="sxs-lookup"><span data-stu-id="078de-109">Get a Cached Property Value</span></span>  
  
1. <span data-ttu-id="078de-110">获取要<xref:System.Windows.Automation.AutomationElement>获取其属性的。</span><span class="sxs-lookup"><span data-stu-id="078de-110">Obtain the <xref:System.Windows.Automation.AutomationElement> whose property you wish to get.</span></span> <span data-ttu-id="078de-111">必须已在中<xref:System.Windows.Automation.CacheRequest>指定了属性。</span><span class="sxs-lookup"><span data-stu-id="078de-111">The property must have been specified in the <xref:System.Windows.Automation.CacheRequest>.</span></span>  
  
2. <span data-ttu-id="078de-112">调用<xref:System.Windows.Automation.AutomationElement.GetCachedPropertyValue%2A>或<xref:System.Windows.Automation.AutomationElement.Cached%2A>检索属性结构, 并从其成员之一获取值。</span><span class="sxs-lookup"><span data-stu-id="078de-112">Call <xref:System.Windows.Automation.AutomationElement.GetCachedPropertyValue%2A>, or retrieve the <xref:System.Windows.Automation.AutomationElement.Cached%2A> property structure and get the value from one of its members.</span></span>  
  
## <a name="example"></a><span data-ttu-id="078de-113">示例</span><span class="sxs-lookup"><span data-stu-id="078de-113">Example</span></span>  
 <span data-ttu-id="078de-114">下面的示例演示了检索的当前属性的<xref:System.Windows.Automation.AutomationElement>各种方法。</span><span class="sxs-lookup"><span data-stu-id="078de-114">The following example shows various ways to retrieve current properties of an <xref:System.Windows.Automation.AutomationElement>.</span></span>  
  
 [!code-csharp[UIAClient_snip#170](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAClient_snip/CSharp/ClientForm.cs#170)]
 [!code-vb[UIAClient_snip#170](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAClient_snip/VisualBasic/ClientForm.vb#170)]  
  
## <a name="see-also"></a><span data-ttu-id="078de-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="078de-115">See also</span></span>

- [<span data-ttu-id="078de-116">客户端的 UI 自动化属性</span><span class="sxs-lookup"><span data-stu-id="078de-116">UI Automation Properties for Clients</span></span>](../../../docs/framework/ui-automation/ui-automation-properties-for-clients.md)
- [<span data-ttu-id="078de-117">在 UI 自动化中使用缓存</span><span class="sxs-lookup"><span data-stu-id="078de-117">Use Caching in UI Automation</span></span>](../../../docs/framework/ui-automation/use-caching-in-ui-automation.md)
- [<span data-ttu-id="078de-118">在 UI 自动化客户端中缓存</span><span class="sxs-lookup"><span data-stu-id="078de-118">Caching in UI Automation Clients</span></span>](../../../docs/framework/ui-automation/caching-in-ui-automation-clients.md)
