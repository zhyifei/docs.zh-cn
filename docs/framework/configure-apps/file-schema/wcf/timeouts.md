---
title: <timeOuts>
ms.date: 03/30/2017
ms.assetid: 7fccd436-b326-48ec-8de1-c16817a09e0d
ms.openlocfilehash: b6ae5faa2dd2ffef9669a0245a75227b0f669cf7
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59118061"
---
# <a name="timeouts"></a><span data-ttu-id="59607-101">\<timeOuts></span><span class="sxs-lookup"><span data-stu-id="59607-101">\<timeOuts></span></span>
<span data-ttu-id="59607-102">表示一个配置元素，该元素指定允许服务主机打开或关闭的时间间隔。</span><span class="sxs-lookup"><span data-stu-id="59607-102">Represents a configuration element that specifies the interval of time allowed for the service host to open or close.</span></span>  
  
 <span data-ttu-id="59607-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="59607-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="59607-104">\<client></span><span class="sxs-lookup"><span data-stu-id="59607-104">\<client></span></span>  
<span data-ttu-id="59607-105">\<endpoint></span><span class="sxs-lookup"><span data-stu-id="59607-105">\<endpoint></span></span>  
<span data-ttu-id="59607-106">\<host></span><span class="sxs-lookup"><span data-stu-id="59607-106">\<host></span></span>  
<span data-ttu-id="59607-107">\<timeOuts></span><span class="sxs-lookup"><span data-stu-id="59607-107">\<timeOuts></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="59607-108">语法</span><span class="sxs-lookup"><span data-stu-id="59607-108">Syntax</span></span>  
  
```xml  
<timeOuts closeTimeout="TimeSpan"
          openTimeout="TimeSpan" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="59607-109">特性和元素</span><span class="sxs-lookup"><span data-stu-id="59607-109">Attributes and Elements</span></span>  
 <span data-ttu-id="59607-110">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="59607-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="59607-111">特性</span><span class="sxs-lookup"><span data-stu-id="59607-111">Attributes</span></span>  
  
|<span data-ttu-id="59607-112">特性</span><span class="sxs-lookup"><span data-stu-id="59607-112">Attribute</span></span>|<span data-ttu-id="59607-113">描述</span><span class="sxs-lookup"><span data-stu-id="59607-113">Description</span></span>|  
|---------------|-----------------|  
|`closeTimeout`|<span data-ttu-id="59607-114">一个 <xref:System.TimeSpan> 值，指定为关闭服务主机预留的时间间隔。</span><span class="sxs-lookup"><span data-stu-id="59607-114">A <xref:System.TimeSpan> value that specifies the interval of time allowed for the service host to close.</span></span>|  
|`openTimeout`|<span data-ttu-id="59607-115">一个 <xref:System.TimeSpan> 值，指定为打开或关闭服务主机预留的时间间隔。</span><span class="sxs-lookup"><span data-stu-id="59607-115">A <xref:System.TimeSpan> value that specifies the interval of time allowed for the service host to open.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="59607-116">子元素</span><span class="sxs-lookup"><span data-stu-id="59607-116">Child Elements</span></span>  
 <span data-ttu-id="59607-117">无。</span><span class="sxs-lookup"><span data-stu-id="59607-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="59607-118">父元素</span><span class="sxs-lookup"><span data-stu-id="59607-118">Parent Elements</span></span>  
  
|<span data-ttu-id="59607-119">元素</span><span class="sxs-lookup"><span data-stu-id="59607-119">Element</span></span>|<span data-ttu-id="59607-120">描述</span><span class="sxs-lookup"><span data-stu-id="59607-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="59607-121">\<host></span><span class="sxs-lookup"><span data-stu-id="59607-121">\<host></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/host.md)|<span data-ttu-id="59607-122">一个指定服务主机设置的配置元素。</span><span class="sxs-lookup"><span data-stu-id="59607-122">A configuration element that specifies settings for a service host.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="59607-123">请参阅</span><span class="sxs-lookup"><span data-stu-id="59607-123">See also</span></span>

- <xref:System.ServiceModel.Configuration.HostElement>
- <xref:System.ServiceModel.ServiceHost>
- [<span data-ttu-id="59607-124">宿主</span><span class="sxs-lookup"><span data-stu-id="59607-124">Hosting</span></span>](../../../../../docs/framework/wcf/feature-details/hosting.md)
