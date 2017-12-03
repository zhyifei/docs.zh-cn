---
title: "&lt;contractTypeNames&gt; 的 &lt;add&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 03aff6be-5dfb-4a64-ada3-e36227cd43c7
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 2d7cfcb8217bbf157af4ba2893773b180f0a9f28
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="ltaddgt-of-ltcontracttypenamesgt"></a><span data-ttu-id="9d0b8-102">&lt;contractTypeNames&gt; 的 &lt;add&gt;</span><span class="sxs-lookup"><span data-stu-id="9d0b8-102">&lt;add&gt; of &lt;contractTypeNames&gt;</span></span>
<span data-ttu-id="9d0b8-103">一个配置元素，指定要搜索的服务的协定名称以及搜索服务时通常使用的条件。</span><span class="sxs-lookup"><span data-stu-id="9d0b8-103">A configuration element that specifies the contract name of the services being searched for, and the criteria typically used when searching for a service.</span></span> <span data-ttu-id="9d0b8-104">如果指定多个协定名称，则只有与全部协定都匹配的服务终结点才会进行答复。</span><span class="sxs-lookup"><span data-stu-id="9d0b8-104">If more than one contract name is specified, only service endpoints matching ALL contracts will reply.</span></span> <span data-ttu-id="9d0b8-105">请注意，在 [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] 中，一个终结点只能支持一个协定。</span><span class="sxs-lookup"><span data-stu-id="9d0b8-105">Note that in [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)], an endpoint can only support one contract.</span></span>  
  
 <span data-ttu-id="9d0b8-106">\<系统。ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="9d0b8-106">\<system.ServiceModel></span></span>  
<span data-ttu-id="9d0b8-107">\<standardEndpoints ></span><span class="sxs-lookup"><span data-stu-id="9d0b8-107">\<standardEndpoints></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9d0b8-108">语法</span><span class="sxs-lookup"><span data-stu-id="9d0b8-108">Syntax</span></span>  
  
```xml  
<system.serviceModel>  
    <standardEndpoints>       <dynamicEndpoint>           <standardEndpoint>             <discoveryClientSettings discoveryEndpoint="String" >               <findCriteria duration="TimeSpan"                  maxResults="Integer"                   scopeMatchBy="Uri" >                  <contractTypeNames>                     <add name="String" namespace="String" />                  <contractTypeNames>                  <extensions />                  <scopes>                    <add scope="URI"/>                  </scopes>               </findCriteria>             </discoveryClientSettings>          <standardEndpoint>       </dynamicEndpoint>            </standardEndpoints>  
</system.serviceModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9d0b8-109">特性和元素</span><span class="sxs-lookup"><span data-stu-id="9d0b8-109">Attributes and Elements</span></span>  
 <span data-ttu-id="9d0b8-110">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="9d0b8-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9d0b8-111">特性</span><span class="sxs-lookup"><span data-stu-id="9d0b8-111">Attributes</span></span>  
  
|<span data-ttu-id="9d0b8-112">特性</span><span class="sxs-lookup"><span data-stu-id="9d0b8-112">Attribute</span></span>|<span data-ttu-id="9d0b8-113">描述</span><span class="sxs-lookup"><span data-stu-id="9d0b8-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="9d0b8-114">name</span><span class="sxs-lookup"><span data-stu-id="9d0b8-114">name</span></span>|<span data-ttu-id="9d0b8-115">一个字符串，指定协定类型的名称。</span><span class="sxs-lookup"><span data-stu-id="9d0b8-115">A string that specifies the name of the contract type.</span></span>|  
|<span data-ttu-id="9d0b8-116">namespace</span><span class="sxs-lookup"><span data-stu-id="9d0b8-116">namespace</span></span>|<span data-ttu-id="9d0b8-117">一个字符串，指定协定类型的命名空间。</span><span class="sxs-lookup"><span data-stu-id="9d0b8-117">A string that specifies the namespace of the contract type.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9d0b8-118">子元素</span><span class="sxs-lookup"><span data-stu-id="9d0b8-118">Child Elements</span></span>  
 <span data-ttu-id="9d0b8-119">无</span><span class="sxs-lookup"><span data-stu-id="9d0b8-119">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="9d0b8-120">父元素</span><span class="sxs-lookup"><span data-stu-id="9d0b8-120">Parent Elements</span></span>  
  
|<span data-ttu-id="9d0b8-121">元素</span><span class="sxs-lookup"><span data-stu-id="9d0b8-121">Element</span></span>|<span data-ttu-id="9d0b8-122">描述</span><span class="sxs-lookup"><span data-stu-id="9d0b8-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9d0b8-123">\<contractTypeNames ></span><span class="sxs-lookup"><span data-stu-id="9d0b8-123">\<contractTypeNames></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/contracttypenames.md)|<span data-ttu-id="9d0b8-124">协定类型名称的集合。</span><span class="sxs-lookup"><span data-stu-id="9d0b8-124">A collection of contract type names.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="9d0b8-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9d0b8-125">See Also</span></span>  
 <xref:System.ServiceModel.Discovery.FindCriteria>  
 <xref:System.ServiceModel.Discovery.Configuration.FindCriteriaElement>  
 <xref:System.ServiceModel.Discovery.Configuration.ContractTypeNameElement>
