---
title: '&lt;backupLists&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 593b3390-f65b-4684-ad40-0596b62f0954
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 437cb1320147d5d76a4df9c3a00b4ee27bf650b0
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="ltbackuplistsgt"></a><span data-ttu-id="6b61f-102">&lt;backupLists&gt;</span><span class="sxs-lookup"><span data-stu-id="6b61f-102">&lt;backupLists&gt;</span></span>
<span data-ttu-id="6b61f-103">表示一个配置节，用于定义一组用来处理错误的备份服务。</span><span class="sxs-lookup"><span data-stu-id="6b61f-103">Represents a configuration section for defining a set of backup services used in error handling.</span></span> <span data-ttu-id="6b61f-104">每个子元素是枚举一组你想要用于在的情况下无法访问主终结点的路由服务的终结点的备份列表。</span><span class="sxs-lookup"><span data-stu-id="6b61f-104">Each child element is a backup list that enumerates a set of endpoints that you would like the Routing Service to use in case the primary endpoint can't be reached.</span></span> <span data-ttu-id="6b61f-105">如果列表中的第一个终结点关闭，则路由服务会自动故障转移到列表中的下一个终结点。</span><span class="sxs-lookup"><span data-stu-id="6b61f-105">If the first endpoint in the list is down, the Routing Service will automatically fail-over to the next one in the list.</span></span>  <span data-ttu-id="6b61f-106">这样，可以方便地提高应用程序的可靠性，而不必告诉客户端应用程序应如何处理复杂模式或所有服务的部署位置。</span><span class="sxs-lookup"><span data-stu-id="6b61f-106">This gives you a quick way to add reliability to your application without having to teach your client application how to handle complex patterns or where all of your services are deployed.</span></span>  
  
 <span data-ttu-id="6b61f-107">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="6b61f-107">\<system.serviceModel></span></span>  
<span data-ttu-id="6b61f-108">\<路由 ></span><span class="sxs-lookup"><span data-stu-id="6b61f-108">\<routing></span></span>  
<span data-ttu-id="6b61f-109">\<backupLists ></span><span class="sxs-lookup"><span data-stu-id="6b61f-109">\<backupLists></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6b61f-110">语法</span><span class="sxs-lookup"><span data-stu-id="6b61f-110">Syntax</span></span>  
  
```xml
   <routing>  <backupLists>    <backupList name="String">      <add endpointName="String" />    </backupList>    </backupLists></routing>  
```

## <a name="attributes-and-elements"></a><span data-ttu-id="6b61f-111">特性和元素</span><span class="sxs-lookup"><span data-stu-id="6b61f-111">Attributes and Elements</span></span>  
 <span data-ttu-id="6b61f-112">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="6b61f-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6b61f-113">特性</span><span class="sxs-lookup"><span data-stu-id="6b61f-113">Attributes</span></span>  
 <span data-ttu-id="6b61f-114">无。</span><span class="sxs-lookup"><span data-stu-id="6b61f-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="6b61f-115">子元素</span><span class="sxs-lookup"><span data-stu-id="6b61f-115">Child Elements</span></span>  
  
|<span data-ttu-id="6b61f-116">元素</span><span class="sxs-lookup"><span data-stu-id="6b61f-116">Element</span></span>|<span data-ttu-id="6b61f-117">描述</span><span class="sxs-lookup"><span data-stu-id="6b61f-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6b61f-118">\<filter></span><span class="sxs-lookup"><span data-stu-id="6b61f-118">\<filter></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/filter.md)|<span data-ttu-id="6b61f-119">包含你想要用于在的情况下无法访问主终结点的路由服务的终结点的列表。</span><span class="sxs-lookup"><span data-stu-id="6b61f-119">Contains a list of endpoints that you would like the Routing Service to use in case the primary endpoint can't be reached.</span></span> <span data-ttu-id="6b61f-120">.</span><span class="sxs-lookup"><span data-stu-id="6b61f-120">.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="6b61f-121">父元素</span><span class="sxs-lookup"><span data-stu-id="6b61f-121">Parent Elements</span></span>  
  
|<span data-ttu-id="6b61f-122">元素</span><span class="sxs-lookup"><span data-stu-id="6b61f-122">Element</span></span>|<span data-ttu-id="6b61f-123">描述</span><span class="sxs-lookup"><span data-stu-id="6b61f-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6b61f-124">\<路由 ></span><span class="sxs-lookup"><span data-stu-id="6b61f-124">\<routing></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md)|<span data-ttu-id="6b61f-125">表示用于定义一组路由筛选器的配置节，这些筛选器确定计算传入消息时使用的 [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)]<xref:System.ServiceModel.Dispatcher.MessageFilter> 的类型，以及用于定义在筛选器匹配时消息发送到的目标终结点的路由表。</span><span class="sxs-lookup"><span data-stu-id="6b61f-125">Represents a configuration section for defining a set of routing filters, which determine the type of [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)]<xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages, as well as routing tables that define the target endpoints to send messages to when a filter matches.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="6b61f-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6b61f-126">See Also</span></span>  
 <xref:System.ServiceModel.Routing.Configuration.BackupEndpointCollection?displayProperty=nameWithType>    
