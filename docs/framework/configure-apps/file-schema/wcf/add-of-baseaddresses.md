---
title: <add> 的 <baseAddresses>
ms.date: 03/30/2017
ms.assetid: 1bd7426f-5f4f-43fc-b8e9-de842219aa32
ms.openlocfilehash: d66be51fa2626283063c250905efdb7d47babfb0
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/30/2019
ms.locfileid: "55279937"
---
# <a name="add-of-baseaddresses"></a><span data-ttu-id="840eb-102">\<add> of \<baseAddresses></span><span class="sxs-lookup"><span data-stu-id="840eb-102">\<add> of \<baseAddresses></span></span>
<span data-ttu-id="840eb-103">表示一个配置元素，该元素指定服务主机所使用的基址。</span><span class="sxs-lookup"><span data-stu-id="840eb-103">Represents a configuration element that specifies the base addresses used by the service host.</span></span>  
  
 <span data-ttu-id="840eb-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="840eb-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="840eb-105">\<client></span><span class="sxs-lookup"><span data-stu-id="840eb-105">\<client></span></span>  
<span data-ttu-id="840eb-106">\<endpoint></span><span class="sxs-lookup"><span data-stu-id="840eb-106">\<endpoint></span></span>  
<span data-ttu-id="840eb-107">\<host></span><span class="sxs-lookup"><span data-stu-id="840eb-107">\<host></span></span>  
<span data-ttu-id="840eb-108">\<baseAddresses></span><span class="sxs-lookup"><span data-stu-id="840eb-108">\<baseAddresses></span></span>  
<span data-ttu-id="840eb-109">\<baseAddress></span><span class="sxs-lookup"><span data-stu-id="840eb-109">\<baseAddress></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="840eb-110">语法</span><span class="sxs-lookup"><span data-stu-id="840eb-110">Syntax</span></span>  
  
```xml  
<add baseAddress="string" />
```  
  
## <a name="type"></a><span data-ttu-id="840eb-111">类型</span><span class="sxs-lookup"><span data-stu-id="840eb-111">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="840eb-112">特性和元素</span><span class="sxs-lookup"><span data-stu-id="840eb-112">Attributes and Elements</span></span>  
 <span data-ttu-id="840eb-113">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="840eb-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="840eb-114">特性</span><span class="sxs-lookup"><span data-stu-id="840eb-114">Attributes</span></span>  
  
|<span data-ttu-id="840eb-115">特性</span><span class="sxs-lookup"><span data-stu-id="840eb-115">Attribute</span></span>|<span data-ttu-id="840eb-116">描述</span><span class="sxs-lookup"><span data-stu-id="840eb-116">Description</span></span>|  
|---------------|-----------------|  
|`baseAddress`|<span data-ttu-id="840eb-117">一个字符串，指定服务主机所使用的基址。</span><span class="sxs-lookup"><span data-stu-id="840eb-117">A string that specifies a base address used by the service host.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="840eb-118">子元素</span><span class="sxs-lookup"><span data-stu-id="840eb-118">Child Elements</span></span>  
 <span data-ttu-id="840eb-119">无。</span><span class="sxs-lookup"><span data-stu-id="840eb-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="840eb-120">父元素</span><span class="sxs-lookup"><span data-stu-id="840eb-120">Parent Elements</span></span>  
  
|<span data-ttu-id="840eb-121">元素</span><span class="sxs-lookup"><span data-stu-id="840eb-121">Element</span></span>|<span data-ttu-id="840eb-122">描述</span><span class="sxs-lookup"><span data-stu-id="840eb-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="840eb-123">\<baseAddresses></span><span class="sxs-lookup"><span data-stu-id="840eb-123">\<baseAddresses></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/baseaddresses.md)|<span data-ttu-id="840eb-124">一个 `baseAddress` 元素集合。</span><span class="sxs-lookup"><span data-stu-id="840eb-124">A collection of `baseAddress` elements.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="840eb-125">请参阅</span><span class="sxs-lookup"><span data-stu-id="840eb-125">See also</span></span>
- <xref:System.ServiceModel.Configuration.HostElement>
- <xref:System.ServiceModel.ServiceHost>
- <xref:System.ServiceModel.ServiceHostBase.BaseAddresses%2A>
- [<span data-ttu-id="840eb-126">承载</span><span class="sxs-lookup"><span data-stu-id="840eb-126">Hosting</span></span>](../../../../../docs/framework/wcf/feature-details/hosting.md)
