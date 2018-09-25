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
author: Xansky
ms.author: mhopkins
ms.openlocfilehash: cb9e37c80c7bc32a29022ede0bffc06a0f6ac5b1
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/25/2018
ms.locfileid: "47078027"
---
# <a name="get-ui-automation-element-properties"></a><span data-ttu-id="5a12c-102">获取 UI 自动化元素的属性</span><span class="sxs-lookup"><span data-stu-id="5a12c-102">Get UI Automation Element Properties</span></span>
> [!NOTE]
>  <span data-ttu-id="5a12c-103">本文档适用于想要使用 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 命名空间中定义的托管 <xref:System.Windows.Automation> 类的 .NET Framework 开发人员。</span><span class="sxs-lookup"><span data-stu-id="5a12c-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="5a12c-104">有关最新信息[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]，请参阅[Windows 自动化 API: UI 自动化](https://go.microsoft.com/fwlink/?LinkID=156746)。</span><span class="sxs-lookup"><span data-stu-id="5a12c-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](https://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="5a12c-105">本主题演示如何检索的属性[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]元素。</span><span class="sxs-lookup"><span data-stu-id="5a12c-105">This topic shows how to retrieve properties of a [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] element.</span></span>  
  
### <a name="get-a-current-property-value"></a><span data-ttu-id="5a12c-106">获取当前属性值</span><span class="sxs-lookup"><span data-stu-id="5a12c-106">Get a Current Property Value</span></span>  
  
1.  <span data-ttu-id="5a12c-107">获取<xref:System.Windows.Automation.AutomationElement>你想要获取其属性。</span><span class="sxs-lookup"><span data-stu-id="5a12c-107">Obtain the <xref:System.Windows.Automation.AutomationElement> whose property you wish to get.</span></span>  
  
2.  <span data-ttu-id="5a12c-108">调用<xref:System.Windows.Automation.AutomationElement.GetCurrentPropertyValue%2A>，或检索<xref:System.Windows.Automation.AutomationElement.Current%2A>属性结构并获取其成员之一的值。</span><span class="sxs-lookup"><span data-stu-id="5a12c-108">Call <xref:System.Windows.Automation.AutomationElement.GetCurrentPropertyValue%2A>, or retrieve the <xref:System.Windows.Automation.AutomationElement.Current%2A> property structure and get the value from one of its members.</span></span>  
  
### <a name="get-a-cached-property-value"></a><span data-ttu-id="5a12c-109">获取缓存的属性值</span><span class="sxs-lookup"><span data-stu-id="5a12c-109">Get a Cached Property Value</span></span>  
  
1.  <span data-ttu-id="5a12c-110">获取<xref:System.Windows.Automation.AutomationElement>你想要获取其属性。</span><span class="sxs-lookup"><span data-stu-id="5a12c-110">Obtain the <xref:System.Windows.Automation.AutomationElement> whose property you wish to get.</span></span> <span data-ttu-id="5a12c-111">该属性必须在指定<xref:System.Windows.Automation.CacheRequest>。</span><span class="sxs-lookup"><span data-stu-id="5a12c-111">The property must have been specified in the <xref:System.Windows.Automation.CacheRequest>.</span></span>  
  
2.  <span data-ttu-id="5a12c-112">调用<xref:System.Windows.Automation.AutomationElement.GetCachedPropertyValue%2A>，或检索<xref:System.Windows.Automation.AutomationElement.Cached%2A>属性结构并获取其成员之一的值。</span><span class="sxs-lookup"><span data-stu-id="5a12c-112">Call <xref:System.Windows.Automation.AutomationElement.GetCachedPropertyValue%2A>, or retrieve the <xref:System.Windows.Automation.AutomationElement.Cached%2A> property structure and get the value from one of its members.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5a12c-113">示例</span><span class="sxs-lookup"><span data-stu-id="5a12c-113">Example</span></span>  
 <span data-ttu-id="5a12c-114">下面的示例显示了各种方法来检索当前属性的<xref:System.Windows.Automation.AutomationElement>。</span><span class="sxs-lookup"><span data-stu-id="5a12c-114">The following example shows various ways to retrieve current properties of an <xref:System.Windows.Automation.AutomationElement>.</span></span>  
  
 [!code-csharp[UIAClient_snip#170](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAClient_snip/CSharp/ClientForm.cs#170)]
 [!code-vb[UIAClient_snip#170](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAClient_snip/VisualBasic/ClientForm.vb#170)]  
  
## <a name="see-also"></a><span data-ttu-id="5a12c-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="5a12c-115">See Also</span></span>  
 [<span data-ttu-id="5a12c-116">客户端的 UI 自动化属性</span><span class="sxs-lookup"><span data-stu-id="5a12c-116">UI Automation Properties for Clients</span></span>](../../../docs/framework/ui-automation/ui-automation-properties-for-clients.md)  
 [<span data-ttu-id="5a12c-117">在 UI 自动化中使用缓存</span><span class="sxs-lookup"><span data-stu-id="5a12c-117">Use Caching in UI Automation</span></span>](../../../docs/framework/ui-automation/use-caching-in-ui-automation.md)  
 [<span data-ttu-id="5a12c-118">在 UI 自动化客户端中缓存</span><span class="sxs-lookup"><span data-stu-id="5a12c-118">Caching in UI Automation Clients</span></span>](../../../docs/framework/ui-automation/caching-in-ui-automation-clients.md)
