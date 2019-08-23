---
title: <host>
ms.date: 03/30/2017
ms.assetid: be566d55-9d50-4b2e-985d-52a5cc26cbbb
ms.openlocfilehash: 21d53df12c2b2d703b771e2b9cb5ee87dafc410e
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69918712"
---
# <a name="host"></a><span data-ttu-id="48552-101">\<主机 ></span><span class="sxs-lookup"><span data-stu-id="48552-101">\<host></span></span>
<span data-ttu-id="48552-102">指定服务主机的设置。</span><span class="sxs-lookup"><span data-stu-id="48552-102">Specifies settings for a service host.</span></span>  
  
 <span data-ttu-id="48552-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="48552-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="48552-104">\<services></span><span class="sxs-lookup"><span data-stu-id="48552-104">\<services></span></span>  
<span data-ttu-id="48552-105">\<service></span><span class="sxs-lookup"><span data-stu-id="48552-105">\<service></span></span>  
<span data-ttu-id="48552-106">\<主机 ></span><span class="sxs-lookup"><span data-stu-id="48552-106">\<host></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="48552-107">语法</span><span class="sxs-lookup"><span data-stu-id="48552-107">Syntax</span></span>  
  
```xml  
<host>
  <baseAddresses>
    <add baseAddress="string" />
  </baseAddresses>
  <timeOuts closeTimeout="TimeSpan"
            openTimeout="TimeSpan" />
</host>
```  
  
## <a name="type"></a><span data-ttu-id="48552-108">类型</span><span class="sxs-lookup"><span data-stu-id="48552-108">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="48552-109">特性和元素</span><span class="sxs-lookup"><span data-stu-id="48552-109">Attributes and Elements</span></span>  
 <span data-ttu-id="48552-110">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="48552-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="48552-111">特性</span><span class="sxs-lookup"><span data-stu-id="48552-111">Attributes</span></span>  
 <span data-ttu-id="48552-112">无。</span><span class="sxs-lookup"><span data-stu-id="48552-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="48552-113">子元素</span><span class="sxs-lookup"><span data-stu-id="48552-113">Child Elements</span></span>  
  
|<span data-ttu-id="48552-114">元素</span><span class="sxs-lookup"><span data-stu-id="48552-114">Element</span></span>|<span data-ttu-id="48552-115">描述</span><span class="sxs-lookup"><span data-stu-id="48552-115">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="48552-116">\<baseAddresses></span><span class="sxs-lookup"><span data-stu-id="48552-116">\<baseAddresses></span></span>](baseaddresses.md)|<span data-ttu-id="48552-117">`baseAddress` 元素的集合，指定服务主机所使用的基址。</span><span class="sxs-lookup"><span data-stu-id="48552-117">A collection of `baseAddress` elements that specifies the base addresses used by the service host.</span></span>|  
|[<span data-ttu-id="48552-118">\<timeOuts></span><span class="sxs-lookup"><span data-stu-id="48552-118">\<timeOuts></span></span>](timeouts.md)|<span data-ttu-id="48552-119">一个配置元素，指定为打开或关闭服务主机预留的时间间隔。</span><span class="sxs-lookup"><span data-stu-id="48552-119">A configuration element that specifies the interval of time allowed for the service host to open or close.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="48552-120">父元素</span><span class="sxs-lookup"><span data-stu-id="48552-120">Parent Elements</span></span>  
  
|<span data-ttu-id="48552-121">元素</span><span class="sxs-lookup"><span data-stu-id="48552-121">Element</span></span>|<span data-ttu-id="48552-122">描述</span><span class="sxs-lookup"><span data-stu-id="48552-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="48552-123">\<service></span><span class="sxs-lookup"><span data-stu-id="48552-123">\<service></span></span>](service.md)|<span data-ttu-id="48552-124">指定 Windows Communication Foundation (WCF) 服务的设置。</span><span class="sxs-lookup"><span data-stu-id="48552-124">Specifies the settings for a Windows Communication Foundation (WCF) service.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="48552-125">请参阅</span><span class="sxs-lookup"><span data-stu-id="48552-125">See also</span></span>

- <xref:System.ServiceModel.Configuration.HostElement>
- <xref:System.ServiceModel.ServiceHost>
- [<span data-ttu-id="48552-126">承载</span><span class="sxs-lookup"><span data-stu-id="48552-126">Hosting</span></span>](../../../wcf/feature-details/hosting.md)
