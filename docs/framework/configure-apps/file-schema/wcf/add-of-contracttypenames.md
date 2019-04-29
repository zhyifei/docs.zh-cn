---
title: <add> 的 <contractTypeNames>
ms.date: 03/30/2017
ms.assetid: 03aff6be-5dfb-4a64-ada3-e36227cd43c7
ms.openlocfilehash: 856298cb0639cf19b941f326b5b9a25aa6663088
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61701185"
---
# <a name="add-of-contracttypenames"></a><span data-ttu-id="7071b-102">\<add> of \<contractTypeNames></span><span class="sxs-lookup"><span data-stu-id="7071b-102">\<add> of \<contractTypeNames></span></span>
<span data-ttu-id="7071b-103">一个配置元素，指定要搜索的服务的协定名称以及搜索服务时通常使用的条件。</span><span class="sxs-lookup"><span data-stu-id="7071b-103">A configuration element that specifies the contract name of the services being searched for, and the criteria typically used when searching for a service.</span></span> <span data-ttu-id="7071b-104">如果指定多个协定名称，则只有与全部协定都匹配的服务终结点才会进行答复。</span><span class="sxs-lookup"><span data-stu-id="7071b-104">If more than one contract name is specified, only service endpoints matching ALL contracts will reply.</span></span> <span data-ttu-id="7071b-105">请注意，在 Windows Communication Foundation (WCF) 终结点只能支持一个协定。</span><span class="sxs-lookup"><span data-stu-id="7071b-105">Note that in Windows Communication Foundation (WCF), an endpoint can only support one contract.</span></span>  
  
 <span data-ttu-id="7071b-106">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="7071b-106">\<system.ServiceModel></span></span>  
<span data-ttu-id="7071b-107">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="7071b-107">\<standardEndpoints></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7071b-108">语法</span><span class="sxs-lookup"><span data-stu-id="7071b-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7071b-109">特性和元素</span><span class="sxs-lookup"><span data-stu-id="7071b-109">Attributes and Elements</span></span>  
 <span data-ttu-id="7071b-110">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="7071b-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7071b-111">特性</span><span class="sxs-lookup"><span data-stu-id="7071b-111">Attributes</span></span>  
  
|<span data-ttu-id="7071b-112">特性</span><span class="sxs-lookup"><span data-stu-id="7071b-112">Attribute</span></span>|<span data-ttu-id="7071b-113">描述</span><span class="sxs-lookup"><span data-stu-id="7071b-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="7071b-114">name</span><span class="sxs-lookup"><span data-stu-id="7071b-114">name</span></span>|<span data-ttu-id="7071b-115">一个字符串，指定协定类型的名称。</span><span class="sxs-lookup"><span data-stu-id="7071b-115">A string that specifies the name of the contract type.</span></span>|  
|<span data-ttu-id="7071b-116">namespace</span><span class="sxs-lookup"><span data-stu-id="7071b-116">namespace</span></span>|<span data-ttu-id="7071b-117">一个字符串，指定协定类型的命名空间。</span><span class="sxs-lookup"><span data-stu-id="7071b-117">A string that specifies the namespace of the contract type.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="7071b-118">子元素</span><span class="sxs-lookup"><span data-stu-id="7071b-118">Child Elements</span></span>  
 <span data-ttu-id="7071b-119">None</span><span class="sxs-lookup"><span data-stu-id="7071b-119">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="7071b-120">父元素</span><span class="sxs-lookup"><span data-stu-id="7071b-120">Parent Elements</span></span>  
  
|<span data-ttu-id="7071b-121">元素</span><span class="sxs-lookup"><span data-stu-id="7071b-121">Element</span></span>|<span data-ttu-id="7071b-122">描述</span><span class="sxs-lookup"><span data-stu-id="7071b-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7071b-123">\<contractTypeNames></span><span class="sxs-lookup"><span data-stu-id="7071b-123">\<contractTypeNames></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/contracttypenames.md)|<span data-ttu-id="7071b-124">协定类型名称的集合。</span><span class="sxs-lookup"><span data-stu-id="7071b-124">A collection of contract type names.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="7071b-125">请参阅</span><span class="sxs-lookup"><span data-stu-id="7071b-125">See also</span></span>

- <xref:System.ServiceModel.Discovery.FindCriteria>
- <xref:System.ServiceModel.Discovery.Configuration.FindCriteriaElement>
- <xref:System.ServiceModel.Discovery.Configuration.ContractTypeNameElement>
