---
title: "获取 UI 自动化元素的属性"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-bcl
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- properties, retrieving
- UI Automation, retrieving properties of elements
ms.assetid: 09576b1a-291f-435c-980e-dee32d899ae1
caps.latest.revision: "5"
author: Xansky
ms.author: mhopkins
manager: markl
ms.workload: dotnet
ms.openlocfilehash: f3fcbb25fab616b60a1f60d9443af13b60f2d27a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="get-ui-automation-element-properties"></a><span data-ttu-id="69ce9-102">获取 UI 自动化元素的属性</span><span class="sxs-lookup"><span data-stu-id="69ce9-102">Get UI Automation Element Properties</span></span>
> [!NOTE]
>  <span data-ttu-id="69ce9-103">本文档适用于想要使用 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 命名空间中定义的托管 <xref:System.Windows.Automation> 类的 .NET Framework 开发人员。</span><span class="sxs-lookup"><span data-stu-id="69ce9-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="69ce9-104">有关 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]的最新信息，请参阅 [Windows 自动化 API：UI 自动化](http://go.microsoft.com/fwlink/?LinkID=156746)。</span><span class="sxs-lookup"><span data-stu-id="69ce9-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](http://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="69ce9-105">本主题演示如何检索的属性[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]元素。</span><span class="sxs-lookup"><span data-stu-id="69ce9-105">This topic shows how to retrieve properties of a [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] element.</span></span>  
  
### <a name="get-a-current-property-value"></a><span data-ttu-id="69ce9-106">获取当前的属性值</span><span class="sxs-lookup"><span data-stu-id="69ce9-106">Get a Current Property Value</span></span>  
  
1.  <span data-ttu-id="69ce9-107">获取<xref:System.Windows.Automation.AutomationElement>你想要获取其属性。</span><span class="sxs-lookup"><span data-stu-id="69ce9-107">Obtain the <xref:System.Windows.Automation.AutomationElement> whose property you wish to get.</span></span>  
  
2.  <span data-ttu-id="69ce9-108">调用<xref:System.Windows.Automation.AutomationElement.GetCurrentPropertyValue%2A>，或检索<xref:System.Windows.Automation.AutomationElement.Current%2A>属性结构并获取其成员之一的值。</span><span class="sxs-lookup"><span data-stu-id="69ce9-108">Call <xref:System.Windows.Automation.AutomationElement.GetCurrentPropertyValue%2A>, or retrieve the <xref:System.Windows.Automation.AutomationElement.Current%2A> property structure and get the value from one of its members.</span></span>  
  
### <a name="get-a-cached-property-value"></a><span data-ttu-id="69ce9-109">获取缓存的属性值</span><span class="sxs-lookup"><span data-stu-id="69ce9-109">Get a Cached Property Value</span></span>  
  
1.  <span data-ttu-id="69ce9-110">获取<xref:System.Windows.Automation.AutomationElement>你想要获取其属性。</span><span class="sxs-lookup"><span data-stu-id="69ce9-110">Obtain the <xref:System.Windows.Automation.AutomationElement> whose property you wish to get.</span></span> <span data-ttu-id="69ce9-111">属性必须在指定<xref:System.Windows.Automation.CacheRequest>。</span><span class="sxs-lookup"><span data-stu-id="69ce9-111">The property must have been specified in the <xref:System.Windows.Automation.CacheRequest>.</span></span>  
  
2.  <span data-ttu-id="69ce9-112">调用<xref:System.Windows.Automation.AutomationElement.GetCachedPropertyValue%2A>，或检索<xref:System.Windows.Automation.AutomationElement.Cached%2A>属性结构并获取其成员之一的值。</span><span class="sxs-lookup"><span data-stu-id="69ce9-112">Call <xref:System.Windows.Automation.AutomationElement.GetCachedPropertyValue%2A>, or retrieve the <xref:System.Windows.Automation.AutomationElement.Cached%2A> property structure and get the value from one of its members.</span></span>  
  
## <a name="example"></a><span data-ttu-id="69ce9-113">示例</span><span class="sxs-lookup"><span data-stu-id="69ce9-113">Example</span></span>  
 <span data-ttu-id="69ce9-114">下面的示例演示各种方法来检索当前属性<xref:System.Windows.Automation.AutomationElement>。</span><span class="sxs-lookup"><span data-stu-id="69ce9-114">The following example shows various ways to retrieve current properties of an <xref:System.Windows.Automation.AutomationElement>.</span></span>  
  
 [!code-csharp[UIAClient_snip#170](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAClient_snip/CSharp/ClientForm.cs#170)]
 [!code-vb[UIAClient_snip#170](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAClient_snip/VisualBasic/ClientForm.vb#170)]  
  
## <a name="see-also"></a><span data-ttu-id="69ce9-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="69ce9-115">See Also</span></span>  
 [<span data-ttu-id="69ce9-116">客户端的 UI 自动化属性</span><span class="sxs-lookup"><span data-stu-id="69ce9-116">UI Automation Properties for Clients</span></span>](../../../docs/framework/ui-automation/ui-automation-properties-for-clients.md)  
 [<span data-ttu-id="69ce9-117">在 UI 自动化中使用缓存</span><span class="sxs-lookup"><span data-stu-id="69ce9-117">Use Caching in UI Automation</span></span>](../../../docs/framework/ui-automation/use-caching-in-ui-automation.md)  
 [<span data-ttu-id="69ce9-118">在 UI 自动化客户端中缓存</span><span class="sxs-lookup"><span data-stu-id="69ce9-118">Caching in UI Automation Clients</span></span>](../../../docs/framework/ui-automation/caching-in-ui-automation-clients.md)
