---
title: <contractTypeNames>
ms.date: 03/30/2017
ms.assetid: 5ec5efc6-87f8-4160-9be0-dcd2e01df3df
ms.openlocfilehash: b1cec9272a1de029ab72ea4d5f36c74630e5b93a
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59089492"
---
# <a name="contracttypenames"></a><span data-ttu-id="18e9f-101">\<contractTypeNames></span><span class="sxs-lookup"><span data-stu-id="18e9f-101">\<contractTypeNames></span></span>
<span data-ttu-id="18e9f-102">一个指定协定类型名称列表的配置节，这些名称是所搜索服务的协定名称以及搜索服务时通常采用的条件。</span><span class="sxs-lookup"><span data-stu-id="18e9f-102">A configuration section that specifies a list of contract type names, which are the contract names of the services being searched for, and the criteria typically used when searching for a service.</span></span> <span data-ttu-id="18e9f-103">如果指定多个协定名称，则只有与全部协定都匹配的服务终结点才会进行答复。</span><span class="sxs-lookup"><span data-stu-id="18e9f-103">If more than one contract name is specified, only service endpoints matching ALL contracts will reply.</span></span> <span data-ttu-id="18e9f-104">请注意，在 Windows Communication Foundation (WCF) 终结点只能支持一个协定。</span><span class="sxs-lookup"><span data-stu-id="18e9f-104">Note that in Windows Communication Foundation (WCF), an endpoint can only support one contract.</span></span>  
  
 <span data-ttu-id="18e9f-105">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="18e9f-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="18e9f-106">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="18e9f-106">\<standardEndpoints></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="18e9f-107">语法</span><span class="sxs-lookup"><span data-stu-id="18e9f-107">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="18e9f-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="18e9f-108">Attributes and Elements</span></span>  
 <span data-ttu-id="18e9f-109">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="18e9f-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="18e9f-110">特性</span><span class="sxs-lookup"><span data-stu-id="18e9f-110">Attributes</span></span>  
 <span data-ttu-id="18e9f-111">无。</span><span class="sxs-lookup"><span data-stu-id="18e9f-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="18e9f-112">子元素</span><span class="sxs-lookup"><span data-stu-id="18e9f-112">Child Elements</span></span>  
  
|<span data-ttu-id="18e9f-113">元素</span><span class="sxs-lookup"><span data-stu-id="18e9f-113">Element</span></span>|<span data-ttu-id="18e9f-114">描述</span><span class="sxs-lookup"><span data-stu-id="18e9f-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="18e9f-115">\<add></span><span class="sxs-lookup"><span data-stu-id="18e9f-115">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/contracttypenames.md)|<span data-ttu-id="18e9f-116">协定类型名称是一个属性，它引用搜索服务时通常采用的条件集。</span><span class="sxs-lookup"><span data-stu-id="18e9f-116">A contract type name is a property that refers to the set of criteria typically used when searching for a service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="18e9f-117">父元素</span><span class="sxs-lookup"><span data-stu-id="18e9f-117">Parent Elements</span></span>  
  
|<span data-ttu-id="18e9f-118">元素</span><span class="sxs-lookup"><span data-stu-id="18e9f-118">Element</span></span>|<span data-ttu-id="18e9f-119">描述</span><span class="sxs-lookup"><span data-stu-id="18e9f-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="18e9f-120">\<findCriteria></span><span class="sxs-lookup"><span data-stu-id="18e9f-120">\<findCriteria></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/findcriteria.md)|<span data-ttu-id="18e9f-121">一个配置元素，提供客户端应用程序用于搜索发现服务的一组条件。</span><span class="sxs-lookup"><span data-stu-id="18e9f-121">A configuration element that supplies a set of criteria used by a client application to search for a discovery service.</span></span> <span data-ttu-id="18e9f-122">条件可以划分为搜索条件 （指定要查找的服务） 和查找终止条件 （搜索应持续多久）。</span><span class="sxs-lookup"><span data-stu-id="18e9f-122">Criteria can be grouped into search criteria (specifying what services you’re looking for) and find termination criteria (how long the search should last).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="18e9f-123">请参阅</span><span class="sxs-lookup"><span data-stu-id="18e9f-123">See also</span></span>

- <xref:System.ServiceModel.Discovery.FindCriteria>
- <xref:System.ServiceModel.Discovery.Configuration.FindCriteriaElement>
- <xref:System.ServiceModel.Discovery.Configuration.ContractTypeNameElementCollection>
