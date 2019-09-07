---
title: <synchronousReceive> 元素
ms.date: 03/30/2017
ms.assetid: cc070387-3d11-4b02-a952-bc08ad2df05a
ms.openlocfilehash: b3f4860be6b7edac776a1c30611271b2eb36968e
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/06/2019
ms.locfileid: "70399499"
---
# <a name="synchronousreceive-element"></a><span data-ttu-id="6338e-102">\<synchronousReceive > 元素</span><span class="sxs-lookup"><span data-stu-id="6338e-102">\<synchronousReceive> element</span></span>
<span data-ttu-id="6338e-103">此配置元素用于指定服务或客户端应用程序中用来接收消息的运行时行为。</span><span class="sxs-lookup"><span data-stu-id="6338e-103">This configuration element is used to specify run-time behavior for receiving messages in either a service or client application.</span></span> <span data-ttu-id="6338e-104">它不具有任何属性或子元素。</span><span class="sxs-lookup"><span data-stu-id="6338e-104">It does not have any attributes or child elements.</span></span>  
  
<span data-ttu-id="6338e-105">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="6338e-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="6338e-106">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="6338e-106">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="6338e-107">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<行为 >** ](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="6338e-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="6338e-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<endpointBehaviors >** ](endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="6338e-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)</span></span>\
<span data-ttu-id="6338e-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<行为 >** ](behavior-of-endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="6338e-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)</span></span>\
<span data-ttu-id="6338e-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<synchronousReceive >**</span><span class="sxs-lookup"><span data-stu-id="6338e-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<synchronousReceive>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6338e-111">语法</span><span class="sxs-lookup"><span data-stu-id="6338e-111">Syntax</span></span>  
  
```xml  
<synchronousReceive />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6338e-112">特性和元素</span><span class="sxs-lookup"><span data-stu-id="6338e-112">Attributes and Elements</span></span>  
 <span data-ttu-id="6338e-113">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="6338e-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6338e-114">特性</span><span class="sxs-lookup"><span data-stu-id="6338e-114">Attributes</span></span>  
 <span data-ttu-id="6338e-115">无。</span><span class="sxs-lookup"><span data-stu-id="6338e-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="6338e-116">子元素</span><span class="sxs-lookup"><span data-stu-id="6338e-116">Child Elements</span></span>  
 <span data-ttu-id="6338e-117">无。</span><span class="sxs-lookup"><span data-stu-id="6338e-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="6338e-118">父元素</span><span class="sxs-lookup"><span data-stu-id="6338e-118">Parent Elements</span></span>  
  
|<span data-ttu-id="6338e-119">元素</span><span class="sxs-lookup"><span data-stu-id="6338e-119">Element</span></span>|<span data-ttu-id="6338e-120">描述</span><span class="sxs-lookup"><span data-stu-id="6338e-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6338e-121">\<behavior></span><span class="sxs-lookup"><span data-stu-id="6338e-121">\<behavior></span></span>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="6338e-122">指定终结点行为。</span><span class="sxs-lookup"><span data-stu-id="6338e-122">Specifies an endpoint behavior.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6338e-123">备注</span><span class="sxs-lookup"><span data-stu-id="6338e-123">Remarks</span></span>  
 <span data-ttu-id="6338e-124">使用此行为可指示通道侦听器使用同步接收，而非默认的异步接受。</span><span class="sxs-lookup"><span data-stu-id="6338e-124">Use this behavior to instruct the channel listener to use a synchronous receive rather than the default, asynchronous.</span></span> <span data-ttu-id="6338e-125">Windows Communication Foundation （WCF）为每个接受的通道发出一个新线程来泵。</span><span class="sxs-lookup"><span data-stu-id="6338e-125">Windows Communication Foundation (WCF) issues a new thread to pump for each accepted channel.</span></span> <span data-ttu-id="6338e-126">如果有许多通道，则可能出现线程溢出的情况。</span><span class="sxs-lookup"><span data-stu-id="6338e-126">If there are a lot of channels, there is the possibility of running out of threads.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6338e-127">请参阅</span><span class="sxs-lookup"><span data-stu-id="6338e-127">See also</span></span>

- <xref:System.ServiceModel.Configuration.SynchronousReceiveElement>
- <xref:System.ServiceModel.Description.SynchronousReceiveBehavior>
