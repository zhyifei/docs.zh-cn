---
title: '&lt;baseAddresses&gt; 的 &lt;add&gt; '
ms.date: 03/30/2017
ms.assetid: 1bd7426f-5f4f-43fc-b8e9-de842219aa32
ms.openlocfilehash: ce476c2d40758cf52eada813873d061d0e441bce
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/09/2019
ms.locfileid: "54149080"
---
# <a name="ltaddgt-of-ltbaseaddressesgt"></a><span data-ttu-id="948d4-102">&lt;baseAddresses&gt; 的 &lt;add&gt; </span><span class="sxs-lookup"><span data-stu-id="948d4-102">&lt;add&gt; of &lt;baseAddresses&gt;</span></span>
<span data-ttu-id="948d4-103">表示一个配置元素，该元素指定服务主机所使用的基址。</span><span class="sxs-lookup"><span data-stu-id="948d4-103">Represents a configuration element that specifies the base addresses used by the service host.</span></span>  
  
 <span data-ttu-id="948d4-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="948d4-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="948d4-105">\<客户端 ></span><span class="sxs-lookup"><span data-stu-id="948d4-105">\<client></span></span>  
<span data-ttu-id="948d4-106">\<终结点 ></span><span class="sxs-lookup"><span data-stu-id="948d4-106">\<endpoint></span></span>  
<span data-ttu-id="948d4-107">\<主机 ></span><span class="sxs-lookup"><span data-stu-id="948d4-107">\<host></span></span>  
<span data-ttu-id="948d4-108">\<baseAddresses ></span><span class="sxs-lookup"><span data-stu-id="948d4-108">\<baseAddresses></span></span>  
<span data-ttu-id="948d4-109">\<baseAddress ></span><span class="sxs-lookup"><span data-stu-id="948d4-109">\<baseAddress></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="948d4-110">语法</span><span class="sxs-lookup"><span data-stu-id="948d4-110">Syntax</span></span>  
  
```xml  
<add baseAddress="string" />
```  
  
## <a name="type"></a><span data-ttu-id="948d4-111">类型</span><span class="sxs-lookup"><span data-stu-id="948d4-111">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="948d4-112">特性和元素</span><span class="sxs-lookup"><span data-stu-id="948d4-112">Attributes and Elements</span></span>  
 <span data-ttu-id="948d4-113">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="948d4-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="948d4-114">特性</span><span class="sxs-lookup"><span data-stu-id="948d4-114">Attributes</span></span>  
  
|<span data-ttu-id="948d4-115">特性</span><span class="sxs-lookup"><span data-stu-id="948d4-115">Attribute</span></span>|<span data-ttu-id="948d4-116">描述</span><span class="sxs-lookup"><span data-stu-id="948d4-116">Description</span></span>|  
|---------------|-----------------|  
|`baseAddress`|<span data-ttu-id="948d4-117">一个字符串，指定服务主机所使用的基址。</span><span class="sxs-lookup"><span data-stu-id="948d4-117">A string that specifies a base address used by the service host.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="948d4-118">子元素</span><span class="sxs-lookup"><span data-stu-id="948d4-118">Child Elements</span></span>  
 <span data-ttu-id="948d4-119">无。</span><span class="sxs-lookup"><span data-stu-id="948d4-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="948d4-120">父元素</span><span class="sxs-lookup"><span data-stu-id="948d4-120">Parent Elements</span></span>  
  
|<span data-ttu-id="948d4-121">元素</span><span class="sxs-lookup"><span data-stu-id="948d4-121">Element</span></span>|<span data-ttu-id="948d4-122">描述</span><span class="sxs-lookup"><span data-stu-id="948d4-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="948d4-123">\<baseAddresses ></span><span class="sxs-lookup"><span data-stu-id="948d4-123">\<baseAddresses></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/baseaddresses.md)|<span data-ttu-id="948d4-124">一个 `baseAddress` 元素集合。</span><span class="sxs-lookup"><span data-stu-id="948d4-124">A collection of `baseAddress` elements.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="948d4-125">请参阅</span><span class="sxs-lookup"><span data-stu-id="948d4-125">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.HostElement>  
 <xref:System.ServiceModel.ServiceHost>  
 <xref:System.ServiceModel.ServiceHostBase.BaseAddresses%2A>  
 [<span data-ttu-id="948d4-126">承载</span><span class="sxs-lookup"><span data-stu-id="948d4-126">Hosting</span></span>](../../../../../docs/framework/wcf/feature-details/hosting.md)
