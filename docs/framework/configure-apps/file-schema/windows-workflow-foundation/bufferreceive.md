---
title: '&lt;bufferReceive&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: b23c3a54-10d4-4f13-ab6d-98b26b76f22a
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: e0fc3fb901e0f70b616f403b98abc7b9645b2b44
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="ltbufferreceivegt"></a><span data-ttu-id="68d33-102">&lt;bufferReceive&gt;</span><span class="sxs-lookup"><span data-stu-id="68d33-102">&lt;bufferReceive&gt;</span></span>
<span data-ttu-id="68d33-103">一种服务行为，允许服务使用缓冲接收处理，以使工作流服务能够处理无序消息。</span><span class="sxs-lookup"><span data-stu-id="68d33-103">A service behavior that enables a service to use buffered receive processing, which enables a workflow service to process out-of-order messages.</span></span>  
  
<span data-ttu-id="68d33-104">\<系统。ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="68d33-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="68d33-105">\<行为 ></span><span class="sxs-lookup"><span data-stu-id="68d33-105">\<behaviors></span></span>  
<span data-ttu-id="68d33-106">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="68d33-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="68d33-107">\<行为 ></span><span class="sxs-lookup"><span data-stu-id="68d33-107">\<behavior></span></span>  
<span data-ttu-id="68d33-108">\<bufferReceive ></span><span class="sxs-lookup"><span data-stu-id="68d33-108">\<bufferReceive></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="68d33-109">语法</span><span class="sxs-lookup"><span data-stu-id="68d33-109">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <bufferReceive maxPendingMessagesPerChannel="Integer" />
    </behavior>
  </serviceBehaviors>
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="68d33-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="68d33-110">Attributes and Elements</span></span>  
 <span data-ttu-id="68d33-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="68d33-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="68d33-112">特性</span><span class="sxs-lookup"><span data-stu-id="68d33-112">Attributes</span></span>  
  
|<span data-ttu-id="68d33-113">特性</span><span class="sxs-lookup"><span data-stu-id="68d33-113">Attribute</span></span>|<span data-ttu-id="68d33-114">描述</span><span class="sxs-lookup"><span data-stu-id="68d33-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="68d33-115">maxPendingMessagesPerChannel</span><span class="sxs-lookup"><span data-stu-id="68d33-115">maxPendingMessagesPerChannel</span></span>|<span data-ttu-id="68d33-116">一个整数，指定每个通道允许的最大挂起消息数。</span><span class="sxs-lookup"><span data-stu-id="68d33-116">An integer that specifies the maximum number of pending messages allowed for each channel.</span></span> <span data-ttu-id="68d33-117">默认值为 512。</span><span class="sxs-lookup"><span data-stu-id="68d33-117">The default value is 512.</span></span> <span data-ttu-id="68d33-118">此属性限制工作流服务可接收的无序消息数。</span><span class="sxs-lookup"><span data-stu-id="68d33-118">This property limits the number of out-of-order messages that can be received by a workflow service.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="68d33-119">子元素</span><span class="sxs-lookup"><span data-stu-id="68d33-119">Child Elements</span></span>  
 <span data-ttu-id="68d33-120">无。</span><span class="sxs-lookup"><span data-stu-id="68d33-120">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="68d33-121">父元素</span><span class="sxs-lookup"><span data-stu-id="68d33-121">Parent Elements</span></span>  
  
|<span data-ttu-id="68d33-122">元素</span><span class="sxs-lookup"><span data-stu-id="68d33-122">Element</span></span>|<span data-ttu-id="68d33-123">描述</span><span class="sxs-lookup"><span data-stu-id="68d33-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="68d33-124">\<行为 > 的\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="68d33-124">\<behavior> of \<serviceBehaviors></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/behavior-of-servicebehaviors-of-workflow.md)|<span data-ttu-id="68d33-125">指定行为元素。</span><span class="sxs-lookup"><span data-stu-id="68d33-125">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="68d33-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="68d33-126">See Also</span></span>  
<!-- <xref:System.ServiceModel.Activities.Description.BufferReceiveServiceBehavior>  -->
 <xref:System.ServiceModel.Activities.Configuration.BufferedReceiveElement>
