---
title: '&lt;dispatcherSynchronization&gt;'
ms.date: 03/30/2017
ms.assetid: cc030f9c-4e38-4b14-94dc-9a0e41ec8e2d
ms.openlocfilehash: 537dee408f1af29a06042de439a2c1e7d7874222
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54555383"
---
# <a name="ltdispatchersynchronizationgt"></a><span data-ttu-id="a4ae5-102">&lt;dispatcherSynchronization&gt;</span><span class="sxs-lookup"><span data-stu-id="a4ae5-102">&lt;dispatcherSynchronization&gt;</span></span>
  
<span data-ttu-id="a4ae5-103">指定允许服务进行异步答复的终结点行为。</span><span class="sxs-lookup"><span data-stu-id="a4ae5-103">Specifies an endpoint behavior that enables a service to send replies asynchronously.</span></span>  
  
<span data-ttu-id="a4ae5-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="a4ae5-104">\<system.serviceModel></span></span>  
<span data-ttu-id="a4ae5-105">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="a4ae5-105">\<behaviors></span></span>  
<span data-ttu-id="a4ae5-106">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="a4ae5-106">\<endpointBehaviors></span></span>  
<span data-ttu-id="a4ae5-107">\<behavior></span><span class="sxs-lookup"><span data-stu-id="a4ae5-107">\<behavior></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a4ae5-108">语法</span><span class="sxs-lookup"><span data-stu-id="a4ae5-108">Syntax</span></span>  
  
```xml  
<dispatcherSynchronizationBehavior asynchronousSendEnabled="Boolean"
                                   maxPendingReceives="Integer" />
```  
  
## <a name="type"></a><span data-ttu-id="a4ae5-109">类型</span><span class="sxs-lookup"><span data-stu-id="a4ae5-109">Type</span></span>  
  
`Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a4ae5-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="a4ae5-110">Attributes and elements</span></span>  
  
<span data-ttu-id="a4ae5-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="a4ae5-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a4ae5-112">特性</span><span class="sxs-lookup"><span data-stu-id="a4ae5-112">Attributes</span></span>

| <span data-ttu-id="a4ae5-113">特性</span><span class="sxs-lookup"><span data-stu-id="a4ae5-113">Attribute</span></span>               | <span data-ttu-id="a4ae5-114">描述</span><span class="sxs-lookup"><span data-stu-id="a4ae5-114">Description</span></span>       |
| ----------------------- | ----------------- |
| <span data-ttu-id="a4ae5-115">asynchronousSendEnabled</span><span class="sxs-lookup"><span data-stu-id="a4ae5-115">asynchronousSendEnabled</span></span> | <span data-ttu-id="a4ae5-116">一个布尔值，指定是否启用异步发送行为。</span><span class="sxs-lookup"><span data-stu-id="a4ae5-116">A Boolean that specifies whether asynchronous send behavior is enabled.</span></span> |
| `maxPendingReceives`    | <span data-ttu-id="a4ae5-117">一个整数，指定可在每个通道上执行的并发接收数。</span><span class="sxs-lookup"><span data-stu-id="a4ae5-117">An integer that specifies the number of concurrent receives that can be issued on the channel.</span></span><br /><br /> <span data-ttu-id="a4ae5-118">仅当已正确配置服务限制行为之后，才能配置此值。</span><span class="sxs-lookup"><span data-stu-id="a4ae5-118">This value should be configured only after you have properly configured service throttling behavior.</span></span> |

### <a name="child-elements"></a><span data-ttu-id="a4ae5-119">子元素</span><span class="sxs-lookup"><span data-stu-id="a4ae5-119">Child elements</span></span>

<span data-ttu-id="a4ae5-120">无。</span><span class="sxs-lookup"><span data-stu-id="a4ae5-120">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="a4ae5-121">父元素</span><span class="sxs-lookup"><span data-stu-id="a4ae5-121">Parent elements</span></span>

| <span data-ttu-id="a4ae5-122">元素</span><span class="sxs-lookup"><span data-stu-id="a4ae5-122">Element</span></span> | <span data-ttu-id="a4ae5-123">描述</span><span class="sxs-lookup"><span data-stu-id="a4ae5-123">Description</span></span> |  
| ------- | ----------- |  
| [<span data-ttu-id="a4ae5-124">\<behavior></span><span class="sxs-lookup"><span data-stu-id="a4ae5-124">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="a4ae5-125">指定终结点行为。</span><span class="sxs-lookup"><span data-stu-id="a4ae5-125">Specifies an endpoint behavior.</span></span> |

## <a name="see-also"></a><span data-ttu-id="a4ae5-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="a4ae5-126">See also</span></span>

- <xref:System.ServiceModel.Configuration.DispatcherSynchronizationElement>
- <xref:System.ServiceModel.Description.DispatcherSynchronizationBehavior>
