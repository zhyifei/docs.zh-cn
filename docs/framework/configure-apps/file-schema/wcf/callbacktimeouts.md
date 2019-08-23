---
title: <callbackTimeouts>
ms.date: 03/30/2017
ms.assetid: d7fcfc5f-6d35-491e-8fa6-2f964c1e792f
ms.openlocfilehash: d57a888a19e684ac13632c1ab2476e304667c3e3
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69919665"
---
# <a name="callbacktimeouts"></a><span data-ttu-id="41a3b-101">\<callbackTimeouts></span><span class="sxs-lookup"><span data-stu-id="41a3b-101">\<callbackTimeouts></span></span>
<span data-ttu-id="41a3b-102">在双工回调协定方案中指定使事务从服务器流动到客户端时的超时值。</span><span class="sxs-lookup"><span data-stu-id="41a3b-102">Specifies the timeout value when flowing transactions from server to client.in a duplex callback contract scenario.</span></span>  
  
 <span data-ttu-id="41a3b-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="41a3b-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="41a3b-104">\<行为 ></span><span class="sxs-lookup"><span data-stu-id="41a3b-104">\<behaviors></span></span>  
<span data-ttu-id="41a3b-105">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="41a3b-105">\<endpointBehaviors></span></span>  
<span data-ttu-id="41a3b-106">\<行为 ></span><span class="sxs-lookup"><span data-stu-id="41a3b-106">\<behavior></span></span>  
<span data-ttu-id="41a3b-107">\<callbackTimeOuts></span><span class="sxs-lookup"><span data-stu-id="41a3b-107">\<callbackTimeOuts></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="41a3b-108">语法</span><span class="sxs-lookup"><span data-stu-id="41a3b-108">Syntax</span></span>  
  
```xml  
<callbackTimeOuts transactionTimeout="TimeSpan" />
```  
  
## <a name="type"></a><span data-ttu-id="41a3b-109">类型</span><span class="sxs-lookup"><span data-stu-id="41a3b-109">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="41a3b-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="41a3b-110">Attributes and Elements</span></span>  
 <span data-ttu-id="41a3b-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="41a3b-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="41a3b-112">特性</span><span class="sxs-lookup"><span data-stu-id="41a3b-112">Attributes</span></span>  
  
|<span data-ttu-id="41a3b-113">特性</span><span class="sxs-lookup"><span data-stu-id="41a3b-113">Attribute</span></span>|<span data-ttu-id="41a3b-114">描述</span><span class="sxs-lookup"><span data-stu-id="41a3b-114">Description</span></span>|  
|---------------|-----------------|  
|`transactionTimeout`|<span data-ttu-id="41a3b-115">一个 <xref:System.TimeSpan> 值，指定时间间隔，事务必须在此期间完成，否则会自动终止。</span><span class="sxs-lookup"><span data-stu-id="41a3b-115">A <xref:System.TimeSpan> value that specifies the interval of time within which transactions must complete or be automatically terminated.</span></span> <span data-ttu-id="41a3b-116">默认值为 "00:00:00"。</span><span class="sxs-lookup"><span data-stu-id="41a3b-116">The default is "00:00:00".</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="41a3b-117">子元素</span><span class="sxs-lookup"><span data-stu-id="41a3b-117">Child Elements</span></span>  
 <span data-ttu-id="41a3b-118">无。</span><span class="sxs-lookup"><span data-stu-id="41a3b-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="41a3b-119">父元素</span><span class="sxs-lookup"><span data-stu-id="41a3b-119">Parent Elements</span></span>  
  
|<span data-ttu-id="41a3b-120">元素</span><span class="sxs-lookup"><span data-stu-id="41a3b-120">Element</span></span>|<span data-ttu-id="41a3b-121">描述</span><span class="sxs-lookup"><span data-stu-id="41a3b-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="41a3b-122">\<behavior></span><span class="sxs-lookup"><span data-stu-id="41a3b-122">\<behavior></span></span>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="41a3b-123">指定终结点行为。</span><span class="sxs-lookup"><span data-stu-id="41a3b-123">Specifies an endpoint behavior.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="41a3b-124">请参阅</span><span class="sxs-lookup"><span data-stu-id="41a3b-124">See also</span></span>

- <xref:System.ServiceModel.Configuration.CallbackTimeoutsElement>
