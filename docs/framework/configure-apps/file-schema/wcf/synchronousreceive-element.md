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
ms.workload: dotnet
ms.openlocfilehash: 63923121ae96b85bd192899a8d8ad285a3ad5b2d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="ltsynchronousreceivegt-element"></a><span data-ttu-id="6af5b-102">&lt;synchronousReceive&gt; 元素</span><span class="sxs-lookup"><span data-stu-id="6af5b-102">&lt;synchronousReceive&gt; element</span></span>
<span data-ttu-id="6af5b-103">此配置元素用于指定服务或客户端应用程序中用来接收消息的运行时行为。</span><span class="sxs-lookup"><span data-stu-id="6af5b-103">This configuration element is used to specify run-time behavior for receiving messages in either a service or client application.</span></span> <span data-ttu-id="6af5b-104">它不具有任何属性或子元素。</span><span class="sxs-lookup"><span data-stu-id="6af5b-104">It does not have any attributes or child elements.</span></span>  
  
 <span data-ttu-id="6af5b-105">\<系统。ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="6af5b-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="6af5b-106">\<行为 ></span><span class="sxs-lookup"><span data-stu-id="6af5b-106">\<behaviors></span></span>  
<span data-ttu-id="6af5b-107">\<endpointBehaviors ></span><span class="sxs-lookup"><span data-stu-id="6af5b-107">\<endpointBehaviors></span></span>  
<span data-ttu-id="6af5b-108">\<行为 ></span><span class="sxs-lookup"><span data-stu-id="6af5b-108">\<behavior></span></span>  
<span data-ttu-id="6af5b-109">\<v e ></span><span class="sxs-lookup"><span data-stu-id="6af5b-109">\<synchronousReceive></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6af5b-110">语法</span><span class="sxs-lookup"><span data-stu-id="6af5b-110">Syntax</span></span>  
  
```xml  
<synchronousReceive />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6af5b-111">特性和元素</span><span class="sxs-lookup"><span data-stu-id="6af5b-111">Attributes and Elements</span></span>  
 <span data-ttu-id="6af5b-112">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="6af5b-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6af5b-113">特性</span><span class="sxs-lookup"><span data-stu-id="6af5b-113">Attributes</span></span>  
 <span data-ttu-id="6af5b-114">无。</span><span class="sxs-lookup"><span data-stu-id="6af5b-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="6af5b-115">子元素</span><span class="sxs-lookup"><span data-stu-id="6af5b-115">Child Elements</span></span>  
 <span data-ttu-id="6af5b-116">无。</span><span class="sxs-lookup"><span data-stu-id="6af5b-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="6af5b-117">父元素</span><span class="sxs-lookup"><span data-stu-id="6af5b-117">Parent Elements</span></span>  
  
|<span data-ttu-id="6af5b-118">元素</span><span class="sxs-lookup"><span data-stu-id="6af5b-118">Element</span></span>|<span data-ttu-id="6af5b-119">描述</span><span class="sxs-lookup"><span data-stu-id="6af5b-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6af5b-120">\<行为 ></span><span class="sxs-lookup"><span data-stu-id="6af5b-120">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="6af5b-121">指定终结点行为。</span><span class="sxs-lookup"><span data-stu-id="6af5b-121">Specifies an endpoint behavior.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6af5b-122">备注</span><span class="sxs-lookup"><span data-stu-id="6af5b-122">Remarks</span></span>  
 <span data-ttu-id="6af5b-123">使用此行为可指示通道侦听器使用同步接收，而非默认的异步接受。</span><span class="sxs-lookup"><span data-stu-id="6af5b-123">Use this behavior to instruct the channel listener to use a synchronous receive rather than the default, asynchronous.</span></span> [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)]<span data-ttu-id="6af5b-124"> 发出一个新线程，以为每个接受的通道进行抽取。</span><span class="sxs-lookup"><span data-stu-id="6af5b-124"> issues a new thread to pump for each accepted channel.</span></span> <span data-ttu-id="6af5b-125">如果有许多通道，则可能出现线程溢出的情况。</span><span class="sxs-lookup"><span data-stu-id="6af5b-125">If there are a lot of channels, there is the possibility of running out of threads.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6af5b-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="6af5b-126">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.SynchronousReceiveElement>  
 <xref:System.ServiceModel.Description.SynchronousReceiveBehavior>
