---
title: "&lt;synchronousReceive&gt; 元素"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: cc070387-3d11-4b02-a952-bc08ad2df05a
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 79d78517b62e4476106ff1ed7978c770a17caf2a
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="ltsynchronousreceivegt-element"></a><span data-ttu-id="049d6-102">&lt;synchronousReceive&gt; 元素</span><span class="sxs-lookup"><span data-stu-id="049d6-102">&lt;synchronousReceive&gt; element</span></span>
<span data-ttu-id="049d6-103">此配置元素用于指定服务或客户端应用程序中用来接收消息的运行时行为。</span><span class="sxs-lookup"><span data-stu-id="049d6-103">This configuration element is used to specify run-time behavior for receiving messages in either a service or client application.</span></span> <span data-ttu-id="049d6-104">它不具有任何属性或子元素。</span><span class="sxs-lookup"><span data-stu-id="049d6-104">It does not have any attributes or child elements.</span></span>  
  
 <span data-ttu-id="049d6-105">\<系统。ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="049d6-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="049d6-106">\<行为 ></span><span class="sxs-lookup"><span data-stu-id="049d6-106">\<behaviors></span></span>  
<span data-ttu-id="049d6-107">\<endpointBehaviors ></span><span class="sxs-lookup"><span data-stu-id="049d6-107">\<endpointBehaviors></span></span>  
<span data-ttu-id="049d6-108">\<行为 ></span><span class="sxs-lookup"><span data-stu-id="049d6-108">\<behavior></span></span>  
<span data-ttu-id="049d6-109">\<v e ></span><span class="sxs-lookup"><span data-stu-id="049d6-109">\<synchronousReceive></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="049d6-110">语法</span><span class="sxs-lookup"><span data-stu-id="049d6-110">Syntax</span></span>  
  
```xml  
<synchronousReceive />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="049d6-111">特性和元素</span><span class="sxs-lookup"><span data-stu-id="049d6-111">Attributes and Elements</span></span>  
 <span data-ttu-id="049d6-112">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="049d6-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="049d6-113">特性</span><span class="sxs-lookup"><span data-stu-id="049d6-113">Attributes</span></span>  
 <span data-ttu-id="049d6-114">无。</span><span class="sxs-lookup"><span data-stu-id="049d6-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="049d6-115">子元素</span><span class="sxs-lookup"><span data-stu-id="049d6-115">Child Elements</span></span>  
 <span data-ttu-id="049d6-116">无。</span><span class="sxs-lookup"><span data-stu-id="049d6-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="049d6-117">父元素</span><span class="sxs-lookup"><span data-stu-id="049d6-117">Parent Elements</span></span>  
  
|<span data-ttu-id="049d6-118">元素</span><span class="sxs-lookup"><span data-stu-id="049d6-118">Element</span></span>|<span data-ttu-id="049d6-119">描述</span><span class="sxs-lookup"><span data-stu-id="049d6-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="049d6-120">\<行为 ></span><span class="sxs-lookup"><span data-stu-id="049d6-120">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="049d6-121">指定终结点行为。</span><span class="sxs-lookup"><span data-stu-id="049d6-121">Specifies an endpoint behavior.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="049d6-122">备注</span><span class="sxs-lookup"><span data-stu-id="049d6-122">Remarks</span></span>  
 <span data-ttu-id="049d6-123">使用此行为可指示通道侦听器使用同步接收，而非默认的异步接受。</span><span class="sxs-lookup"><span data-stu-id="049d6-123">Use this behavior to instruct the channel listener to use a synchronous receive rather than the default, asynchronous.</span></span> [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)]<span data-ttu-id="049d6-124"> 发出一个新线程，以为每个接受的通道进行抽取。</span><span class="sxs-lookup"><span data-stu-id="049d6-124"> issues a new thread to pump for each accepted channel.</span></span> <span data-ttu-id="049d6-125">如果有许多通道，则可能出现线程溢出的情况。</span><span class="sxs-lookup"><span data-stu-id="049d6-125">If there are a lot of channels, there is the possibility of running out of threads.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="049d6-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="049d6-126">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.SynchronousReceiveElement>  
 <xref:System.ServiceModel.Description.SynchronousReceiveBehavior>
