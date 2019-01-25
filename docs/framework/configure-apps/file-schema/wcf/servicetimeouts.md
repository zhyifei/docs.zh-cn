---
title: '&lt;serviceTimeouts&gt;'
ms.date: 03/30/2017
ms.assetid: ada536cf-97dc-4cd7-89ec-ed1466c1c557
ms.openlocfilehash: f7aa623ee387f67f3bbff32249d3695049359cde
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54524463"
---
# <a name="ltservicetimeoutsgt"></a><span data-ttu-id="36c0c-102">&lt;serviceTimeouts&gt;</span><span class="sxs-lookup"><span data-stu-id="36c0c-102">&lt;serviceTimeouts&gt;</span></span>
<span data-ttu-id="36c0c-103">指定服务的超时。</span><span class="sxs-lookup"><span data-stu-id="36c0c-103">Specifies the timeout for a service.</span></span>  
  
 <span data-ttu-id="36c0c-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="36c0c-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="36c0c-105">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="36c0c-105">\<behaviors></span></span>  
<span data-ttu-id="36c0c-106">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="36c0c-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="36c0c-107">\<behavior></span><span class="sxs-lookup"><span data-stu-id="36c0c-107">\<behavior></span></span>  
<span data-ttu-id="36c0c-108">\<serviceTimeouts></span><span class="sxs-lookup"><span data-stu-id="36c0c-108">\<serviceTimeouts></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="36c0c-109">语法</span><span class="sxs-lookup"><span data-stu-id="36c0c-109">Syntax</span></span>  
  
```xml  
<serviceTimeouts transactionTimeout="TimeSpan" />
```  
  
## <a name="type"></a><span data-ttu-id="36c0c-110">类型</span><span class="sxs-lookup"><span data-stu-id="36c0c-110">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="36c0c-111">特性和元素</span><span class="sxs-lookup"><span data-stu-id="36c0c-111">Attributes and Elements</span></span>  
 <span data-ttu-id="36c0c-112">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="36c0c-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="36c0c-113">特性</span><span class="sxs-lookup"><span data-stu-id="36c0c-113">Attributes</span></span>  
  
|<span data-ttu-id="36c0c-114">特性</span><span class="sxs-lookup"><span data-stu-id="36c0c-114">Attribute</span></span>|<span data-ttu-id="36c0c-115">描述</span><span class="sxs-lookup"><span data-stu-id="36c0c-115">Description</span></span>|  
|---------------|-----------------|  
|`transactionTimeout`|<span data-ttu-id="36c0c-116">一个 <xref:System.TimeSpan> 值，指定事务从客户端流动到服务器所必须经历的时间间隔。</span><span class="sxs-lookup"><span data-stu-id="36c0c-116">A <xref:System.TimeSpan> value that specifies the interval of time a transaction must flow from client to server.</span></span> <span data-ttu-id="36c0c-117">默认值是"00: 00:00"。</span><span class="sxs-lookup"><span data-stu-id="36c0c-117">The default is "00:00:00".</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="36c0c-118">子元素</span><span class="sxs-lookup"><span data-stu-id="36c0c-118">Child Elements</span></span>  
 <span data-ttu-id="36c0c-119">无。</span><span class="sxs-lookup"><span data-stu-id="36c0c-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="36c0c-120">父元素</span><span class="sxs-lookup"><span data-stu-id="36c0c-120">Parent Elements</span></span>  
  
|<span data-ttu-id="36c0c-121">元素</span><span class="sxs-lookup"><span data-stu-id="36c0c-121">Element</span></span>|<span data-ttu-id="36c0c-122">描述</span><span class="sxs-lookup"><span data-stu-id="36c0c-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="36c0c-123">\<behavior></span><span class="sxs-lookup"><span data-stu-id="36c0c-123">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="36c0c-124">指定行为元素。</span><span class="sxs-lookup"><span data-stu-id="36c0c-124">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="36c0c-125">请参阅</span><span class="sxs-lookup"><span data-stu-id="36c0c-125">See also</span></span>
- <xref:System.ServiceModel.Configuration.ServiceTimeoutsElement>
