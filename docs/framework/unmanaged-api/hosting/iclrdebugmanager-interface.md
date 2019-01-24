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
ms.openlocfilehash: 515eb0633c82c3e1386487d1866de79c9898c9cd
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54654602"
---
# <a name="iclrdebugmanager-interface"></a><span data-ttu-id="33c93-102">ICLRDebugManager 接口</span><span class="sxs-lookup"><span data-stu-id="33c93-102">ICLRDebugManager Interface</span></span>
<span data-ttu-id="33c93-103">提供允许主机以将一组任务标识符和友好名称与相关联的方法。</span><span class="sxs-lookup"><span data-stu-id="33c93-103">Provides methods that allow a host to associate a set of tasks with an identifier and a friendly name.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="33c93-104">方法</span><span class="sxs-lookup"><span data-stu-id="33c93-104">Methods</span></span>  
  
|<span data-ttu-id="33c93-105">方法</span><span class="sxs-lookup"><span data-stu-id="33c93-105">Method</span></span>|<span data-ttu-id="33c93-106">描述</span><span class="sxs-lookup"><span data-stu-id="33c93-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="33c93-107">BeginConnection 方法</span><span class="sxs-lookup"><span data-stu-id="33c93-107">BeginConnection Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-beginconnection-method.md)|<span data-ttu-id="33c93-108">建立新连接来将任务与标识符和友好名称相关联的主机与调试器之间。</span><span class="sxs-lookup"><span data-stu-id="33c93-108">Establishes a new connection between the host and the debugger to associate tasks with an identifier and a friendly name.</span></span>|  
|[<span data-ttu-id="33c93-109">EndConnection 方法</span><span class="sxs-lookup"><span data-stu-id="33c93-109">EndConnection Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-endconnection-method.md)|<span data-ttu-id="33c93-110">删除任务列表和标识符和友好名称之间的关联。</span><span class="sxs-lookup"><span data-stu-id="33c93-110">Removes the association between a list of tasks and an identifier and a friendly name.</span></span>|  
|[<span data-ttu-id="33c93-111">GetDacl 方法</span><span class="sxs-lookup"><span data-stu-id="33c93-111">GetDacl Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-getdacl-method.md)|<span data-ttu-id="33c93-112">未实现此方法。</span><span class="sxs-lookup"><span data-stu-id="33c93-112">This method is not implemented.</span></span>|  
|[<span data-ttu-id="33c93-113">IsDebuggerAttached 方法</span><span class="sxs-lookup"><span data-stu-id="33c93-113">IsDebuggerAttached Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-isdebuggerattached-method.md)|<span data-ttu-id="33c93-114">获取一个值，它指示调试器是否已附加到进程。</span><span class="sxs-lookup"><span data-stu-id="33c93-114">Gets a value that indicates whether a debugger is attached to the process.</span></span>|  
|[<span data-ttu-id="33c93-115">SetConnectionTasks 方法</span><span class="sxs-lookup"><span data-stu-id="33c93-115">SetConnectionTasks Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setconnectiontasks-method.md)|<span data-ttu-id="33c93-116">将一组相关联[ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)实例标识符和友好名称。</span><span class="sxs-lookup"><span data-stu-id="33c93-116">Associates a list of [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instances with an identifier and a friendly name.</span></span>|  
|[<span data-ttu-id="33c93-117">SetDacl 方法</span><span class="sxs-lookup"><span data-stu-id="33c93-117">SetDacl Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setdacl-method.md)|<span data-ttu-id="33c93-118">未实现此方法。</span><span class="sxs-lookup"><span data-stu-id="33c93-118">This method is not implemented.</span></span>|  
|[<span data-ttu-id="33c93-119">SetSymbolReadingPolicy 方法</span><span class="sxs-lookup"><span data-stu-id="33c93-119">SetSymbolReadingPolicy Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setsymbolreadingpolicy-method.md)|<span data-ttu-id="33c93-120">设置用于读取程序数据库 (PDB) 文件的策略。</span><span class="sxs-lookup"><span data-stu-id="33c93-120">Sets the policy for reading program database (PDB) files.</span></span> <span data-ttu-id="33c93-121">策略将确定是否在调用堆栈中包括行号和文件相关信息。</span><span class="sxs-lookup"><span data-stu-id="33c93-121">The policy determines whether information about line numbers and files is included in call stacks.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="33c93-122">备注</span><span class="sxs-lookup"><span data-stu-id="33c93-122">Remarks</span></span>  
 <span data-ttu-id="33c93-123">在调试方案中，主机可能需要根据其自己的编程逻辑组任务。</span><span class="sxs-lookup"><span data-stu-id="33c93-123">In debugging scenarios, a host might want to group tasks according to its own programming logic.</span></span> <span data-ttu-id="33c93-124">例如，一组将允许开发人员若要查看仅由开发人员的 Api，而不是查看在进程中运行的每项任务所需的任务。</span><span class="sxs-lookup"><span data-stu-id="33c93-124">For example, a grouping would allow a developer to see only the tasks required by the developer's APIs, instead of seeing every task running in the process.</span></span> <span data-ttu-id="33c93-125">`ICLRDebugManager` 允许主机来实现这种类型的分组。</span><span class="sxs-lookup"><span data-stu-id="33c93-125">`ICLRDebugManager` allows the host to implement this kind of grouping.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="33c93-126">三个`ICLRDebugManager`方法， `BeginConnection`，`SetConnectionTasks`和`EndConnection`，依赖于彼此。</span><span class="sxs-lookup"><span data-stu-id="33c93-126">Three `ICLRDebugManager` methods, `BeginConnection`, `SetConnectionTasks` and `EndConnection`, are dependent upon each other.</span></span> <span data-ttu-id="33c93-127">按给定的顺序按预期方式工作，必须调用它们。</span><span class="sxs-lookup"><span data-stu-id="33c93-127">They must be called in the given order to work as expected.</span></span>  
  
 <span data-ttu-id="33c93-128">分组的标识符和友好名称的主机分配给分组，具有对公共语言运行时 (CLR) 没有意义。</span><span class="sxs-lookup"><span data-stu-id="33c93-128">The grouping, and the identifiers and friendly names that the host assigns to the grouping, have no meaning for the common language runtime (CLR).</span></span> <span data-ttu-id="33c93-129">CLR 只是将信息传递到调试器。</span><span class="sxs-lookup"><span data-stu-id="33c93-129">The CLR merely passes the information along to the debugger.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="33c93-130">要求</span><span class="sxs-lookup"><span data-stu-id="33c93-130">Requirements</span></span>  
 <span data-ttu-id="33c93-131">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="33c93-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="33c93-132">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="33c93-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="33c93-133">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="33c93-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="33c93-134">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="33c93-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="33c93-135">请参阅</span><span class="sxs-lookup"><span data-stu-id="33c93-135">See also</span></span>
- [<span data-ttu-id="33c93-136">承载接口</span><span class="sxs-lookup"><span data-stu-id="33c93-136">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
