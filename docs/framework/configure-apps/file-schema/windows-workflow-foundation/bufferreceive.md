---
title: <bufferReceive>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: b23c3a54-10d4-4f13-ab6d-98b26b76f22a
ms.openlocfilehash: 1e095e3da11277c6b7b3c24e98a769500e1a0c0b
ms.sourcegitcommit: 01ea420eaa4bf76d5fc47673294c8881379b3369
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2019
ms.locfileid: "55759530"
---
# <a name="bufferreceive"></a><span data-ttu-id="37456-101">\<bufferReceive></span><span class="sxs-lookup"><span data-stu-id="37456-101">\<bufferReceive></span></span>
<span data-ttu-id="37456-102">一种服务行为，允许服务使用缓冲接收处理，以使工作流服务能够处理无序消息。</span><span class="sxs-lookup"><span data-stu-id="37456-102">A service behavior that enables a service to use buffered receive processing, which enables a workflow service to process out-of-order messages.</span></span>  
  
<span data-ttu-id="37456-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="37456-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="37456-104">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="37456-104">\<behaviors></span></span>  
<span data-ttu-id="37456-105">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="37456-105">\<serviceBehaviors></span></span>  
<span data-ttu-id="37456-106">\<behavior></span><span class="sxs-lookup"><span data-stu-id="37456-106">\<behavior></span></span>  
<span data-ttu-id="37456-107">\<bufferReceive></span><span class="sxs-lookup"><span data-stu-id="37456-107">\<bufferReceive></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="37456-108">语法</span><span class="sxs-lookup"><span data-stu-id="37456-108">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <bufferReceive maxPendingMessagesPerChannel="Integer" />
    </behavior>
  </serviceBehaviors>
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="37456-109">特性和元素</span><span class="sxs-lookup"><span data-stu-id="37456-109">Attributes and Elements</span></span>  
 <span data-ttu-id="37456-110">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="37456-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="37456-111">特性</span><span class="sxs-lookup"><span data-stu-id="37456-111">Attributes</span></span>  
  
|<span data-ttu-id="37456-112">特性</span><span class="sxs-lookup"><span data-stu-id="37456-112">Attribute</span></span>|<span data-ttu-id="37456-113">描述</span><span class="sxs-lookup"><span data-stu-id="37456-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="37456-114">maxPendingMessagesPerChannel</span><span class="sxs-lookup"><span data-stu-id="37456-114">maxPendingMessagesPerChannel</span></span>|<span data-ttu-id="37456-115">一个整数，指定每个通道允许的最大挂起消息数。</span><span class="sxs-lookup"><span data-stu-id="37456-115">An integer that specifies the maximum number of pending messages allowed for each channel.</span></span> <span data-ttu-id="37456-116">默认值为 512。</span><span class="sxs-lookup"><span data-stu-id="37456-116">The default value is 512.</span></span> <span data-ttu-id="37456-117">此属性限制工作流服务可接收的无序消息数。</span><span class="sxs-lookup"><span data-stu-id="37456-117">This property limits the number of out-of-order messages that can be received by a workflow service.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="37456-118">子元素</span><span class="sxs-lookup"><span data-stu-id="37456-118">Child Elements</span></span>  
 <span data-ttu-id="37456-119">无。</span><span class="sxs-lookup"><span data-stu-id="37456-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="37456-120">父元素</span><span class="sxs-lookup"><span data-stu-id="37456-120">Parent Elements</span></span>  
  
|<span data-ttu-id="37456-121">元素</span><span class="sxs-lookup"><span data-stu-id="37456-121">Element</span></span>|<span data-ttu-id="37456-122">描述</span><span class="sxs-lookup"><span data-stu-id="37456-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="37456-123">\<行为 > 的\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="37456-123">\<behavior> of \<serviceBehaviors></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/behavior-of-servicebehaviors-of-workflow.md)|<span data-ttu-id="37456-124">指定行为元素。</span><span class="sxs-lookup"><span data-stu-id="37456-124">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="37456-125">请参阅</span><span class="sxs-lookup"><span data-stu-id="37456-125">See also</span></span>
- <xref:System.ServiceModel.Activities.Description.BufferedReceiveServiceBehavior>
- <xref:System.ServiceModel.Activities.Configuration.BufferedReceiveElement>
