---
title: '&lt;bufferReceive&gt;'
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: b23c3a54-10d4-4f13-ab6d-98b26b76f22a
ms.openlocfilehash: 07d5b66b14d9495808f972734cdce4476efaefde
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
ms.locfileid: "32766831"
---
# <a name="ltbufferreceivegt"></a><span data-ttu-id="b488f-102">&lt;bufferReceive&gt;</span><span class="sxs-lookup"><span data-stu-id="b488f-102">&lt;bufferReceive&gt;</span></span>
<span data-ttu-id="b488f-103">一种服务行为，允许服务使用缓冲接收处理，以使工作流服务能够处理无序消息。</span><span class="sxs-lookup"><span data-stu-id="b488f-103">A service behavior that enables a service to use buffered receive processing, which enables a workflow service to process out-of-order messages.</span></span>  
  
<span data-ttu-id="b488f-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="b488f-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="b488f-105">\<行为 ></span><span class="sxs-lookup"><span data-stu-id="b488f-105">\<behaviors></span></span>  
<span data-ttu-id="b488f-106">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="b488f-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="b488f-107">\<行为 ></span><span class="sxs-lookup"><span data-stu-id="b488f-107">\<behavior></span></span>  
<span data-ttu-id="b488f-108">\<bufferReceive ></span><span class="sxs-lookup"><span data-stu-id="b488f-108">\<bufferReceive></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b488f-109">语法</span><span class="sxs-lookup"><span data-stu-id="b488f-109">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <bufferReceive maxPendingMessagesPerChannel="Integer" />
    </behavior>
  </serviceBehaviors>
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b488f-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="b488f-110">Attributes and Elements</span></span>  
 <span data-ttu-id="b488f-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="b488f-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b488f-112">特性</span><span class="sxs-lookup"><span data-stu-id="b488f-112">Attributes</span></span>  
  
|<span data-ttu-id="b488f-113">特性</span><span class="sxs-lookup"><span data-stu-id="b488f-113">Attribute</span></span>|<span data-ttu-id="b488f-114">描述</span><span class="sxs-lookup"><span data-stu-id="b488f-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="b488f-115">maxPendingMessagesPerChannel</span><span class="sxs-lookup"><span data-stu-id="b488f-115">maxPendingMessagesPerChannel</span></span>|<span data-ttu-id="b488f-116">一个整数，指定每个通道允许的最大挂起消息数。</span><span class="sxs-lookup"><span data-stu-id="b488f-116">An integer that specifies the maximum number of pending messages allowed for each channel.</span></span> <span data-ttu-id="b488f-117">默认值为 512。</span><span class="sxs-lookup"><span data-stu-id="b488f-117">The default value is 512.</span></span> <span data-ttu-id="b488f-118">此属性限制工作流服务可接收的无序消息数。</span><span class="sxs-lookup"><span data-stu-id="b488f-118">This property limits the number of out-of-order messages that can be received by a workflow service.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b488f-119">子元素</span><span class="sxs-lookup"><span data-stu-id="b488f-119">Child Elements</span></span>  
 <span data-ttu-id="b488f-120">无。</span><span class="sxs-lookup"><span data-stu-id="b488f-120">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="b488f-121">父元素</span><span class="sxs-lookup"><span data-stu-id="b488f-121">Parent Elements</span></span>  
  
|<span data-ttu-id="b488f-122">元素</span><span class="sxs-lookup"><span data-stu-id="b488f-122">Element</span></span>|<span data-ttu-id="b488f-123">描述</span><span class="sxs-lookup"><span data-stu-id="b488f-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b488f-124">\<行为 > 的\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="b488f-124">\<behavior> of \<serviceBehaviors></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/behavior-of-servicebehaviors-of-workflow.md)|<span data-ttu-id="b488f-125">指定行为元素。</span><span class="sxs-lookup"><span data-stu-id="b488f-125">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b488f-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="b488f-126">See Also</span></span>  
<!-- <xref:System.ServiceModel.Activities.Description.BufferReceiveServiceBehavior>  -->
 <xref:System.ServiceModel.Activities.Configuration.BufferedReceiveElement>
