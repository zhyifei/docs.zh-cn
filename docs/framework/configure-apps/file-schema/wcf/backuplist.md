---
title: <backupList>
ms.date: 03/30/2017
ms.assetid: a3d9d1f9-4a53-45e9-a880-86c8bee0b833
ms.openlocfilehash: 478211755b9131c03b72777ee95ff7223b9092c9
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2019
ms.locfileid: "70850270"
---
# <a name="backuplist"></a><span data-ttu-id="88d40-101">\<backupList></span><span class="sxs-lookup"><span data-stu-id="88d40-101">\<backupList></span></span>
<span data-ttu-id="88d40-102">表示一个配置节，该配置节用于定义一个备份列表，该列表枚举在无法访问主终结点时路由服务将使用的一组终结点。</span><span class="sxs-lookup"><span data-stu-id="88d40-102">Represents a configuration section for defining a backup list that enumerates a set of endpoints that you would like the Routing Service to use in case the primary endpoint can't be reached.</span></span> <span data-ttu-id="88d40-103">如果列表中的第一个终结点关闭，则路由服务会自动故障转移到列表中的下一个终结点。</span><span class="sxs-lookup"><span data-stu-id="88d40-103">If the first endpoint in the list is down, the Routing Service will automatically fail-over to the next one in the list.</span></span>  <span data-ttu-id="88d40-104">这样，可以方便地提高应用程序的可靠性，而不必告诉客户端应用程序应如何处理复杂模式或所有服务的部署位置。</span><span class="sxs-lookup"><span data-stu-id="88d40-104">This gives you a quick way to add reliability to your application without having to teach your client application how to handle complex patterns or where all of your services are deployed.</span></span>  
  
<span data-ttu-id="88d40-105">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="88d40-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="88d40-106">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="88d40-106">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="88d40-107">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<路由 >** ](routing.md)</span><span class="sxs-lookup"><span data-stu-id="88d40-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<routing>**](routing.md)</span></span>\
<span data-ttu-id="88d40-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<backupLists >** ](backuplists.md)</span><span class="sxs-lookup"><span data-stu-id="88d40-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<backupLists>**](backuplists.md)</span></span>\
<span data-ttu-id="88d40-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<backupList >**</span><span class="sxs-lookup"><span data-stu-id="88d40-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<backupList>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="88d40-110">语法</span><span class="sxs-lookup"><span data-stu-id="88d40-110">Syntax</span></span>  
  
```xml  
<routing>
  <backupLists>
    <backupList name="String">
      <add endpointName="String" />
    </backupList>
  </backupLists>
</routing>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="88d40-111">特性和元素</span><span class="sxs-lookup"><span data-stu-id="88d40-111">Attributes and Elements</span></span>  
 <span data-ttu-id="88d40-112">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="88d40-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="88d40-113">特性</span><span class="sxs-lookup"><span data-stu-id="88d40-113">Attributes</span></span>  
  
|<span data-ttu-id="88d40-114">特性</span><span class="sxs-lookup"><span data-stu-id="88d40-114">Attribute</span></span>|<span data-ttu-id="88d40-115">描述</span><span class="sxs-lookup"><span data-stu-id="88d40-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="88d40-116">NAME</span><span class="sxs-lookup"><span data-stu-id="88d40-116">name</span></span>|<span data-ttu-id="88d40-117">一个字符串，指定用于标识此终结点列表的名称。</span><span class="sxs-lookup"><span data-stu-id="88d40-117">A string that specifies the name used to identify this endpoint list.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="88d40-118">子元素</span><span class="sxs-lookup"><span data-stu-id="88d40-118">Child Elements</span></span>  
  
|<span data-ttu-id="88d40-119">元素</span><span class="sxs-lookup"><span data-stu-id="88d40-119">Element</span></span>|<span data-ttu-id="88d40-120">描述</span><span class="sxs-lookup"><span data-stu-id="88d40-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="88d40-121">\<filter></span><span class="sxs-lookup"><span data-stu-id="88d40-121">\<filter></span></span>](filter.md)||  
  
### <a name="parent-elements"></a><span data-ttu-id="88d40-122">父元素</span><span class="sxs-lookup"><span data-stu-id="88d40-122">Parent Elements</span></span>  
  
|<span data-ttu-id="88d40-123">元素</span><span class="sxs-lookup"><span data-stu-id="88d40-123">Element</span></span>|<span data-ttu-id="88d40-124">描述</span><span class="sxs-lookup"><span data-stu-id="88d40-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="88d40-125">\<routing></span><span class="sxs-lookup"><span data-stu-id="88d40-125">\<routing></span></span>](routing.md)|<span data-ttu-id="88d40-126">备份终结点列表。</span><span class="sxs-lookup"><span data-stu-id="88d40-126">A list of backup endpoints.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="88d40-127">备注</span><span class="sxs-lookup"><span data-stu-id="88d40-127">Remarks</span></span>  
 <span data-ttu-id="88d40-128">此节包含终结点的有序集合，如果在将消息发送到主终结点时发生通信异常，则会将消息传输到此集合。</span><span class="sxs-lookup"><span data-stu-id="88d40-128">This section contains an ordered collection of endpoints that a message will be transmitted to in the event of a communications exception when sending to the primary endpoint.</span></span>  
  
 <span data-ttu-id="88d40-129">如果发送到`endpointName` [ \<add >](add-of-entries.md)的属性中列出的主终结点失败并出现通信异常，则路由服务会尝试将消息发送到此配置节中的第一个终结点。</span><span class="sxs-lookup"><span data-stu-id="88d40-129">If a send to the primary endpoint listed in the `endpointName` attribute of [\<add>](add-of-entries.md) fails with a communications exception, the Routing Service will attempt to send the message to the first endpoint in this configuration section.</span></span> <span data-ttu-id="88d40-130">如果此操作同样发生通信异常而导致发送失败，则路由服务会尝试将消息发送到此节包含的下一消息，直到发送尝试成功、返回除通信异常以外的故障或集合中的所有终结点均返回故障为止。</span><span class="sxs-lookup"><span data-stu-id="88d40-130">If this also fails with a communications exception, the Routing Service will attempt to send the message to the next message contained in this section until the send attempt succeeds, returns a failure other than a communication exception, or all endpoints in the collection have returned a failure.</span></span>  
  
 <span data-ttu-id="88d40-131">在以下示例中，如果发送到名为 "Destination" 的主终结点返回通信异常，则该服务将尝试将消息发送到 "alternateServiceQueue"。</span><span class="sxs-lookup"><span data-stu-id="88d40-131">In the following example, if a send to the primary endpoint named "Destination" returns a communication exception, the service will attempt to send the message to the "alternateServiceQueue".</span></span> <span data-ttu-id="88d40-132">如果此尝试也返回一个通信异常，则路由服务会尝试将消息发送到集合中的下一个终结点。</span><span class="sxs-lookup"><span data-stu-id="88d40-132">If this attempt also returns a communication exception, the Routing Service will attempt to send the message to the next endpoint in the collection.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="88d40-133">请参阅</span><span class="sxs-lookup"><span data-stu-id="88d40-133">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.BackupEndpointCollection?displayProperty=nameWithType>
