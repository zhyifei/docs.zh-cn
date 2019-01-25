---
title: '&lt;contractTypeNames&gt;'
ms.date: 03/30/2017
ms.assetid: 5ec5efc6-87f8-4160-9be0-dcd2e01df3df
ms.openlocfilehash: 2c3f501f44d9e3c601e654041eb9d5a7de8a0a07
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54626766"
---
# <a name="ltcontracttypenamesgt"></a><span data-ttu-id="06e15-102">&lt;contractTypeNames&gt;</span><span class="sxs-lookup"><span data-stu-id="06e15-102">&lt;contractTypeNames&gt;</span></span>
<span data-ttu-id="06e15-103">一个指定协定类型名称列表的配置节，这些名称是所搜索服务的协定名称以及搜索服务时通常采用的条件。</span><span class="sxs-lookup"><span data-stu-id="06e15-103">A configuration section that specifies a list of contract type names, which are the contract names of the services being searched for, and the criteria typically used when searching for a service.</span></span> <span data-ttu-id="06e15-104">如果指定多个协定名称，则只有与全部协定都匹配的服务终结点才会进行答复。</span><span class="sxs-lookup"><span data-stu-id="06e15-104">If more than one contract name is specified, only service endpoints matching ALL contracts will reply.</span></span> <span data-ttu-id="06e15-105">请注意，在 Windows Communication Foundation (WCF) 终结点只能支持一个协定。</span><span class="sxs-lookup"><span data-stu-id="06e15-105">Note that in Windows Communication Foundation (WCF), an endpoint can only support one contract.</span></span>  
  
 <span data-ttu-id="06e15-106">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="06e15-106">\<system.ServiceModel></span></span>  
<span data-ttu-id="06e15-107">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="06e15-107">\<standardEndpoints></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="06e15-108">语法</span><span class="sxs-lookup"><span data-stu-id="06e15-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="06e15-109">特性和元素</span><span class="sxs-lookup"><span data-stu-id="06e15-109">Attributes and Elements</span></span>  
 <span data-ttu-id="06e15-110">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="06e15-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="06e15-111">特性</span><span class="sxs-lookup"><span data-stu-id="06e15-111">Attributes</span></span>  
 <span data-ttu-id="06e15-112">无。</span><span class="sxs-lookup"><span data-stu-id="06e15-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="06e15-113">子元素</span><span class="sxs-lookup"><span data-stu-id="06e15-113">Child Elements</span></span>  
  
|<span data-ttu-id="06e15-114">元素</span><span class="sxs-lookup"><span data-stu-id="06e15-114">Element</span></span>|<span data-ttu-id="06e15-115">描述</span><span class="sxs-lookup"><span data-stu-id="06e15-115">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="06e15-116">\<add></span><span class="sxs-lookup"><span data-stu-id="06e15-116">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/contracttypenames.md)|<span data-ttu-id="06e15-117">协定类型名称是一个属性，它引用搜索服务时通常采用的条件集。</span><span class="sxs-lookup"><span data-stu-id="06e15-117">A contract type name is a property that refers to the set of criteria typically used when searching for a service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="06e15-118">父元素</span><span class="sxs-lookup"><span data-stu-id="06e15-118">Parent Elements</span></span>  
  
|<span data-ttu-id="06e15-119">元素</span><span class="sxs-lookup"><span data-stu-id="06e15-119">Element</span></span>|<span data-ttu-id="06e15-120">描述</span><span class="sxs-lookup"><span data-stu-id="06e15-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="06e15-121">\<findCriteria></span><span class="sxs-lookup"><span data-stu-id="06e15-121">\<findCriteria></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/findcriteria.md)|<span data-ttu-id="06e15-122">一个配置元素，提供客户端应用程序用于搜索发现服务的一组条件。</span><span class="sxs-lookup"><span data-stu-id="06e15-122">A configuration element that supplies a set of criteria used by a client application to search for a discovery service.</span></span> <span data-ttu-id="06e15-123">条件可以划分为搜索条件 （指定要查找的服务） 和查找终止条件 （搜索应持续多久）。</span><span class="sxs-lookup"><span data-stu-id="06e15-123">Criteria can be grouped into search criteria (specifying what services you’re looking for) and find termination criteria (how long the search should last).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="06e15-124">请参阅</span><span class="sxs-lookup"><span data-stu-id="06e15-124">See also</span></span>
- <xref:System.ServiceModel.Discovery.FindCriteria>
- <xref:System.ServiceModel.Discovery.Configuration.FindCriteriaElement>
- <xref:System.ServiceModel.Discovery.Configuration.ContractTypeNameElementCollection>
