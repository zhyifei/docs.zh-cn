---
title: <backupLists>
ms.date: 03/30/2017
ms.assetid: 593b3390-f65b-4684-ad40-0596b62f0954
ms.openlocfilehash: 5f2bb030d13389e15cb44f1ddff3b8168b4f2140
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2019
ms.locfileid: "70850266"
---
# <a name="backuplists"></a><span data-ttu-id="62523-101">\<backupLists></span><span class="sxs-lookup"><span data-stu-id="62523-101">\<backupLists></span></span>
<span data-ttu-id="62523-102">表示一个配置节，用于定义一组用来处理错误的备份服务。</span><span class="sxs-lookup"><span data-stu-id="62523-102">Represents a configuration section for defining a set of backup services used in error handling.</span></span> <span data-ttu-id="62523-103">每个子元素都是一个备份列表，该列表枚举了在无法访问主终结点时路由服务将使用的一组终结点。</span><span class="sxs-lookup"><span data-stu-id="62523-103">Each child element is a backup list that enumerates a set of endpoints that you would like the Routing Service to use in case the primary endpoint can't be reached.</span></span> <span data-ttu-id="62523-104">如果列表中的第一个终结点关闭，则路由服务会自动故障转移到列表中的下一个终结点。</span><span class="sxs-lookup"><span data-stu-id="62523-104">If the first endpoint in the list is down, the Routing Service will automatically fail-over to the next one in the list.</span></span>  <span data-ttu-id="62523-105">这样，可以方便地提高应用程序的可靠性，而不必告诉客户端应用程序应如何处理复杂模式或所有服务的部署位置。</span><span class="sxs-lookup"><span data-stu-id="62523-105">This gives you a quick way to add reliability to your application without having to teach your client application how to handle complex patterns or where all of your services are deployed.</span></span>  
  
<span data-ttu-id="62523-106">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="62523-106">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="62523-107">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="62523-107">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="62523-108">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<路由 >** ](routing.md)</span><span class="sxs-lookup"><span data-stu-id="62523-108">&nbsp;&nbsp;&nbsp;&nbsp;[**\<routing>**](routing.md)</span></span>\
<span data-ttu-id="62523-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<backupLists >**</span><span class="sxs-lookup"><span data-stu-id="62523-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<backupLists>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="62523-110">语法</span><span class="sxs-lookup"><span data-stu-id="62523-110">Syntax</span></span>  
  
```xml  
<routing>
  <backupLists>
    <backupList name="String">
      <add endpointName="String" />
    </backupList>
  </backupLists>
</routing>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="62523-111">特性和元素</span><span class="sxs-lookup"><span data-stu-id="62523-111">Attributes and Elements</span></span>  
 <span data-ttu-id="62523-112">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="62523-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="62523-113">特性</span><span class="sxs-lookup"><span data-stu-id="62523-113">Attributes</span></span>  
 <span data-ttu-id="62523-114">无。</span><span class="sxs-lookup"><span data-stu-id="62523-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="62523-115">子元素</span><span class="sxs-lookup"><span data-stu-id="62523-115">Child Elements</span></span>  
  
|<span data-ttu-id="62523-116">元素</span><span class="sxs-lookup"><span data-stu-id="62523-116">Element</span></span>|<span data-ttu-id="62523-117">描述</span><span class="sxs-lookup"><span data-stu-id="62523-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="62523-118">\<filter></span><span class="sxs-lookup"><span data-stu-id="62523-118">\<filter></span></span>](filter.md)|<span data-ttu-id="62523-119">包含当无法访问主终结点时路由服务将使用的终结点的列表。</span><span class="sxs-lookup"><span data-stu-id="62523-119">Contains a list of endpoints that you would like the Routing Service to use in case the primary endpoint can't be reached.</span></span> <span data-ttu-id="62523-120">.</span><span class="sxs-lookup"><span data-stu-id="62523-120">.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="62523-121">父元素</span><span class="sxs-lookup"><span data-stu-id="62523-121">Parent Elements</span></span>  
  
|<span data-ttu-id="62523-122">元素</span><span class="sxs-lookup"><span data-stu-id="62523-122">Element</span></span>|<span data-ttu-id="62523-123">描述</span><span class="sxs-lookup"><span data-stu-id="62523-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="62523-124">\<routing></span><span class="sxs-lookup"><span data-stu-id="62523-124">\<routing></span></span>](routing.md)|<span data-ttu-id="62523-125">表示用于定义一组路由筛选器的配置节，这些筛选器确定计算传入消息时要<xref:System.ServiceModel.Dispatcher.MessageFilter>使用的 Windows Communication Foundation （WCF）的类型，以及用于定义目标终结点的路由表。当筛选器匹配时向发送消息。</span><span class="sxs-lookup"><span data-stu-id="62523-125">Represents a configuration section for defining a set of routing filters, which determine the type of Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages, as well as routing tables that define the target endpoints to send messages to when a filter matches.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="62523-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="62523-126">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.BackupEndpointCollection?displayProperty=nameWithType>
