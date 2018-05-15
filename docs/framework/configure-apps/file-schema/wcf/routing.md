---
title: '&lt;路由&gt;'
ms.date: 03/30/2017
ms.assetid: a210c209-3940-4288-9a8e-39b1e62606bc
ms.openlocfilehash: 1771d8a2603a8f61af6ba6e2acf6243d2fd073f7
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
---
# <a name="ltroutinggt"></a><span data-ttu-id="863eb-102">&lt;路由&gt;</span><span class="sxs-lookup"><span data-stu-id="863eb-102">&lt;routing&gt;</span></span>

<span data-ttu-id="863eb-103">表示一个配置节，用于定义一组路由筛选器，这些扩展名决定了类型的 Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter>计算传入消息，以及路由表定义到的目标终结点时使用将消息发送到筛选器匹配时。</span><span class="sxs-lookup"><span data-stu-id="863eb-103">Represents a configuration section for defining a set of routing filters, which determine the type of Windows Communication Foundation (WCF) <xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages, as well as routing tables that define the target endpoints to send messages to when a filter matches.</span></span>

<span data-ttu-id="863eb-104">[**\<system.serviceModel >**](system-servicemodel.md) </span><span class="sxs-lookup"><span data-stu-id="863eb-104">[**\<system.serviceModel>**](system-servicemodel.md) </span></span>  
<span data-ttu-id="863eb-105">&nbsp;&nbsp;**\<路由 >**</span><span class="sxs-lookup"><span data-stu-id="863eb-105">&nbsp;&nbsp;**\<routing>**</span></span>

## <a name="syntax"></a><span data-ttu-id="863eb-106">语法</span><span class="sxs-lookup"><span data-stu-id="863eb-106">Syntax</span></span>

```xml
<system.serviceModel>
  <routing>
    <filters>
      <filter customType="String" 
              filterData="String" 
              filterType="Action/Address/AddressPrefix/And/Custom/Endpoint/MatchAll/XPath" 
              name="String" />
    </filters>
    <routingTables>
      <table name="String">
        <entries>
          <add endpoint="String" 
               filterName="String" 
               priority="Integer" />
        </entries>
      </table>
    </routingTables>
  </routing>
</system.serviceModel>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="863eb-107">特性和元素</span><span class="sxs-lookup"><span data-stu-id="863eb-107">Attributes and elements</span></span>

<span data-ttu-id="863eb-108">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="863eb-108">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="863eb-109">特性</span><span class="sxs-lookup"><span data-stu-id="863eb-109">Attributes</span></span>

<span data-ttu-id="863eb-110">无</span><span class="sxs-lookup"><span data-stu-id="863eb-110">None</span></span>

### <a name="child-elements"></a><span data-ttu-id="863eb-111">子元素</span><span class="sxs-lookup"><span data-stu-id="863eb-111">Child elements</span></span>

|     | <span data-ttu-id="863eb-112">描述</span><span class="sxs-lookup"><span data-stu-id="863eb-112">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="863eb-113">**\<筛选器 >**</span><span class="sxs-lookup"><span data-stu-id="863eb-113">**\<filters>**</span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/filters-of-routing.md) | <span data-ttu-id="863eb-114">包含一组路由筛选器确定计算传入消息时，将使用 Windows Communication Foundation (WCF) MessageFilter 的类型。</span><span class="sxs-lookup"><span data-stu-id="863eb-114">Contains a set of routing filters that determine the type of Windows Communication Foundation (WCF) MessageFilter will be used when evaluating incoming messages.</span></span> |
| [<span data-ttu-id="863eb-115">**\<filterTables >**</span><span class="sxs-lookup"><span data-stu-id="863eb-115">**\<filterTables>**</span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/filtertables.md) | <span data-ttu-id="863eb-116">包含路由筛选器和目标终结点之间的映射，以便指定在筛选器匹配时使用的终结点。</span><span class="sxs-lookup"><span data-stu-id="863eb-116">Contains mappings between the routing filters and the target endpoints to specify which endpoint to use when the filter matches.</span></span> |

### <a name="parent-elements"></a><span data-ttu-id="863eb-117">父元素</span><span class="sxs-lookup"><span data-stu-id="863eb-117">Parent elements</span></span>

|     | <span data-ttu-id="863eb-118">描述</span><span class="sxs-lookup"><span data-stu-id="863eb-118">Description</span></span> |
| --- | ----------- |
| <span data-ttu-id="863eb-119">**\<系统。ServiceModel >**</span><span class="sxs-lookup"><span data-stu-id="863eb-119">**\<system.ServiceModel>**</span></span> | <span data-ttu-id="863eb-120">所有 WCF 配置元素的根元素。</span><span class="sxs-lookup"><span data-stu-id="863eb-120">The root element of all WCF configuration elements.</span></span> |

## <a name="see-also"></a><span data-ttu-id="863eb-121">请参阅</span><span class="sxs-lookup"><span data-stu-id="863eb-121">See also</span></span>

<xref:System.ServiceModel.Routing.Configuration.RoutingSection?displayProperty=nameWithType>
