---
title: <host>
ms.date: 03/30/2017
ms.assetid: be566d55-9d50-4b2e-985d-52a5cc26cbbb
ms.openlocfilehash: b764bc21e9c4555b39c3d096212b6e6bcabb62ff
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855213"
---
# <a name="host"></a><span data-ttu-id="edecc-101">\<主机 ></span><span class="sxs-lookup"><span data-stu-id="edecc-101">\<host></span></span>
<span data-ttu-id="edecc-102">指定服务主机的设置。</span><span class="sxs-lookup"><span data-stu-id="edecc-102">Specifies settings for a service host.</span></span>  
  
<span data-ttu-id="edecc-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="edecc-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="edecc-104">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="edecc-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="edecc-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<服务 >** ](services.md)</span><span class="sxs-lookup"><span data-stu-id="edecc-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<services>**](services.md)</span></span>\
<span data-ttu-id="edecc-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<服务 >** ](service.md)</span><span class="sxs-lookup"><span data-stu-id="edecc-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<service>**](service.md)</span></span>\
<span data-ttu-id="edecc-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<主机 >**</span><span class="sxs-lookup"><span data-stu-id="edecc-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<host>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="edecc-108">语法</span><span class="sxs-lookup"><span data-stu-id="edecc-108">Syntax</span></span>  
  
```xml  
<host>
  <baseAddresses>
    <add baseAddress="string" />
  </baseAddresses>
  <timeOuts closeTimeout="TimeSpan"
            openTimeout="TimeSpan" />
</host>
```  
  
## <a name="type"></a><span data-ttu-id="edecc-109">类型</span><span class="sxs-lookup"><span data-stu-id="edecc-109">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="edecc-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="edecc-110">Attributes and Elements</span></span>  
 <span data-ttu-id="edecc-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="edecc-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="edecc-112">特性</span><span class="sxs-lookup"><span data-stu-id="edecc-112">Attributes</span></span>  
 <span data-ttu-id="edecc-113">无。</span><span class="sxs-lookup"><span data-stu-id="edecc-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="edecc-114">子元素</span><span class="sxs-lookup"><span data-stu-id="edecc-114">Child Elements</span></span>  
  
|<span data-ttu-id="edecc-115">元素</span><span class="sxs-lookup"><span data-stu-id="edecc-115">Element</span></span>|<span data-ttu-id="edecc-116">描述</span><span class="sxs-lookup"><span data-stu-id="edecc-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="edecc-117">\<baseAddresses></span><span class="sxs-lookup"><span data-stu-id="edecc-117">\<baseAddresses></span></span>](baseaddresses.md)|<span data-ttu-id="edecc-118">`baseAddress` 元素的集合，指定服务主机所使用的基址。</span><span class="sxs-lookup"><span data-stu-id="edecc-118">A collection of `baseAddress` elements that specifies the base addresses used by the service host.</span></span>|  
|[<span data-ttu-id="edecc-119">\<timeOuts></span><span class="sxs-lookup"><span data-stu-id="edecc-119">\<timeOuts></span></span>](timeouts.md)|<span data-ttu-id="edecc-120">一个配置元素，指定为打开或关闭服务主机预留的时间间隔。</span><span class="sxs-lookup"><span data-stu-id="edecc-120">A configuration element that specifies the interval of time allowed for the service host to open or close.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="edecc-121">父元素</span><span class="sxs-lookup"><span data-stu-id="edecc-121">Parent Elements</span></span>  
  
|<span data-ttu-id="edecc-122">元素</span><span class="sxs-lookup"><span data-stu-id="edecc-122">Element</span></span>|<span data-ttu-id="edecc-123">描述</span><span class="sxs-lookup"><span data-stu-id="edecc-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="edecc-124">\<service></span><span class="sxs-lookup"><span data-stu-id="edecc-124">\<service></span></span>](service.md)|<span data-ttu-id="edecc-125">指定 Windows Communication Foundation （WCF）服务的设置。</span><span class="sxs-lookup"><span data-stu-id="edecc-125">Specifies the settings for a Windows Communication Foundation (WCF) service.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="edecc-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="edecc-126">See also</span></span>

- <xref:System.ServiceModel.Configuration.HostElement>
- <xref:System.ServiceModel.ServiceHost>
- [<span data-ttu-id="edecc-127">承载</span><span class="sxs-lookup"><span data-stu-id="edecc-127">Hosting</span></span>](../../../wcf/feature-details/hosting.md)
