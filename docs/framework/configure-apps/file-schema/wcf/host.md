---
title: '&lt;host&gt;'
ms.date: 03/30/2017
ms.assetid: be566d55-9d50-4b2e-985d-52a5cc26cbbb
ms.openlocfilehash: 1fb35058d407d0fbae78092bb4ccd45b0aaa40e6
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54702023"
---
# <a name="lthostgt"></a><span data-ttu-id="6455a-102">&lt;host&gt;</span><span class="sxs-lookup"><span data-stu-id="6455a-102">&lt;host&gt;</span></span>
<span data-ttu-id="6455a-103">指定服务主机的设置。</span><span class="sxs-lookup"><span data-stu-id="6455a-103">Specifies settings for a service host.</span></span>  
  
 <span data-ttu-id="6455a-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="6455a-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="6455a-105">\<services></span><span class="sxs-lookup"><span data-stu-id="6455a-105">\<services></span></span>  
<span data-ttu-id="6455a-106">\<service></span><span class="sxs-lookup"><span data-stu-id="6455a-106">\<service></span></span>  
<span data-ttu-id="6455a-107">\<host></span><span class="sxs-lookup"><span data-stu-id="6455a-107">\<host></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6455a-108">语法</span><span class="sxs-lookup"><span data-stu-id="6455a-108">Syntax</span></span>  
  
```xml  
<host>
  <baseAddresses>
    <add baseAddress="string" />
  </baseAddresses>
  <timeOuts closeTimeout="TimeSpan"
            openTimeout="TimeSpan" />
</host>
```  
  
## <a name="type"></a><span data-ttu-id="6455a-109">类型</span><span class="sxs-lookup"><span data-stu-id="6455a-109">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6455a-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="6455a-110">Attributes and Elements</span></span>  
 <span data-ttu-id="6455a-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="6455a-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6455a-112">特性</span><span class="sxs-lookup"><span data-stu-id="6455a-112">Attributes</span></span>  
 <span data-ttu-id="6455a-113">无。</span><span class="sxs-lookup"><span data-stu-id="6455a-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="6455a-114">子元素</span><span class="sxs-lookup"><span data-stu-id="6455a-114">Child Elements</span></span>  
  
|<span data-ttu-id="6455a-115">元素</span><span class="sxs-lookup"><span data-stu-id="6455a-115">Element</span></span>|<span data-ttu-id="6455a-116">描述</span><span class="sxs-lookup"><span data-stu-id="6455a-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6455a-117">\<baseAddresses></span><span class="sxs-lookup"><span data-stu-id="6455a-117">\<baseAddresses></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/baseaddresses.md)|<span data-ttu-id="6455a-118">`baseAddress` 元素的集合，指定服务主机所使用的基址。</span><span class="sxs-lookup"><span data-stu-id="6455a-118">A collection of `baseAddress` elements that specifies the base addresses used by the service host.</span></span>|  
|[<span data-ttu-id="6455a-119">\<timeOuts></span><span class="sxs-lookup"><span data-stu-id="6455a-119">\<timeOuts></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/timeouts.md)|<span data-ttu-id="6455a-120">一个配置元素，指定为打开或关闭服务主机预留的时间间隔。</span><span class="sxs-lookup"><span data-stu-id="6455a-120">A configuration element that specifies the interval of time allowed for the service host to open or close.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="6455a-121">父元素</span><span class="sxs-lookup"><span data-stu-id="6455a-121">Parent Elements</span></span>  
  
|<span data-ttu-id="6455a-122">元素</span><span class="sxs-lookup"><span data-stu-id="6455a-122">Element</span></span>|<span data-ttu-id="6455a-123">描述</span><span class="sxs-lookup"><span data-stu-id="6455a-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6455a-124">\<service></span><span class="sxs-lookup"><span data-stu-id="6455a-124">\<service></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/service.md)|<span data-ttu-id="6455a-125">指定 Windows Communication Foundation (WCF) 服务的设置。</span><span class="sxs-lookup"><span data-stu-id="6455a-125">Specifies the settings for a Windows Communication Foundation (WCF) service.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="6455a-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="6455a-126">See also</span></span>
- <xref:System.ServiceModel.Configuration.HostElement>
- <xref:System.ServiceModel.ServiceHost>
- [<span data-ttu-id="6455a-127">承载</span><span class="sxs-lookup"><span data-stu-id="6455a-127">Hosting</span></span>](../../../../../docs/framework/wcf/feature-details/hosting.md)
