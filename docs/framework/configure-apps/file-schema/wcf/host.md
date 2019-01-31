---
title: <host>
ms.date: 03/30/2017
ms.assetid: be566d55-9d50-4b2e-985d-52a5cc26cbbb
ms.openlocfilehash: 8a8f9db96281d8d775ff5c2923018228b3a9c1e5
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/30/2019
ms.locfileid: "55269024"
---
# <a name="host"></a><span data-ttu-id="14688-101">\<host></span><span class="sxs-lookup"><span data-stu-id="14688-101">\<host></span></span>
<span data-ttu-id="14688-102">指定服务主机的设置。</span><span class="sxs-lookup"><span data-stu-id="14688-102">Specifies settings for a service host.</span></span>  
  
 <span data-ttu-id="14688-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="14688-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="14688-104">\<services></span><span class="sxs-lookup"><span data-stu-id="14688-104">\<services></span></span>  
<span data-ttu-id="14688-105">\<service></span><span class="sxs-lookup"><span data-stu-id="14688-105">\<service></span></span>  
<span data-ttu-id="14688-106">\<host></span><span class="sxs-lookup"><span data-stu-id="14688-106">\<host></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="14688-107">语法</span><span class="sxs-lookup"><span data-stu-id="14688-107">Syntax</span></span>  
  
```xml  
<host>
  <baseAddresses>
    <add baseAddress="string" />
  </baseAddresses>
  <timeOuts closeTimeout="TimeSpan"
            openTimeout="TimeSpan" />
</host>
```  
  
## <a name="type"></a><span data-ttu-id="14688-108">类型</span><span class="sxs-lookup"><span data-stu-id="14688-108">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="14688-109">特性和元素</span><span class="sxs-lookup"><span data-stu-id="14688-109">Attributes and Elements</span></span>  
 <span data-ttu-id="14688-110">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="14688-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="14688-111">特性</span><span class="sxs-lookup"><span data-stu-id="14688-111">Attributes</span></span>  
 <span data-ttu-id="14688-112">无。</span><span class="sxs-lookup"><span data-stu-id="14688-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="14688-113">子元素</span><span class="sxs-lookup"><span data-stu-id="14688-113">Child Elements</span></span>  
  
|<span data-ttu-id="14688-114">元素</span><span class="sxs-lookup"><span data-stu-id="14688-114">Element</span></span>|<span data-ttu-id="14688-115">描述</span><span class="sxs-lookup"><span data-stu-id="14688-115">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="14688-116">\<baseAddresses></span><span class="sxs-lookup"><span data-stu-id="14688-116">\<baseAddresses></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/baseaddresses.md)|<span data-ttu-id="14688-117">`baseAddress` 元素的集合，指定服务主机所使用的基址。</span><span class="sxs-lookup"><span data-stu-id="14688-117">A collection of `baseAddress` elements that specifies the base addresses used by the service host.</span></span>|  
|[<span data-ttu-id="14688-118">\<timeOuts></span><span class="sxs-lookup"><span data-stu-id="14688-118">\<timeOuts></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/timeouts.md)|<span data-ttu-id="14688-119">一个配置元素，指定为打开或关闭服务主机预留的时间间隔。</span><span class="sxs-lookup"><span data-stu-id="14688-119">A configuration element that specifies the interval of time allowed for the service host to open or close.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="14688-120">父元素</span><span class="sxs-lookup"><span data-stu-id="14688-120">Parent Elements</span></span>  
  
|<span data-ttu-id="14688-121">元素</span><span class="sxs-lookup"><span data-stu-id="14688-121">Element</span></span>|<span data-ttu-id="14688-122">描述</span><span class="sxs-lookup"><span data-stu-id="14688-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="14688-123">\<service></span><span class="sxs-lookup"><span data-stu-id="14688-123">\<service></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/service.md)|<span data-ttu-id="14688-124">指定 Windows Communication Foundation (WCF) 服务的设置。</span><span class="sxs-lookup"><span data-stu-id="14688-124">Specifies the settings for a Windows Communication Foundation (WCF) service.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="14688-125">请参阅</span><span class="sxs-lookup"><span data-stu-id="14688-125">See also</span></span>
- <xref:System.ServiceModel.Configuration.HostElement>
- <xref:System.ServiceModel.ServiceHost>
- [<span data-ttu-id="14688-126">承载</span><span class="sxs-lookup"><span data-stu-id="14688-126">Hosting</span></span>](../../../../../docs/framework/wcf/feature-details/hosting.md)
