---
title: '&lt;callbackTimeouts&gt;'
ms.date: 03/30/2017
ms.assetid: d7fcfc5f-6d35-491e-8fa6-2f964c1e792f
ms.openlocfilehash: 01932fe2b7b7e699311e2c65ec8adaf0aef82dc5
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54557898"
---
# <a name="ltcallbacktimeoutsgt"></a><span data-ttu-id="fdce3-102">&lt;callbackTimeouts&gt;</span><span class="sxs-lookup"><span data-stu-id="fdce3-102">&lt;callbackTimeouts&gt;</span></span>
<span data-ttu-id="fdce3-103">在双工回调协定方案中指定使事务从服务器流动到客户端时的超时值。</span><span class="sxs-lookup"><span data-stu-id="fdce3-103">Specifies the timeout value when flowing transactions from server to client.in a duplex callback contract scenario.</span></span>  
  
 <span data-ttu-id="fdce3-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="fdce3-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="fdce3-105">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="fdce3-105">\<behaviors></span></span>  
<span data-ttu-id="fdce3-106">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="fdce3-106">\<endpointBehaviors></span></span>  
<span data-ttu-id="fdce3-107">\<behavior></span><span class="sxs-lookup"><span data-stu-id="fdce3-107">\<behavior></span></span>  
<span data-ttu-id="fdce3-108">\<callbackTimeOuts></span><span class="sxs-lookup"><span data-stu-id="fdce3-108">\<callbackTimeOuts></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fdce3-109">语法</span><span class="sxs-lookup"><span data-stu-id="fdce3-109">Syntax</span></span>  
  
```xml  
<callbackTimeOuts transactionTimeout="TimeSpan" />
```  
  
## <a name="type"></a><span data-ttu-id="fdce3-110">类型</span><span class="sxs-lookup"><span data-stu-id="fdce3-110">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="fdce3-111">特性和元素</span><span class="sxs-lookup"><span data-stu-id="fdce3-111">Attributes and Elements</span></span>  
 <span data-ttu-id="fdce3-112">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="fdce3-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="fdce3-113">特性</span><span class="sxs-lookup"><span data-stu-id="fdce3-113">Attributes</span></span>  
  
|<span data-ttu-id="fdce3-114">特性</span><span class="sxs-lookup"><span data-stu-id="fdce3-114">Attribute</span></span>|<span data-ttu-id="fdce3-115">描述</span><span class="sxs-lookup"><span data-stu-id="fdce3-115">Description</span></span>|  
|---------------|-----------------|  
|`transactionTimeout`|<span data-ttu-id="fdce3-116">一个 <xref:System.TimeSpan> 值，指定时间间隔，事务必须在此期间完成，否则会自动终止。</span><span class="sxs-lookup"><span data-stu-id="fdce3-116">A <xref:System.TimeSpan> value that specifies the interval of time within which transactions must complete or be automatically terminated.</span></span> <span data-ttu-id="fdce3-117">默认值是"00: 00:00"。</span><span class="sxs-lookup"><span data-stu-id="fdce3-117">The default is "00:00:00".</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="fdce3-118">子元素</span><span class="sxs-lookup"><span data-stu-id="fdce3-118">Child Elements</span></span>  
 <span data-ttu-id="fdce3-119">无。</span><span class="sxs-lookup"><span data-stu-id="fdce3-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="fdce3-120">父元素</span><span class="sxs-lookup"><span data-stu-id="fdce3-120">Parent Elements</span></span>  
  
|<span data-ttu-id="fdce3-121">元素</span><span class="sxs-lookup"><span data-stu-id="fdce3-121">Element</span></span>|<span data-ttu-id="fdce3-122">描述</span><span class="sxs-lookup"><span data-stu-id="fdce3-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="fdce3-123">\<behavior></span><span class="sxs-lookup"><span data-stu-id="fdce3-123">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="fdce3-124">指定终结点行为。</span><span class="sxs-lookup"><span data-stu-id="fdce3-124">Specifies an endpoint behavior.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="fdce3-125">请参阅</span><span class="sxs-lookup"><span data-stu-id="fdce3-125">See also</span></span>
- <xref:System.ServiceModel.Configuration.CallbackTimeoutsElement>
