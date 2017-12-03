---
title: ServiceThrottlingBehavior
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 37b9e517-1f1f-4ec4-9fcb-2b8016794f5b
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 59f85a148d6707876a4df512d5cfbd07ca0e54b7
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="servicethrottlingbehavior"></a><span data-ttu-id="2372d-102">ServiceThrottlingBehavior</span><span class="sxs-lookup"><span data-stu-id="2372d-102">ServiceThrottlingBehavior</span></span>
<span data-ttu-id="2372d-103">ServiceThrottlingBehavior</span><span class="sxs-lookup"><span data-stu-id="2372d-103">ServiceThrottlingBehavior</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2372d-104">语法</span><span class="sxs-lookup"><span data-stu-id="2372d-104">Syntax</span></span>  
  
```  
class ServiceThrottlingBehavior : Behavior  
{  
  sint32 MaxConcurrentCalls;  
  sint32 MaxConcurrentInstances;  
  sint32 MaxConcurrentSessions;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="2372d-105">方法</span><span class="sxs-lookup"><span data-stu-id="2372d-105">Methods</span></span>  
 <span data-ttu-id="2372d-106">ServiceThrottlingBehavior 类未定义任何方法。</span><span class="sxs-lookup"><span data-stu-id="2372d-106">The ServiceThrottlingBehavior class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="2372d-107">属性</span><span class="sxs-lookup"><span data-stu-id="2372d-107">Properties</span></span>  
 <span data-ttu-id="2372d-108">ServiceThrottlingBehavior 类有以下属性：</span><span class="sxs-lookup"><span data-stu-id="2372d-108">The ServiceThrottlingBehavior class has the following properties:</span></span>  
  
### <a name="maxconcurrentcalls"></a><span data-ttu-id="2372d-109">MaxConcurrentCalls</span><span class="sxs-lookup"><span data-stu-id="2372d-109">MaxConcurrentCalls</span></span>  
 <span data-ttu-id="2372d-110">数据类型：sint32</span><span class="sxs-lookup"><span data-stu-id="2372d-110">Data type: sint32</span></span>  
  
 <span data-ttu-id="2372d-111">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="2372d-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="2372d-112">ServiceHost 中所有调度程序对象正在积极处理的消息的最大数量。</span><span class="sxs-lookup"><span data-stu-id="2372d-112">The maximum number of messages actively processing across all dispatcher objects in a ServiceHost.</span></span>  
  
### <a name="maxconcurrentinstances"></a><span data-ttu-id="2372d-113">MaxConcurrentInstances</span><span class="sxs-lookup"><span data-stu-id="2372d-113">MaxConcurrentInstances</span></span>  
 <span data-ttu-id="2372d-114">数据类型：sint32</span><span class="sxs-lookup"><span data-stu-id="2372d-114">Data type: sint32</span></span>  
  
 <span data-ttu-id="2372d-115">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="2372d-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="2372d-116">一次可执行的服务对象的最大数量。</span><span class="sxs-lookup"><span data-stu-id="2372d-116">The maximum number of service objects that can execute at one time.</span></span>  
  
### <a name="maxconcurrentsessions"></a><span data-ttu-id="2372d-117">MaxConcurrentSessions</span><span class="sxs-lookup"><span data-stu-id="2372d-117">MaxConcurrentSessions</span></span>  
 <span data-ttu-id="2372d-118">数据类型：sint32</span><span class="sxs-lookup"><span data-stu-id="2372d-118">Data type: sint32</span></span>  
  
 <span data-ttu-id="2372d-119">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="2372d-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="2372d-120">主机一次可接受的最大会话数。</span><span class="sxs-lookup"><span data-stu-id="2372d-120">The maximum number of sessions a host can accept at one time.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2372d-121">要求</span><span class="sxs-lookup"><span data-stu-id="2372d-121">Requirements</span></span>  
  
|<span data-ttu-id="2372d-122">MOF</span><span class="sxs-lookup"><span data-stu-id="2372d-122">MOF</span></span>|<span data-ttu-id="2372d-123">已在 Servicemodel.mof 中声明。</span><span class="sxs-lookup"><span data-stu-id="2372d-123">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="2372d-124">命名空间</span><span class="sxs-lookup"><span data-stu-id="2372d-124">Namespace</span></span>|<span data-ttu-id="2372d-125">已在 root\ServiceModel 中定义</span><span class="sxs-lookup"><span data-stu-id="2372d-125">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="2372d-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2372d-126">See Also</span></span>  
 <xref:System.ServiceModel.Description.ServiceThrottlingBehavior>
