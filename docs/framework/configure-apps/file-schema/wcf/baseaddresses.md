---
title: <baseAddresses>
ms.date: 03/30/2017
ms.assetid: 78918102-2898-46e0-9ea8-6b8afe65603e
ms.openlocfilehash: 9b3ed6b39f1743249925d5b6d9a47845c87983bc
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2019
ms.locfileid: "70850205"
---
# <a name="baseaddresses"></a><span data-ttu-id="ce8ab-101">\<baseAddresses></span><span class="sxs-lookup"><span data-stu-id="ce8ab-101">\<baseAddresses></span></span>
<span data-ttu-id="ce8ab-102">表示一个 `baseAddress` 元素集合，这些元素是自承载环境中服务主机的基址。</span><span class="sxs-lookup"><span data-stu-id="ce8ab-102">Represents a collection of `baseAddress` elements, which are base addresses for a service host in a self-hosted environment.</span></span> <span data-ttu-id="ce8ab-103">如果存在基址，则可以使用相对于基址的地址配置终结点。</span><span class="sxs-lookup"><span data-stu-id="ce8ab-103">If a base address is present, endpoints can be configured with addresses relative to the base address.</span></span>  
  
<span data-ttu-id="ce8ab-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="ce8ab-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="ce8ab-105">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="ce8ab-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="ce8ab-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<服务 >** ](services.md)</span><span class="sxs-lookup"><span data-stu-id="ce8ab-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<services>**](services.md)</span></span>\
<span data-ttu-id="ce8ab-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<服务 >** ](service.md)</span><span class="sxs-lookup"><span data-stu-id="ce8ab-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<service>**](service.md)</span></span>\
<span data-ttu-id="ce8ab-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<主机 >** ](host.md)</span><span class="sxs-lookup"><span data-stu-id="ce8ab-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<host>**](host.md)</span></span>\
<span data-ttu-id="ce8ab-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<baseAddresses >**</span><span class="sxs-lookup"><span data-stu-id="ce8ab-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<baseAddresses>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ce8ab-110">语法</span><span class="sxs-lookup"><span data-stu-id="ce8ab-110">Syntax</span></span>  
  
```xml  
<baseAddresses>
  <add baseAddress="string" />
</baseAddresses>
```  
  
## <a name="type"></a><span data-ttu-id="ce8ab-111">类型</span><span class="sxs-lookup"><span data-stu-id="ce8ab-111">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ce8ab-112">特性和元素</span><span class="sxs-lookup"><span data-stu-id="ce8ab-112">Attributes and Elements</span></span>  
 <span data-ttu-id="ce8ab-113">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="ce8ab-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ce8ab-114">特性</span><span class="sxs-lookup"><span data-stu-id="ce8ab-114">Attributes</span></span>  
 <span data-ttu-id="ce8ab-115">无。</span><span class="sxs-lookup"><span data-stu-id="ce8ab-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="ce8ab-116">子元素</span><span class="sxs-lookup"><span data-stu-id="ce8ab-116">Child Elements</span></span>  
  
|<span data-ttu-id="ce8ab-117">元素</span><span class="sxs-lookup"><span data-stu-id="ce8ab-117">Element</span></span>|<span data-ttu-id="ce8ab-118">描述</span><span class="sxs-lookup"><span data-stu-id="ce8ab-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ce8ab-119">\<add></span><span class="sxs-lookup"><span data-stu-id="ce8ab-119">\<add></span></span>](add-of-baseaddresses.md)|<span data-ttu-id="ce8ab-120">一个配置元素，指定服务主机所使用的基址。</span><span class="sxs-lookup"><span data-stu-id="ce8ab-120">A configuration element that specifies the base addresses used by the service host.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="ce8ab-121">父元素</span><span class="sxs-lookup"><span data-stu-id="ce8ab-121">Parent Elements</span></span>  
  
|<span data-ttu-id="ce8ab-122">元素</span><span class="sxs-lookup"><span data-stu-id="ce8ab-122">Element</span></span>|<span data-ttu-id="ce8ab-123">描述</span><span class="sxs-lookup"><span data-stu-id="ce8ab-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ce8ab-124">\<host></span><span class="sxs-lookup"><span data-stu-id="ce8ab-124">\<host></span></span>](host.md)|<span data-ttu-id="ce8ab-125">一个指定服务主机设置的配置元素。</span><span class="sxs-lookup"><span data-stu-id="ce8ab-125">A configuration element that specifies settings for a service host.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ce8ab-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="ce8ab-126">See also</span></span>

- <xref:System.ServiceModel.Configuration.HostElement>
- <xref:System.ServiceModel.ServiceHost>
- <xref:System.ServiceModel.ServiceHostBase.BaseAddresses%2A>
- [<span data-ttu-id="ce8ab-127">承载</span><span class="sxs-lookup"><span data-stu-id="ce8ab-127">Hosting</span></span>](../../../wcf/feature-details/hosting.md)
