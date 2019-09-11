---
title: <entries>
ms.date: 03/30/2017
ms.assetid: 202e430c-c1b9-4343-abe2-ac78c181a3b7
ms.openlocfilehash: ffe2538fa2c3cb680285cfaa68c975c0f9d4b1bd
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855280"
---
# <a name="entries"></a><span data-ttu-id="7116f-101">\<条目 ></span><span class="sxs-lookup"><span data-stu-id="7116f-101">\<entries></span></span>
<span data-ttu-id="7116f-102">一个路由项，包含路由筛选器与在筛选器匹配时消息要发送到的目标终结点之间的映射。</span><span class="sxs-lookup"><span data-stu-id="7116f-102">A routing entry that contain mappings between the routing filters and the target endpoints to send messages to when the filter matches.</span></span>  
  
<span data-ttu-id="7116f-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="7116f-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="7116f-104">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="7116f-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="7116f-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<路由 >** ](routing.md)</span><span class="sxs-lookup"><span data-stu-id="7116f-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<routing>**](routing.md)</span></span>\
<span data-ttu-id="7116f-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<filterTables >** ](filtertables.md)</span><span class="sxs-lookup"><span data-stu-id="7116f-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<filterTables>**](filtertables.md)</span></span>\
<span data-ttu-id="7116f-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<filterTable >** ](filtertable.md)</span><span class="sxs-lookup"><span data-stu-id="7116f-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<filterTable>**](filtertable.md)</span></span>\
<span data-ttu-id="7116f-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<条目 >**</span><span class="sxs-lookup"><span data-stu-id="7116f-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<entries>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7116f-109">语法</span><span class="sxs-lookup"><span data-stu-id="7116f-109">Syntax</span></span>  
  
```xml  
<routing>
  <filterTables>
    <filterTable name="String">
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7116f-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="7116f-110">Attributes and Elements</span></span>  
 <span data-ttu-id="7116f-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="7116f-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7116f-112">特性</span><span class="sxs-lookup"><span data-stu-id="7116f-112">Attributes</span></span>  
 <span data-ttu-id="7116f-113">无。</span><span class="sxs-lookup"><span data-stu-id="7116f-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="7116f-114">子元素</span><span class="sxs-lookup"><span data-stu-id="7116f-114">Child Elements</span></span>  
  
|<span data-ttu-id="7116f-115">元素</span><span class="sxs-lookup"><span data-stu-id="7116f-115">Element</span></span>|<span data-ttu-id="7116f-116">描述</span><span class="sxs-lookup"><span data-stu-id="7116f-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7116f-117">\<filters></span><span class="sxs-lookup"><span data-stu-id="7116f-117">\<filters></span></span>](filters-of-routing.md)|<span data-ttu-id="7116f-118">将筛选器映射到以前定义的客户端终结点。</span><span class="sxs-lookup"><span data-stu-id="7116f-118">Maps a filter to a client endpoint that was previously defined.</span></span> <span data-ttu-id="7116f-119">与此筛选器匹配的消息将发送到此目标。</span><span class="sxs-lookup"><span data-stu-id="7116f-119">Messages matching this filter will be sent to this destination.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="7116f-120">父元素</span><span class="sxs-lookup"><span data-stu-id="7116f-120">Parent Elements</span></span>  
  
|<span data-ttu-id="7116f-121">元素</span><span class="sxs-lookup"><span data-stu-id="7116f-121">Element</span></span>|<span data-ttu-id="7116f-122">描述</span><span class="sxs-lookup"><span data-stu-id="7116f-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7116f-123">\<routing></span><span class="sxs-lookup"><span data-stu-id="7116f-123">\<routing></span></span>](routing.md)|<span data-ttu-id="7116f-124">一个包含路由表的配置节。</span><span class="sxs-lookup"><span data-stu-id="7116f-124">A configuration section that contains a routing table.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="7116f-125">请参阅</span><span class="sxs-lookup"><span data-stu-id="7116f-125">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.RoutingSection?displayProperty=nameWithType>
- <xref:System.ServiceModel.Routing.Configuration.FilterTableEntryElement?displayProperty=nameWithType>
