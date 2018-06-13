---
title: '&lt;baseAddresses&gt; 的 &lt;add&gt; '
ms.date: 03/30/2017
ms.assetid: 1bd7426f-5f4f-43fc-b8e9-de842219aa32
ms.openlocfilehash: 3f1b7e8f1f4ab8542270d459ce5020ce4320eea9
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
ms.locfileid: "32754140"
---
# <a name="ltaddgt-of-ltbaseaddressesgt"></a><span data-ttu-id="b7dce-102">&lt;baseAddresses&gt; 的 &lt;add&gt; </span><span class="sxs-lookup"><span data-stu-id="b7dce-102">&lt;add&gt; of &lt;baseAddresses&gt;</span></span>
<span data-ttu-id="b7dce-103">表示一个配置元素，该元素指定服务主机所使用的基址。</span><span class="sxs-lookup"><span data-stu-id="b7dce-103">Represents a configuration element that specifies the base addresses used by the service host.</span></span>  
  
 <span data-ttu-id="b7dce-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="b7dce-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="b7dce-105">\<客户端 ></span><span class="sxs-lookup"><span data-stu-id="b7dce-105">\<client></span></span>  
<span data-ttu-id="b7dce-106">\<终结点 ></span><span class="sxs-lookup"><span data-stu-id="b7dce-106">\<endpoint></span></span>  
<span data-ttu-id="b7dce-107">\<主机 ></span><span class="sxs-lookup"><span data-stu-id="b7dce-107">\<host></span></span>  
<span data-ttu-id="b7dce-108">\<基址 ></span><span class="sxs-lookup"><span data-stu-id="b7dce-108">\<baseAddresses></span></span>  
<span data-ttu-id="b7dce-109">\<baseAddress ></span><span class="sxs-lookup"><span data-stu-id="b7dce-109">\<baseAddress></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b7dce-110">语法</span><span class="sxs-lookup"><span data-stu-id="b7dce-110">Syntax</span></span>  
  
```xml  
<add baseAddress="string" />  
```  
  
## <a name="type"></a><span data-ttu-id="b7dce-111">类型</span><span class="sxs-lookup"><span data-stu-id="b7dce-111">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b7dce-112">特性和元素</span><span class="sxs-lookup"><span data-stu-id="b7dce-112">Attributes and Elements</span></span>  
 <span data-ttu-id="b7dce-113">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="b7dce-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b7dce-114">特性</span><span class="sxs-lookup"><span data-stu-id="b7dce-114">Attributes</span></span>  
  
|<span data-ttu-id="b7dce-115">特性</span><span class="sxs-lookup"><span data-stu-id="b7dce-115">Attribute</span></span>|<span data-ttu-id="b7dce-116">描述</span><span class="sxs-lookup"><span data-stu-id="b7dce-116">Description</span></span>|  
|---------------|-----------------|  
|`baseAddress`|<span data-ttu-id="b7dce-117">一个字符串，指定服务主机所使用的基址。</span><span class="sxs-lookup"><span data-stu-id="b7dce-117">A string that specifies a base address used by the service host.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b7dce-118">子元素</span><span class="sxs-lookup"><span data-stu-id="b7dce-118">Child Elements</span></span>  
 <span data-ttu-id="b7dce-119">无。</span><span class="sxs-lookup"><span data-stu-id="b7dce-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="b7dce-120">父元素</span><span class="sxs-lookup"><span data-stu-id="b7dce-120">Parent Elements</span></span>  
  
|<span data-ttu-id="b7dce-121">元素</span><span class="sxs-lookup"><span data-stu-id="b7dce-121">Element</span></span>|<span data-ttu-id="b7dce-122">描述</span><span class="sxs-lookup"><span data-stu-id="b7dce-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b7dce-123">\<基址 ></span><span class="sxs-lookup"><span data-stu-id="b7dce-123">\<baseAddresses></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/baseaddresses.md)|<span data-ttu-id="b7dce-124">一个 `baseAddress` 元素集合。</span><span class="sxs-lookup"><span data-stu-id="b7dce-124">A collection of `baseAddress` elements.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b7dce-125">请参阅</span><span class="sxs-lookup"><span data-stu-id="b7dce-125">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.HostElement>  
 <xref:System.ServiceModel.ServiceHost>  
 <xref:System.ServiceModel.ServiceHostBase.BaseAddresses%2A>  
 [<span data-ttu-id="b7dce-126">承载</span><span class="sxs-lookup"><span data-stu-id="b7dce-126">Hosting</span></span>](../../../../../docs/framework/wcf/feature-details/hosting.md)
