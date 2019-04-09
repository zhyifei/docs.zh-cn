---
title: <backupLists>
ms.date: 03/30/2017
ms.assetid: 593b3390-f65b-4684-ad40-0596b62f0954
ms.openlocfilehash: 6e44dbe3c0966c6d243db343b9f9b0dec2480cb1
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59134441"
---
# <a name="backuplists"></a><span data-ttu-id="7e4c4-101">\<backupLists></span><span class="sxs-lookup"><span data-stu-id="7e4c4-101">\<backupLists></span></span>
<span data-ttu-id="7e4c4-102">表示一个配置节，用于定义一组用来处理错误的备份服务。</span><span class="sxs-lookup"><span data-stu-id="7e4c4-102">Represents a configuration section for defining a set of backup services used in error handling.</span></span> <span data-ttu-id="7e4c4-103">每个子元素是枚举一组你想要使用在的情况下无法访问主终结点的路由服务的终结点的备份列表。</span><span class="sxs-lookup"><span data-stu-id="7e4c4-103">Each child element is a backup list that enumerates a set of endpoints that you would like the Routing Service to use in case the primary endpoint can't be reached.</span></span> <span data-ttu-id="7e4c4-104">如果列表中的第一个终结点关闭，则路由服务会自动故障转移到列表中的下一个终结点。</span><span class="sxs-lookup"><span data-stu-id="7e4c4-104">If the first endpoint in the list is down, the Routing Service will automatically fail-over to the next one in the list.</span></span>  <span data-ttu-id="7e4c4-105">这样，可以方便地提高应用程序的可靠性，而不必告诉客户端应用程序应如何处理复杂模式或所有服务的部署位置。</span><span class="sxs-lookup"><span data-stu-id="7e4c4-105">This gives you a quick way to add reliability to your application without having to teach your client application how to handle complex patterns or where all of your services are deployed.</span></span>  
  
 <span data-ttu-id="7e4c4-106">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="7e4c4-106">\<system.serviceModel></span></span>  
<span data-ttu-id="7e4c4-107">\<路由 ></span><span class="sxs-lookup"><span data-stu-id="7e4c4-107">\<routing></span></span>  
<span data-ttu-id="7e4c4-108">\<backupLists></span><span class="sxs-lookup"><span data-stu-id="7e4c4-108">\<backupLists></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7e4c4-109">语法</span><span class="sxs-lookup"><span data-stu-id="7e4c4-109">Syntax</span></span>  
  
```xml  
<routing>
  <backupLists>
    <backupList name="String">
      <add endpointName="String" />
    </backupList>
  </backupLists>
</routing>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7e4c4-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="7e4c4-110">Attributes and Elements</span></span>  
 <span data-ttu-id="7e4c4-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="7e4c4-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7e4c4-112">特性</span><span class="sxs-lookup"><span data-stu-id="7e4c4-112">Attributes</span></span>  
 <span data-ttu-id="7e4c4-113">无。</span><span class="sxs-lookup"><span data-stu-id="7e4c4-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="7e4c4-114">子元素</span><span class="sxs-lookup"><span data-stu-id="7e4c4-114">Child Elements</span></span>  
  
|<span data-ttu-id="7e4c4-115">元素</span><span class="sxs-lookup"><span data-stu-id="7e4c4-115">Element</span></span>|<span data-ttu-id="7e4c4-116">描述</span><span class="sxs-lookup"><span data-stu-id="7e4c4-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7e4c4-117">\<filter></span><span class="sxs-lookup"><span data-stu-id="7e4c4-117">\<filter></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/filter.md)|<span data-ttu-id="7e4c4-118">包含你想要使用在的情况下无法访问主终结点的路由服务的终结点的列表。</span><span class="sxs-lookup"><span data-stu-id="7e4c4-118">Contains a list of endpoints that you would like the Routing Service to use in case the primary endpoint can't be reached.</span></span> <span data-ttu-id="7e4c4-119">.</span><span class="sxs-lookup"><span data-stu-id="7e4c4-119">.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="7e4c4-120">父元素</span><span class="sxs-lookup"><span data-stu-id="7e4c4-120">Parent Elements</span></span>  
  
|<span data-ttu-id="7e4c4-121">元素</span><span class="sxs-lookup"><span data-stu-id="7e4c4-121">Element</span></span>|<span data-ttu-id="7e4c4-122">描述</span><span class="sxs-lookup"><span data-stu-id="7e4c4-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7e4c4-123">\<路由 ></span><span class="sxs-lookup"><span data-stu-id="7e4c4-123">\<routing></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md)|<span data-ttu-id="7e4c4-124">表示一个配置节，用于定义一组路由筛选器，确定类型的 Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter>用于计算传入消息，以及路由表定义到的目标终结点将消息发送到筛选器匹配时。</span><span class="sxs-lookup"><span data-stu-id="7e4c4-124">Represents a configuration section for defining a set of routing filters, which determine the type of Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages, as well as routing tables that define the target endpoints to send messages to when a filter matches.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="7e4c4-125">请参阅</span><span class="sxs-lookup"><span data-stu-id="7e4c4-125">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.BackupEndpointCollection?displayProperty=nameWithType>
