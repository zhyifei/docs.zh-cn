---
title: '&lt;contractTypeNames&gt;'
ms.date: 03/30/2017
ms.assetid: 5ec5efc6-87f8-4160-9be0-dcd2e01df3df
ms.openlocfilehash: 99547967b65e5d7663ec11be98247e2018aaa34c
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
---
# <a name="ltcontracttypenamesgt"></a><span data-ttu-id="26710-102">&lt;contractTypeNames&gt;</span><span class="sxs-lookup"><span data-stu-id="26710-102">&lt;contractTypeNames&gt;</span></span>
<span data-ttu-id="26710-103">一个指定协定类型名称列表的配置节，这些名称是所搜索服务的协定名称以及搜索服务时通常采用的条件。</span><span class="sxs-lookup"><span data-stu-id="26710-103">A configuration section that specifies a list of contract type names, which are the contract names of the services being searched for, and the criteria typically used when searching for a service.</span></span> <span data-ttu-id="26710-104">如果指定多个协定名称，则只有与全部协定都匹配的服务终结点才会进行答复。</span><span class="sxs-lookup"><span data-stu-id="26710-104">If more than one contract name is specified, only service endpoints matching ALL contracts will reply.</span></span> <span data-ttu-id="26710-105">请注意，在 Windows Communication Foundation (WCF) 中，终结点只能支持一个协定。</span><span class="sxs-lookup"><span data-stu-id="26710-105">Note that in Windows Communication Foundation (WCF), an endpoint can only support one contract.</span></span>  
  
 <span data-ttu-id="26710-106">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="26710-106">\<system.ServiceModel></span></span>  
<span data-ttu-id="26710-107">\<standardEndpoints ></span><span class="sxs-lookup"><span data-stu-id="26710-107">\<standardEndpoints></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="26710-108">语法</span><span class="sxs-lookup"><span data-stu-id="26710-108">Syntax</span></span>  
  
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
              <add name="String" namespace="String" />
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="26710-109">特性和元素</span><span class="sxs-lookup"><span data-stu-id="26710-109">Attributes and Elements</span></span>  
 <span data-ttu-id="26710-110">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="26710-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="26710-111">特性</span><span class="sxs-lookup"><span data-stu-id="26710-111">Attributes</span></span>  
 <span data-ttu-id="26710-112">无。</span><span class="sxs-lookup"><span data-stu-id="26710-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="26710-113">子元素</span><span class="sxs-lookup"><span data-stu-id="26710-113">Child Elements</span></span>  
  
|<span data-ttu-id="26710-114">元素</span><span class="sxs-lookup"><span data-stu-id="26710-114">Element</span></span>|<span data-ttu-id="26710-115">描述</span><span class="sxs-lookup"><span data-stu-id="26710-115">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="26710-116">\<add></span><span class="sxs-lookup"><span data-stu-id="26710-116">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/contracttypenames.md)|<span data-ttu-id="26710-117">协定类型名称是一个属性，它引用搜索服务时通常采用的条件集。</span><span class="sxs-lookup"><span data-stu-id="26710-117">A contract type name is a property that refers to the set of criteria typically used when searching for a service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="26710-118">父元素</span><span class="sxs-lookup"><span data-stu-id="26710-118">Parent Elements</span></span>  
  
|<span data-ttu-id="26710-119">元素</span><span class="sxs-lookup"><span data-stu-id="26710-119">Element</span></span>|<span data-ttu-id="26710-120">描述</span><span class="sxs-lookup"><span data-stu-id="26710-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="26710-121">\<findCriteria ></span><span class="sxs-lookup"><span data-stu-id="26710-121">\<findCriteria></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/findcriteria.md)|<span data-ttu-id="26710-122">一个配置元素，提供客户端应用程序用于搜索发现服务的一组条件。</span><span class="sxs-lookup"><span data-stu-id="26710-122">A configuration element that supplies a set of criteria used by a client application to search for a discovery service.</span></span> <span data-ttu-id="26710-123">条件可以划分为搜索条件 （指定要查找的服务） 和查找终止条件 （搜索应持续的时长）。</span><span class="sxs-lookup"><span data-stu-id="26710-123">Criteria can be grouped into search criteria (specifying what services you’re looking for) and find termination criteria (how long the search should last).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="26710-124">请参阅</span><span class="sxs-lookup"><span data-stu-id="26710-124">See Also</span></span>  
 <xref:System.ServiceModel.Discovery.FindCriteria>  
 <xref:System.ServiceModel.Discovery.Configuration.FindCriteriaElement>  
 <xref:System.ServiceModel.Discovery.Configuration.ContractTypeNameElementCollection>
