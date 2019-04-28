---
title: <synchronousReceive> 元素
ms.date: 03/30/2017
ms.assetid: cc070387-3d11-4b02-a952-bc08ad2df05a
ms.openlocfilehash: 20390f747c8beaccba1cfea7a9ea0ed366037ecb
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61757919"
---
# <a name="synchronousreceive-element"></a><span data-ttu-id="4e8d1-102">\<synchronousReceive > 元素</span><span class="sxs-lookup"><span data-stu-id="4e8d1-102">\<synchronousReceive> element</span></span>
<span data-ttu-id="4e8d1-103">此配置元素用于指定服务或客户端应用程序中用来接收消息的运行时行为。</span><span class="sxs-lookup"><span data-stu-id="4e8d1-103">This configuration element is used to specify run-time behavior for receiving messages in either a service or client application.</span></span> <span data-ttu-id="4e8d1-104">它不具有任何属性或子元素。</span><span class="sxs-lookup"><span data-stu-id="4e8d1-104">It does not have any attributes or child elements.</span></span>  
  
 <span data-ttu-id="4e8d1-105">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="4e8d1-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="4e8d1-106">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="4e8d1-106">\<behaviors></span></span>  
<span data-ttu-id="4e8d1-107">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="4e8d1-107">\<endpointBehaviors></span></span>  
<span data-ttu-id="4e8d1-108">\<behavior></span><span class="sxs-lookup"><span data-stu-id="4e8d1-108">\<behavior></span></span>  
<span data-ttu-id="4e8d1-109">\<synchronousReceive></span><span class="sxs-lookup"><span data-stu-id="4e8d1-109">\<synchronousReceive></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4e8d1-110">语法</span><span class="sxs-lookup"><span data-stu-id="4e8d1-110">Syntax</span></span>  
  
```xml  
<synchronousReceive />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4e8d1-111">特性和元素</span><span class="sxs-lookup"><span data-stu-id="4e8d1-111">Attributes and Elements</span></span>  
 <span data-ttu-id="4e8d1-112">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="4e8d1-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4e8d1-113">特性</span><span class="sxs-lookup"><span data-stu-id="4e8d1-113">Attributes</span></span>  
 <span data-ttu-id="4e8d1-114">无。</span><span class="sxs-lookup"><span data-stu-id="4e8d1-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="4e8d1-115">子元素</span><span class="sxs-lookup"><span data-stu-id="4e8d1-115">Child Elements</span></span>  
 <span data-ttu-id="4e8d1-116">无。</span><span class="sxs-lookup"><span data-stu-id="4e8d1-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="4e8d1-117">父元素</span><span class="sxs-lookup"><span data-stu-id="4e8d1-117">Parent Elements</span></span>  
  
|<span data-ttu-id="4e8d1-118">元素</span><span class="sxs-lookup"><span data-stu-id="4e8d1-118">Element</span></span>|<span data-ttu-id="4e8d1-119">描述</span><span class="sxs-lookup"><span data-stu-id="4e8d1-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4e8d1-120">\<behavior></span><span class="sxs-lookup"><span data-stu-id="4e8d1-120">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="4e8d1-121">指定终结点行为。</span><span class="sxs-lookup"><span data-stu-id="4e8d1-121">Specifies an endpoint behavior.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4e8d1-122">备注</span><span class="sxs-lookup"><span data-stu-id="4e8d1-122">Remarks</span></span>  
 <span data-ttu-id="4e8d1-123">使用此行为可指示通道侦听器使用同步接收，而非默认的异步接受。</span><span class="sxs-lookup"><span data-stu-id="4e8d1-123">Use this behavior to instruct the channel listener to use a synchronous receive rather than the default, asynchronous.</span></span> <span data-ttu-id="4e8d1-124">Windows Communication Foundation (WCF) 发出一个新线程，以为每个接受通道进行抽取。</span><span class="sxs-lookup"><span data-stu-id="4e8d1-124">Windows Communication Foundation (WCF) issues a new thread to pump for each accepted channel.</span></span> <span data-ttu-id="4e8d1-125">如果有许多通道，则可能出现线程溢出的情况。</span><span class="sxs-lookup"><span data-stu-id="4e8d1-125">If there are a lot of channels, there is the possibility of running out of threads.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4e8d1-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="4e8d1-126">See also</span></span>

- <xref:System.ServiceModel.Configuration.SynchronousReceiveElement>
- <xref:System.ServiceModel.Description.SynchronousReceiveBehavior>
