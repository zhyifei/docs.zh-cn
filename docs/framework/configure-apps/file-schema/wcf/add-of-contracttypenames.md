---
title: <add> 的 <contractTypeNames>
ms.date: 03/30/2017
ms.assetid: 03aff6be-5dfb-4a64-ada3-e36227cd43c7
ms.openlocfilehash: 696752470aa39c2bcc66a1337f84119031742ae9
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2019
ms.locfileid: "70850531"
---
# <a name="add-of-contracttypenames"></a><span data-ttu-id="581e1-102">\<添加 contractTypeNames > \<的 ></span><span class="sxs-lookup"><span data-stu-id="581e1-102">\<add> of \<contractTypeNames></span></span>
<span data-ttu-id="581e1-103">一个配置元素，指定要搜索的服务的协定名称以及搜索服务时通常使用的条件。</span><span class="sxs-lookup"><span data-stu-id="581e1-103">A configuration element that specifies the contract name of the services being searched for, and the criteria typically used when searching for a service.</span></span> <span data-ttu-id="581e1-104">如果指定多个协定名称，则只有与全部协定都匹配的服务终结点才会进行答复。</span><span class="sxs-lookup"><span data-stu-id="581e1-104">If more than one contract name is specified, only service endpoints matching ALL contracts will reply.</span></span> <span data-ttu-id="581e1-105">请注意，在 Windows Communication Foundation （WCF）中，一个终结点只能支持一个协定。</span><span class="sxs-lookup"><span data-stu-id="581e1-105">Note that in Windows Communication Foundation (WCF), an endpoint can only support one contract.</span></span>  
  
<span data-ttu-id="581e1-106">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="581e1-106">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="581e1-107">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="581e1-107">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="581e1-108">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<standardEndpoints >** ](standardendpoints.md)</span><span class="sxs-lookup"><span data-stu-id="581e1-108">&nbsp;&nbsp;&nbsp;&nbsp;[**\<standardEndpoints>**](standardendpoints.md)</span></span>\
<span data-ttu-id="581e1-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<dynamicEndpoint >** ](dynamicendpoint.md)</span><span class="sxs-lookup"><span data-stu-id="581e1-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<dynamicEndpoint>**](dynamicendpoint.md)</span></span>\
<span data-ttu-id="581e1-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<standardEndpoint >** </span><span class="sxs-lookup"><span data-stu-id="581e1-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<standardEndpoint>**</span></span>\
<span data-ttu-id="581e1-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<discoveryClientSettings >** ](discoveryclientsettings.md)</span><span class="sxs-lookup"><span data-stu-id="581e1-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<discoveryClientSettings>**](discoveryclientsettings.md)</span></span>\
<span data-ttu-id="581e1-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<s >** ](findcriteria.md)</span><span class="sxs-lookup"><span data-stu-id="581e1-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<findCriteria>**](findcriteria.md)</span></span>\
<span data-ttu-id="581e1-113">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<contractTypeNames >** ](contracttypenames.md)</span><span class="sxs-lookup"><span data-stu-id="581e1-113">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<contractTypeNames>**](contracttypenames.md)</span></span>\
<span data-ttu-id="581e1-114">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<添加 >**</span><span class="sxs-lookup"><span data-stu-id="581e1-114">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="581e1-115">语法</span><span class="sxs-lookup"><span data-stu-id="581e1-115">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="581e1-116">特性和元素</span><span class="sxs-lookup"><span data-stu-id="581e1-116">Attributes and Elements</span></span>  
 <span data-ttu-id="581e1-117">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="581e1-117">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="581e1-118">特性</span><span class="sxs-lookup"><span data-stu-id="581e1-118">Attributes</span></span>  
  
|<span data-ttu-id="581e1-119">特性</span><span class="sxs-lookup"><span data-stu-id="581e1-119">Attribute</span></span>|<span data-ttu-id="581e1-120">描述</span><span class="sxs-lookup"><span data-stu-id="581e1-120">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="581e1-121">NAME</span><span class="sxs-lookup"><span data-stu-id="581e1-121">name</span></span>|<span data-ttu-id="581e1-122">一个字符串，指定协定类型的名称。</span><span class="sxs-lookup"><span data-stu-id="581e1-122">A string that specifies the name of the contract type.</span></span>|  
|<span data-ttu-id="581e1-123">namespace</span><span class="sxs-lookup"><span data-stu-id="581e1-123">namespace</span></span>|<span data-ttu-id="581e1-124">一个字符串，指定协定类型的命名空间。</span><span class="sxs-lookup"><span data-stu-id="581e1-124">A string that specifies the namespace of the contract type.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="581e1-125">子元素</span><span class="sxs-lookup"><span data-stu-id="581e1-125">Child Elements</span></span>  
 <span data-ttu-id="581e1-126">无</span><span class="sxs-lookup"><span data-stu-id="581e1-126">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="581e1-127">父元素</span><span class="sxs-lookup"><span data-stu-id="581e1-127">Parent Elements</span></span>  
  
|<span data-ttu-id="581e1-128">元素</span><span class="sxs-lookup"><span data-stu-id="581e1-128">Element</span></span>|<span data-ttu-id="581e1-129">描述</span><span class="sxs-lookup"><span data-stu-id="581e1-129">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="581e1-130">\<contractTypeNames></span><span class="sxs-lookup"><span data-stu-id="581e1-130">\<contractTypeNames></span></span>](contracttypenames.md)|<span data-ttu-id="581e1-131">协定类型名称的集合。</span><span class="sxs-lookup"><span data-stu-id="581e1-131">A collection of contract type names.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="581e1-132">请参阅</span><span class="sxs-lookup"><span data-stu-id="581e1-132">See also</span></span>

- <xref:System.ServiceModel.Discovery.FindCriteria>
- <xref:System.ServiceModel.Discovery.Configuration.FindCriteriaElement>
- <xref:System.ServiceModel.Discovery.Configuration.ContractTypeNameElement>
