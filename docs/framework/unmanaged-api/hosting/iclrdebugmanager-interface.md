---
title: ICLRDebugManager 接口
ms.date: 03/30/2017
api_name:
- ICLRDebugManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRDebugManager
helpviewer_keywords:
- ICLRDebugManager interface [.NET Framework hosting]
ms.assetid: e835062c-c7d6-4945-8a44-2de7ebf3928e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5a408995793caf879f8d5624ab727102c4859195
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69959616"
---
# <a name="iclrdebugmanager-interface"></a><span data-ttu-id="8b2cf-102">ICLRDebugManager 接口</span><span class="sxs-lookup"><span data-stu-id="8b2cf-102">ICLRDebugManager Interface</span></span>
<span data-ttu-id="8b2cf-103">提供允许主机将一组任务与标识符和友好名称关联的方法。</span><span class="sxs-lookup"><span data-stu-id="8b2cf-103">Provides methods that allow a host to associate a set of tasks with an identifier and a friendly name.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="8b2cf-104">方法</span><span class="sxs-lookup"><span data-stu-id="8b2cf-104">Methods</span></span>  
  
|<span data-ttu-id="8b2cf-105">方法</span><span class="sxs-lookup"><span data-stu-id="8b2cf-105">Method</span></span>|<span data-ttu-id="8b2cf-106">描述</span><span class="sxs-lookup"><span data-stu-id="8b2cf-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="8b2cf-107">BeginConnection 方法</span><span class="sxs-lookup"><span data-stu-id="8b2cf-107">BeginConnection Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-beginconnection-method.md)|<span data-ttu-id="8b2cf-108">在宿主和调试器之间建立新的连接, 以将任务与标识符和友好名称关联起来。</span><span class="sxs-lookup"><span data-stu-id="8b2cf-108">Establishes a new connection between the host and the debugger to associate tasks with an identifier and a friendly name.</span></span>|  
|[<span data-ttu-id="8b2cf-109">EndConnection 方法</span><span class="sxs-lookup"><span data-stu-id="8b2cf-109">EndConnection Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-endconnection-method.md)|<span data-ttu-id="8b2cf-110">删除任务列表与标识符和友好名称之间的关联。</span><span class="sxs-lookup"><span data-stu-id="8b2cf-110">Removes the association between a list of tasks and an identifier and a friendly name.</span></span>|  
|[<span data-ttu-id="8b2cf-111">GetDacl 方法</span><span class="sxs-lookup"><span data-stu-id="8b2cf-111">GetDacl Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-getdacl-method.md)|<span data-ttu-id="8b2cf-112">未实现此方法。</span><span class="sxs-lookup"><span data-stu-id="8b2cf-112">This method is not implemented.</span></span>|  
|[<span data-ttu-id="8b2cf-113">IsDebuggerAttached 方法</span><span class="sxs-lookup"><span data-stu-id="8b2cf-113">IsDebuggerAttached Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-isdebuggerattached-method.md)|<span data-ttu-id="8b2cf-114">获取一个值，它指示调试器是否已附加到进程。</span><span class="sxs-lookup"><span data-stu-id="8b2cf-114">Gets a value that indicates whether a debugger is attached to the process.</span></span>|  
|[<span data-ttu-id="8b2cf-115">SetConnectionTasks 方法</span><span class="sxs-lookup"><span data-stu-id="8b2cf-115">SetConnectionTasks Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setconnectiontasks-method.md)|<span data-ttu-id="8b2cf-116">将[ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)实例列表与标识符和友好名称关联。</span><span class="sxs-lookup"><span data-stu-id="8b2cf-116">Associates a list of [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instances with an identifier and a friendly name.</span></span>|  
|[<span data-ttu-id="8b2cf-117">SetDacl 方法</span><span class="sxs-lookup"><span data-stu-id="8b2cf-117">SetDacl Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setdacl-method.md)|<span data-ttu-id="8b2cf-118">未实现此方法。</span><span class="sxs-lookup"><span data-stu-id="8b2cf-118">This method is not implemented.</span></span>|  
|[<span data-ttu-id="8b2cf-119">SetSymbolReadingPolicy 方法</span><span class="sxs-lookup"><span data-stu-id="8b2cf-119">SetSymbolReadingPolicy Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setsymbolreadingpolicy-method.md)|<span data-ttu-id="8b2cf-120">设置用于读取程序数据库 (PDB) 文件的策略。</span><span class="sxs-lookup"><span data-stu-id="8b2cf-120">Sets the policy for reading program database (PDB) files.</span></span> <span data-ttu-id="8b2cf-121">策略确定有关行号和文件的信息是否包含在调用堆栈中。</span><span class="sxs-lookup"><span data-stu-id="8b2cf-121">The policy determines whether information about line numbers and files is included in call stacks.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8b2cf-122">备注</span><span class="sxs-lookup"><span data-stu-id="8b2cf-122">Remarks</span></span>  
 <span data-ttu-id="8b2cf-123">在调试方案中, 主机可能需要根据任务自己的编程逻辑对任务进行分组。</span><span class="sxs-lookup"><span data-stu-id="8b2cf-123">In debugging scenarios, a host might want to group tasks according to its own programming logic.</span></span> <span data-ttu-id="8b2cf-124">例如, 分组允许开发人员仅查看开发人员的 Api 所需的任务, 而不是查看在进程中运行的每个任务。</span><span class="sxs-lookup"><span data-stu-id="8b2cf-124">For example, a grouping would allow a developer to see only the tasks required by the developer's APIs, instead of seeing every task running in the process.</span></span> <span data-ttu-id="8b2cf-125">`ICLRDebugManager`允许宿主实现这种分组。</span><span class="sxs-lookup"><span data-stu-id="8b2cf-125">`ICLRDebugManager` allows the host to implement this kind of grouping.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="8b2cf-126">三`ICLRDebugManager`个方法`BeginConnection` (和`EndConnection`)相互依赖。 `SetConnectionTasks`</span><span class="sxs-lookup"><span data-stu-id="8b2cf-126">Three `ICLRDebugManager` methods, `BeginConnection`, `SetConnectionTasks` and `EndConnection`, are dependent upon each other.</span></span> <span data-ttu-id="8b2cf-127">必须按给定顺序调用它们才能按预期方式工作。</span><span class="sxs-lookup"><span data-stu-id="8b2cf-127">They must be called in the given order to work as expected.</span></span>  
  
 <span data-ttu-id="8b2cf-128">对于公共语言运行时 (CLR), 分组以及宿主分配给分组的标识符和友好名称没有任何意义。</span><span class="sxs-lookup"><span data-stu-id="8b2cf-128">The grouping, and the identifiers and friendly names that the host assigns to the grouping, have no meaning for the common language runtime (CLR).</span></span> <span data-ttu-id="8b2cf-129">CLR 只会将信息传递到调试器。</span><span class="sxs-lookup"><span data-stu-id="8b2cf-129">The CLR merely passes the information along to the debugger.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8b2cf-130">要求</span><span class="sxs-lookup"><span data-stu-id="8b2cf-130">Requirements</span></span>  
 <span data-ttu-id="8b2cf-131">**适用**请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="8b2cf-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8b2cf-132">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="8b2cf-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="8b2cf-133">**类库**作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="8b2cf-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8b2cf-134">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8b2cf-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8b2cf-135">请参阅</span><span class="sxs-lookup"><span data-stu-id="8b2cf-135">See also</span></span>

- [<span data-ttu-id="8b2cf-136">承载接口</span><span class="sxs-lookup"><span data-stu-id="8b2cf-136">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
