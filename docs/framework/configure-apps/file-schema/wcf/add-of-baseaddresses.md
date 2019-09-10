---
title: <add> 的 <baseAddresses>
ms.date: 03/30/2017
ms.assetid: 1bd7426f-5f4f-43fc-b8e9-de842219aa32
ms.openlocfilehash: d75142209ad8706d0cad5ce188d9d991a5e881bc
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2019
ms.locfileid: "70850585"
---
# <a name="add-of-baseaddresses"></a><span data-ttu-id="60534-102">\<添加 baseAddresses > \<的 ></span><span class="sxs-lookup"><span data-stu-id="60534-102">\<add> of \<baseAddresses></span></span>
<span data-ttu-id="60534-103">表示一个配置元素，该元素指定服务主机所使用的基址。</span><span class="sxs-lookup"><span data-stu-id="60534-103">Represents a configuration element that specifies the base addresses used by the service host.</span></span>  
  
<span data-ttu-id="60534-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="60534-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="60534-105">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="60534-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="60534-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<服务 >** ](services.md)</span><span class="sxs-lookup"><span data-stu-id="60534-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<services>**](services.md)</span></span>\
<span data-ttu-id="60534-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<服务 >** ](service.md)</span><span class="sxs-lookup"><span data-stu-id="60534-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<service>**](service.md)</span></span>\
<span data-ttu-id="60534-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<主机 >** ](host.md)</span><span class="sxs-lookup"><span data-stu-id="60534-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<host>**](host.md)</span></span>\
<span data-ttu-id="60534-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<baseAddresses >** ](baseaddresses.md)</span><span class="sxs-lookup"><span data-stu-id="60534-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<baseAddresses>**](baseaddresses.md)</span></span>\
<span data-ttu-id="60534-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<添加 >**</span><span class="sxs-lookup"><span data-stu-id="60534-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="60534-111">语法</span><span class="sxs-lookup"><span data-stu-id="60534-111">Syntax</span></span>  
  
```xml  
<add baseAddress="string" />
```  
  
## <a name="type"></a><span data-ttu-id="60534-112">类型</span><span class="sxs-lookup"><span data-stu-id="60534-112">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="60534-113">特性和元素</span><span class="sxs-lookup"><span data-stu-id="60534-113">Attributes and Elements</span></span>  
 <span data-ttu-id="60534-114">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="60534-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="60534-115">特性</span><span class="sxs-lookup"><span data-stu-id="60534-115">Attributes</span></span>  
  
|<span data-ttu-id="60534-116">特性</span><span class="sxs-lookup"><span data-stu-id="60534-116">Attribute</span></span>|<span data-ttu-id="60534-117">描述</span><span class="sxs-lookup"><span data-stu-id="60534-117">Description</span></span>|  
|---------------|-----------------|  
|`baseAddress`|<span data-ttu-id="60534-118">一个字符串，指定服务主机所使用的基址。</span><span class="sxs-lookup"><span data-stu-id="60534-118">A string that specifies a base address used by the service host.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="60534-119">子元素</span><span class="sxs-lookup"><span data-stu-id="60534-119">Child Elements</span></span>  
 <span data-ttu-id="60534-120">无。</span><span class="sxs-lookup"><span data-stu-id="60534-120">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="60534-121">父元素</span><span class="sxs-lookup"><span data-stu-id="60534-121">Parent Elements</span></span>  
  
|<span data-ttu-id="60534-122">元素</span><span class="sxs-lookup"><span data-stu-id="60534-122">Element</span></span>|<span data-ttu-id="60534-123">描述</span><span class="sxs-lookup"><span data-stu-id="60534-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="60534-124">\<baseAddresses></span><span class="sxs-lookup"><span data-stu-id="60534-124">\<baseAddresses></span></span>](baseaddresses.md)|<span data-ttu-id="60534-125">一个 `baseAddress` 元素集合。</span><span class="sxs-lookup"><span data-stu-id="60534-125">A collection of `baseAddress` elements.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="60534-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="60534-126">See also</span></span>

- <xref:System.ServiceModel.Configuration.HostElement>
- <xref:System.ServiceModel.ServiceHost>
- <xref:System.ServiceModel.ServiceHostBase.BaseAddresses%2A>
- [<span data-ttu-id="60534-127">承载</span><span class="sxs-lookup"><span data-stu-id="60534-127">Hosting</span></span>](../../../wcf/feature-details/hosting.md)
