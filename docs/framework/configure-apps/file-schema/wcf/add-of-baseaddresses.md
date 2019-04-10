---
title: <add> 的 <baseAddresses>
ms.date: 03/30/2017
ms.assetid: 1bd7426f-5f4f-43fc-b8e9-de842219aa32
ms.openlocfilehash: fbcb3a07bf40c96a4cd1b2ec87277b6fefdfb89d
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59164471"
---
# <a name="add-of-baseaddresses"></a><span data-ttu-id="63bf0-102">\<add> of \<baseAddresses></span><span class="sxs-lookup"><span data-stu-id="63bf0-102">\<add> of \<baseAddresses></span></span>
<span data-ttu-id="63bf0-103">表示一个配置元素，该元素指定服务主机所使用的基址。</span><span class="sxs-lookup"><span data-stu-id="63bf0-103">Represents a configuration element that specifies the base addresses used by the service host.</span></span>  
  
 <span data-ttu-id="63bf0-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="63bf0-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="63bf0-105">\<client></span><span class="sxs-lookup"><span data-stu-id="63bf0-105">\<client></span></span>  
<span data-ttu-id="63bf0-106">\<endpoint></span><span class="sxs-lookup"><span data-stu-id="63bf0-106">\<endpoint></span></span>  
<span data-ttu-id="63bf0-107">\<host></span><span class="sxs-lookup"><span data-stu-id="63bf0-107">\<host></span></span>  
<span data-ttu-id="63bf0-108">\<baseAddresses></span><span class="sxs-lookup"><span data-stu-id="63bf0-108">\<baseAddresses></span></span>  
<span data-ttu-id="63bf0-109">\<baseAddress></span><span class="sxs-lookup"><span data-stu-id="63bf0-109">\<baseAddress></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="63bf0-110">语法</span><span class="sxs-lookup"><span data-stu-id="63bf0-110">Syntax</span></span>  
  
```xml  
<add baseAddress="string" />
```  
  
## <a name="type"></a><span data-ttu-id="63bf0-111">类型</span><span class="sxs-lookup"><span data-stu-id="63bf0-111">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="63bf0-112">特性和元素</span><span class="sxs-lookup"><span data-stu-id="63bf0-112">Attributes and Elements</span></span>  
 <span data-ttu-id="63bf0-113">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="63bf0-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="63bf0-114">特性</span><span class="sxs-lookup"><span data-stu-id="63bf0-114">Attributes</span></span>  
  
|<span data-ttu-id="63bf0-115">特性</span><span class="sxs-lookup"><span data-stu-id="63bf0-115">Attribute</span></span>|<span data-ttu-id="63bf0-116">描述</span><span class="sxs-lookup"><span data-stu-id="63bf0-116">Description</span></span>|  
|---------------|-----------------|  
|`baseAddress`|<span data-ttu-id="63bf0-117">一个字符串，指定服务主机所使用的基址。</span><span class="sxs-lookup"><span data-stu-id="63bf0-117">A string that specifies a base address used by the service host.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="63bf0-118">子元素</span><span class="sxs-lookup"><span data-stu-id="63bf0-118">Child Elements</span></span>  
 <span data-ttu-id="63bf0-119">无。</span><span class="sxs-lookup"><span data-stu-id="63bf0-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="63bf0-120">父元素</span><span class="sxs-lookup"><span data-stu-id="63bf0-120">Parent Elements</span></span>  
  
|<span data-ttu-id="63bf0-121">元素</span><span class="sxs-lookup"><span data-stu-id="63bf0-121">Element</span></span>|<span data-ttu-id="63bf0-122">描述</span><span class="sxs-lookup"><span data-stu-id="63bf0-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="63bf0-123">\<baseAddresses></span><span class="sxs-lookup"><span data-stu-id="63bf0-123">\<baseAddresses></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/baseaddresses.md)|<span data-ttu-id="63bf0-124">一个 `baseAddress` 元素集合。</span><span class="sxs-lookup"><span data-stu-id="63bf0-124">A collection of `baseAddress` elements.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="63bf0-125">请参阅</span><span class="sxs-lookup"><span data-stu-id="63bf0-125">See also</span></span>

- <xref:System.ServiceModel.Configuration.HostElement>
- <xref:System.ServiceModel.ServiceHost>
- <xref:System.ServiceModel.ServiceHostBase.BaseAddresses%2A>
- [<span data-ttu-id="63bf0-126">宿主</span><span class="sxs-lookup"><span data-stu-id="63bf0-126">Hosting</span></span>](../../../../../docs/framework/wcf/feature-details/hosting.md)
