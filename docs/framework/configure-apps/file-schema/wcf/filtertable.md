---
title: <filterTable>
ms.date: 03/30/2017
ms.assetid: e9f05441-3ad1-49b9-a267-71724aa094b4
ms.openlocfilehash: 918a365004efea82f4ef4c8868f6821d4bb6da18
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855189"
---
# <a name="filtertable"></a><span data-ttu-id="bd5fa-101">\<filterTable></span><span class="sxs-lookup"><span data-stu-id="bd5fa-101">\<filterTable></span></span>
<span data-ttu-id="bd5fa-102">表示一个路由表，该表包含用于评估消息的筛选器的列表，以及在筛选器计算结果为 true 时要将消息路由到的客户端终结点。</span><span class="sxs-lookup"><span data-stu-id="bd5fa-102">Represents a routing table that contains a list of filters to evaluate messages against and the client endpoint to route messages to if the filter evaluates to true.</span></span>  
  
<span data-ttu-id="bd5fa-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="bd5fa-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="bd5fa-104">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="bd5fa-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="bd5fa-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<路由 >** ](routing.md)</span><span class="sxs-lookup"><span data-stu-id="bd5fa-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<routing>**](routing.md)</span></span>\
<span data-ttu-id="bd5fa-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<filterTables >** ](filtertables.md)</span><span class="sxs-lookup"><span data-stu-id="bd5fa-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<filterTables>**](filtertables.md)</span></span>\
<span data-ttu-id="bd5fa-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<filterTable >**</span><span class="sxs-lookup"><span data-stu-id="bd5fa-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<filterTable>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bd5fa-108">语法</span><span class="sxs-lookup"><span data-stu-id="bd5fa-108">Syntax</span></span>  
  
```xml  
<routing>
  <filterTables>
     name="String">
      <entries>
        <add backupList="String"
             endpointName="String"
             filterName="String"
             priority="Integer" />
      </entries>
    </filterTable>
  </filterTables>
</routing>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="bd5fa-109">特性和元素</span><span class="sxs-lookup"><span data-stu-id="bd5fa-109">Attributes and Elements</span></span>  
 <span data-ttu-id="bd5fa-110">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="bd5fa-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="bd5fa-111">特性</span><span class="sxs-lookup"><span data-stu-id="bd5fa-111">Attributes</span></span>  
  
|<span data-ttu-id="bd5fa-112">元素</span><span class="sxs-lookup"><span data-stu-id="bd5fa-112">Element</span></span>|<span data-ttu-id="bd5fa-113">描述</span><span class="sxs-lookup"><span data-stu-id="bd5fa-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="bd5fa-114">NAME</span><span class="sxs-lookup"><span data-stu-id="bd5fa-114">name</span></span>|<span data-ttu-id="bd5fa-115">一个字符串，包含此配置元素的唯一名称。</span><span class="sxs-lookup"><span data-stu-id="bd5fa-115">A string that contains the unique name of this configuration element.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="bd5fa-116">子元素</span><span class="sxs-lookup"><span data-stu-id="bd5fa-116">Child Elements</span></span>  
  
|<span data-ttu-id="bd5fa-117">元素</span><span class="sxs-lookup"><span data-stu-id="bd5fa-117">Element</span></span>|<span data-ttu-id="bd5fa-118">描述</span><span class="sxs-lookup"><span data-stu-id="bd5fa-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="bd5fa-119">\<filters></span><span class="sxs-lookup"><span data-stu-id="bd5fa-119">\<filters></span></span>](filters-of-routing.md)|<span data-ttu-id="bd5fa-120">路由筛选器与在筛选器匹配时消息要发送到的目标终结点之间的映射。</span><span class="sxs-lookup"><span data-stu-id="bd5fa-120">Mappings between the routing filters and the target endpoints to send messages to when the filter matches.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="bd5fa-121">父元素</span><span class="sxs-lookup"><span data-stu-id="bd5fa-121">Parent Elements</span></span>  
  
|<span data-ttu-id="bd5fa-122">元素</span><span class="sxs-lookup"><span data-stu-id="bd5fa-122">Element</span></span>|<span data-ttu-id="bd5fa-123">描述</span><span class="sxs-lookup"><span data-stu-id="bd5fa-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="bd5fa-124">\<routing></span><span class="sxs-lookup"><span data-stu-id="bd5fa-124">\<routing></span></span>](routing.md)|<span data-ttu-id="bd5fa-125">一个包含路由表的配置节。</span><span class="sxs-lookup"><span data-stu-id="bd5fa-125">A configuration section that contains routing tables.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="bd5fa-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="bd5fa-126">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.RoutingSection?displayProperty=nameWithType>
