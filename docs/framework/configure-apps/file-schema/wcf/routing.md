---
title: <routing>
ms.date: 03/30/2017
ms.assetid: a210c209-3940-4288-9a8e-39b1e62606bc
ms.openlocfilehash: cc7c1a64f9481a7ab41cf35241ade04bd690dae0
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/30/2019
ms.locfileid: "55275569"
---
# <a name="routing"></a><span data-ttu-id="9a5c3-101">\<路由 ></span><span class="sxs-lookup"><span data-stu-id="9a5c3-101">\<routing></span></span>

<span data-ttu-id="9a5c3-102">表示一个配置节，用于定义一组路由筛选器，确定类型的 Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter>用于计算传入消息，以及路由表定义到的目标终结点将消息发送到筛选器匹配时。</span><span class="sxs-lookup"><span data-stu-id="9a5c3-102">Represents a configuration section for defining a set of routing filters, which determine the type of Windows Communication Foundation (WCF) <xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages, as well as routing tables that define the target endpoints to send messages to when a filter matches.</span></span>

<span data-ttu-id="9a5c3-103">[**\<system.serviceModel>**](system-servicemodel.md) </span><span class="sxs-lookup"><span data-stu-id="9a5c3-103">[**\<system.serviceModel>**](system-servicemodel.md) </span></span>  
<span data-ttu-id="9a5c3-104">&nbsp;&nbsp;**\<routing>**</span><span class="sxs-lookup"><span data-stu-id="9a5c3-104">&nbsp;&nbsp;**\<routing>**</span></span>
  
## <a name="syntax"></a><span data-ttu-id="9a5c3-105">语法</span><span class="sxs-lookup"><span data-stu-id="9a5c3-105">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9a5c3-106">特性和元素</span><span class="sxs-lookup"><span data-stu-id="9a5c3-106">Attributes and elements</span></span>

<span data-ttu-id="9a5c3-107">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="9a5c3-107">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="9a5c3-108">特性</span><span class="sxs-lookup"><span data-stu-id="9a5c3-108">Attributes</span></span>

<span data-ttu-id="9a5c3-109">无</span><span class="sxs-lookup"><span data-stu-id="9a5c3-109">None</span></span>

### <a name="child-elements"></a><span data-ttu-id="9a5c3-110">子元素</span><span class="sxs-lookup"><span data-stu-id="9a5c3-110">Child elements</span></span>

|     | <span data-ttu-id="9a5c3-111">描述</span><span class="sxs-lookup"><span data-stu-id="9a5c3-111">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="9a5c3-112">**\<filters>**</span><span class="sxs-lookup"><span data-stu-id="9a5c3-112">**\<filters>**</span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/filters-of-routing.md) | <span data-ttu-id="9a5c3-113">包含一组路由筛选器确定计算传入消息时，将使用 Windows Communication Foundation (WCF) MessageFilter 的类型。</span><span class="sxs-lookup"><span data-stu-id="9a5c3-113">Contains a set of routing filters that determine the type of Windows Communication Foundation (WCF) MessageFilter will be used when evaluating incoming messages.</span></span> |
| [<span data-ttu-id="9a5c3-114">**\<filterTables>**</span><span class="sxs-lookup"><span data-stu-id="9a5c3-114">**\<filterTables>**</span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/filtertables.md) | <span data-ttu-id="9a5c3-115">包含路由筛选器和目标终结点之间的映射，以便指定在筛选器匹配时使用的终结点。</span><span class="sxs-lookup"><span data-stu-id="9a5c3-115">Contains mappings between the routing filters and the target endpoints to specify which endpoint to use when the filter matches.</span></span> |

### <a name="parent-elements"></a><span data-ttu-id="9a5c3-116">父元素</span><span class="sxs-lookup"><span data-stu-id="9a5c3-116">Parent elements</span></span>

|     | <span data-ttu-id="9a5c3-117">描述</span><span class="sxs-lookup"><span data-stu-id="9a5c3-117">Description</span></span> |
| --- | ----------- |
| <span data-ttu-id="9a5c3-118">**\<system.ServiceModel>**</span><span class="sxs-lookup"><span data-stu-id="9a5c3-118">**\<system.ServiceModel>**</span></span> | <span data-ttu-id="9a5c3-119">所有 WCF 配置元素的根元素。</span><span class="sxs-lookup"><span data-stu-id="9a5c3-119">The root element of all WCF configuration elements.</span></span> |

## <a name="see-also"></a><span data-ttu-id="9a5c3-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="9a5c3-120">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.RoutingSection?displayProperty=nameWithType>
