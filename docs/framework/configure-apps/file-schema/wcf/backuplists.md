---
title: '&lt;backupLists&gt;'
ms.date: 03/30/2017
ms.assetid: 593b3390-f65b-4684-ad40-0596b62f0954
ms.openlocfilehash: 5fb89ce5a942db40b07a65f59ddd05ab4cd624aa
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
ms.locfileid: "32749590"
---
# <a name="ltbackuplistsgt"></a><span data-ttu-id="39aa6-102">&lt;backupLists&gt;</span><span class="sxs-lookup"><span data-stu-id="39aa6-102">&lt;backupLists&gt;</span></span>
<span data-ttu-id="39aa6-103">表示一个配置节，用于定义一组用来处理错误的备份服务。</span><span class="sxs-lookup"><span data-stu-id="39aa6-103">Represents a configuration section for defining a set of backup services used in error handling.</span></span> <span data-ttu-id="39aa6-104">每个子元素是枚举一组你想要用于在的情况下无法访问主终结点的路由服务的终结点的备份列表。</span><span class="sxs-lookup"><span data-stu-id="39aa6-104">Each child element is a backup list that enumerates a set of endpoints that you would like the Routing Service to use in case the primary endpoint can't be reached.</span></span> <span data-ttu-id="39aa6-105">如果列表中的第一个终结点关闭，则路由服务会自动故障转移到列表中的下一个终结点。</span><span class="sxs-lookup"><span data-stu-id="39aa6-105">If the first endpoint in the list is down, the Routing Service will automatically fail-over to the next one in the list.</span></span>  <span data-ttu-id="39aa6-106">这样，可以方便地提高应用程序的可靠性，而不必告诉客户端应用程序应如何处理复杂模式或所有服务的部署位置。</span><span class="sxs-lookup"><span data-stu-id="39aa6-106">This gives you a quick way to add reliability to your application without having to teach your client application how to handle complex patterns or where all of your services are deployed.</span></span>  
  
 <span data-ttu-id="39aa6-107">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="39aa6-107">\<system.serviceModel></span></span>  
<span data-ttu-id="39aa6-108">\<路由 ></span><span class="sxs-lookup"><span data-stu-id="39aa6-108">\<routing></span></span>  
<span data-ttu-id="39aa6-109">\<backupLists ></span><span class="sxs-lookup"><span data-stu-id="39aa6-109">\<backupLists></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="39aa6-110">语法</span><span class="sxs-lookup"><span data-stu-id="39aa6-110">Syntax</span></span>  
  
```xml
   <routing>  <backupLists>    <backupList name="String">      <add endpointName="String" />    </backupList>    </backupLists></routing>  
```

## <a name="attributes-and-elements"></a><span data-ttu-id="39aa6-111">特性和元素</span><span class="sxs-lookup"><span data-stu-id="39aa6-111">Attributes and Elements</span></span>  
 <span data-ttu-id="39aa6-112">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="39aa6-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="39aa6-113">特性</span><span class="sxs-lookup"><span data-stu-id="39aa6-113">Attributes</span></span>  
 <span data-ttu-id="39aa6-114">无。</span><span class="sxs-lookup"><span data-stu-id="39aa6-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="39aa6-115">子元素</span><span class="sxs-lookup"><span data-stu-id="39aa6-115">Child Elements</span></span>  
  
|<span data-ttu-id="39aa6-116">元素</span><span class="sxs-lookup"><span data-stu-id="39aa6-116">Element</span></span>|<span data-ttu-id="39aa6-117">描述</span><span class="sxs-lookup"><span data-stu-id="39aa6-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="39aa6-118">\<filter></span><span class="sxs-lookup"><span data-stu-id="39aa6-118">\<filter></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/filter.md)|<span data-ttu-id="39aa6-119">包含你想要用于在的情况下无法访问主终结点的路由服务的终结点的列表。</span><span class="sxs-lookup"><span data-stu-id="39aa6-119">Contains a list of endpoints that you would like the Routing Service to use in case the primary endpoint can't be reached.</span></span> <span data-ttu-id="39aa6-120">.</span><span class="sxs-lookup"><span data-stu-id="39aa6-120">.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="39aa6-121">父元素</span><span class="sxs-lookup"><span data-stu-id="39aa6-121">Parent Elements</span></span>  
  
|<span data-ttu-id="39aa6-122">元素</span><span class="sxs-lookup"><span data-stu-id="39aa6-122">Element</span></span>|<span data-ttu-id="39aa6-123">描述</span><span class="sxs-lookup"><span data-stu-id="39aa6-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="39aa6-124">\<路由 ></span><span class="sxs-lookup"><span data-stu-id="39aa6-124">\<routing></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md)|<span data-ttu-id="39aa6-125">表示一个配置节，用于定义一组路由筛选器，这些扩展名决定了类型的 Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter>计算传入消息，以及路由表定义到的目标终结点时使用将消息发送到筛选器匹配时。</span><span class="sxs-lookup"><span data-stu-id="39aa6-125">Represents a configuration section for defining a set of routing filters, which determine the type of Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages, as well as routing tables that define the target endpoints to send messages to when a filter matches.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="39aa6-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="39aa6-126">See Also</span></span>  
 <xref:System.ServiceModel.Routing.Configuration.BackupEndpointCollection?displayProperty=nameWithType>    
