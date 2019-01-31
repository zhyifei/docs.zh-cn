---
title: <filters> 的 <routing>
ms.date: 03/30/2017
ms.assetid: 7993cf90-9afd-4c3c-9608-184d5da1105c
ms.openlocfilehash: 8b2c735a19c4cece16dcb77e3ec548eb2d39ec18
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/30/2019
ms.locfileid: "55272655"
---
# <a name="filters-of-routing"></a><span data-ttu-id="23590-102">\<筛选器 > 的\<路由 ></span><span class="sxs-lookup"><span data-stu-id="23590-102">\<filters> of \<routing></span></span>

<span data-ttu-id="23590-103">表示一个配置节，用于定义一组路由筛选器，确定类型的 Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter>要评估传入消息时使用。</span><span class="sxs-lookup"><span data-stu-id="23590-103">Represents a configuration section for defining a set of routing filters, which determine the type of Windows Communication Foundation (WCF) <xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages.</span></span>

<span data-ttu-id="23590-104">[**\<system.serviceModel>**](system-servicemodel.md) </span><span class="sxs-lookup"><span data-stu-id="23590-104">[**\<system.serviceModel>**](system-servicemodel.md) </span></span>  
<span data-ttu-id="23590-105">&nbsp;&nbsp;[**\<routing>**](routing.md) </span><span class="sxs-lookup"><span data-stu-id="23590-105">&nbsp;&nbsp;[**\<routing>**](routing.md) </span></span>  
<span data-ttu-id="23590-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<filters>**</span><span class="sxs-lookup"><span data-stu-id="23590-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<filters>**</span></span>
  
## <a name="syntax"></a><span data-ttu-id="23590-107">语法</span><span class="sxs-lookup"><span data-stu-id="23590-107">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="23590-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="23590-108">Attributes and elements</span></span>

<span data-ttu-id="23590-109">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="23590-109">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="23590-110">特性</span><span class="sxs-lookup"><span data-stu-id="23590-110">Attributes</span></span>

<span data-ttu-id="23590-111">无</span><span class="sxs-lookup"><span data-stu-id="23590-111">None</span></span>

### <a name="child-elements"></a><span data-ttu-id="23590-112">子元素</span><span class="sxs-lookup"><span data-stu-id="23590-112">Child elements</span></span>

|     | <span data-ttu-id="23590-113">描述</span><span class="sxs-lookup"><span data-stu-id="23590-113">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="23590-114">**\<filter>**</span><span class="sxs-lookup"><span data-stu-id="23590-114">**\<filter>**</span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/filter.md) | <span data-ttu-id="23590-115">包含确定类型的 Windows Communication Foundation (WCF) 的路由筛选器<xref:System.ServiceModel.Dispatcher.MessageFilter>计算传入消息时将使用。</span><span class="sxs-lookup"><span data-stu-id="23590-115">Contains a routing filter that determines the type of Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> will be used when evaluating incoming messages.</span></span> |

### <a name="parent-elements"></a><span data-ttu-id="23590-116">父元素</span><span class="sxs-lookup"><span data-stu-id="23590-116">Parent elements</span></span>

|     | <span data-ttu-id="23590-117">描述</span><span class="sxs-lookup"><span data-stu-id="23590-117">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="23590-118">**\<routing>**</span><span class="sxs-lookup"><span data-stu-id="23590-118">**\<routing>**</span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md) | <span data-ttu-id="23590-119">表示一个配置节，用于定义一组路由筛选器，确定类型的 Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter>用于计算传入消息，以及路由表定义到的目标终结点将消息发送到筛选器匹配时。</span><span class="sxs-lookup"><span data-stu-id="23590-119">Represents a configuration section for defining a set of routing filters, which determine the type of Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages, as well as routing tables that define the target endpoints to send messages to when a filter matches.</span></span> |

## <a name="see-also"></a><span data-ttu-id="23590-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="23590-120">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.FilterElement?displayProperty=nameWithType>
