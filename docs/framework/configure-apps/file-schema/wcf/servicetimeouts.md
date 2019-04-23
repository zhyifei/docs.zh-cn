---
title: <serviceTimeouts>
ms.date: 03/30/2017
ms.assetid: ada536cf-97dc-4cd7-89ec-ed1466c1c557
ms.openlocfilehash: 5c2f0ef7ad509eb5d6c686802c3fe5a75ea1a258
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59075511"
---
# <a name="servicetimeouts"></a><span data-ttu-id="09971-101">\<serviceTimeouts></span><span class="sxs-lookup"><span data-stu-id="09971-101">\<serviceTimeouts></span></span>
<span data-ttu-id="09971-102">指定服务的超时。</span><span class="sxs-lookup"><span data-stu-id="09971-102">Specifies the timeout for a service.</span></span>  
  
 <span data-ttu-id="09971-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="09971-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="09971-104">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="09971-104">\<behaviors></span></span>  
<span data-ttu-id="09971-105">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="09971-105">\<serviceBehaviors></span></span>  
<span data-ttu-id="09971-106">\<behavior></span><span class="sxs-lookup"><span data-stu-id="09971-106">\<behavior></span></span>  
<span data-ttu-id="09971-107">\<serviceTimeouts></span><span class="sxs-lookup"><span data-stu-id="09971-107">\<serviceTimeouts></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="09971-108">语法</span><span class="sxs-lookup"><span data-stu-id="09971-108">Syntax</span></span>  
  
```xml  
<serviceTimeouts transactionTimeout="TimeSpan" />
```  
  
## <a name="type"></a><span data-ttu-id="09971-109">类型</span><span class="sxs-lookup"><span data-stu-id="09971-109">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="09971-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="09971-110">Attributes and Elements</span></span>  
 <span data-ttu-id="09971-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="09971-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="09971-112">特性</span><span class="sxs-lookup"><span data-stu-id="09971-112">Attributes</span></span>  
  
|<span data-ttu-id="09971-113">特性</span><span class="sxs-lookup"><span data-stu-id="09971-113">Attribute</span></span>|<span data-ttu-id="09971-114">描述</span><span class="sxs-lookup"><span data-stu-id="09971-114">Description</span></span>|  
|---------------|-----------------|  
|`transactionTimeout`|<span data-ttu-id="09971-115">一个 <xref:System.TimeSpan> 值，指定事务从客户端流动到服务器所必须经历的时间间隔。</span><span class="sxs-lookup"><span data-stu-id="09971-115">A <xref:System.TimeSpan> value that specifies the interval of time a transaction must flow from client to server.</span></span> <span data-ttu-id="09971-116">默认值是"00: 00:00"。</span><span class="sxs-lookup"><span data-stu-id="09971-116">The default is "00:00:00".</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="09971-117">子元素</span><span class="sxs-lookup"><span data-stu-id="09971-117">Child Elements</span></span>  
 <span data-ttu-id="09971-118">无。</span><span class="sxs-lookup"><span data-stu-id="09971-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="09971-119">父元素</span><span class="sxs-lookup"><span data-stu-id="09971-119">Parent Elements</span></span>  
  
|<span data-ttu-id="09971-120">元素</span><span class="sxs-lookup"><span data-stu-id="09971-120">Element</span></span>|<span data-ttu-id="09971-121">描述</span><span class="sxs-lookup"><span data-stu-id="09971-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="09971-122">\<behavior></span><span class="sxs-lookup"><span data-stu-id="09971-122">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="09971-123">指定行为元素。</span><span class="sxs-lookup"><span data-stu-id="09971-123">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="09971-124">请参阅</span><span class="sxs-lookup"><span data-stu-id="09971-124">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServiceTimeoutsElement>
