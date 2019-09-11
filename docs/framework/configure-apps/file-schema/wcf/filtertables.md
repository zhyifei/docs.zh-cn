---
title: <filterTables>
ms.date: 03/30/2017
ms.assetid: 41f1ac35-f559-473a-b2c3-8cc83a6a3831
ms.openlocfilehash: c68479737cefe542a10a404a8b31a4820a430ffb
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855197"
---
# <a name="filtertables"></a><span data-ttu-id="79813-101">\<filterTables></span><span class="sxs-lookup"><span data-stu-id="79813-101">\<filterTables></span></span>
<span data-ttu-id="79813-102">表示一个用于定义路由表的配置节，这些路由表包含路由筛选器与在筛选器匹配时消息要发送到的目标终结点之间的映射。</span><span class="sxs-lookup"><span data-stu-id="79813-102">Represents a configuration section for defining routing tables that contain mappings between the routing filters and the target endpoints to send messages to when the filter matches.</span></span>  
  
<span data-ttu-id="79813-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="79813-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="79813-104">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="79813-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="79813-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<路由 >** ](routing.md)</span><span class="sxs-lookup"><span data-stu-id="79813-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<routing>**](routing.md)</span></span>\
<span data-ttu-id="79813-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<filterTables >**</span><span class="sxs-lookup"><span data-stu-id="79813-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<filterTables>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="79813-107">语法</span><span class="sxs-lookup"><span data-stu-id="79813-107">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="79813-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="79813-108">Attributes and Elements</span></span>  
 <span data-ttu-id="79813-109">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="79813-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="79813-110">特性</span><span class="sxs-lookup"><span data-stu-id="79813-110">Attributes</span></span>  
 <span data-ttu-id="79813-111">无。</span><span class="sxs-lookup"><span data-stu-id="79813-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="79813-112">子元素</span><span class="sxs-lookup"><span data-stu-id="79813-112">Child Elements</span></span>  
  
|<span data-ttu-id="79813-113">元素</span><span class="sxs-lookup"><span data-stu-id="79813-113">Element</span></span>|<span data-ttu-id="79813-114">描述</span><span class="sxs-lookup"><span data-stu-id="79813-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="79813-115">\<filters></span><span class="sxs-lookup"><span data-stu-id="79813-115">\<filters></span></span>](filters-of-routing.md)|<span data-ttu-id="79813-116">一个路由表，包含路由筛选器与在筛选器匹配时消息要发送到的目标终结点之间的映射。</span><span class="sxs-lookup"><span data-stu-id="79813-116">A routing table that contain mappings between the routing filters and the target endpoints to send messages to when the filter matches.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="79813-117">父元素</span><span class="sxs-lookup"><span data-stu-id="79813-117">Parent Elements</span></span>  
  
|<span data-ttu-id="79813-118">元素</span><span class="sxs-lookup"><span data-stu-id="79813-118">Element</span></span>|<span data-ttu-id="79813-119">描述</span><span class="sxs-lookup"><span data-stu-id="79813-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="79813-120">\<routing></span><span class="sxs-lookup"><span data-stu-id="79813-120">\<routing></span></span>](routing.md)|<span data-ttu-id="79813-121">一个包含路由筛选器和路由表的配置节。</span><span class="sxs-lookup"><span data-stu-id="79813-121">A configuration section that contains routing filters and routing tables.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="79813-122">请参阅</span><span class="sxs-lookup"><span data-stu-id="79813-122">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.RoutingSection?displayProperty=nameWithType>
- <xref:System.ServiceModel.Routing.Configuration.FilterTableCollection?displayProperty=nameWithType>
