---
title: '&lt;路由&gt;'
ms.date: 03/30/2017
ms.assetid: a210c209-3940-4288-9a8e-39b1e62606bc
ms.openlocfilehash: 220c18ab8ea6222fcf7d9fb8a93950281c9de796
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/09/2019
ms.locfileid: "54145141"
---
# <a name="ltroutinggt"></a><span data-ttu-id="206f3-102">&lt;路由&gt;</span><span class="sxs-lookup"><span data-stu-id="206f3-102">&lt;routing&gt;</span></span>

<span data-ttu-id="206f3-103">表示一个配置节，用于定义一组路由筛选器，确定类型的 Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter>用于计算传入消息，以及路由表定义到的目标终结点将消息发送到筛选器匹配时。</span><span class="sxs-lookup"><span data-stu-id="206f3-103">Represents a configuration section for defining a set of routing filters, which determine the type of Windows Communication Foundation (WCF) <xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages, as well as routing tables that define the target endpoints to send messages to when a filter matches.</span></span>

<span data-ttu-id="206f3-104">[**\<system.serviceModel >**](system-servicemodel.md) </span><span class="sxs-lookup"><span data-stu-id="206f3-104">[**\<system.serviceModel>**](system-servicemodel.md) </span></span>  
<span data-ttu-id="206f3-105">&nbsp;&nbsp;**\<路由 >**</span><span class="sxs-lookup"><span data-stu-id="206f3-105">&nbsp;&nbsp;**\<routing>**</span></span>
  
## <a name="syntax"></a><span data-ttu-id="206f3-106">语法</span><span class="sxs-lookup"><span data-stu-id="206f3-106">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="206f3-107">特性和元素</span><span class="sxs-lookup"><span data-stu-id="206f3-107">Attributes and elements</span></span>

<span data-ttu-id="206f3-108">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="206f3-108">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="206f3-109">特性</span><span class="sxs-lookup"><span data-stu-id="206f3-109">Attributes</span></span>

<span data-ttu-id="206f3-110">无</span><span class="sxs-lookup"><span data-stu-id="206f3-110">None</span></span>

### <a name="child-elements"></a><span data-ttu-id="206f3-111">子元素</span><span class="sxs-lookup"><span data-stu-id="206f3-111">Child elements</span></span>

|     | <span data-ttu-id="206f3-112">描述</span><span class="sxs-lookup"><span data-stu-id="206f3-112">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="206f3-113">**\<筛选器 >**</span><span class="sxs-lookup"><span data-stu-id="206f3-113">**\<filters>**</span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/filters-of-routing.md) | <span data-ttu-id="206f3-114">包含一组路由筛选器确定计算传入消息时，将使用 Windows Communication Foundation (WCF) MessageFilter 的类型。</span><span class="sxs-lookup"><span data-stu-id="206f3-114">Contains a set of routing filters that determine the type of Windows Communication Foundation (WCF) MessageFilter will be used when evaluating incoming messages.</span></span> |
| [<span data-ttu-id="206f3-115">**\<filterTables >**</span><span class="sxs-lookup"><span data-stu-id="206f3-115">**\<filterTables>**</span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/filtertables.md) | <span data-ttu-id="206f3-116">包含路由筛选器和目标终结点之间的映射，以便指定在筛选器匹配时使用的终结点。</span><span class="sxs-lookup"><span data-stu-id="206f3-116">Contains mappings between the routing filters and the target endpoints to specify which endpoint to use when the filter matches.</span></span> |

### <a name="parent-elements"></a><span data-ttu-id="206f3-117">父元素</span><span class="sxs-lookup"><span data-stu-id="206f3-117">Parent elements</span></span>

|     | <span data-ttu-id="206f3-118">描述</span><span class="sxs-lookup"><span data-stu-id="206f3-118">Description</span></span> |
| --- | ----------- |
| <span data-ttu-id="206f3-119">**\<系统。ServiceModel >**</span><span class="sxs-lookup"><span data-stu-id="206f3-119">**\<system.ServiceModel>**</span></span> | <span data-ttu-id="206f3-120">所有 WCF 配置元素的根元素。</span><span class="sxs-lookup"><span data-stu-id="206f3-120">The root element of all WCF configuration elements.</span></span> |

## <a name="see-also"></a><span data-ttu-id="206f3-121">请参阅</span><span class="sxs-lookup"><span data-stu-id="206f3-121">See also</span></span>

<xref:System.ServiceModel.Routing.Configuration.RoutingSection?displayProperty=nameWithType>
