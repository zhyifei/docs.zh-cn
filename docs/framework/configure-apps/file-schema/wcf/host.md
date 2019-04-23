---
title: <host>
ms.date: 03/30/2017
ms.assetid: be566d55-9d50-4b2e-985d-52a5cc26cbbb
ms.openlocfilehash: 3d1f7774f61060880a5c3b0327bdd6c2cc4dd74e
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59102994"
---
# <a name="host"></a><span data-ttu-id="7ee18-101">\<host></span><span class="sxs-lookup"><span data-stu-id="7ee18-101">\<host></span></span>
<span data-ttu-id="7ee18-102">指定服务主机的设置。</span><span class="sxs-lookup"><span data-stu-id="7ee18-102">Specifies settings for a service host.</span></span>  
  
 <span data-ttu-id="7ee18-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="7ee18-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="7ee18-104">\<services></span><span class="sxs-lookup"><span data-stu-id="7ee18-104">\<services></span></span>  
<span data-ttu-id="7ee18-105">\<service></span><span class="sxs-lookup"><span data-stu-id="7ee18-105">\<service></span></span>  
<span data-ttu-id="7ee18-106">\<host></span><span class="sxs-lookup"><span data-stu-id="7ee18-106">\<host></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7ee18-107">语法</span><span class="sxs-lookup"><span data-stu-id="7ee18-107">Syntax</span></span>  
  
```xml  
<host>
  <baseAddresses>
    <add baseAddress="string" />
  </baseAddresses>
  <timeOuts closeTimeout="TimeSpan"
            openTimeout="TimeSpan" />
</host>
```  
  
## <a name="type"></a><span data-ttu-id="7ee18-108">类型</span><span class="sxs-lookup"><span data-stu-id="7ee18-108">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7ee18-109">特性和元素</span><span class="sxs-lookup"><span data-stu-id="7ee18-109">Attributes and Elements</span></span>  
 <span data-ttu-id="7ee18-110">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="7ee18-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7ee18-111">特性</span><span class="sxs-lookup"><span data-stu-id="7ee18-111">Attributes</span></span>  
 <span data-ttu-id="7ee18-112">无。</span><span class="sxs-lookup"><span data-stu-id="7ee18-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="7ee18-113">子元素</span><span class="sxs-lookup"><span data-stu-id="7ee18-113">Child Elements</span></span>  
  
|<span data-ttu-id="7ee18-114">元素</span><span class="sxs-lookup"><span data-stu-id="7ee18-114">Element</span></span>|<span data-ttu-id="7ee18-115">描述</span><span class="sxs-lookup"><span data-stu-id="7ee18-115">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7ee18-116">\<baseAddresses></span><span class="sxs-lookup"><span data-stu-id="7ee18-116">\<baseAddresses></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/baseaddresses.md)|<span data-ttu-id="7ee18-117">`baseAddress` 元素的集合，指定服务主机所使用的基址。</span><span class="sxs-lookup"><span data-stu-id="7ee18-117">A collection of `baseAddress` elements that specifies the base addresses used by the service host.</span></span>|  
|[<span data-ttu-id="7ee18-118">\<timeOuts></span><span class="sxs-lookup"><span data-stu-id="7ee18-118">\<timeOuts></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/timeouts.md)|<span data-ttu-id="7ee18-119">一个配置元素，指定为打开或关闭服务主机预留的时间间隔。</span><span class="sxs-lookup"><span data-stu-id="7ee18-119">A configuration element that specifies the interval of time allowed for the service host to open or close.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="7ee18-120">父元素</span><span class="sxs-lookup"><span data-stu-id="7ee18-120">Parent Elements</span></span>  
  
|<span data-ttu-id="7ee18-121">元素</span><span class="sxs-lookup"><span data-stu-id="7ee18-121">Element</span></span>|<span data-ttu-id="7ee18-122">描述</span><span class="sxs-lookup"><span data-stu-id="7ee18-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7ee18-123">\<service></span><span class="sxs-lookup"><span data-stu-id="7ee18-123">\<service></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/service.md)|<span data-ttu-id="7ee18-124">指定 Windows Communication Foundation (WCF) 服务的设置。</span><span class="sxs-lookup"><span data-stu-id="7ee18-124">Specifies the settings for a Windows Communication Foundation (WCF) service.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="7ee18-125">请参阅</span><span class="sxs-lookup"><span data-stu-id="7ee18-125">See also</span></span>

- <xref:System.ServiceModel.Configuration.HostElement>
- <xref:System.ServiceModel.ServiceHost>
- [<span data-ttu-id="7ee18-126">承载</span><span class="sxs-lookup"><span data-stu-id="7ee18-126">Hosting</span></span>](../../../../../docs/framework/wcf/feature-details/hosting.md)
