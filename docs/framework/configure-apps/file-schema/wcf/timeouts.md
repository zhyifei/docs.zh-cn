---
title: <timeOuts>
ms.date: 03/30/2017
ms.assetid: 7fccd436-b326-48ec-8de1-c16817a09e0d
ms.openlocfilehash: b9c67ac03f0eb73a2a4cdd43ab48fe12871a1cc3
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2019
ms.locfileid: "70854967"
---
# <a name="timeouts"></a><span data-ttu-id="509fb-101">\<timeOuts></span><span class="sxs-lookup"><span data-stu-id="509fb-101">\<timeOuts></span></span>
<span data-ttu-id="509fb-102">表示一个配置元素，该元素指定允许服务主机打开或关闭的时间间隔。</span><span class="sxs-lookup"><span data-stu-id="509fb-102">Represents a configuration element that specifies the interval of time allowed for the service host to open or close.</span></span>  
  
<span data-ttu-id="509fb-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="509fb-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="509fb-104">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="509fb-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="509fb-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<服务 >** ](services.md)</span><span class="sxs-lookup"><span data-stu-id="509fb-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<services>**](services.md)</span></span>\
<span data-ttu-id="509fb-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<服务 >** ](service.md)</span><span class="sxs-lookup"><span data-stu-id="509fb-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<service>**](service.md)</span></span>\
<span data-ttu-id="509fb-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<主机 >** ](host.md)</span><span class="sxs-lookup"><span data-stu-id="509fb-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<host>**](host.md)</span></span>\
<span data-ttu-id="509fb-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<超时 >**</span><span class="sxs-lookup"><span data-stu-id="509fb-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<timeOuts>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="509fb-109">语法</span><span class="sxs-lookup"><span data-stu-id="509fb-109">Syntax</span></span>  
  
```xml  
<timeOuts closeTimeout="TimeSpan"
          openTimeout="TimeSpan" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="509fb-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="509fb-110">Attributes and Elements</span></span>  
 <span data-ttu-id="509fb-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="509fb-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="509fb-112">特性</span><span class="sxs-lookup"><span data-stu-id="509fb-112">Attributes</span></span>  
  
|<span data-ttu-id="509fb-113">特性</span><span class="sxs-lookup"><span data-stu-id="509fb-113">Attribute</span></span>|<span data-ttu-id="509fb-114">描述</span><span class="sxs-lookup"><span data-stu-id="509fb-114">Description</span></span>|  
|---------------|-----------------|  
|`closeTimeout`|<span data-ttu-id="509fb-115">一个 <xref:System.TimeSpan> 值，指定为关闭服务主机预留的时间间隔。</span><span class="sxs-lookup"><span data-stu-id="509fb-115">A <xref:System.TimeSpan> value that specifies the interval of time allowed for the service host to close.</span></span>|  
|`openTimeout`|<span data-ttu-id="509fb-116">一个 <xref:System.TimeSpan> 值，指定为打开或关闭服务主机预留的时间间隔。</span><span class="sxs-lookup"><span data-stu-id="509fb-116">A <xref:System.TimeSpan> value that specifies the interval of time allowed for the service host to open.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="509fb-117">子元素</span><span class="sxs-lookup"><span data-stu-id="509fb-117">Child Elements</span></span>  
 <span data-ttu-id="509fb-118">无。</span><span class="sxs-lookup"><span data-stu-id="509fb-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="509fb-119">父元素</span><span class="sxs-lookup"><span data-stu-id="509fb-119">Parent Elements</span></span>  
  
|<span data-ttu-id="509fb-120">元素</span><span class="sxs-lookup"><span data-stu-id="509fb-120">Element</span></span>|<span data-ttu-id="509fb-121">描述</span><span class="sxs-lookup"><span data-stu-id="509fb-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="509fb-122">\<host></span><span class="sxs-lookup"><span data-stu-id="509fb-122">\<host></span></span>](host.md)|<span data-ttu-id="509fb-123">一个指定服务主机设置的配置元素。</span><span class="sxs-lookup"><span data-stu-id="509fb-123">A configuration element that specifies settings for a service host.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="509fb-124">请参阅</span><span class="sxs-lookup"><span data-stu-id="509fb-124">See also</span></span>

- <xref:System.ServiceModel.Configuration.HostElement>
- <xref:System.ServiceModel.ServiceHost>
- [<span data-ttu-id="509fb-125">承载</span><span class="sxs-lookup"><span data-stu-id="509fb-125">Hosting</span></span>](../../../wcf/feature-details/hosting.md)
