---
title: EClrFailure 枚举
ms.date: 03/30/2017
api_name:
- EClrFailure
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- EClrFailure
helpviewer_keywords:
- EClrFailure enumeration [.NET Framework hosting]
ms.assetid: 37b95cce-9bfb-4ecf-a00b-33dcba782c67
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ef4e12015adc3d6e67ad9c8ba8b152cd775b85e2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33431924"
---
# <a name="eclrfailure-enumeration"></a><span data-ttu-id="e9e65-102">EClrFailure 枚举</span><span class="sxs-lookup"><span data-stu-id="e9e65-102">EClrFailure Enumeration</span></span>
<span data-ttu-id="e9e65-103">介绍一的系列主机可以对这些设置的策略操作的故障。</span><span class="sxs-lookup"><span data-stu-id="e9e65-103">Describes the set of failures for which a host can set policy actions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e9e65-104">语法</span><span class="sxs-lookup"><span data-stu-id="e9e65-104">Syntax</span></span>  
  
```  
typedef enum {  
    FAIL_NonCriticalResource,  
    FAIL_CriticalResource,  
    FAIL_FatalRuntime,  
    FAIL_OrphanedLock  
    FAIL_StackOverflow  
    FAIL_AccessViolation  
    FAIL_CodeContract  
} EClrFailure;  
```  
  
## <a name="members"></a><span data-ttu-id="e9e65-105">成员</span><span class="sxs-lookup"><span data-stu-id="e9e65-105">Members</span></span>  
  
|<span data-ttu-id="e9e65-106">成员</span><span class="sxs-lookup"><span data-stu-id="e9e65-106">Member</span></span>|<span data-ttu-id="e9e65-107">描述</span><span class="sxs-lookup"><span data-stu-id="e9e65-107">Description</span></span>|  
|------------|-----------------|  
|`FAIL_NonCriticalResource`|<span data-ttu-id="e9e65-108">代码的非关键区域中尝试分配资源 （例如线程、 的内存，块或锁定） 时出现的错误。</span><span class="sxs-lookup"><span data-stu-id="e9e65-108">A failure occurred during an attempt to allocate a resource (such as a thread, a block of memory, or a lock) in a non-critical region of code.</span></span>|  
|`FAIL_CriticalResource`|<span data-ttu-id="e9e65-109">代码的关键区域中尝试分配资源 （例如线程、 的内存，块或锁定） 时出现的错误。</span><span class="sxs-lookup"><span data-stu-id="e9e65-109">A failure occurred during an attempt to allocate a resource (such as a thread, a block of memory, or a lock) in a critical region of code.</span></span>|  
|`FAIL_FatalRuntime`|<span data-ttu-id="e9e65-110">公共语言运行时 (CLR) 不再能够在进程中运行托管的代码。</span><span class="sxs-lookup"><span data-stu-id="e9e65-110">The common language runtime (CLR) is no longer able to run managed code in the process.</span></span> <span data-ttu-id="e9e65-111">自此以后，对任何托管函数的调用返回 HOST_E_CLRNOTAVAILABLE HRESULT 的值。</span><span class="sxs-lookup"><span data-stu-id="e9e65-111">Henceforth, calls to any hosting functions return an HRESULT value of HOST_E_CLRNOTAVAILABLE.</span></span>|  
|`FAIL_OrphanedLock`|<span data-ttu-id="e9e65-112">线程未能释放锁后从返回<xref:System.AppDomain>对象。</span><span class="sxs-lookup"><span data-stu-id="e9e65-112">A thread has failed to release a lock upon returning from an <xref:System.AppDomain> object.</span></span> <span data-ttu-id="e9e65-113">主机不能设置此故障以使中止的线程。</span><span class="sxs-lookup"><span data-stu-id="e9e65-113">The host cannot set this failure to cause a thread to abort.</span></span>|  
|`FAIL_StackOverflow`|<span data-ttu-id="e9e65-114">发生堆栈溢出。</span><span class="sxs-lookup"><span data-stu-id="e9e65-114">A stack overflow has occurred.</span></span>|  
|`FAIL_AccessViolation`|<span data-ttu-id="e9e65-115">尝试读取或写入受保护的内存。</span><span class="sxs-lookup"><span data-stu-id="e9e65-115">An attempt was made to read or write protected memory.</span></span> <span data-ttu-id="e9e65-116">中不受支持[!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="e9e65-116">Not supported in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>|  
|`FAIL_CodeContract`|<span data-ttu-id="e9e65-117">代码协定出错。</span><span class="sxs-lookup"><span data-stu-id="e9e65-117">A code contract failure occurred.</span></span> <span data-ttu-id="e9e65-118">请参阅[代码协定](../../../../docs/framework/debug-trace-profile/code-contracts.md)。</span><span class="sxs-lookup"><span data-stu-id="e9e65-118">See [Code Contracts](../../../../docs/framework/debug-trace-profile/code-contracts.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e9e65-119">备注</span><span class="sxs-lookup"><span data-stu-id="e9e65-119">Remarks</span></span>  
 <span data-ttu-id="e9e65-120">请参阅[iclrpolicymanager:: Setactiononfailure](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactiononfailure-method.md)方法有关的列表[EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md)主机可用于指定在故障条件的策略操作的值。</span><span class="sxs-lookup"><span data-stu-id="e9e65-120">See the [ICLRPolicyManager::SetActionOnFailure](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactiononfailure-method.md) method for a list of [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) values the host can use to specify the policy actions for failure conditions.</span></span> <span data-ttu-id="e9e65-121">有关代码的关键和非关键区域的详细信息，请参阅[EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md)。</span><span class="sxs-lookup"><span data-stu-id="e9e65-121">For more information about critical and non-critical regions of code, see [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e9e65-122">要求</span><span class="sxs-lookup"><span data-stu-id="e9e65-122">Requirements</span></span>  
 <span data-ttu-id="e9e65-123">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="e9e65-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e9e65-124">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="e9e65-124">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e9e65-125">**库：** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="e9e65-125">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e9e65-126">**.NET framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e9e65-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e9e65-127">请参阅</span><span class="sxs-lookup"><span data-stu-id="e9e65-127">See Also</span></span>  
 [<span data-ttu-id="e9e65-128">ICLRPolicyManager 接口</span><span class="sxs-lookup"><span data-stu-id="e9e65-128">ICLRPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)  
 [<span data-ttu-id="e9e65-129">SetActionOnFailure 方法</span><span class="sxs-lookup"><span data-stu-id="e9e65-129">SetActionOnFailure Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactiononfailure-method.md)  
 [<span data-ttu-id="e9e65-130">IHostPolicyManager 接口</span><span class="sxs-lookup"><span data-stu-id="e9e65-130">IHostPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-interface.md)  
 [<span data-ttu-id="e9e65-131">承载枚举</span><span class="sxs-lookup"><span data-stu-id="e9e65-131">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
