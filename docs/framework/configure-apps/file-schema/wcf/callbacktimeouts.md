---
title: '&lt;callbackTimeouts&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d7fcfc5f-6d35-491e-8fa6-2f964c1e792f
caps.latest.revision: "8"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: e86b69b7d633fd99728936070e94da964e16de58
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="ltcallbacktimeoutsgt"></a><span data-ttu-id="878b4-102">&lt;callbackTimeouts&gt;</span><span class="sxs-lookup"><span data-stu-id="878b4-102">&lt;callbackTimeouts&gt;</span></span>
<span data-ttu-id="878b4-103">在双工回调协定方案中指定使事务从服务器流动到客户端时的超时值。</span><span class="sxs-lookup"><span data-stu-id="878b4-103">Specifies the timeout value when flowing transactions from server to client.in a duplex callback contract scenario.</span></span>  
  
 <span data-ttu-id="878b4-104">\<系统。ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="878b4-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="878b4-105">\<行为 ></span><span class="sxs-lookup"><span data-stu-id="878b4-105">\<behaviors></span></span>  
<span data-ttu-id="878b4-106">\<endpointBehaviors ></span><span class="sxs-lookup"><span data-stu-id="878b4-106">\<endpointBehaviors></span></span>  
<span data-ttu-id="878b4-107">\<行为 ></span><span class="sxs-lookup"><span data-stu-id="878b4-107">\<behavior></span></span>  
<span data-ttu-id="878b4-108">\<callbackTimeOuts ></span><span class="sxs-lookup"><span data-stu-id="878b4-108">\<callbackTimeOuts></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="878b4-109">语法</span><span class="sxs-lookup"><span data-stu-id="878b4-109">Syntax</span></span>  
  
```xml  
<callbackTimeOuts transactionTimeout="TimeSpan" />  
```  
  
## <a name="type"></a><span data-ttu-id="878b4-110">类型</span><span class="sxs-lookup"><span data-stu-id="878b4-110">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="878b4-111">特性和元素</span><span class="sxs-lookup"><span data-stu-id="878b4-111">Attributes and Elements</span></span>  
 <span data-ttu-id="878b4-112">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="878b4-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="878b4-113">特性</span><span class="sxs-lookup"><span data-stu-id="878b4-113">Attributes</span></span>  
  
|<span data-ttu-id="878b4-114">特性</span><span class="sxs-lookup"><span data-stu-id="878b4-114">Attribute</span></span>|<span data-ttu-id="878b4-115">描述</span><span class="sxs-lookup"><span data-stu-id="878b4-115">Description</span></span>|  
|---------------|-----------------|  
|`transactionTimeout`|<span data-ttu-id="878b4-116">一个 <xref:System.TimeSpan> 值，指定时间间隔，事务必须在此期间完成，否则会自动终止。</span><span class="sxs-lookup"><span data-stu-id="878b4-116">A <xref:System.TimeSpan> value that specifies the interval of time within which transactions must complete or be automatically terminated.</span></span> <span data-ttu-id="878b4-117">默认值为"00: 00:00"。</span><span class="sxs-lookup"><span data-stu-id="878b4-117">The default is "00:00:00".</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="878b4-118">子元素</span><span class="sxs-lookup"><span data-stu-id="878b4-118">Child Elements</span></span>  
 <span data-ttu-id="878b4-119">无。</span><span class="sxs-lookup"><span data-stu-id="878b4-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="878b4-120">父元素</span><span class="sxs-lookup"><span data-stu-id="878b4-120">Parent Elements</span></span>  
  
|<span data-ttu-id="878b4-121">元素</span><span class="sxs-lookup"><span data-stu-id="878b4-121">Element</span></span>|<span data-ttu-id="878b4-122">描述</span><span class="sxs-lookup"><span data-stu-id="878b4-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="878b4-123">\<行为 ></span><span class="sxs-lookup"><span data-stu-id="878b4-123">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="878b4-124">指定终结点行为。</span><span class="sxs-lookup"><span data-stu-id="878b4-124">Specifies an endpoint behavior.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="878b4-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="878b4-125">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.CallbackTimeoutsElement>
