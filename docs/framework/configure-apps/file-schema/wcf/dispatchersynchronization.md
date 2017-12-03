---
title: '&lt;dispatcherSynchronization&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: cc030f9c-4e38-4b14-94dc-9a0e41ec8e2d
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: c0a6349f50c8810d834d7887daecb6ac9cffb2e9
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="ltdispatchersynchronizationgt"></a><span data-ttu-id="9eae4-102">&lt;dispatcherSynchronization&gt;</span><span class="sxs-lookup"><span data-stu-id="9eae4-102">&lt;dispatcherSynchronization&gt;</span></span>

<span data-ttu-id="9eae4-103">指定允许服务进行异步答复的终结点行为。</span><span class="sxs-lookup"><span data-stu-id="9eae4-103">Specifies an endpoint behavior that enables a service to send replies asynchronously.</span></span>

<span data-ttu-id="9eae4-104">\<system.serviceModel >\<行为 > \<endpointBehaviors >\<行为 ></span><span class="sxs-lookup"><span data-stu-id="9eae4-104">\<system.serviceModel> \<behaviors> \<endpointBehaviors> \<behavior></span></span>

## <a name="syntax"></a><span data-ttu-id="9eae4-105">语法</span><span class="sxs-lookup"><span data-stu-id="9eae4-105">Syntax</span></span>

```xml
<dispatcherSynchronizationBehavior asynchronousSendEnabled="Boolean" 
                                   maxPendingReceives="Integer" />
```

## <a name="type"></a><span data-ttu-id="9eae4-106">类型</span><span class="sxs-lookup"><span data-stu-id="9eae4-106">Type</span></span>

`Type`

## <a name="attributes-and-elements"></a><span data-ttu-id="9eae4-107">特性和元素</span><span class="sxs-lookup"><span data-stu-id="9eae4-107">Attributes and elements</span></span>

<span data-ttu-id="9eae4-108">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="9eae4-108">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="9eae4-109">特性</span><span class="sxs-lookup"><span data-stu-id="9eae4-109">Attributes</span></span>

| <span data-ttu-id="9eae4-110">特性</span><span class="sxs-lookup"><span data-stu-id="9eae4-110">Attribute</span></span>               | <span data-ttu-id="9eae4-111">描述</span><span class="sxs-lookup"><span data-stu-id="9eae4-111">Description</span></span>       |
| ----------------------- | ----------------- |
| <span data-ttu-id="9eae4-112">asynchronousSendEnabled</span><span class="sxs-lookup"><span data-stu-id="9eae4-112">asynchronousSendEnabled</span></span> | <span data-ttu-id="9eae4-113">一个布尔值，指定是否启用异步发送行为。</span><span class="sxs-lookup"><span data-stu-id="9eae4-113">A Boolean that specifies whether asynchronous send behavior is enabled.</span></span> |
| `maxPendingReceives`    | <span data-ttu-id="9eae4-114">一个整数，指定可在每个通道上执行的并发接收数。</span><span class="sxs-lookup"><span data-stu-id="9eae4-114">An integer that specifies the number of concurrent receives that can be issued on the channel.</span></span><br /><br /> <span data-ttu-id="9eae4-115">仅当已正确配置服务限制行为之后，才能配置此值。</span><span class="sxs-lookup"><span data-stu-id="9eae4-115">This value should be configured only after you have properly configured service throttling behavior.</span></span> |

### <a name="child-elements"></a><span data-ttu-id="9eae4-116">子元素</span><span class="sxs-lookup"><span data-stu-id="9eae4-116">Child elements</span></span>

<span data-ttu-id="9eae4-117">无。</span><span class="sxs-lookup"><span data-stu-id="9eae4-117">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="9eae4-118">父元素</span><span class="sxs-lookup"><span data-stu-id="9eae4-118">Parent elements</span></span>

| <span data-ttu-id="9eae4-119">元素</span><span class="sxs-lookup"><span data-stu-id="9eae4-119">Element</span></span> | <span data-ttu-id="9eae4-120">描述</span><span class="sxs-lookup"><span data-stu-id="9eae4-120">Description</span></span> |  
| ------- | ----------- |  
| [<span data-ttu-id="9eae4-121">\<行为 ></span><span class="sxs-lookup"><span data-stu-id="9eae4-121">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="9eae4-122">指定终结点行为。</span><span class="sxs-lookup"><span data-stu-id="9eae4-122">Specifies an endpoint behavior.</span></span> |

## <a name="see-also"></a><span data-ttu-id="9eae4-123">请参阅</span><span class="sxs-lookup"><span data-stu-id="9eae4-123">See also</span></span>

 <span data-ttu-id="9eae4-124"><xref:System.ServiceModel.Configuration.DispatcherSynchronizationElement> <xref:System.ServiceModel.Description.DispatcherSynchronizationBehavior></span><span class="sxs-lookup"><span data-stu-id="9eae4-124"><xref:System.ServiceModel.Configuration.DispatcherSynchronizationElement> <xref:System.ServiceModel.Description.DispatcherSynchronizationBehavior></span></span>
