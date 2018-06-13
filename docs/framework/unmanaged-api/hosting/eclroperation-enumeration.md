---
title: EClrOperation 枚举
ms.date: 03/30/2017
api_name:
- EClrOperation
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- EClrOperation
helpviewer_keywords:
- EClrOperation enumeration [.NET Framework hosting]
ms.assetid: 5aef6808-5aac-4b2f-a2c7-fee1575c55ed
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4b18c89cee0c3f5088a9978e448a0d61de1b9848
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33434240"
---
# <a name="eclroperation-enumeration"></a><span data-ttu-id="0e5cf-102">EClrOperation 枚举</span><span class="sxs-lookup"><span data-stu-id="0e5cf-102">EClrOperation Enumeration</span></span>
<span data-ttu-id="0e5cf-103">介绍一的组主机可以为其应用策略操作的操作。</span><span class="sxs-lookup"><span data-stu-id="0e5cf-103">Describes the set of operations for which a host can apply policy actions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0e5cf-104">语法</span><span class="sxs-lookup"><span data-stu-id="0e5cf-104">Syntax</span></span>  
  
```  
typedef enum {  
    OPR_ThreadAbort,  
    OPR_ThreadRudeAbortInNonCriticalRegion,  
    OPR_ThreadRudeAbortInCriticalRegion,  
    OPR_AppDomainUnload,  
    OPR_AppDomainRudeUnload,  
    OPR_ProcessExit,  
    OPR_FinalizerRun  
} EClrOperation;  
```  
  
## <a name="members"></a><span data-ttu-id="0e5cf-105">成员</span><span class="sxs-lookup"><span data-stu-id="0e5cf-105">Members</span></span>  
  
|<span data-ttu-id="0e5cf-106">成员</span><span class="sxs-lookup"><span data-stu-id="0e5cf-106">Member</span></span>|<span data-ttu-id="0e5cf-107">描述</span><span class="sxs-lookup"><span data-stu-id="0e5cf-107">Description</span></span>|  
|------------|-----------------|  
|`OPR_AppDomainRudeUnload`|<span data-ttu-id="0e5cf-108">主机可以指定策略操作时所要采取<xref:System.AppDomain>卸载的非正常的 （强制） 方式。</span><span class="sxs-lookup"><span data-stu-id="0e5cf-108">The host can specify policy actions to be taken when an <xref:System.AppDomain> is unloaded in a non-graceful (rude) manner.</span></span>|  
|`OPR_AppDomainUnload`|<span data-ttu-id="0e5cf-109">主机可以指定策略操作时所要采取<xref:System.AppDomain>卸载。</span><span class="sxs-lookup"><span data-stu-id="0e5cf-109">The host can specify policy actions to be taken when an <xref:System.AppDomain> is unloaded.</span></span>|  
|`OPR_FinalizerRun`|<span data-ttu-id="0e5cf-110">主机可以指定要执行终结器运行时策略操作。</span><span class="sxs-lookup"><span data-stu-id="0e5cf-110">The host can specify policy actions to be taken when finalizers run.</span></span>|  
|`OPR_ProcessExit`|<span data-ttu-id="0e5cf-111">主机可以指定在进程退出时要执行策略操作。</span><span class="sxs-lookup"><span data-stu-id="0e5cf-111">The host can specify policy actions to be taken when the process exits.</span></span>|  
|`OPR_ThreadAbort`|<span data-ttu-id="0e5cf-112">主机可以指定策略中止线程时要执行操作。</span><span class="sxs-lookup"><span data-stu-id="0e5cf-112">The host can specify policy actions to be taken when a thread is aborted.</span></span>|  
|`OPR_ThreadRudeAbortInCriticalRegion`|<span data-ttu-id="0e5cf-113">主机可以指定策略强制中止线程代码的关键区域中发生时要执行操作。</span><span class="sxs-lookup"><span data-stu-id="0e5cf-113">The host can specify policy actions to be taken when a rude thread abort occurs in a critical region of code.</span></span>|  
|`OPR_ThreadRudeAbortInNonCriticalRegion`|<span data-ttu-id="0e5cf-114">主机可以指定策略强制中止线程代码的非关键区域中发生时所采取的操作。</span><span class="sxs-lookup"><span data-stu-id="0e5cf-114">The host can specify policy actions to be take when a rude thread abort occurs in a non-critical region of code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0e5cf-115">备注</span><span class="sxs-lookup"><span data-stu-id="0e5cf-115">Remarks</span></span>  
 <span data-ttu-id="0e5cf-116">公共语言运行时 (CLR) 可靠性基础结构将区分中止和资源的代码和那些出现的代码的非关键区域中的关键区域中发生的分配失败。</span><span class="sxs-lookup"><span data-stu-id="0e5cf-116">The common language runtime (CLR) reliability infrastructure distinguishes between aborts and resource allocation failures that occur in critical regions of code and those that occur in non-critical regions of code.</span></span> <span data-ttu-id="0e5cf-117">这一区别设计用于允许宿主能够设置不同的策略，具体取决于代码中发生故障。</span><span class="sxs-lookup"><span data-stu-id="0e5cf-117">This distinction is designed to allow hosts to set different policies depending on where a failure occurs in the code.</span></span>  
  
 <span data-ttu-id="0e5cf-118">A*关键代码区域*是任何区域，CLR 不能保证该中止任务或无法完成请求的资源将影响当前的任务。</span><span class="sxs-lookup"><span data-stu-id="0e5cf-118">A *critical region of code* is any space where the CLR cannot guarantee that aborting a task or failing to complete a request for resources will affect only the current task.</span></span> <span data-ttu-id="0e5cf-119">例如，如果任务持有的锁，并且收到一个 HRESULT，指示在发出内存分配请求时失败，它是不足仅仅是为了中止该任务以确保的稳定性<xref:System.AppDomain>，这是因为<xref:System.AppDomain>可能包含其他等待同一个锁的任务。</span><span class="sxs-lookup"><span data-stu-id="0e5cf-119">For example, if a task is holding a lock and receives an HRESULT that indicates failure upon making a memory allocation request, it is insufficient simply to abort that task to ensure the stability of the <xref:System.AppDomain>, because the <xref:System.AppDomain> might contain other tasks waiting for the same lock.</span></span> <span data-ttu-id="0e5cf-120">放弃当前任务可能会导致其他任务来停止响应 （或挂起）; 如果无限期。</span><span class="sxs-lookup"><span data-stu-id="0e5cf-120">To abandon the current task might cause those other tasks to stop responding (or hang) indefinitely.</span></span> <span data-ttu-id="0e5cf-121">在这种情况下，主机需要能够将卸载整个<xref:System.AppDomain>而不是风险潜在的不稳定性。</span><span class="sxs-lookup"><span data-stu-id="0e5cf-121">In such a case, the host needs the ability to unload the entire <xref:System.AppDomain> rather than risk potential instability.</span></span>  
  
 <span data-ttu-id="0e5cf-122">A*的代码的非关键区域*，另一方面，是，CLR 可以保证仅在其出错的任务，将会中止或失败影响的区域。</span><span class="sxs-lookup"><span data-stu-id="0e5cf-122">A *non-critical region of code*, on the other hand, is a region where the CLR can guarantee that an abort or a failure will affect only the task upon which the error occurs.</span></span>  
  
 <span data-ttu-id="0e5cf-123">CLR 还区分中止正常和非正常 （强制） 中止。</span><span class="sxs-lookup"><span data-stu-id="0e5cf-123">The CLR also distinguishes between graceful and non-graceful (rude) aborts.</span></span> <span data-ttu-id="0e5cf-124">一般情况下，正常中止使各种方法，以便中止任务，而强制中止则没有此类保证之前运行异常处理例程和终结器。</span><span class="sxs-lookup"><span data-stu-id="0e5cf-124">In general, a normal or graceful abort makes every effort to run exception-handling routines and finalizers before aborting a task, while a rude abort makes no such guarantees.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0e5cf-125">要求</span><span class="sxs-lookup"><span data-stu-id="0e5cf-125">Requirements</span></span>  
 <span data-ttu-id="0e5cf-126">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="0e5cf-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0e5cf-127">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="0e5cf-127">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="0e5cf-128">**库：** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="0e5cf-128">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0e5cf-129">**.NET framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0e5cf-129">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0e5cf-130">请参阅</span><span class="sxs-lookup"><span data-stu-id="0e5cf-130">See Also</span></span>  
 [<span data-ttu-id="0e5cf-131">EClrFailure 枚举</span><span class="sxs-lookup"><span data-stu-id="0e5cf-131">EClrFailure Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md)  
 [<span data-ttu-id="0e5cf-132">EPolicyAction 枚举</span><span class="sxs-lookup"><span data-stu-id="0e5cf-132">EPolicyAction Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md)  
 [<span data-ttu-id="0e5cf-133">ICLRPolicyManager 接口</span><span class="sxs-lookup"><span data-stu-id="0e5cf-133">ICLRPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)  
 [<span data-ttu-id="0e5cf-134">IHostPolicyManager 接口</span><span class="sxs-lookup"><span data-stu-id="0e5cf-134">IHostPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-interface.md)  
 [<span data-ttu-id="0e5cf-135">承载枚举</span><span class="sxs-lookup"><span data-stu-id="0e5cf-135">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
