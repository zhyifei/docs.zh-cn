---
title: <backupList>
ms.date: 03/30/2017
ms.assetid: a3d9d1f9-4a53-45e9-a880-86c8bee0b833
ms.openlocfilehash: 1e2b3eacbc845ad40030f3a48be2ef93c4ddbd8c
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/30/2019
ms.locfileid: "55262421"
---
# <a name="backuplist"></a><span data-ttu-id="03f06-101">\<backupList></span><span class="sxs-lookup"><span data-stu-id="03f06-101">\<backupList></span></span>
<span data-ttu-id="03f06-102">表示用于定义枚举一组你想要使用在的情况下无法访问主终结点的路由服务的终结点的备份列表的配置节。</span><span class="sxs-lookup"><span data-stu-id="03f06-102">Represents a configuration section for defining a backup list that enumerates a set of endpoints that you would like the Routing Service to use in case the primary endpoint can't be reached.</span></span> <span data-ttu-id="03f06-103">如果列表中的第一个终结点关闭，则路由服务会自动故障转移到列表中的下一个终结点。</span><span class="sxs-lookup"><span data-stu-id="03f06-103">If the first endpoint in the list is down, the Routing Service will automatically fail-over to the next one in the list.</span></span>  <span data-ttu-id="03f06-104">这样，可以方便地提高应用程序的可靠性，而不必告诉客户端应用程序应如何处理复杂模式或所有服务的部署位置。</span><span class="sxs-lookup"><span data-stu-id="03f06-104">This gives you a quick way to add reliability to your application without having to teach your client application how to handle complex patterns or where all of your services are deployed.</span></span>  
  
 <span data-ttu-id="03f06-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="03f06-105">\<system.serviceModel></span></span>  
<span data-ttu-id="03f06-106">\<路由 ></span><span class="sxs-lookup"><span data-stu-id="03f06-106">\<routing></span></span>  
<span data-ttu-id="03f06-107">\<backupLists></span><span class="sxs-lookup"><span data-stu-id="03f06-107">\<backupLists></span></span>  
<span data-ttu-id="03f06-108">\<backupList></span><span class="sxs-lookup"><span data-stu-id="03f06-108">\<backupList></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="03f06-109">语法</span><span class="sxs-lookup"><span data-stu-id="03f06-109">Syntax</span></span>  
  
```xml  
<routing>
  <backupLists>
    <backupList name="String">
      <add endpointName="String" />
    </backupList>
  </backupLists>
</routing>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="03f06-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="03f06-110">Attributes and Elements</span></span>  
 <span data-ttu-id="03f06-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="03f06-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="03f06-112">特性</span><span class="sxs-lookup"><span data-stu-id="03f06-112">Attributes</span></span>  
  
|<span data-ttu-id="03f06-113">特性</span><span class="sxs-lookup"><span data-stu-id="03f06-113">Attribute</span></span>|<span data-ttu-id="03f06-114">描述</span><span class="sxs-lookup"><span data-stu-id="03f06-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="03f06-115">name</span><span class="sxs-lookup"><span data-stu-id="03f06-115">name</span></span>|<span data-ttu-id="03f06-116">一个字符串，指定用于标识此终结点列表的名称。</span><span class="sxs-lookup"><span data-stu-id="03f06-116">A string that specifies the name used to identify this endpoint list.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="03f06-117">子元素</span><span class="sxs-lookup"><span data-stu-id="03f06-117">Child Elements</span></span>  
  
|<span data-ttu-id="03f06-118">元素</span><span class="sxs-lookup"><span data-stu-id="03f06-118">Element</span></span>|<span data-ttu-id="03f06-119">描述</span><span class="sxs-lookup"><span data-stu-id="03f06-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="03f06-120">\<filter></span><span class="sxs-lookup"><span data-stu-id="03f06-120">\<filter></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/filter.md)||  
  
### <a name="parent-elements"></a><span data-ttu-id="03f06-121">父元素</span><span class="sxs-lookup"><span data-stu-id="03f06-121">Parent Elements</span></span>  
  
|<span data-ttu-id="03f06-122">元素</span><span class="sxs-lookup"><span data-stu-id="03f06-122">Element</span></span>|<span data-ttu-id="03f06-123">描述</span><span class="sxs-lookup"><span data-stu-id="03f06-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="03f06-124">\<routing></span><span class="sxs-lookup"><span data-stu-id="03f06-124">\<routing></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md)|<span data-ttu-id="03f06-125">备份终结点列表。</span><span class="sxs-lookup"><span data-stu-id="03f06-125">A list of backup endpoints.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="03f06-126">备注</span><span class="sxs-lookup"><span data-stu-id="03f06-126">Remarks</span></span>  
 <span data-ttu-id="03f06-127">此节包含终结点的有序集合，如果在将消息发送到主终结点时发生通信异常，则会将消息传输到此集合。</span><span class="sxs-lookup"><span data-stu-id="03f06-127">This section contains an ordered collection of endpoints that a message will be transmitted to in the event of a communications exception when sending to the primary endpoint.</span></span>  
  
 <span data-ttu-id="03f06-128">如果在中列出的主终结点发送`endpointName`的属性[\<添加 >](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-entries.md)失败通信异常，路由服务会尝试将消息发送到在此第一个终结点配置节。</span><span class="sxs-lookup"><span data-stu-id="03f06-128">If a send to the primary endpoint listed in the `endpointName` attribute of [\<add>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-entries.md) fails with a communications exception, the Routing Service will attempt to send the message to the first endpoint in this configuration section.</span></span> <span data-ttu-id="03f06-129">如果此操作同样发生通信异常而导致发送失败，则路由服务会尝试将消息发送到此节包含的下一消息，直到发送尝试成功、返回除通信异常以外的故障或集合中的所有终结点均返回故障为止。</span><span class="sxs-lookup"><span data-stu-id="03f06-129">If this also fails with a communications exception, the Routing Service will attempt to send the message to the next message contained in this section until the send attempt succeeds, returns a failure other than a communication exception, or all endpoints in the collection have returned a failure.</span></span>  
  
 <span data-ttu-id="03f06-130">在以下示例中，如果名为"Destination"的主终结点发送返回通信异常，则服务会尝试将消息发送到"alternateServiceQueue"。</span><span class="sxs-lookup"><span data-stu-id="03f06-130">In the following example, if a send to the primary endpoint named "Destination" returns a communication exception, the service will attempt to send the message to the "alternateServiceQueue".</span></span> <span data-ttu-id="03f06-131">如果此尝试也返回一个通信异常，则路由服务会尝试将消息发送到集合中的下一个终结点。</span><span class="sxs-lookup"><span data-stu-id="03f06-131">If this attempt also returns a communication exception, the Routing Service will attempt to send the message to the next endpoint in the collection.</span></span>  
  
```xml  
<filterTables>
  <filterTable name="filterTable1">
    <add filterName="MatchAllFilter1"
         endpointName="Destination"
         backupList="backupEndpointList" />
  </filterTable>
</filterTables>
<backupLists>
  <backupList name="backupEndpointList">
    <add endpointName="backupServiceQueue" />
    <add endpointName="alternateServiceQueue" />
  </backupList>
</backupLists>
```  
  
## <a name="see-also"></a><span data-ttu-id="03f06-132">请参阅</span><span class="sxs-lookup"><span data-stu-id="03f06-132">See also</span></span>
- <xref:System.ServiceModel.Routing.Configuration.BackupEndpointCollection?displayProperty=nameWithType>
