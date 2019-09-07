---
title: <dispatcherSynchronization>
ms.date: 03/30/2017
ms.assetid: cc030f9c-4e38-4b14-94dc-9a0e41ec8e2d
ms.openlocfilehash: b95f25217c2a3558846cc7a0ef43e21aacd2ee2a
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/06/2019
ms.locfileid: "70398000"
---
# <a name="dispatchersynchronization"></a><span data-ttu-id="36b9e-101">\<dispatcherSynchronization></span><span class="sxs-lookup"><span data-stu-id="36b9e-101">\<dispatcherSynchronization></span></span>
  
<span data-ttu-id="36b9e-102">指定允许服务进行异步答复的终结点行为。</span><span class="sxs-lookup"><span data-stu-id="36b9e-102">Specifies an endpoint behavior that enables a service to send replies asynchronously.</span></span>  
  
<span data-ttu-id="36b9e-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="36b9e-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="36b9e-104">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="36b9e-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="36b9e-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<行为 >** ](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="36b9e-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="36b9e-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<endpointBehaviors >** ](endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="36b9e-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)</span></span>\
<span data-ttu-id="36b9e-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<行为 >** ](behavior-of-endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="36b9e-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)</span></span>\
<span data-ttu-id="36b9e-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<dispatcherSynchronization >**</span><span class="sxs-lookup"><span data-stu-id="36b9e-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<dispatcherSynchronization>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="36b9e-109">语法</span><span class="sxs-lookup"><span data-stu-id="36b9e-109">Syntax</span></span>  
  
```xml  
<dispatcherSynchronizationBehavior asynchronousSendEnabled="Boolean"
                                   maxPendingReceives="Integer" />
```  
  
## <a name="type"></a><span data-ttu-id="36b9e-110">类型</span><span class="sxs-lookup"><span data-stu-id="36b9e-110">Type</span></span>  
  
`Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="36b9e-111">特性和元素</span><span class="sxs-lookup"><span data-stu-id="36b9e-111">Attributes and elements</span></span>  
  
<span data-ttu-id="36b9e-112">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="36b9e-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="36b9e-113">特性</span><span class="sxs-lookup"><span data-stu-id="36b9e-113">Attributes</span></span>

| <span data-ttu-id="36b9e-114">特性</span><span class="sxs-lookup"><span data-stu-id="36b9e-114">Attribute</span></span>               | <span data-ttu-id="36b9e-115">描述</span><span class="sxs-lookup"><span data-stu-id="36b9e-115">Description</span></span>       |
| ----------------------- | ----------------- |
| <span data-ttu-id="36b9e-116">asynchronousSendEnabled</span><span class="sxs-lookup"><span data-stu-id="36b9e-116">asynchronousSendEnabled</span></span> | <span data-ttu-id="36b9e-117">一个布尔值，指定是否启用异步发送行为。</span><span class="sxs-lookup"><span data-stu-id="36b9e-117">A Boolean that specifies whether asynchronous send behavior is enabled.</span></span> |
| `maxPendingReceives`    | <span data-ttu-id="36b9e-118">一个整数，指定可在每个通道上执行的并发接收数。</span><span class="sxs-lookup"><span data-stu-id="36b9e-118">An integer that specifies the number of concurrent receives that can be issued on the channel.</span></span><br /><br /> <span data-ttu-id="36b9e-119">仅当已正确配置服务限制行为之后，才能配置此值。</span><span class="sxs-lookup"><span data-stu-id="36b9e-119">This value should be configured only after you have properly configured service throttling behavior.</span></span> |

### <a name="child-elements"></a><span data-ttu-id="36b9e-120">子元素</span><span class="sxs-lookup"><span data-stu-id="36b9e-120">Child elements</span></span>

<span data-ttu-id="36b9e-121">无。</span><span class="sxs-lookup"><span data-stu-id="36b9e-121">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="36b9e-122">父元素</span><span class="sxs-lookup"><span data-stu-id="36b9e-122">Parent elements</span></span>

| <span data-ttu-id="36b9e-123">元素</span><span class="sxs-lookup"><span data-stu-id="36b9e-123">Element</span></span> | <span data-ttu-id="36b9e-124">描述</span><span class="sxs-lookup"><span data-stu-id="36b9e-124">Description</span></span> |  
| ------- | ----------- |  
| [<span data-ttu-id="36b9e-125">\<behavior></span><span class="sxs-lookup"><span data-stu-id="36b9e-125">\<behavior></span></span>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="36b9e-126">指定终结点行为。</span><span class="sxs-lookup"><span data-stu-id="36b9e-126">Specifies an endpoint behavior.</span></span> |

## <a name="see-also"></a><span data-ttu-id="36b9e-127">请参阅</span><span class="sxs-lookup"><span data-stu-id="36b9e-127">See also</span></span>

- <xref:System.ServiceModel.Configuration.DispatcherSynchronizationElement>
- <xref:System.ServiceModel.Description.DispatcherSynchronizationBehavior>
