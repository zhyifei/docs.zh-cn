---
title: '&lt;serviceTimeouts&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ada536cf-97dc-4cd7-89ec-ed1466c1c557
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: f6d2940a4c4615a922efcc74802a82adbe10267c
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="ltservicetimeoutsgt"></a><span data-ttu-id="73ddb-102">&lt;serviceTimeouts&gt;</span><span class="sxs-lookup"><span data-stu-id="73ddb-102">&lt;serviceTimeouts&gt;</span></span>
<span data-ttu-id="73ddb-103">指定服务的超时。</span><span class="sxs-lookup"><span data-stu-id="73ddb-103">Specifies the timeout for a service.</span></span>  
  
 <span data-ttu-id="73ddb-104">\<系统。ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="73ddb-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="73ddb-105">\<行为 ></span><span class="sxs-lookup"><span data-stu-id="73ddb-105">\<behaviors></span></span>  
<span data-ttu-id="73ddb-106">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="73ddb-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="73ddb-107">\<行为 ></span><span class="sxs-lookup"><span data-stu-id="73ddb-107">\<behavior></span></span>  
<span data-ttu-id="73ddb-108">\<serviceTimeouts ></span><span class="sxs-lookup"><span data-stu-id="73ddb-108">\<serviceTimeouts></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="73ddb-109">语法</span><span class="sxs-lookup"><span data-stu-id="73ddb-109">Syntax</span></span>  
  
```xml  
<serviceTimeouts transactionTimeout="TimeSpan" />  
```  
  
## <a name="type"></a><span data-ttu-id="73ddb-110">类型</span><span class="sxs-lookup"><span data-stu-id="73ddb-110">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="73ddb-111">特性和元素</span><span class="sxs-lookup"><span data-stu-id="73ddb-111">Attributes and Elements</span></span>  
 <span data-ttu-id="73ddb-112">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="73ddb-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="73ddb-113">特性</span><span class="sxs-lookup"><span data-stu-id="73ddb-113">Attributes</span></span>  
  
|<span data-ttu-id="73ddb-114">特性</span><span class="sxs-lookup"><span data-stu-id="73ddb-114">Attribute</span></span>|<span data-ttu-id="73ddb-115">描述</span><span class="sxs-lookup"><span data-stu-id="73ddb-115">Description</span></span>|  
|---------------|-----------------|  
|`transactionTimeout`|<span data-ttu-id="73ddb-116">一个 <xref:System.TimeSpan> 值，指定事务从客户端流动到服务器所必须经历的时间间隔。</span><span class="sxs-lookup"><span data-stu-id="73ddb-116">A <xref:System.TimeSpan> value that specifies the interval of time a transaction must flow from client to server.</span></span> <span data-ttu-id="73ddb-117">默认值为"00: 00:00"。</span><span class="sxs-lookup"><span data-stu-id="73ddb-117">The default is "00:00:00".</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="73ddb-118">子元素</span><span class="sxs-lookup"><span data-stu-id="73ddb-118">Child Elements</span></span>  
 <span data-ttu-id="73ddb-119">无。</span><span class="sxs-lookup"><span data-stu-id="73ddb-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="73ddb-120">父元素</span><span class="sxs-lookup"><span data-stu-id="73ddb-120">Parent Elements</span></span>  
  
|<span data-ttu-id="73ddb-121">元素</span><span class="sxs-lookup"><span data-stu-id="73ddb-121">Element</span></span>|<span data-ttu-id="73ddb-122">描述</span><span class="sxs-lookup"><span data-stu-id="73ddb-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="73ddb-123">\<行为 ></span><span class="sxs-lookup"><span data-stu-id="73ddb-123">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="73ddb-124">指定行为元素。</span><span class="sxs-lookup"><span data-stu-id="73ddb-124">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="73ddb-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="73ddb-125">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.ServiceTimeoutsElement>
