---
title: "&lt;路由&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a210c209-3940-4288-9a8e-39b1e62606bc
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 6ef71753a4b0ff20a966842119adb6e637ded1f9
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="ltroutinggt"></a><span data-ttu-id="40f47-102">&lt;路由&gt;</span><span class="sxs-lookup"><span data-stu-id="40f47-102">&lt;routing&gt;</span></span>

<span data-ttu-id="40f47-103">表示用于定义一组路由筛选器的配置节，这些筛选器确定计算传入消息时使用的 [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] <xref:System.ServiceModel.Dispatcher.MessageFilter> 的类型，以及用于定义在筛选器匹配时消息发送到的目标终结点的路由表。</span><span class="sxs-lookup"><span data-stu-id="40f47-103">Represents a configuration section for defining a set of routing filters, which determine the type of [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] <xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages, as well as routing tables that define the target endpoints to send messages to when a filter matches.</span></span>

<span data-ttu-id="40f47-104">[**\<system.serviceModel >**](system-servicemodel.md) </span><span class="sxs-lookup"><span data-stu-id="40f47-104">[**\<system.serviceModel>**](system-servicemodel.md) </span></span>  
<span data-ttu-id="40f47-105">&nbsp;&nbsp;**\<路由 >**</span><span class="sxs-lookup"><span data-stu-id="40f47-105">&nbsp;&nbsp;**\<routing>**</span></span>

## <a name="syntax"></a><span data-ttu-id="40f47-106">语法</span><span class="sxs-lookup"><span data-stu-id="40f47-106">Syntax</span></span>

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

## <a name="attributes-and-elements"></a><span data-ttu-id="40f47-107">特性和元素</span><span class="sxs-lookup"><span data-stu-id="40f47-107">Attributes and elements</span></span>

<span data-ttu-id="40f47-108">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="40f47-108">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="40f47-109">特性</span><span class="sxs-lookup"><span data-stu-id="40f47-109">Attributes</span></span>

<span data-ttu-id="40f47-110">无</span><span class="sxs-lookup"><span data-stu-id="40f47-110">None</span></span>

### <a name="child-elements"></a><span data-ttu-id="40f47-111">子元素</span><span class="sxs-lookup"><span data-stu-id="40f47-111">Child elements</span></span>

|     | <span data-ttu-id="40f47-112">描述</span><span class="sxs-lookup"><span data-stu-id="40f47-112">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="40f47-113">**\<筛选器 >**</span><span class="sxs-lookup"><span data-stu-id="40f47-113">**\<filters>**</span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/filters-of-routing.md) | <span data-ttu-id="40f47-114">包含一组路由筛选器，这些筛选器确定计算传入消息时将使用的 [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] MessageFilter 的类型。</span><span class="sxs-lookup"><span data-stu-id="40f47-114">Contains a set of routing filters that determine the type of [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] MessageFilter will be used when evaluating incoming messages.</span></span> |
| [<span data-ttu-id="40f47-115">**\<filterTables >**</span><span class="sxs-lookup"><span data-stu-id="40f47-115">**\<filterTables>**</span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/filtertables.md) | <span data-ttu-id="40f47-116">包含路由筛选器和目标终结点之间的映射，以便指定在筛选器匹配时使用的终结点。</span><span class="sxs-lookup"><span data-stu-id="40f47-116">Contains mappings between the routing filters and the target endpoints to specify which endpoint to use when the filter matches.</span></span> |

### <a name="parent-elements"></a><span data-ttu-id="40f47-117">父元素</span><span class="sxs-lookup"><span data-stu-id="40f47-117">Parent elements</span></span>

|     | <span data-ttu-id="40f47-118">描述</span><span class="sxs-lookup"><span data-stu-id="40f47-118">Description</span></span> |
| --- | ----------- |
| <span data-ttu-id="40f47-119">**\<系统。ServiceModel >**</span><span class="sxs-lookup"><span data-stu-id="40f47-119">**\<system.ServiceModel>**</span></span> | <span data-ttu-id="40f47-120">所有 WCF 配置元素的根元素。</span><span class="sxs-lookup"><span data-stu-id="40f47-120">The root element of all WCF configuration elements.</span></span> |

## <a name="see-also"></a><span data-ttu-id="40f47-121">请参阅</span><span class="sxs-lookup"><span data-stu-id="40f47-121">See also</span></span>

<xref:System.ServiceModel.Routing.Configuration.RoutingSection?displayProperty=nameWithType>
