---
title: '&lt;timeOuts&gt;'
ms.date: 03/30/2017
ms.assetid: 7fccd436-b326-48ec-8de1-c16817a09e0d
ms.openlocfilehash: 42f4db1d954834cbfa3c526328cca45443751506
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54629652"
---
# <a name="lttimeoutsgt"></a><span data-ttu-id="32038-102">&lt;timeOuts&gt;</span><span class="sxs-lookup"><span data-stu-id="32038-102">&lt;timeOuts&gt;</span></span>
<span data-ttu-id="32038-103">表示一个配置元素，该元素指定允许服务主机打开或关闭的时间间隔。</span><span class="sxs-lookup"><span data-stu-id="32038-103">Represents a configuration element that specifies the interval of time allowed for the service host to open or close.</span></span>  
  
 <span data-ttu-id="32038-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="32038-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="32038-105">\<client></span><span class="sxs-lookup"><span data-stu-id="32038-105">\<client></span></span>  
<span data-ttu-id="32038-106">\<endpoint></span><span class="sxs-lookup"><span data-stu-id="32038-106">\<endpoint></span></span>  
<span data-ttu-id="32038-107">\<host></span><span class="sxs-lookup"><span data-stu-id="32038-107">\<host></span></span>  
<span data-ttu-id="32038-108">\<timeOuts></span><span class="sxs-lookup"><span data-stu-id="32038-108">\<timeOuts></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="32038-109">语法</span><span class="sxs-lookup"><span data-stu-id="32038-109">Syntax</span></span>  
  
```xml  
<timeOuts closeTimeout="TimeSpan"
          openTimeout="TimeSpan" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="32038-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="32038-110">Attributes and Elements</span></span>  
 <span data-ttu-id="32038-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="32038-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="32038-112">特性</span><span class="sxs-lookup"><span data-stu-id="32038-112">Attributes</span></span>  
  
|<span data-ttu-id="32038-113">特性</span><span class="sxs-lookup"><span data-stu-id="32038-113">Attribute</span></span>|<span data-ttu-id="32038-114">描述</span><span class="sxs-lookup"><span data-stu-id="32038-114">Description</span></span>|  
|---------------|-----------------|  
|`closeTimeout`|<span data-ttu-id="32038-115">一个 <xref:System.TimeSpan> 值，指定为关闭服务主机预留的时间间隔。</span><span class="sxs-lookup"><span data-stu-id="32038-115">A <xref:System.TimeSpan> value that specifies the interval of time allowed for the service host to close.</span></span>|  
|`openTimeout`|<span data-ttu-id="32038-116">一个 <xref:System.TimeSpan> 值，指定为打开或关闭服务主机预留的时间间隔。</span><span class="sxs-lookup"><span data-stu-id="32038-116">A <xref:System.TimeSpan> value that specifies the interval of time allowed for the service host to open.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="32038-117">子元素</span><span class="sxs-lookup"><span data-stu-id="32038-117">Child Elements</span></span>  
 <span data-ttu-id="32038-118">无。</span><span class="sxs-lookup"><span data-stu-id="32038-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="32038-119">父元素</span><span class="sxs-lookup"><span data-stu-id="32038-119">Parent Elements</span></span>  
  
|<span data-ttu-id="32038-120">元素</span><span class="sxs-lookup"><span data-stu-id="32038-120">Element</span></span>|<span data-ttu-id="32038-121">描述</span><span class="sxs-lookup"><span data-stu-id="32038-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="32038-122">\<host></span><span class="sxs-lookup"><span data-stu-id="32038-122">\<host></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/host.md)|<span data-ttu-id="32038-123">一个指定服务主机设置的配置元素。</span><span class="sxs-lookup"><span data-stu-id="32038-123">A configuration element that specifies settings for a service host.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="32038-124">请参阅</span><span class="sxs-lookup"><span data-stu-id="32038-124">See also</span></span>
- <xref:System.ServiceModel.Configuration.HostElement>
- <xref:System.ServiceModel.ServiceHost>
- [<span data-ttu-id="32038-125">承载</span><span class="sxs-lookup"><span data-stu-id="32038-125">Hosting</span></span>](../../../../../docs/framework/wcf/feature-details/hosting.md)
