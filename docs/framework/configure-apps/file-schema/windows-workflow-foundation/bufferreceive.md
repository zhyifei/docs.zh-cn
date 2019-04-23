---
title: <bufferReceive>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: b23c3a54-10d4-4f13-ab6d-98b26b76f22a
ms.openlocfilehash: 360d26fda964fa33640e833ad22dab7e06e153f6
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59203153"
---
# <a name="bufferreceive"></a><span data-ttu-id="fc4e8-101">\<bufferReceive></span><span class="sxs-lookup"><span data-stu-id="fc4e8-101">\<bufferReceive></span></span>
<span data-ttu-id="fc4e8-102">一种服务行为，允许服务使用缓冲接收处理，以使工作流服务能够处理无序消息。</span><span class="sxs-lookup"><span data-stu-id="fc4e8-102">A service behavior that enables a service to use buffered receive processing, which enables a workflow service to process out-of-order messages.</span></span>  
  
<span data-ttu-id="fc4e8-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="fc4e8-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="fc4e8-104">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="fc4e8-104">\<behaviors></span></span>  
<span data-ttu-id="fc4e8-105">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="fc4e8-105">\<serviceBehaviors></span></span>  
<span data-ttu-id="fc4e8-106">\<behavior></span><span class="sxs-lookup"><span data-stu-id="fc4e8-106">\<behavior></span></span>  
<span data-ttu-id="fc4e8-107">\<bufferReceive></span><span class="sxs-lookup"><span data-stu-id="fc4e8-107">\<bufferReceive></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fc4e8-108">语法</span><span class="sxs-lookup"><span data-stu-id="fc4e8-108">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <bufferReceive maxPendingMessagesPerChannel="Integer" />
    </behavior>
  </serviceBehaviors>
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="fc4e8-109">特性和元素</span><span class="sxs-lookup"><span data-stu-id="fc4e8-109">Attributes and Elements</span></span>  
 <span data-ttu-id="fc4e8-110">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="fc4e8-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="fc4e8-111">特性</span><span class="sxs-lookup"><span data-stu-id="fc4e8-111">Attributes</span></span>  
  
|<span data-ttu-id="fc4e8-112">特性</span><span class="sxs-lookup"><span data-stu-id="fc4e8-112">Attribute</span></span>|<span data-ttu-id="fc4e8-113">描述</span><span class="sxs-lookup"><span data-stu-id="fc4e8-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="fc4e8-114">maxPendingMessagesPerChannel</span><span class="sxs-lookup"><span data-stu-id="fc4e8-114">maxPendingMessagesPerChannel</span></span>|<span data-ttu-id="fc4e8-115">一个整数，指定每个通道允许的最大挂起消息数。</span><span class="sxs-lookup"><span data-stu-id="fc4e8-115">An integer that specifies the maximum number of pending messages allowed for each channel.</span></span> <span data-ttu-id="fc4e8-116">默认值为 512。</span><span class="sxs-lookup"><span data-stu-id="fc4e8-116">The default value is 512.</span></span> <span data-ttu-id="fc4e8-117">此属性限制工作流服务可接收的无序消息数。</span><span class="sxs-lookup"><span data-stu-id="fc4e8-117">This property limits the number of out-of-order messages that can be received by a workflow service.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="fc4e8-118">子元素</span><span class="sxs-lookup"><span data-stu-id="fc4e8-118">Child Elements</span></span>  
 <span data-ttu-id="fc4e8-119">无。</span><span class="sxs-lookup"><span data-stu-id="fc4e8-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="fc4e8-120">父元素</span><span class="sxs-lookup"><span data-stu-id="fc4e8-120">Parent Elements</span></span>  
  
|<span data-ttu-id="fc4e8-121">元素</span><span class="sxs-lookup"><span data-stu-id="fc4e8-121">Element</span></span>|<span data-ttu-id="fc4e8-122">描述</span><span class="sxs-lookup"><span data-stu-id="fc4e8-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="fc4e8-123">\<行为 > 的\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="fc4e8-123">\<behavior> of \<serviceBehaviors></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/behavior-of-servicebehaviors-of-workflow.md)|<span data-ttu-id="fc4e8-124">指定行为元素。</span><span class="sxs-lookup"><span data-stu-id="fc4e8-124">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="fc4e8-125">请参阅</span><span class="sxs-lookup"><span data-stu-id="fc4e8-125">See also</span></span>

- <xref:System.ServiceModel.Activities.Description.BufferedReceiveServiceBehavior>
- <xref:System.ServiceModel.Activities.Configuration.BufferedReceiveElement>
