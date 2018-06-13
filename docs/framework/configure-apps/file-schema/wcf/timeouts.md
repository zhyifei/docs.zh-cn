---
title: '&lt;超时&gt;'
ms.date: 03/30/2017
ms.assetid: 7fccd436-b326-48ec-8de1-c16817a09e0d
ms.openlocfilehash: 1f0638f85177d2acb6f61e3246a1a5ee9a4e2f5c
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
ms.locfileid: "32752996"
---
# <a name="lttimeoutsgt"></a><span data-ttu-id="b0a40-102">&lt;超时&gt;</span><span class="sxs-lookup"><span data-stu-id="b0a40-102">&lt;timeOuts&gt;</span></span>
<span data-ttu-id="b0a40-103">表示一个配置元素，该元素指定允许服务主机打开或关闭的时间间隔。</span><span class="sxs-lookup"><span data-stu-id="b0a40-103">Represents a configuration element that specifies the interval of time allowed for the service host to open or close.</span></span>  
  
 <span data-ttu-id="b0a40-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="b0a40-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="b0a40-105">\<客户端 ></span><span class="sxs-lookup"><span data-stu-id="b0a40-105">\<client></span></span>  
<span data-ttu-id="b0a40-106">\<终结点 ></span><span class="sxs-lookup"><span data-stu-id="b0a40-106">\<endpoint></span></span>  
<span data-ttu-id="b0a40-107">\<主机 ></span><span class="sxs-lookup"><span data-stu-id="b0a40-107">\<host></span></span>  
<span data-ttu-id="b0a40-108">\<超时 ></span><span class="sxs-lookup"><span data-stu-id="b0a40-108">\<timeOuts></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b0a40-109">语法</span><span class="sxs-lookup"><span data-stu-id="b0a40-109">Syntax</span></span>  
  
```xml  
<timeOuts closeTimeout="TimeSpan"  
   openTimeout="TimeSpan" >  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b0a40-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="b0a40-110">Attributes and Elements</span></span>  
 <span data-ttu-id="b0a40-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="b0a40-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b0a40-112">特性</span><span class="sxs-lookup"><span data-stu-id="b0a40-112">Attributes</span></span>  
  
|<span data-ttu-id="b0a40-113">特性</span><span class="sxs-lookup"><span data-stu-id="b0a40-113">Attribute</span></span>|<span data-ttu-id="b0a40-114">描述</span><span class="sxs-lookup"><span data-stu-id="b0a40-114">Description</span></span>|  
|---------------|-----------------|  
|`closeTimeout`|<span data-ttu-id="b0a40-115">一个 <xref:System.TimeSpan> 值，指定为关闭服务主机预留的时间间隔。</span><span class="sxs-lookup"><span data-stu-id="b0a40-115">A <xref:System.TimeSpan> value that specifies the interval of time allowed for the service host to close.</span></span>|  
|`openTimeout`|<span data-ttu-id="b0a40-116">一个 <xref:System.TimeSpan> 值，指定为打开或关闭服务主机预留的时间间隔。</span><span class="sxs-lookup"><span data-stu-id="b0a40-116">A <xref:System.TimeSpan> value that specifies the interval of time allowed for the service host to open.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b0a40-117">子元素</span><span class="sxs-lookup"><span data-stu-id="b0a40-117">Child Elements</span></span>  
 <span data-ttu-id="b0a40-118">无。</span><span class="sxs-lookup"><span data-stu-id="b0a40-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="b0a40-119">父元素</span><span class="sxs-lookup"><span data-stu-id="b0a40-119">Parent Elements</span></span>  
  
|<span data-ttu-id="b0a40-120">元素</span><span class="sxs-lookup"><span data-stu-id="b0a40-120">Element</span></span>|<span data-ttu-id="b0a40-121">描述</span><span class="sxs-lookup"><span data-stu-id="b0a40-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b0a40-122">\<主机 ></span><span class="sxs-lookup"><span data-stu-id="b0a40-122">\<host></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/host.md)|<span data-ttu-id="b0a40-123">一个指定服务主机设置的配置元素。</span><span class="sxs-lookup"><span data-stu-id="b0a40-123">A configuration element that specifies settings for a service host.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b0a40-124">请参阅</span><span class="sxs-lookup"><span data-stu-id="b0a40-124">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.HostElement>  
 <xref:System.ServiceModel.ServiceHost>  
 [<span data-ttu-id="b0a40-125">承载</span><span class="sxs-lookup"><span data-stu-id="b0a40-125">Hosting</span></span>](../../../../../docs/framework/wcf/feature-details/hosting.md)
