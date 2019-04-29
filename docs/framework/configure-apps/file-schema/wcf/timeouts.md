---
title: <timeOuts>
ms.date: 03/30/2017
ms.assetid: 7fccd436-b326-48ec-8de1-c16817a09e0d
ms.openlocfilehash: b6ae5faa2dd2ffef9669a0245a75227b0f669cf7
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61758218"
---
# <a name="timeouts"></a><span data-ttu-id="a3a9a-101">\<timeOuts></span><span class="sxs-lookup"><span data-stu-id="a3a9a-101">\<timeOuts></span></span>
<span data-ttu-id="a3a9a-102">表示一个配置元素，该元素指定允许服务主机打开或关闭的时间间隔。</span><span class="sxs-lookup"><span data-stu-id="a3a9a-102">Represents a configuration element that specifies the interval of time allowed for the service host to open or close.</span></span>  
  
 <span data-ttu-id="a3a9a-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="a3a9a-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="a3a9a-104">\<client></span><span class="sxs-lookup"><span data-stu-id="a3a9a-104">\<client></span></span>  
<span data-ttu-id="a3a9a-105">\<endpoint></span><span class="sxs-lookup"><span data-stu-id="a3a9a-105">\<endpoint></span></span>  
<span data-ttu-id="a3a9a-106">\<host></span><span class="sxs-lookup"><span data-stu-id="a3a9a-106">\<host></span></span>  
<span data-ttu-id="a3a9a-107">\<timeOuts></span><span class="sxs-lookup"><span data-stu-id="a3a9a-107">\<timeOuts></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a3a9a-108">语法</span><span class="sxs-lookup"><span data-stu-id="a3a9a-108">Syntax</span></span>  
  
```xml  
<timeOuts closeTimeout="TimeSpan"
          openTimeout="TimeSpan" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a3a9a-109">特性和元素</span><span class="sxs-lookup"><span data-stu-id="a3a9a-109">Attributes and Elements</span></span>  
 <span data-ttu-id="a3a9a-110">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="a3a9a-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a3a9a-111">特性</span><span class="sxs-lookup"><span data-stu-id="a3a9a-111">Attributes</span></span>  
  
|<span data-ttu-id="a3a9a-112">特性</span><span class="sxs-lookup"><span data-stu-id="a3a9a-112">Attribute</span></span>|<span data-ttu-id="a3a9a-113">描述</span><span class="sxs-lookup"><span data-stu-id="a3a9a-113">Description</span></span>|  
|---------------|-----------------|  
|`closeTimeout`|<span data-ttu-id="a3a9a-114">一个 <xref:System.TimeSpan> 值，指定为关闭服务主机预留的时间间隔。</span><span class="sxs-lookup"><span data-stu-id="a3a9a-114">A <xref:System.TimeSpan> value that specifies the interval of time allowed for the service host to close.</span></span>|  
|`openTimeout`|<span data-ttu-id="a3a9a-115">一个 <xref:System.TimeSpan> 值，指定为打开或关闭服务主机预留的时间间隔。</span><span class="sxs-lookup"><span data-stu-id="a3a9a-115">A <xref:System.TimeSpan> value that specifies the interval of time allowed for the service host to open.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a3a9a-116">子元素</span><span class="sxs-lookup"><span data-stu-id="a3a9a-116">Child Elements</span></span>  
 <span data-ttu-id="a3a9a-117">无。</span><span class="sxs-lookup"><span data-stu-id="a3a9a-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a3a9a-118">父元素</span><span class="sxs-lookup"><span data-stu-id="a3a9a-118">Parent Elements</span></span>  
  
|<span data-ttu-id="a3a9a-119">元素</span><span class="sxs-lookup"><span data-stu-id="a3a9a-119">Element</span></span>|<span data-ttu-id="a3a9a-120">描述</span><span class="sxs-lookup"><span data-stu-id="a3a9a-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a3a9a-121">\<host></span><span class="sxs-lookup"><span data-stu-id="a3a9a-121">\<host></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/host.md)|<span data-ttu-id="a3a9a-122">一个指定服务主机设置的配置元素。</span><span class="sxs-lookup"><span data-stu-id="a3a9a-122">A configuration element that specifies settings for a service host.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a3a9a-123">请参阅</span><span class="sxs-lookup"><span data-stu-id="a3a9a-123">See also</span></span>

- <xref:System.ServiceModel.Configuration.HostElement>
- <xref:System.ServiceModel.ServiceHost>
- [<span data-ttu-id="a3a9a-124">承载</span><span class="sxs-lookup"><span data-stu-id="a3a9a-124">Hosting</span></span>](../../../../../docs/framework/wcf/feature-details/hosting.md)
