---
title: <serviceTimeouts>
ms.date: 03/30/2017
ms.assetid: ada536cf-97dc-4cd7-89ec-ed1466c1c557
ms.openlocfilehash: b67ea137e6c116d00a8a098b9c0df99430114dc5
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/30/2019
ms.locfileid: "55267279"
---
# <a name="servicetimeouts"></a><span data-ttu-id="3dc01-101">\<serviceTimeouts></span><span class="sxs-lookup"><span data-stu-id="3dc01-101">\<serviceTimeouts></span></span>
<span data-ttu-id="3dc01-102">指定服务的超时。</span><span class="sxs-lookup"><span data-stu-id="3dc01-102">Specifies the timeout for a service.</span></span>  
  
 <span data-ttu-id="3dc01-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="3dc01-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="3dc01-104">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="3dc01-104">\<behaviors></span></span>  
<span data-ttu-id="3dc01-105">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="3dc01-105">\<serviceBehaviors></span></span>  
<span data-ttu-id="3dc01-106">\<behavior></span><span class="sxs-lookup"><span data-stu-id="3dc01-106">\<behavior></span></span>  
<span data-ttu-id="3dc01-107">\<serviceTimeouts></span><span class="sxs-lookup"><span data-stu-id="3dc01-107">\<serviceTimeouts></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3dc01-108">语法</span><span class="sxs-lookup"><span data-stu-id="3dc01-108">Syntax</span></span>  
  
```xml  
<serviceTimeouts transactionTimeout="TimeSpan" />
```  
  
## <a name="type"></a><span data-ttu-id="3dc01-109">类型</span><span class="sxs-lookup"><span data-stu-id="3dc01-109">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3dc01-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="3dc01-110">Attributes and Elements</span></span>  
 <span data-ttu-id="3dc01-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="3dc01-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3dc01-112">特性</span><span class="sxs-lookup"><span data-stu-id="3dc01-112">Attributes</span></span>  
  
|<span data-ttu-id="3dc01-113">特性</span><span class="sxs-lookup"><span data-stu-id="3dc01-113">Attribute</span></span>|<span data-ttu-id="3dc01-114">描述</span><span class="sxs-lookup"><span data-stu-id="3dc01-114">Description</span></span>|  
|---------------|-----------------|  
|`transactionTimeout`|<span data-ttu-id="3dc01-115">一个 <xref:System.TimeSpan> 值，指定事务从客户端流动到服务器所必须经历的时间间隔。</span><span class="sxs-lookup"><span data-stu-id="3dc01-115">A <xref:System.TimeSpan> value that specifies the interval of time a transaction must flow from client to server.</span></span> <span data-ttu-id="3dc01-116">默认值是"00: 00:00"。</span><span class="sxs-lookup"><span data-stu-id="3dc01-116">The default is "00:00:00".</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3dc01-117">子元素</span><span class="sxs-lookup"><span data-stu-id="3dc01-117">Child Elements</span></span>  
 <span data-ttu-id="3dc01-118">无。</span><span class="sxs-lookup"><span data-stu-id="3dc01-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="3dc01-119">父元素</span><span class="sxs-lookup"><span data-stu-id="3dc01-119">Parent Elements</span></span>  
  
|<span data-ttu-id="3dc01-120">元素</span><span class="sxs-lookup"><span data-stu-id="3dc01-120">Element</span></span>|<span data-ttu-id="3dc01-121">描述</span><span class="sxs-lookup"><span data-stu-id="3dc01-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3dc01-122">\<behavior></span><span class="sxs-lookup"><span data-stu-id="3dc01-122">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="3dc01-123">指定行为元素。</span><span class="sxs-lookup"><span data-stu-id="3dc01-123">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="3dc01-124">请参阅</span><span class="sxs-lookup"><span data-stu-id="3dc01-124">See also</span></span>
- <xref:System.ServiceModel.Configuration.ServiceTimeoutsElement>
