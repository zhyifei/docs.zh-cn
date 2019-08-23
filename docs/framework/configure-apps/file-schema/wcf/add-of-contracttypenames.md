---
title: <add> 的 <contractTypeNames>
ms.date: 03/30/2017
ms.assetid: 03aff6be-5dfb-4a64-ada3-e36227cd43c7
ms.openlocfilehash: 24f1478b99aef909ae93f87a70be257e9ba10d7a
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69926739"
---
# <a name="add-of-contracttypenames"></a><span data-ttu-id="3ab03-102">\<添加 contractTypeNames > \<的 ></span><span class="sxs-lookup"><span data-stu-id="3ab03-102">\<add> of \<contractTypeNames></span></span>
<span data-ttu-id="3ab03-103">一个配置元素，指定要搜索的服务的协定名称以及搜索服务时通常使用的条件。</span><span class="sxs-lookup"><span data-stu-id="3ab03-103">A configuration element that specifies the contract name of the services being searched for, and the criteria typically used when searching for a service.</span></span> <span data-ttu-id="3ab03-104">如果指定多个协定名称，则只有与全部协定都匹配的服务终结点才会进行答复。</span><span class="sxs-lookup"><span data-stu-id="3ab03-104">If more than one contract name is specified, only service endpoints matching ALL contracts will reply.</span></span> <span data-ttu-id="3ab03-105">请注意, 在 Windows Communication Foundation (WCF) 中, 一个终结点只能支持一个协定。</span><span class="sxs-lookup"><span data-stu-id="3ab03-105">Note that in Windows Communication Foundation (WCF), an endpoint can only support one contract.</span></span>  
  
 <span data-ttu-id="3ab03-106">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="3ab03-106">\<system.ServiceModel></span></span>  
<span data-ttu-id="3ab03-107">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="3ab03-107">\<standardEndpoints></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3ab03-108">语法</span><span class="sxs-lookup"><span data-stu-id="3ab03-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3ab03-109">特性和元素</span><span class="sxs-lookup"><span data-stu-id="3ab03-109">Attributes and Elements</span></span>  
 <span data-ttu-id="3ab03-110">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="3ab03-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3ab03-111">特性</span><span class="sxs-lookup"><span data-stu-id="3ab03-111">Attributes</span></span>  
  
|<span data-ttu-id="3ab03-112">特性</span><span class="sxs-lookup"><span data-stu-id="3ab03-112">Attribute</span></span>|<span data-ttu-id="3ab03-113">描述</span><span class="sxs-lookup"><span data-stu-id="3ab03-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="3ab03-114">NAME</span><span class="sxs-lookup"><span data-stu-id="3ab03-114">name</span></span>|<span data-ttu-id="3ab03-115">一个字符串，指定协定类型的名称。</span><span class="sxs-lookup"><span data-stu-id="3ab03-115">A string that specifies the name of the contract type.</span></span>|  
|<span data-ttu-id="3ab03-116">namespace</span><span class="sxs-lookup"><span data-stu-id="3ab03-116">namespace</span></span>|<span data-ttu-id="3ab03-117">一个字符串，指定协定类型的命名空间。</span><span class="sxs-lookup"><span data-stu-id="3ab03-117">A string that specifies the namespace of the contract type.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3ab03-118">子元素</span><span class="sxs-lookup"><span data-stu-id="3ab03-118">Child Elements</span></span>  
 <span data-ttu-id="3ab03-119">无</span><span class="sxs-lookup"><span data-stu-id="3ab03-119">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="3ab03-120">父元素</span><span class="sxs-lookup"><span data-stu-id="3ab03-120">Parent Elements</span></span>  
  
|<span data-ttu-id="3ab03-121">元素</span><span class="sxs-lookup"><span data-stu-id="3ab03-121">Element</span></span>|<span data-ttu-id="3ab03-122">描述</span><span class="sxs-lookup"><span data-stu-id="3ab03-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3ab03-123">\<contractTypeNames></span><span class="sxs-lookup"><span data-stu-id="3ab03-123">\<contractTypeNames></span></span>](contracttypenames.md)|<span data-ttu-id="3ab03-124">协定类型名称的集合。</span><span class="sxs-lookup"><span data-stu-id="3ab03-124">A collection of contract type names.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="3ab03-125">请参阅</span><span class="sxs-lookup"><span data-stu-id="3ab03-125">See also</span></span>

- <xref:System.ServiceModel.Discovery.FindCriteria>
- <xref:System.ServiceModel.Discovery.Configuration.FindCriteriaElement>
- <xref:System.ServiceModel.Discovery.Configuration.ContractTypeNameElement>
