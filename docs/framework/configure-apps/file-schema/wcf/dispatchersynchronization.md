---
title: <dispatcherSynchronization>
ms.date: 03/30/2017
ms.assetid: cc030f9c-4e38-4b14-94dc-9a0e41ec8e2d
ms.openlocfilehash: 6be9752e8102a5d4db4fed31aae8ff6d56fdd24e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61673402"
---
# <a name="dispatchersynchronization"></a><span data-ttu-id="23446-101">\<dispatcherSynchronization></span><span class="sxs-lookup"><span data-stu-id="23446-101">\<dispatcherSynchronization></span></span>
  
<span data-ttu-id="23446-102">指定允许服务进行异步答复的终结点行为。</span><span class="sxs-lookup"><span data-stu-id="23446-102">Specifies an endpoint behavior that enables a service to send replies asynchronously.</span></span>  
  
<span data-ttu-id="23446-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="23446-103">\<system.serviceModel></span></span>  
<span data-ttu-id="23446-104">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="23446-104">\<behaviors></span></span>  
<span data-ttu-id="23446-105">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="23446-105">\<endpointBehaviors></span></span>  
<span data-ttu-id="23446-106">\<behavior></span><span class="sxs-lookup"><span data-stu-id="23446-106">\<behavior></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="23446-107">语法</span><span class="sxs-lookup"><span data-stu-id="23446-107">Syntax</span></span>  
  
```xml  
<dispatcherSynchronizationBehavior asynchronousSendEnabled="Boolean"
                                   maxPendingReceives="Integer" />
```  
  
## <a name="type"></a><span data-ttu-id="23446-108">类型</span><span class="sxs-lookup"><span data-stu-id="23446-108">Type</span></span>  
  
`Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="23446-109">特性和元素</span><span class="sxs-lookup"><span data-stu-id="23446-109">Attributes and elements</span></span>  
  
<span data-ttu-id="23446-110">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="23446-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="23446-111">特性</span><span class="sxs-lookup"><span data-stu-id="23446-111">Attributes</span></span>

| <span data-ttu-id="23446-112">特性</span><span class="sxs-lookup"><span data-stu-id="23446-112">Attribute</span></span>               | <span data-ttu-id="23446-113">描述</span><span class="sxs-lookup"><span data-stu-id="23446-113">Description</span></span>       |
| ----------------------- | ----------------- |
| <span data-ttu-id="23446-114">asynchronousSendEnabled</span><span class="sxs-lookup"><span data-stu-id="23446-114">asynchronousSendEnabled</span></span> | <span data-ttu-id="23446-115">一个布尔值，指定是否启用异步发送行为。</span><span class="sxs-lookup"><span data-stu-id="23446-115">A Boolean that specifies whether asynchronous send behavior is enabled.</span></span> |
| `maxPendingReceives`    | <span data-ttu-id="23446-116">一个整数，指定可在每个通道上执行的并发接收数。</span><span class="sxs-lookup"><span data-stu-id="23446-116">An integer that specifies the number of concurrent receives that can be issued on the channel.</span></span><br /><br /> <span data-ttu-id="23446-117">仅当已正确配置服务限制行为之后，才能配置此值。</span><span class="sxs-lookup"><span data-stu-id="23446-117">This value should be configured only after you have properly configured service throttling behavior.</span></span> |

### <a name="child-elements"></a><span data-ttu-id="23446-118">子元素</span><span class="sxs-lookup"><span data-stu-id="23446-118">Child elements</span></span>

<span data-ttu-id="23446-119">无。</span><span class="sxs-lookup"><span data-stu-id="23446-119">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="23446-120">父元素</span><span class="sxs-lookup"><span data-stu-id="23446-120">Parent elements</span></span>

| <span data-ttu-id="23446-121">元素</span><span class="sxs-lookup"><span data-stu-id="23446-121">Element</span></span> | <span data-ttu-id="23446-122">描述</span><span class="sxs-lookup"><span data-stu-id="23446-122">Description</span></span> |  
| ------- | ----------- |  
| [<span data-ttu-id="23446-123">\<behavior></span><span class="sxs-lookup"><span data-stu-id="23446-123">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="23446-124">指定终结点行为。</span><span class="sxs-lookup"><span data-stu-id="23446-124">Specifies an endpoint behavior.</span></span> |

## <a name="see-also"></a><span data-ttu-id="23446-125">请参阅</span><span class="sxs-lookup"><span data-stu-id="23446-125">See also</span></span>

- <xref:System.ServiceModel.Configuration.DispatcherSynchronizationElement>
- <xref:System.ServiceModel.Description.DispatcherSynchronizationBehavior>
