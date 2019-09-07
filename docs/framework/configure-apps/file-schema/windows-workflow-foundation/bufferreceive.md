---
title: <bufferReceive>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: b23c3a54-10d4-4f13-ab6d-98b26b76f22a
ms.openlocfilehash: be5173ea43c6f7fca7180a311885a26c889b12db
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/06/2019
ms.locfileid: "70398837"
---
# <a name="bufferreceive"></a><span data-ttu-id="74ab6-101">\<bufferReceive></span><span class="sxs-lookup"><span data-stu-id="74ab6-101">\<bufferReceive></span></span>
<span data-ttu-id="74ab6-102">一种服务行为，允许服务使用缓冲接收处理，以使工作流服务能够处理无序消息。</span><span class="sxs-lookup"><span data-stu-id="74ab6-102">A service behavior that enables a service to use buffered receive processing, which enables a workflow service to process out-of-order messages.</span></span>  
  
<span data-ttu-id="74ab6-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="74ab6-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="74ab6-104">&nbsp;&nbsp;[ **\<主板.>** ](system-servicemodel-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="74ab6-104">&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)</span></span>\
<span data-ttu-id="74ab6-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<行为 >** ](behaviors-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="74ab6-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors-of-workflow.md)</span></span>\
<span data-ttu-id="74ab6-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<serviceBehaviors >** ](servicebehaviors-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="74ab6-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors-of-workflow.md)</span></span>\
<span data-ttu-id="74ab6-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<行为 >** ](behavior-of-servicebehaviors-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="74ab6-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors-of-workflow.md)</span></span>\
<span data-ttu-id="74ab6-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<bufferReceive >**</span><span class="sxs-lookup"><span data-stu-id="74ab6-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<bufferReceive>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="74ab6-109">语法</span><span class="sxs-lookup"><span data-stu-id="74ab6-109">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <bufferReceive maxPendingMessagesPerChannel="Integer" />
    </behavior>
  </serviceBehaviors>
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="74ab6-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="74ab6-110">Attributes and Elements</span></span>  
 <span data-ttu-id="74ab6-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="74ab6-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="74ab6-112">特性</span><span class="sxs-lookup"><span data-stu-id="74ab6-112">Attributes</span></span>  
  
|<span data-ttu-id="74ab6-113">特性</span><span class="sxs-lookup"><span data-stu-id="74ab6-113">Attribute</span></span>|<span data-ttu-id="74ab6-114">描述</span><span class="sxs-lookup"><span data-stu-id="74ab6-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="74ab6-115">maxPendingMessagesPerChannel</span><span class="sxs-lookup"><span data-stu-id="74ab6-115">maxPendingMessagesPerChannel</span></span>|<span data-ttu-id="74ab6-116">一个整数，指定每个通道允许的最大挂起消息数。</span><span class="sxs-lookup"><span data-stu-id="74ab6-116">An integer that specifies the maximum number of pending messages allowed for each channel.</span></span> <span data-ttu-id="74ab6-117">默认值为 512。</span><span class="sxs-lookup"><span data-stu-id="74ab6-117">The default value is 512.</span></span> <span data-ttu-id="74ab6-118">此属性限制工作流服务可接收的无序消息数。</span><span class="sxs-lookup"><span data-stu-id="74ab6-118">This property limits the number of out-of-order messages that can be received by a workflow service.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="74ab6-119">子元素</span><span class="sxs-lookup"><span data-stu-id="74ab6-119">Child Elements</span></span>  
 <span data-ttu-id="74ab6-120">无。</span><span class="sxs-lookup"><span data-stu-id="74ab6-120">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="74ab6-121">父元素</span><span class="sxs-lookup"><span data-stu-id="74ab6-121">Parent Elements</span></span>  
  
|<span data-ttu-id="74ab6-122">元素</span><span class="sxs-lookup"><span data-stu-id="74ab6-122">Element</span></span>|<span data-ttu-id="74ab6-123">描述</span><span class="sxs-lookup"><span data-stu-id="74ab6-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="74ab6-124">\<serviceBehaviors > 的\<行为 ></span><span class="sxs-lookup"><span data-stu-id="74ab6-124">\<behavior> of \<serviceBehaviors></span></span>](behavior-of-servicebehaviors-of-workflow.md)|<span data-ttu-id="74ab6-125">指定行为元素。</span><span class="sxs-lookup"><span data-stu-id="74ab6-125">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="74ab6-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="74ab6-126">See also</span></span>

- <xref:System.ServiceModel.Activities.Description.BufferedReceiveServiceBehavior>
- <xref:System.ServiceModel.Activities.Configuration.BufferedReceiveElement>
