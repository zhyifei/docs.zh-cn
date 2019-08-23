---
title: <filters> 的 <routing>
ms.date: 03/30/2017
ms.assetid: 7993cf90-9afd-4c3c-9608-184d5da1105c
ms.openlocfilehash: ba60958ad33b46b40285f3f70001273bb3af3a63
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69925619"
---
# <a name="filters-of-routing"></a><span data-ttu-id="429c2-102">\<筛选\<路由 > ></span><span class="sxs-lookup"><span data-stu-id="429c2-102">\<filters> of \<routing></span></span>

<span data-ttu-id="429c2-103">表示用于定义一组路由筛选器的配置节, 这些筛选器确定计算传入消息时使用<xref:System.ServiceModel.Dispatcher.MessageFilter>的 Windows Communication Foundation (WCF) 的类型。</span><span class="sxs-lookup"><span data-stu-id="429c2-103">Represents a configuration section for defining a set of routing filters, which determine the type of Windows Communication Foundation (WCF) <xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages.</span></span>

<span data-ttu-id="429c2-104">[ **\<system.serviceModel>** ](system-servicemodel.md) </span><span class="sxs-lookup"><span data-stu-id="429c2-104">[**\<system.serviceModel>**](system-servicemodel.md) </span></span>  
<span data-ttu-id="429c2-105">&nbsp;&nbsp;[ **\<routing>** ](routing.md) </span><span class="sxs-lookup"><span data-stu-id="429c2-105">&nbsp;&nbsp;[**\<routing>**](routing.md) </span></span>  
<span data-ttu-id="429c2-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<filters>**</span><span class="sxs-lookup"><span data-stu-id="429c2-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<filters>**</span></span>
  
## <a name="syntax"></a><span data-ttu-id="429c2-107">语法</span><span class="sxs-lookup"><span data-stu-id="429c2-107">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="429c2-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="429c2-108">Attributes and elements</span></span>

<span data-ttu-id="429c2-109">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="429c2-109">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="429c2-110">特性</span><span class="sxs-lookup"><span data-stu-id="429c2-110">Attributes</span></span>

<span data-ttu-id="429c2-111">无</span><span class="sxs-lookup"><span data-stu-id="429c2-111">None</span></span>

### <a name="child-elements"></a><span data-ttu-id="429c2-112">子元素</span><span class="sxs-lookup"><span data-stu-id="429c2-112">Child elements</span></span>

|     | <span data-ttu-id="429c2-113">描述</span><span class="sxs-lookup"><span data-stu-id="429c2-113">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="429c2-114"> **\<filter>** </span><span class="sxs-lookup"><span data-stu-id="429c2-114">**\<filter>**</span></span>](filter.md) | <span data-ttu-id="429c2-115">包含一个路由筛选器, 该筛选器确定计算传入消息<xref:System.ServiceModel.Dispatcher.MessageFilter>时将使用的 Windows Communication Foundation (WCF) 的类型。</span><span class="sxs-lookup"><span data-stu-id="429c2-115">Contains a routing filter that determines the type of Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> will be used when evaluating incoming messages.</span></span> |

### <a name="parent-elements"></a><span data-ttu-id="429c2-116">父元素</span><span class="sxs-lookup"><span data-stu-id="429c2-116">Parent elements</span></span>

|     | <span data-ttu-id="429c2-117">描述</span><span class="sxs-lookup"><span data-stu-id="429c2-117">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="429c2-118"> **\<routing>** </span><span class="sxs-lookup"><span data-stu-id="429c2-118">**\<routing>**</span></span>](routing.md) | <span data-ttu-id="429c2-119">表示用于定义一组路由筛选器的配置节, 这些筛选器确定计算传入消息时要<xref:System.ServiceModel.Dispatcher.MessageFilter>使用的 Windows Communication Foundation (WCF) 的类型, 以及用于定义目标终结点的路由表。当筛选器匹配时向发送消息。</span><span class="sxs-lookup"><span data-stu-id="429c2-119">Represents a configuration section for defining a set of routing filters, which determine the type of Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages, as well as routing tables that define the target endpoints to send messages to when a filter matches.</span></span> |

## <a name="see-also"></a><span data-ttu-id="429c2-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="429c2-120">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.FilterElement?displayProperty=nameWithType>
