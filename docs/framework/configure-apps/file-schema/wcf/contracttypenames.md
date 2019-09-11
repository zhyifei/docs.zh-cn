---
title: <contractTypeNames>
ms.date: 03/30/2017
ms.assetid: 5ec5efc6-87f8-4160-9be0-dcd2e01df3df
ms.openlocfilehash: c67e5b9e82b96e27ce73512680bd4236b26ef4dd
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855449"
---
# <a name="contracttypenames"></a><span data-ttu-id="a0f14-101">\<contractTypeNames></span><span class="sxs-lookup"><span data-stu-id="a0f14-101">\<contractTypeNames></span></span>
<span data-ttu-id="a0f14-102">一个指定协定类型名称列表的配置节，这些名称是所搜索服务的协定名称以及搜索服务时通常采用的条件。</span><span class="sxs-lookup"><span data-stu-id="a0f14-102">A configuration section that specifies a list of contract type names, which are the contract names of the services being searched for, and the criteria typically used when searching for a service.</span></span> <span data-ttu-id="a0f14-103">如果指定多个协定名称，则只有与全部协定都匹配的服务终结点才会进行答复。</span><span class="sxs-lookup"><span data-stu-id="a0f14-103">If more than one contract name is specified, only service endpoints matching ALL contracts will reply.</span></span> <span data-ttu-id="a0f14-104">请注意，在 Windows Communication Foundation （WCF）中，一个终结点只能支持一个协定。</span><span class="sxs-lookup"><span data-stu-id="a0f14-104">Note that in Windows Communication Foundation (WCF), an endpoint can only support one contract.</span></span>  
  
<span data-ttu-id="a0f14-105">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="a0f14-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="a0f14-106">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="a0f14-106">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="a0f14-107">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<standardEndpoints >** ](standardendpoints.md)</span><span class="sxs-lookup"><span data-stu-id="a0f14-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<standardEndpoints>**](standardendpoints.md)</span></span>\
<span data-ttu-id="a0f14-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<dynamicEndpoint >** ](dynamicendpoint.md)</span><span class="sxs-lookup"><span data-stu-id="a0f14-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<dynamicEndpoint>**](dynamicendpoint.md)</span></span>\
<span data-ttu-id="a0f14-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<standardEndpoint >** </span><span class="sxs-lookup"><span data-stu-id="a0f14-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<standardEndpoint>**</span></span>\
<span data-ttu-id="a0f14-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<discoveryClientSettings >** ](discoveryclientsettings.md)</span><span class="sxs-lookup"><span data-stu-id="a0f14-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<discoveryClientSettings>**](discoveryclientsettings.md)</span></span>\
<span data-ttu-id="a0f14-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<s >** ](findcriteria.md)</span><span class="sxs-lookup"><span data-stu-id="a0f14-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<findCriteria>**](findcriteria.md)</span></span>\
<span data-ttu-id="a0f14-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<contractTypeNames >**</span><span class="sxs-lookup"><span data-stu-id="a0f14-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<contractTypeNames>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a0f14-113">语法</span><span class="sxs-lookup"><span data-stu-id="a0f14-113">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <standardEndpoints>
    <dynamicEndpoint>
      <standardEndpoint>
        <discoveryClientSettings discoveryEndpoint="String">
          <findCriteria duration="TimeSpan"
                        maxResults="Integer"
                        scopeMatchBy="Uri">
            <contractTypeNames>
              <add name="String"
                   namespace="String" />
            <contractTypeNames>
            <extensions />
            <scopes>
              <add scope="URI"/>
            </scopes>
          </findCriteria>
        </discoveryClientSettings>
      <standardEndpoint>
    </dynamicEndpoint>
  </standardEndpoints>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a0f14-114">特性和元素</span><span class="sxs-lookup"><span data-stu-id="a0f14-114">Attributes and Elements</span></span>  
 <span data-ttu-id="a0f14-115">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="a0f14-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a0f14-116">特性</span><span class="sxs-lookup"><span data-stu-id="a0f14-116">Attributes</span></span>  
 <span data-ttu-id="a0f14-117">无。</span><span class="sxs-lookup"><span data-stu-id="a0f14-117">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="a0f14-118">子元素</span><span class="sxs-lookup"><span data-stu-id="a0f14-118">Child Elements</span></span>  
  
|<span data-ttu-id="a0f14-119">元素</span><span class="sxs-lookup"><span data-stu-id="a0f14-119">Element</span></span>|<span data-ttu-id="a0f14-120">描述</span><span class="sxs-lookup"><span data-stu-id="a0f14-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a0f14-121">\<add></span><span class="sxs-lookup"><span data-stu-id="a0f14-121">\<add></span></span>](contracttypenames.md)|<span data-ttu-id="a0f14-122">协定类型名称是一个属性，它引用搜索服务时通常采用的条件集。</span><span class="sxs-lookup"><span data-stu-id="a0f14-122">A contract type name is a property that refers to the set of criteria typically used when searching for a service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="a0f14-123">父元素</span><span class="sxs-lookup"><span data-stu-id="a0f14-123">Parent Elements</span></span>  
  
|<span data-ttu-id="a0f14-124">元素</span><span class="sxs-lookup"><span data-stu-id="a0f14-124">Element</span></span>|<span data-ttu-id="a0f14-125">描述</span><span class="sxs-lookup"><span data-stu-id="a0f14-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a0f14-126">\<findCriteria></span><span class="sxs-lookup"><span data-stu-id="a0f14-126">\<findCriteria></span></span>](findcriteria.md)|<span data-ttu-id="a0f14-127">一个配置元素，提供客户端应用程序用于搜索发现服务的一组条件。</span><span class="sxs-lookup"><span data-stu-id="a0f14-127">A configuration element that supplies a set of criteria used by a client application to search for a discovery service.</span></span> <span data-ttu-id="a0f14-128">可以将条件分组为搜索条件（指定要查找的服务）和查找终止条件（搜索应持续的时间长度）。</span><span class="sxs-lookup"><span data-stu-id="a0f14-128">Criteria can be grouped into search criteria (specifying what services you’re looking for) and find termination criteria (how long the search should last).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a0f14-129">请参阅</span><span class="sxs-lookup"><span data-stu-id="a0f14-129">See also</span></span>

- <xref:System.ServiceModel.Discovery.FindCriteria>
- <xref:System.ServiceModel.Discovery.Configuration.FindCriteriaElement>
- <xref:System.ServiceModel.Discovery.Configuration.ContractTypeNameElementCollection>
