---
title: IHostSecurityManager 接口
ms.date: 03/30/2017
api_name:
- IHostSecurityManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSecurityManager
helpviewer_keywords:
- IHostSecurityManager interface [.NET Framework hosting]
ms.assetid: c3be2cbd-2d93-438b-9888-9a0251b63c03
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2637f54fcddaf82d30527d7318503a2b9aa740dc
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54565834"
---
# <a name="ihostsecuritymanager-interface"></a><span data-ttu-id="0b693-102">IHostSecurityManager 接口</span><span class="sxs-lookup"><span data-stu-id="0b693-102">IHostSecurityManager Interface</span></span>
<span data-ttu-id="0b693-103">提供方法，以允许访问和控制当前正在执行的线程的安全上下文。</span><span class="sxs-lookup"><span data-stu-id="0b693-103">Provides methods that allow access to and control over the security context of the currently executing thread.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="0b693-104">方法</span><span class="sxs-lookup"><span data-stu-id="0b693-104">Methods</span></span>  
  
|<span data-ttu-id="0b693-105">方法</span><span class="sxs-lookup"><span data-stu-id="0b693-105">Method</span></span>|<span data-ttu-id="0b693-106">描述</span><span class="sxs-lookup"><span data-stu-id="0b693-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="0b693-107">GetSecurityContext 方法</span><span class="sxs-lookup"><span data-stu-id="0b693-107">GetSecurityContext Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-getsecuritycontext-method.md)|<span data-ttu-id="0b693-108">获取所请求[IHostSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md)从主机。</span><span class="sxs-lookup"><span data-stu-id="0b693-108">Gets the requested [IHostSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md) from the host.</span></span>|  
|[<span data-ttu-id="0b693-109">ImpersonateLoggedOnUser 方法</span><span class="sxs-lookup"><span data-stu-id="0b693-109">ImpersonateLoggedOnUser Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-impersonateloggedonuser-method.md)|<span data-ttu-id="0b693-110">请求的代码在执行使用当前用户标识的凭据。</span><span class="sxs-lookup"><span data-stu-id="0b693-110">Requests that code be executed using the credentials of the current user identity.</span></span>|  
|[<span data-ttu-id="0b693-111">OpenThreadToken 方法</span><span class="sxs-lookup"><span data-stu-id="0b693-111">OpenThreadToken Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-openthreadtoken-method.md)|<span data-ttu-id="0b693-112">将打开与当前线程关联的自由访问令牌。</span><span class="sxs-lookup"><span data-stu-id="0b693-112">Opens the discretionary access token associated with the current thread.</span></span>|  
|[<span data-ttu-id="0b693-113">RevertToSelf 方法</span><span class="sxs-lookup"><span data-stu-id="0b693-113">RevertToSelf Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-reverttoself-method.md)|<span data-ttu-id="0b693-114">终止模拟当前用户标识，并返回原始线程标记。</span><span class="sxs-lookup"><span data-stu-id="0b693-114">Terminates impersonation of the current user identity and returns the original thread token.</span></span>|  
|[<span data-ttu-id="0b693-115">SetSecurityContext 方法</span><span class="sxs-lookup"><span data-stu-id="0b693-115">SetSecurityContext Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-setsecuritycontext-method.md)|<span data-ttu-id="0b693-116">设置当前执行线程的安全上下文。</span><span class="sxs-lookup"><span data-stu-id="0b693-116">Sets the security context for the currently executing thread.</span></span>|  
|[<span data-ttu-id="0b693-117">SetThreadToken 方法</span><span class="sxs-lookup"><span data-stu-id="0b693-117">SetThreadToken Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-setthreadtoken-method.md)|<span data-ttu-id="0b693-118">设置当前执行线程的句柄。</span><span class="sxs-lookup"><span data-stu-id="0b693-118">Sets a handle for the currently executing thread.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0b693-119">备注</span><span class="sxs-lookup"><span data-stu-id="0b693-119">Remarks</span></span>  
 <span data-ttu-id="0b693-120">主机可以控制由公共语言运行时 (CLR) 和用户代码对线程令牌的所有代码访问权限。</span><span class="sxs-lookup"><span data-stu-id="0b693-120">A host can control all code access to thread tokens by both the common language runtime (CLR) and user code.</span></span> <span data-ttu-id="0b693-121">它还可确保完整的安全跨异步操作或具有受限制的代码访问权限的代码点传递上下文信息。</span><span class="sxs-lookup"><span data-stu-id="0b693-121">It can also ensure that complete security context information is passed across asynchronous operations or code points with restricted code access.</span></span> <span data-ttu-id="0b693-122">`IHostSecurityContext` 封装此安全上下文信息，这是不透明的 CLR。</span><span class="sxs-lookup"><span data-stu-id="0b693-122">`IHostSecurityContext` encapsulates this security context information, which is opaque to the CLR.</span></span>  
  
 <span data-ttu-id="0b693-123">CLR 会在内部处理托管的线程上下文。</span><span class="sxs-lookup"><span data-stu-id="0b693-123">The CLR handles managed thread context internally.</span></span> <span data-ttu-id="0b693-124">它会查询特定于进程的`IHostSecurityManager`在以下情况下：</span><span class="sxs-lookup"><span data-stu-id="0b693-124">It queries the process-specific `IHostSecurityManager` in the following situations:</span></span>  
  
-   <span data-ttu-id="0b693-125">在终结器执行期间的终结器线程。</span><span class="sxs-lookup"><span data-stu-id="0b693-125">On the finalizer thread, during finalizer execution.</span></span>  
  
-   <span data-ttu-id="0b693-126">在类和模块构造函数执行。</span><span class="sxs-lookup"><span data-stu-id="0b693-126">During class and module constructor execution.</span></span>  
  
-   <span data-ttu-id="0b693-127">在对的调用中，在辅助线程上异步点[ihostthreadpoolmanager:: Queueuserworkitem](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-queueuserworkitem-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="0b693-127">At asynchronous points on the worker thread, in calls to the [IHostThreadPoolManager::QueueUserWorkItem](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-queueuserworkitem-method.md) method.</span></span>  
  
-   <span data-ttu-id="0b693-128">处于维护的 I/O 完成端口。</span><span class="sxs-lookup"><span data-stu-id="0b693-128">In servicing of I/O completion ports.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0b693-129">要求</span><span class="sxs-lookup"><span data-stu-id="0b693-129">Requirements</span></span>  
 <span data-ttu-id="0b693-130">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="0b693-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0b693-131">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="0b693-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="0b693-132">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="0b693-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0b693-133">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0b693-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0b693-134">请参阅</span><span class="sxs-lookup"><span data-stu-id="0b693-134">See also</span></span>
- [<span data-ttu-id="0b693-135">IHostSecurityContext 接口</span><span class="sxs-lookup"><span data-stu-id="0b693-135">IHostSecurityContext Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md)
- [<span data-ttu-id="0b693-136">承载接口</span><span class="sxs-lookup"><span data-stu-id="0b693-136">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
