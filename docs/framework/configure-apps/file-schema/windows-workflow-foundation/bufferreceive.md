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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 623ff924e171282c399bddcdc212a0606a3416d6
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="ltbufferreceivegt"></a><span data-ttu-id="5e07e-102">&lt;bufferReceive&gt;</span><span class="sxs-lookup"><span data-stu-id="5e07e-102">&lt;bufferReceive&gt;</span></span>
<span data-ttu-id="5e07e-103">一种服务行为，允许服务使用缓冲接收处理，以使工作流服务能够处理无序消息。</span><span class="sxs-lookup"><span data-stu-id="5e07e-103">A service behavior that enables a service to use buffered receive processing, which enables a workflow service to process out-of-order messages.</span></span>  
  
<span data-ttu-id="5e07e-104">\<系统。ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="5e07e-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="5e07e-105">\<行为 ></span><span class="sxs-lookup"><span data-stu-id="5e07e-105">\<behaviors></span></span>  
<span data-ttu-id="5e07e-106">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="5e07e-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="5e07e-107">\<行为 ></span><span class="sxs-lookup"><span data-stu-id="5e07e-107">\<behavior></span></span>  
<span data-ttu-id="5e07e-108">\<bufferReceive ></span><span class="sxs-lookup"><span data-stu-id="5e07e-108">\<bufferReceive></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5e07e-109">语法</span><span class="sxs-lookup"><span data-stu-id="5e07e-109">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <bufferReceive maxPendingMessagesPerChannel="Integer" />
    </behavior>
  </serviceBehaviors>
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5e07e-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="5e07e-110">Attributes and Elements</span></span>  
 <span data-ttu-id="5e07e-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="5e07e-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5e07e-112">特性</span><span class="sxs-lookup"><span data-stu-id="5e07e-112">Attributes</span></span>  
  
|<span data-ttu-id="5e07e-113">特性</span><span class="sxs-lookup"><span data-stu-id="5e07e-113">Attribute</span></span>|<span data-ttu-id="5e07e-114">描述</span><span class="sxs-lookup"><span data-stu-id="5e07e-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="5e07e-115">maxPendingMessagesPerChannel</span><span class="sxs-lookup"><span data-stu-id="5e07e-115">maxPendingMessagesPerChannel</span></span>|<span data-ttu-id="5e07e-116">一个整数，指定每个通道允许的最大挂起消息数。</span><span class="sxs-lookup"><span data-stu-id="5e07e-116">An integer that specifies the maximum number of pending messages allowed for each channel.</span></span> <span data-ttu-id="5e07e-117">默认值为 512。</span><span class="sxs-lookup"><span data-stu-id="5e07e-117">The default value is 512.</span></span> <span data-ttu-id="5e07e-118">此属性限制工作流服务可接收的无序消息数。</span><span class="sxs-lookup"><span data-stu-id="5e07e-118">This property limits the number of out-of-order messages that can be received by a workflow service.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="5e07e-119">子元素</span><span class="sxs-lookup"><span data-stu-id="5e07e-119">Child Elements</span></span>  
 <span data-ttu-id="5e07e-120">无。</span><span class="sxs-lookup"><span data-stu-id="5e07e-120">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="5e07e-121">父元素</span><span class="sxs-lookup"><span data-stu-id="5e07e-121">Parent Elements</span></span>  
  
|<span data-ttu-id="5e07e-122">元素</span><span class="sxs-lookup"><span data-stu-id="5e07e-122">Element</span></span>|<span data-ttu-id="5e07e-123">描述</span><span class="sxs-lookup"><span data-stu-id="5e07e-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5e07e-124">\<行为 > 的\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="5e07e-124">\<behavior> of \<serviceBehaviors></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/behavior-of-servicebehaviors-of-workflow.md)|<span data-ttu-id="5e07e-125">指定行为元素。</span><span class="sxs-lookup"><span data-stu-id="5e07e-125">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="5e07e-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5e07e-126">See Also</span></span>  
<!-- <xref:System.ServiceModel.Activities.Description.BufferReceiveServiceBehavior>  -->
 <xref:System.ServiceModel.Activities.Configuration.BufferedReceiveElement>
