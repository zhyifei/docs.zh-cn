---
title: '&lt;persistenceProvider&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a37049c5-a7ea-4519-94f2-912eeb010380
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 447384ef34c1ca2c7e641f0ba0d3d3718139e579
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="ltpersistenceprovidergt"></a><span data-ttu-id="d35bf-102">&lt;persistenceProvider&gt;</span><span class="sxs-lookup"><span data-stu-id="d35bf-102">&lt;persistenceProvider&gt;</span></span>
<span data-ttu-id="d35bf-103">指定要使用的持久性提供程序实现的类型以及用于持久性操作的超时值。</span><span class="sxs-lookup"><span data-stu-id="d35bf-103">Specifies the type of the persistence provider implementation to use, as well as the time-out to use for persistence operations.</span></span>  
  
 <span data-ttu-id="d35bf-104">\<系统。ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="d35bf-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="d35bf-105">\<行为 ></span><span class="sxs-lookup"><span data-stu-id="d35bf-105">\<behaviors></span></span>  
<span data-ttu-id="d35bf-106">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="d35bf-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="d35bf-107">\<行为 ></span><span class="sxs-lookup"><span data-stu-id="d35bf-107">\<behavior></span></span>  
<span data-ttu-id="d35bf-108">\<persistenceProvider ></span><span class="sxs-lookup"><span data-stu-id="d35bf-108">\<persistenceProvider></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d35bf-109">语法</span><span class="sxs-lookup"><span data-stu-id="d35bf-109">Syntax</span></span>  
  
```xml  
<persistenceProvider persistenceOperationTimeout="TimeSpan"  
   type="String" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d35bf-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="d35bf-110">Attributes and Elements</span></span>  
 <span data-ttu-id="d35bf-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="d35bf-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d35bf-112">特性</span><span class="sxs-lookup"><span data-stu-id="d35bf-112">Attributes</span></span>  
  
|<span data-ttu-id="d35bf-113">特性</span><span class="sxs-lookup"><span data-stu-id="d35bf-113">Attribute</span></span>|<span data-ttu-id="d35bf-114">描述</span><span class="sxs-lookup"><span data-stu-id="d35bf-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="d35bf-115">persistenceOperationTimeout</span><span class="sxs-lookup"><span data-stu-id="d35bf-115">persistenceOperationTimeout</span></span>|<span data-ttu-id="d35bf-116">一个 <xref:System.TimeSpan> 值，指定用于持久性操作的超时值。</span><span class="sxs-lookup"><span data-stu-id="d35bf-116">A <xref:System.TimeSpan> value that specifies the time-out used for persistence operations.</span></span> <span data-ttu-id="d35bf-117">默认值为"00: 00:30"。</span><span class="sxs-lookup"><span data-stu-id="d35bf-117">The default is "00:00:30".</span></span>|  
|<span data-ttu-id="d35bf-118">类型</span><span class="sxs-lookup"><span data-stu-id="d35bf-118">type</span></span>|<span data-ttu-id="d35bf-119">一个字符串，指定要使用的永久性提供程序工厂的类型。</span><span class="sxs-lookup"><span data-stu-id="d35bf-119">A string that specifies the type of the persistence provider factory to use.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d35bf-120">子元素</span><span class="sxs-lookup"><span data-stu-id="d35bf-120">Child Elements</span></span>  
 <span data-ttu-id="d35bf-121">无。</span><span class="sxs-lookup"><span data-stu-id="d35bf-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="d35bf-122">父元素</span><span class="sxs-lookup"><span data-stu-id="d35bf-122">Parent Elements</span></span>  
  
|<span data-ttu-id="d35bf-123">元素</span><span class="sxs-lookup"><span data-stu-id="d35bf-123">Element</span></span>|<span data-ttu-id="d35bf-124">描述</span><span class="sxs-lookup"><span data-stu-id="d35bf-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d35bf-125">\<行为 ></span><span class="sxs-lookup"><span data-stu-id="d35bf-125">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="d35bf-126">指定行为元素。</span><span class="sxs-lookup"><span data-stu-id="d35bf-126">Specifies a behavior element.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d35bf-127">备注</span><span class="sxs-lookup"><span data-stu-id="d35bf-127">Remarks</span></span>  
 <span data-ttu-id="d35bf-128">此元素指定要用于序列化 WCF 服务的状态的永久性提供程序。</span><span class="sxs-lookup"><span data-stu-id="d35bf-128">This element specifies the persistence provider to be used to serialize the state of a WCF service.</span></span> <span data-ttu-id="d35bf-129">它应该与 `wsHttpContextBinding` 一起使用，后者在 HTTP 头中传递状态信息。</span><span class="sxs-lookup"><span data-stu-id="d35bf-129">It should be used together with the `wsHttpContextBinding` which passes state information in HTTP headers.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d35bf-130">请参阅</span><span class="sxs-lookup"><span data-stu-id="d35bf-130">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.PersistenceProviderElement>  
 <xref:System.ServiceModel.Persistence.PersistenceProvider>
