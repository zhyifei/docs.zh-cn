---
title: "&lt;超时&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7fccd436-b326-48ec-8de1-c16817a09e0d
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 04003584cf12355116d32cccffdcb2b9990b1b85
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="lttimeoutsgt"></a><span data-ttu-id="f2a62-102">&lt;超时&gt;</span><span class="sxs-lookup"><span data-stu-id="f2a62-102">&lt;timeOuts&gt;</span></span>
<span data-ttu-id="f2a62-103">表示一个配置元素，该元素指定允许服务主机打开或关闭的时间间隔。</span><span class="sxs-lookup"><span data-stu-id="f2a62-103">Represents a configuration element that specifies the interval of time allowed for the service host to open or close.</span></span>  
  
 <span data-ttu-id="f2a62-104">\<系统。ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="f2a62-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="f2a62-105">\<客户端 ></span><span class="sxs-lookup"><span data-stu-id="f2a62-105">\<client></span></span>  
<span data-ttu-id="f2a62-106">\<终结点 ></span><span class="sxs-lookup"><span data-stu-id="f2a62-106">\<endpoint></span></span>  
<span data-ttu-id="f2a62-107">\<主机 ></span><span class="sxs-lookup"><span data-stu-id="f2a62-107">\<host></span></span>  
<span data-ttu-id="f2a62-108">\<超时 ></span><span class="sxs-lookup"><span data-stu-id="f2a62-108">\<timeOuts></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f2a62-109">语法</span><span class="sxs-lookup"><span data-stu-id="f2a62-109">Syntax</span></span>  
  
```xml  
<timeOuts closeTimeout="TimeSpan"  
   openTimeout="TimeSpan" >  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f2a62-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="f2a62-110">Attributes and Elements</span></span>  
 <span data-ttu-id="f2a62-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="f2a62-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f2a62-112">特性</span><span class="sxs-lookup"><span data-stu-id="f2a62-112">Attributes</span></span>  
  
|<span data-ttu-id="f2a62-113">特性</span><span class="sxs-lookup"><span data-stu-id="f2a62-113">Attribute</span></span>|<span data-ttu-id="f2a62-114">描述</span><span class="sxs-lookup"><span data-stu-id="f2a62-114">Description</span></span>|  
|---------------|-----------------|  
|`closeTimeout`|<span data-ttu-id="f2a62-115">一个 <xref:System.TimeSpan> 值，指定为关闭服务主机预留的时间间隔。</span><span class="sxs-lookup"><span data-stu-id="f2a62-115">A <xref:System.TimeSpan> value that specifies the interval of time allowed for the service host to close.</span></span>|  
|`openTimeout`|<span data-ttu-id="f2a62-116">一个 <xref:System.TimeSpan> 值，指定为打开或关闭服务主机预留的时间间隔。</span><span class="sxs-lookup"><span data-stu-id="f2a62-116">A <xref:System.TimeSpan> value that specifies the interval of time allowed for the service host to open.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f2a62-117">子元素</span><span class="sxs-lookup"><span data-stu-id="f2a62-117">Child Elements</span></span>  
 <span data-ttu-id="f2a62-118">无。</span><span class="sxs-lookup"><span data-stu-id="f2a62-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="f2a62-119">父元素</span><span class="sxs-lookup"><span data-stu-id="f2a62-119">Parent Elements</span></span>  
  
|<span data-ttu-id="f2a62-120">元素</span><span class="sxs-lookup"><span data-stu-id="f2a62-120">Element</span></span>|<span data-ttu-id="f2a62-121">描述</span><span class="sxs-lookup"><span data-stu-id="f2a62-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f2a62-122">\<主机 ></span><span class="sxs-lookup"><span data-stu-id="f2a62-122">\<host></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/host.md)|<span data-ttu-id="f2a62-123">一个指定服务主机设置的配置元素。</span><span class="sxs-lookup"><span data-stu-id="f2a62-123">A configuration element that specifies settings for a service host.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f2a62-124">请参阅</span><span class="sxs-lookup"><span data-stu-id="f2a62-124">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.HostElement>  
 <xref:System.ServiceModel.ServiceHost>  
 [<span data-ttu-id="f2a62-125">承载</span><span class="sxs-lookup"><span data-stu-id="f2a62-125">Hosting</span></span>](../../../../../docs/framework/wcf/feature-details/hosting.md)
