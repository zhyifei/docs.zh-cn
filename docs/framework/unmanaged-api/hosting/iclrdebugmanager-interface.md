---
title: "ICLRDebugManager 接口"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRDebugManager
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRDebugManager
helpviewer_keywords: ICLRDebugManager interface [.NET Framework hosting]
ms.assetid: e835062c-c7d6-4945-8a44-2de7ebf3928e
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 0e537b955524f2721868ddf5da9fccf68f9d4efd
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="iclrdebugmanager-interface"></a><span data-ttu-id="c592a-102">ICLRDebugManager 接口</span><span class="sxs-lookup"><span data-stu-id="c592a-102">ICLRDebugManager Interface</span></span>
<span data-ttu-id="c592a-103">提供使主机可将一组任务标识符和友好名称与相关联的方法。</span><span class="sxs-lookup"><span data-stu-id="c592a-103">Provides methods that allow a host to associate a set of tasks with an identifier and a friendly name.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="c592a-104">方法</span><span class="sxs-lookup"><span data-stu-id="c592a-104">Methods</span></span>  
  
|<span data-ttu-id="c592a-105">方法</span><span class="sxs-lookup"><span data-stu-id="c592a-105">Method</span></span>|<span data-ttu-id="c592a-106">描述</span><span class="sxs-lookup"><span data-stu-id="c592a-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="c592a-107">BeginConnection 方法</span><span class="sxs-lookup"><span data-stu-id="c592a-107">BeginConnection Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-beginconnection-method.md)|<span data-ttu-id="c592a-108">建立新连接在主机和调试器要与任务关联的友好名称标识符与之间。</span><span class="sxs-lookup"><span data-stu-id="c592a-108">Establishes a new connection between the host and the debugger to associate tasks with an identifier and a friendly name.</span></span>|  
|[<span data-ttu-id="c592a-109">EndConnection 方法</span><span class="sxs-lookup"><span data-stu-id="c592a-109">EndConnection Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-endconnection-method.md)|<span data-ttu-id="c592a-110">删除的任务列表和标识符和友好名称之间的关联。</span><span class="sxs-lookup"><span data-stu-id="c592a-110">Removes the association between a list of tasks and an identifier and a friendly name.</span></span>|  
|[<span data-ttu-id="c592a-111">GetDacl 方法</span><span class="sxs-lookup"><span data-stu-id="c592a-111">GetDacl Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-getdacl-method.md)|<span data-ttu-id="c592a-112">未实现此方法。</span><span class="sxs-lookup"><span data-stu-id="c592a-112">This method is not implemented.</span></span>|  
|[<span data-ttu-id="c592a-113">IsDebuggerAttached 方法</span><span class="sxs-lookup"><span data-stu-id="c592a-113">IsDebuggerAttached Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-isdebuggerattached-method.md)|<span data-ttu-id="c592a-114">获取一个值，它指示调试器是否已附加到进程。</span><span class="sxs-lookup"><span data-stu-id="c592a-114">Gets a value that indicates whether a debugger is attached to the process.</span></span>|  
|[<span data-ttu-id="c592a-115">SetConnectionTasks 方法</span><span class="sxs-lookup"><span data-stu-id="c592a-115">SetConnectionTasks Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setconnectiontasks-method.md)|<span data-ttu-id="c592a-116">将相关联的列表[ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)标识符并具有友好名称的实例。</span><span class="sxs-lookup"><span data-stu-id="c592a-116">Associates a list of [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instances with an identifier and a friendly name.</span></span>|  
|[<span data-ttu-id="c592a-117">SetDacl 方法</span><span class="sxs-lookup"><span data-stu-id="c592a-117">SetDacl Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setdacl-method.md)|<span data-ttu-id="c592a-118">未实现此方法。</span><span class="sxs-lookup"><span data-stu-id="c592a-118">This method is not implemented.</span></span>|  
|[<span data-ttu-id="c592a-119">SetSymbolReadingPolicy 方法</span><span class="sxs-lookup"><span data-stu-id="c592a-119">SetSymbolReadingPolicy Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setsymbolreadingpolicy-method.md)|<span data-ttu-id="c592a-120">设置用于读取程序数据库 (PDB) 文件的策略。</span><span class="sxs-lookup"><span data-stu-id="c592a-120">Sets the policy for reading program database (PDB) files.</span></span> <span data-ttu-id="c592a-121">策略将确定调用堆栈中是否包括行号和文件有关的信息。</span><span class="sxs-lookup"><span data-stu-id="c592a-121">The policy determines whether information about line numbers and files is included in call stacks.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c592a-122">备注</span><span class="sxs-lookup"><span data-stu-id="c592a-122">Remarks</span></span>  
 <span data-ttu-id="c592a-123">在调试方案中，宿主可能需要对任务进行分组根据其自己的编程逻辑。</span><span class="sxs-lookup"><span data-stu-id="c592a-123">In debugging scenarios, a host might want to group tasks according to its own programming logic.</span></span> <span data-ttu-id="c592a-124">例如，分组将允许开发人员以查看开发人员 Api，而不是在进程中运行的每项任务所需的任务。</span><span class="sxs-lookup"><span data-stu-id="c592a-124">For example, a grouping would allow a developer to see only the tasks required by the developer's APIs, instead of seeing every task running in the process.</span></span> <span data-ttu-id="c592a-125">`ICLRDebugManager`允许宿主实现这种分组。</span><span class="sxs-lookup"><span data-stu-id="c592a-125">`ICLRDebugManager` allows the host to implement this kind of grouping.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="c592a-126">三个`ICLRDebugManager`方法， `BeginConnection`，`SetConnectionTasks`和`EndConnection`，依赖于彼此。</span><span class="sxs-lookup"><span data-stu-id="c592a-126">Three `ICLRDebugManager` methods, `BeginConnection`, `SetConnectionTasks` and `EndConnection`, are dependent upon each other.</span></span> <span data-ttu-id="c592a-127">在给定的顺序，以便按预期方式工作，必须调用它们。</span><span class="sxs-lookup"><span data-stu-id="c592a-127">They must be called in the given order to work as expected.</span></span>  
  
 <span data-ttu-id="c592a-128">分组的标识符和主机分配给分组的友好名称具有对公共语言运行时 (CLR) 没有意义。</span><span class="sxs-lookup"><span data-stu-id="c592a-128">The grouping, and the identifiers and friendly names that the host assigns to the grouping, have no meaning for the common language runtime (CLR).</span></span> <span data-ttu-id="c592a-129">CLR 仅将信息传递给该调试器。</span><span class="sxs-lookup"><span data-stu-id="c592a-129">The CLR merely passes the information along to the debugger.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c592a-130">要求</span><span class="sxs-lookup"><span data-stu-id="c592a-130">Requirements</span></span>  
 <span data-ttu-id="c592a-131">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="c592a-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c592a-132">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="c592a-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c592a-133">**库：**作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="c592a-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c592a-134">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c592a-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c592a-135">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c592a-135">See Also</span></span>  
 [<span data-ttu-id="c592a-136">承载接口</span><span class="sxs-lookup"><span data-stu-id="c592a-136">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
