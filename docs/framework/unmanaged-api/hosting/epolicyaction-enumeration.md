---
title: EPolicyAction 枚举
ms.date: 03/30/2017
api_name:
- EPolicyAction
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- EPolicyAction
helpviewer_keywords:
- EPolicyAction enumeration [.NET Framework hosting]
ms.assetid: 72dd76ba-239e-45ac-9ded-318fb07d6c6d
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 75bd7da67cbac958f0b34c8295454a719962c7ed
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61628712"
---
# <a name="epolicyaction-enumeration"></a><span data-ttu-id="83315-102">EPolicyAction 枚举</span><span class="sxs-lookup"><span data-stu-id="83315-102">EPolicyAction Enumeration</span></span>
<span data-ttu-id="83315-103">描述主机可以为通过所述的操作设置的策略操作[EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md)和所描述的失败[EClrFailure](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md)。</span><span class="sxs-lookup"><span data-stu-id="83315-103">Describes the policy actions the host can set for operations described by [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) and failures described by [EClrFailure](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="83315-104">语法</span><span class="sxs-lookup"><span data-stu-id="83315-104">Syntax</span></span>  
  
```  
typedef enum {  
    eNoAction,  
    eThrowException,  
    eAbortThread,  
    eRudeAbortThread,  
    eUnloadAppDomain,  
    eRudeUnloadAppDomain,  
    eExitProcess,  
    eFastExitProcess,  
    eRudeExitProcess,  
    eDisableRuntime  
} EPolicyAction;  
```  
  
## <a name="members"></a><span data-ttu-id="83315-105">成员</span><span class="sxs-lookup"><span data-stu-id="83315-105">Members</span></span>  
  
|<span data-ttu-id="83315-106">成员</span><span class="sxs-lookup"><span data-stu-id="83315-106">Member</span></span>|<span data-ttu-id="83315-107">描述</span><span class="sxs-lookup"><span data-stu-id="83315-107">Description</span></span>|  
|------------|-----------------|  
|`eAbortThread`|<span data-ttu-id="83315-108">指定公共语言运行时 (CLR) 应正常中止线程。</span><span class="sxs-lookup"><span data-stu-id="83315-108">Specifies that the common language runtime (CLR) should abort the thread gracefully.</span></span> <span data-ttu-id="83315-109">包括正常中止： 尝试运行所有`finally`阻止任何`catch`块与线程中止和终结器。</span><span class="sxs-lookup"><span data-stu-id="83315-109">A graceful abort includes attempts to run all `finally` blocks, any `catch` blocks related to thread aborts, and finalizers.</span></span>|  
|`eDisableRuntime`|<span data-ttu-id="83315-110">指定 CLR 应进入禁用的状态。</span><span class="sxs-lookup"><span data-stu-id="83315-110">Specifies that the CLR should enter a disabled state.</span></span> <span data-ttu-id="83315-111">无需再在受影响的过程中，执行托管的代码和线程被阻止进入 CLR。</span><span class="sxs-lookup"><span data-stu-id="83315-111">No further managed code can be executed in the affected process, and threads are blocked from entering the CLR.</span></span>|  
|`eExitProcess`|<span data-ttu-id="83315-112">指定 CLR 应尝试的进程，包括运行终结器和执行清理和日志记录操作正常退出。</span><span class="sxs-lookup"><span data-stu-id="83315-112">Specifies that the CLR should attempt a graceful exit of the process, including running finalizers and performing cleanup and logging operations.</span></span>|  
|`eFastExitProcess`|<span data-ttu-id="83315-113">指定的 CLR 应立即退出进程，而无需运行终结器或执行清理和日志记录操作。</span><span class="sxs-lookup"><span data-stu-id="83315-113">Specifies that the CLR should exit the process immediately, without running finalizers or performing cleanup and logging operations.</span></span> <span data-ttu-id="83315-114">但是，将通知发送到调试器。</span><span class="sxs-lookup"><span data-stu-id="83315-114">However, notification is sent to the debugger.</span></span>|  
|`eNoAction`|<span data-ttu-id="83315-115">指定应执行任何操作。</span><span class="sxs-lookup"><span data-stu-id="83315-115">Specifies that no action should be taken.</span></span>|  
|`eRudeAbortThread`|<span data-ttu-id="83315-116">指定 CLR 应执行强制中止线程。</span><span class="sxs-lookup"><span data-stu-id="83315-116">Specifies that the CLR should perform a rude thread abort.</span></span> <span data-ttu-id="83315-117">只有那些`catch`并`finally`块标记为<xref:System.EnterpriseServices.MustRunInClientContextAttribute>执行。</span><span class="sxs-lookup"><span data-stu-id="83315-117">Only those `catch` and `finally` blocks marked with <xref:System.EnterpriseServices.MustRunInClientContextAttribute> are executed.</span></span>|  
|`eRudeExitProcess`|<span data-ttu-id="83315-118">指定 CLR 应退出进程，而无需运行终结器或日志记录操作。</span><span class="sxs-lookup"><span data-stu-id="83315-118">Specifies that the CLR should exit the process without running finalizers or logging operations.</span></span>|  
|`eRudeUnloadAppDomain`|<span data-ttu-id="83315-119">指定 CLR 应执行的强制卸载<xref:System.AppDomain>。</span><span class="sxs-lookup"><span data-stu-id="83315-119">Specifies that the CLR should perform a rude unload of the <xref:System.AppDomain>.</span></span> <span data-ttu-id="83315-120">唯一的终结器标记为<xref:System.EnterpriseServices.MustRunInClientContextAttribute>执行。</span><span class="sxs-lookup"><span data-stu-id="83315-120">Only finalizers marked with <xref:System.EnterpriseServices.MustRunInClientContextAttribute> are executed.</span></span> <span data-ttu-id="83315-121">同样，所有线程与此<xref:System.AppDomain>其堆栈中接收`ThreadAbortException`，而只能`catch`并`finally`块标记为<xref:System.EnterpriseServices.MustRunInClientContextAttribute>执行。</span><span class="sxs-lookup"><span data-stu-id="83315-121">Similarly, all threads with this <xref:System.AppDomain> in their stack receive a `ThreadAbortException`, but only those `catch` and `finally` blocks marked with <xref:System.EnterpriseServices.MustRunInClientContextAttribute> are executed.</span></span>|  
|`eThrowException`|<span data-ttu-id="83315-122">指定应引发异常的条件，例如内存不足，缓冲区溢出等，适合。</span><span class="sxs-lookup"><span data-stu-id="83315-122">Specifies that an exception appropriate to the condition, such as out-of-memory, buffer overflow, and so forth, should be thrown.</span></span>|  
|`eUnloadAppDomain`|<span data-ttu-id="83315-123">指定<xref:System.AppDomain>应卸载。</span><span class="sxs-lookup"><span data-stu-id="83315-123">Specifies that the <xref:System.AppDomain> should be unloaded.</span></span> <span data-ttu-id="83315-124">CLR 会试图运行终结器。</span><span class="sxs-lookup"><span data-stu-id="83315-124">The CLR attempts to run finalizers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="83315-125">备注</span><span class="sxs-lookup"><span data-stu-id="83315-125">Remarks</span></span>  
 <span data-ttu-id="83315-126">主机设置的策略操作是通过调用的方法[ICLRPolicyManager](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)接口。</span><span class="sxs-lookup"><span data-stu-id="83315-126">The host sets policy actions by calling methods of the [ICLRPolicyManager](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md) interface.</span></span> <span data-ttu-id="83315-127">有关原始和正常中止的信息，请参阅[EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md)枚举。</span><span class="sxs-lookup"><span data-stu-id="83315-127">For information about rude and graceful aborts, see the [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) enumeration.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="83315-128">要求</span><span class="sxs-lookup"><span data-stu-id="83315-128">Requirements</span></span>  
 <span data-ttu-id="83315-129">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="83315-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="83315-130">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="83315-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="83315-131">**库：** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="83315-131">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="83315-132">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="83315-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="83315-133">请参阅</span><span class="sxs-lookup"><span data-stu-id="83315-133">See also</span></span>

- [<span data-ttu-id="83315-134">EClrFailure 枚举</span><span class="sxs-lookup"><span data-stu-id="83315-134">EClrFailure Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md)
- [<span data-ttu-id="83315-135">ICLRPolicyManager 接口</span><span class="sxs-lookup"><span data-stu-id="83315-135">ICLRPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)
- [<span data-ttu-id="83315-136">IHostPolicyManager 接口</span><span class="sxs-lookup"><span data-stu-id="83315-136">IHostPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-interface.md)
- [<span data-ttu-id="83315-137">承载枚举</span><span class="sxs-lookup"><span data-stu-id="83315-137">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
