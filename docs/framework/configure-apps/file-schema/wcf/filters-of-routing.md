---
title: '&lt;routing&gt; 的 &lt;filters&gt;'
ms.date: 03/30/2017
ms.assetid: 7993cf90-9afd-4c3c-9608-184d5da1105c
ms.openlocfilehash: 468c10bc06b60f80ce93cf413c02582fe3861f70
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54704428"
---
# <a name="ltfiltersgt-of-ltroutinggt"></a><span data-ttu-id="859d7-102">&lt;routing&gt; 的 &lt;filters&gt;</span><span class="sxs-lookup"><span data-stu-id="859d7-102">&lt;filters&gt; of &lt;routing&gt;</span></span>

<span data-ttu-id="859d7-103">表示一个配置节，用于定义一组路由筛选器，确定类型的 Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter>要评估传入消息时使用。</span><span class="sxs-lookup"><span data-stu-id="859d7-103">Represents a configuration section for defining a set of routing filters, which determine the type of Windows Communication Foundation (WCF) <xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages.</span></span>

<span data-ttu-id="859d7-104">[**\<system.serviceModel>**](system-servicemodel.md) </span><span class="sxs-lookup"><span data-stu-id="859d7-104">[**\<system.serviceModel>**](system-servicemodel.md) </span></span>  
<span data-ttu-id="859d7-105">&nbsp;&nbsp;[**\<routing>**](routing.md) </span><span class="sxs-lookup"><span data-stu-id="859d7-105">&nbsp;&nbsp;[**\<routing>**](routing.md) </span></span>  
<span data-ttu-id="859d7-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<filters>**</span><span class="sxs-lookup"><span data-stu-id="859d7-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<filters>**</span></span>
  
## <a name="syntax"></a><span data-ttu-id="859d7-107">语法</span><span class="sxs-lookup"><span data-stu-id="859d7-107">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <routing>
    <filters>
      <filter customType="String"
              filterData="String"
              filterType="Action/Address/AddressPrefix/And/Custom/Endpoint/MatchAll/XPath"
              name="String" />
    </filters>
  </routing>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="859d7-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="859d7-108">Attributes and elements</span></span>

<span data-ttu-id="859d7-109">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="859d7-109">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="859d7-110">特性</span><span class="sxs-lookup"><span data-stu-id="859d7-110">Attributes</span></span>

<span data-ttu-id="859d7-111">无</span><span class="sxs-lookup"><span data-stu-id="859d7-111">None</span></span>

### <a name="child-elements"></a><span data-ttu-id="859d7-112">子元素</span><span class="sxs-lookup"><span data-stu-id="859d7-112">Child elements</span></span>

|     | <span data-ttu-id="859d7-113">描述</span><span class="sxs-lookup"><span data-stu-id="859d7-113">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="859d7-114">**\<filter>**</span><span class="sxs-lookup"><span data-stu-id="859d7-114">**\<filter>**</span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/filter.md) | <span data-ttu-id="859d7-115">包含确定类型的 Windows Communication Foundation (WCF) 的路由筛选器<xref:System.ServiceModel.Dispatcher.MessageFilter>计算传入消息时将使用。</span><span class="sxs-lookup"><span data-stu-id="859d7-115">Contains a routing filter that determines the type of Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> will be used when evaluating incoming messages.</span></span> |

### <a name="parent-elements"></a><span data-ttu-id="859d7-116">父元素</span><span class="sxs-lookup"><span data-stu-id="859d7-116">Parent elements</span></span>

|     | <span data-ttu-id="859d7-117">描述</span><span class="sxs-lookup"><span data-stu-id="859d7-117">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="859d7-118">**\<routing>**</span><span class="sxs-lookup"><span data-stu-id="859d7-118">**\<routing>**</span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md) | <span data-ttu-id="859d7-119">表示一个配置节，用于定义一组路由筛选器，确定类型的 Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter>用于计算传入消息，以及路由表定义到的目标终结点将消息发送到筛选器匹配时。</span><span class="sxs-lookup"><span data-stu-id="859d7-119">Represents a configuration section for defining a set of routing filters, which determine the type of Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages, as well as routing tables that define the target endpoints to send messages to when a filter matches.</span></span> |

## <a name="see-also"></a><span data-ttu-id="859d7-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="859d7-120">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.FilterElement?displayProperty=nameWithType>
