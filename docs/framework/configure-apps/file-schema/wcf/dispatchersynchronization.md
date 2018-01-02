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
ms.workload: dotnet
ms.openlocfilehash: 57477ea60337e5032b80bd9ae8da850099dd08f7
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="ltdispatchersynchronizationgt"></a><span data-ttu-id="bb1b7-102">&lt;dispatcherSynchronization&gt;</span><span class="sxs-lookup"><span data-stu-id="bb1b7-102">&lt;dispatcherSynchronization&gt;</span></span>

<span data-ttu-id="bb1b7-103">指定允许服务进行异步答复的终结点行为。</span><span class="sxs-lookup"><span data-stu-id="bb1b7-103">Specifies an endpoint behavior that enables a service to send replies asynchronously.</span></span>

<span data-ttu-id="bb1b7-104">\<system.serviceModel >\<行为 > \<endpointBehaviors >\<行为 ></span><span class="sxs-lookup"><span data-stu-id="bb1b7-104">\<system.serviceModel> \<behaviors> \<endpointBehaviors> \<behavior></span></span>

## <a name="syntax"></a><span data-ttu-id="bb1b7-105">语法</span><span class="sxs-lookup"><span data-stu-id="bb1b7-105">Syntax</span></span>

```xml
<dispatcherSynchronizationBehavior asynchronousSendEnabled="Boolean" 
                                   maxPendingReceives="Integer" />
```

## <a name="type"></a><span data-ttu-id="bb1b7-106">类型</span><span class="sxs-lookup"><span data-stu-id="bb1b7-106">Type</span></span>

`Type`

## <a name="attributes-and-elements"></a><span data-ttu-id="bb1b7-107">特性和元素</span><span class="sxs-lookup"><span data-stu-id="bb1b7-107">Attributes and elements</span></span>

<span data-ttu-id="bb1b7-108">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="bb1b7-108">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="bb1b7-109">特性</span><span class="sxs-lookup"><span data-stu-id="bb1b7-109">Attributes</span></span>

| <span data-ttu-id="bb1b7-110">特性</span><span class="sxs-lookup"><span data-stu-id="bb1b7-110">Attribute</span></span>               | <span data-ttu-id="bb1b7-111">描述</span><span class="sxs-lookup"><span data-stu-id="bb1b7-111">Description</span></span>       |
| ----------------------- | ----------------- |
| <span data-ttu-id="bb1b7-112">asynchronousSendEnabled</span><span class="sxs-lookup"><span data-stu-id="bb1b7-112">asynchronousSendEnabled</span></span> | <span data-ttu-id="bb1b7-113">一个布尔值，指定是否启用异步发送行为。</span><span class="sxs-lookup"><span data-stu-id="bb1b7-113">A Boolean that specifies whether asynchronous send behavior is enabled.</span></span> |
| `maxPendingReceives`    | <span data-ttu-id="bb1b7-114">一个整数，指定可在每个通道上执行的并发接收数。</span><span class="sxs-lookup"><span data-stu-id="bb1b7-114">An integer that specifies the number of concurrent receives that can be issued on the channel.</span></span><br /><br /> <span data-ttu-id="bb1b7-115">仅当已正确配置服务限制行为之后，才能配置此值。</span><span class="sxs-lookup"><span data-stu-id="bb1b7-115">This value should be configured only after you have properly configured service throttling behavior.</span></span> |

### <a name="child-elements"></a><span data-ttu-id="bb1b7-116">子元素</span><span class="sxs-lookup"><span data-stu-id="bb1b7-116">Child elements</span></span>

<span data-ttu-id="bb1b7-117">无。</span><span class="sxs-lookup"><span data-stu-id="bb1b7-117">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="bb1b7-118">父元素</span><span class="sxs-lookup"><span data-stu-id="bb1b7-118">Parent elements</span></span>

| <span data-ttu-id="bb1b7-119">元素</span><span class="sxs-lookup"><span data-stu-id="bb1b7-119">Element</span></span> | <span data-ttu-id="bb1b7-120">描述</span><span class="sxs-lookup"><span data-stu-id="bb1b7-120">Description</span></span> |  
| ------- | ----------- |  
| [<span data-ttu-id="bb1b7-121">\<行为 ></span><span class="sxs-lookup"><span data-stu-id="bb1b7-121">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="bb1b7-122">指定终结点行为。</span><span class="sxs-lookup"><span data-stu-id="bb1b7-122">Specifies an endpoint behavior.</span></span> |

## <a name="see-also"></a><span data-ttu-id="bb1b7-123">请参阅</span><span class="sxs-lookup"><span data-stu-id="bb1b7-123">See also</span></span>

 <span data-ttu-id="bb1b7-124"><xref:System.ServiceModel.Configuration.DispatcherSynchronizationElement> <xref:System.ServiceModel.Description.DispatcherSynchronizationBehavior></span><span class="sxs-lookup"><span data-stu-id="bb1b7-124"><xref:System.ServiceModel.Configuration.DispatcherSynchronizationElement> <xref:System.ServiceModel.Description.DispatcherSynchronizationBehavior></span></span>
