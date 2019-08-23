---
title: <dispatcherSynchronization>
ms.date: 03/30/2017
ms.assetid: cc030f9c-4e38-4b14-94dc-9a0e41ec8e2d
ms.openlocfilehash: 7336c9f7d8a117f9a9bfd338e47941eeb648fa51
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69925844"
---
# <a name="dispatchersynchronization"></a><span data-ttu-id="17fcf-101">\<dispatcherSynchronization></span><span class="sxs-lookup"><span data-stu-id="17fcf-101">\<dispatcherSynchronization></span></span>
  
<span data-ttu-id="17fcf-102">指定允许服务进行异步答复的终结点行为。</span><span class="sxs-lookup"><span data-stu-id="17fcf-102">Specifies an endpoint behavior that enables a service to send replies asynchronously.</span></span>  
  
<span data-ttu-id="17fcf-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="17fcf-103">\<system.serviceModel></span></span>  
<span data-ttu-id="17fcf-104">\<行为 ></span><span class="sxs-lookup"><span data-stu-id="17fcf-104">\<behaviors></span></span>  
<span data-ttu-id="17fcf-105">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="17fcf-105">\<endpointBehaviors></span></span>  
<span data-ttu-id="17fcf-106">\<行为 ></span><span class="sxs-lookup"><span data-stu-id="17fcf-106">\<behavior></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="17fcf-107">语法</span><span class="sxs-lookup"><span data-stu-id="17fcf-107">Syntax</span></span>  
  
```xml  
<dispatcherSynchronizationBehavior asynchronousSendEnabled="Boolean"
                                   maxPendingReceives="Integer" />
```  
  
## <a name="type"></a><span data-ttu-id="17fcf-108">类型</span><span class="sxs-lookup"><span data-stu-id="17fcf-108">Type</span></span>  
  
`Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="17fcf-109">特性和元素</span><span class="sxs-lookup"><span data-stu-id="17fcf-109">Attributes and elements</span></span>  
  
<span data-ttu-id="17fcf-110">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="17fcf-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="17fcf-111">特性</span><span class="sxs-lookup"><span data-stu-id="17fcf-111">Attributes</span></span>

| <span data-ttu-id="17fcf-112">特性</span><span class="sxs-lookup"><span data-stu-id="17fcf-112">Attribute</span></span>               | <span data-ttu-id="17fcf-113">描述</span><span class="sxs-lookup"><span data-stu-id="17fcf-113">Description</span></span>       |
| ----------------------- | ----------------- |
| <span data-ttu-id="17fcf-114">asynchronousSendEnabled</span><span class="sxs-lookup"><span data-stu-id="17fcf-114">asynchronousSendEnabled</span></span> | <span data-ttu-id="17fcf-115">一个布尔值，指定是否启用异步发送行为。</span><span class="sxs-lookup"><span data-stu-id="17fcf-115">A Boolean that specifies whether asynchronous send behavior is enabled.</span></span> |
| `maxPendingReceives`    | <span data-ttu-id="17fcf-116">一个整数，指定可在每个通道上执行的并发接收数。</span><span class="sxs-lookup"><span data-stu-id="17fcf-116">An integer that specifies the number of concurrent receives that can be issued on the channel.</span></span><br /><br /> <span data-ttu-id="17fcf-117">仅当已正确配置服务限制行为之后，才能配置此值。</span><span class="sxs-lookup"><span data-stu-id="17fcf-117">This value should be configured only after you have properly configured service throttling behavior.</span></span> |

### <a name="child-elements"></a><span data-ttu-id="17fcf-118">子元素</span><span class="sxs-lookup"><span data-stu-id="17fcf-118">Child elements</span></span>

<span data-ttu-id="17fcf-119">无。</span><span class="sxs-lookup"><span data-stu-id="17fcf-119">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="17fcf-120">父元素</span><span class="sxs-lookup"><span data-stu-id="17fcf-120">Parent elements</span></span>

| <span data-ttu-id="17fcf-121">元素</span><span class="sxs-lookup"><span data-stu-id="17fcf-121">Element</span></span> | <span data-ttu-id="17fcf-122">描述</span><span class="sxs-lookup"><span data-stu-id="17fcf-122">Description</span></span> |  
| ------- | ----------- |  
| [<span data-ttu-id="17fcf-123">\<behavior></span><span class="sxs-lookup"><span data-stu-id="17fcf-123">\<behavior></span></span>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="17fcf-124">指定终结点行为。</span><span class="sxs-lookup"><span data-stu-id="17fcf-124">Specifies an endpoint behavior.</span></span> |

## <a name="see-also"></a><span data-ttu-id="17fcf-125">请参阅</span><span class="sxs-lookup"><span data-stu-id="17fcf-125">See also</span></span>

- <xref:System.ServiceModel.Configuration.DispatcherSynchronizationElement>
- <xref:System.ServiceModel.Description.DispatcherSynchronizationBehavior>
