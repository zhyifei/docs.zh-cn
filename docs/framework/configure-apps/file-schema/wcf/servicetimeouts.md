---
title: <serviceTimeouts>
ms.date: 03/30/2017
ms.assetid: ada536cf-97dc-4cd7-89ec-ed1466c1c557
ms.openlocfilehash: 801a7aaf1f0d0fa267fa8cca3d2e7fd02919c475
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/06/2019
ms.locfileid: "70399553"
---
# <a name="servicetimeouts"></a><span data-ttu-id="1feba-101">\<serviceTimeouts></span><span class="sxs-lookup"><span data-stu-id="1feba-101">\<serviceTimeouts></span></span>
<span data-ttu-id="1feba-102">指定服务的超时。</span><span class="sxs-lookup"><span data-stu-id="1feba-102">Specifies the timeout for a service.</span></span>  
  
<span data-ttu-id="1feba-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="1feba-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="1feba-104">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="1feba-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="1feba-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<行为 >** ](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="1feba-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="1feba-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<serviceBehaviors >** ](servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="1feba-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)</span></span>\
<span data-ttu-id="1feba-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<行为 >** ](behavior-of-servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="1feba-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)</span></span>\
<span data-ttu-id="1feba-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<serviceTimeouts >**</span><span class="sxs-lookup"><span data-stu-id="1feba-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<serviceTimeouts>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1feba-109">语法</span><span class="sxs-lookup"><span data-stu-id="1feba-109">Syntax</span></span>  
  
```xml  
<serviceTimeouts transactionTimeout="TimeSpan" />
```  
  
## <a name="type"></a><span data-ttu-id="1feba-110">类型</span><span class="sxs-lookup"><span data-stu-id="1feba-110">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1feba-111">特性和元素</span><span class="sxs-lookup"><span data-stu-id="1feba-111">Attributes and Elements</span></span>  
 <span data-ttu-id="1feba-112">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="1feba-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1feba-113">特性</span><span class="sxs-lookup"><span data-stu-id="1feba-113">Attributes</span></span>  
  
|<span data-ttu-id="1feba-114">特性</span><span class="sxs-lookup"><span data-stu-id="1feba-114">Attribute</span></span>|<span data-ttu-id="1feba-115">描述</span><span class="sxs-lookup"><span data-stu-id="1feba-115">Description</span></span>|  
|---------------|-----------------|  
|`transactionTimeout`|<span data-ttu-id="1feba-116">一个 <xref:System.TimeSpan> 值，指定事务从客户端流动到服务器所必须经历的时间间隔。</span><span class="sxs-lookup"><span data-stu-id="1feba-116">A <xref:System.TimeSpan> value that specifies the interval of time a transaction must flow from client to server.</span></span> <span data-ttu-id="1feba-117">默认值为 "00:00:00"。</span><span class="sxs-lookup"><span data-stu-id="1feba-117">The default is "00:00:00".</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1feba-118">子元素</span><span class="sxs-lookup"><span data-stu-id="1feba-118">Child Elements</span></span>  
 <span data-ttu-id="1feba-119">无。</span><span class="sxs-lookup"><span data-stu-id="1feba-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="1feba-120">父元素</span><span class="sxs-lookup"><span data-stu-id="1feba-120">Parent Elements</span></span>  
  
|<span data-ttu-id="1feba-121">元素</span><span class="sxs-lookup"><span data-stu-id="1feba-121">Element</span></span>|<span data-ttu-id="1feba-122">描述</span><span class="sxs-lookup"><span data-stu-id="1feba-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1feba-123">\<behavior></span><span class="sxs-lookup"><span data-stu-id="1feba-123">\<behavior></span></span>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="1feba-124">指定行为元素。</span><span class="sxs-lookup"><span data-stu-id="1feba-124">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="1feba-125">请参阅</span><span class="sxs-lookup"><span data-stu-id="1feba-125">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServiceTimeoutsElement>
