---
title: IHostSecurityManager::OpenThreadToken 方法
ms.date: 03/30/2017
api_name:
- IHostSecurityManager.OpenThreadToken
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSecurityManager::OpenThreadToken
helpviewer_keywords:
- IHostSecurityManager::OpenThreadToken method [.NET Framework hosting]
- OpenThreadToken method [.NET Framework hosting]
ms.assetid: d5999052-8bf0-4a9e-8621-da6284406b18
topic_type:
- apiref
ms.openlocfilehash: 11d042ea9eecc8d428761da6eaa15f7c2907ebd8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176261"
---
# <a name="ihostsecuritymanageropenthreadtoken-method"></a><span data-ttu-id="3012e-102">IHostSecurityManager::OpenThreadToken 方法</span><span class="sxs-lookup"><span data-stu-id="3012e-102">IHostSecurityManager::OpenThreadToken Method</span></span>
<span data-ttu-id="3012e-103">打开与当前正在执行的线程关联的可自由访问令牌。</span><span class="sxs-lookup"><span data-stu-id="3012e-103">Opens the discretionary access token associated with the currently executing thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3012e-104">语法</span><span class="sxs-lookup"><span data-stu-id="3012e-104">Syntax</span></span>  
  
```cpp  
HRESULT OpenThreadToken (  
    [in]  DWORD    dwDesiredAccess,
    [in]  BOOL     bOpenAsSelf,
    [out] HANDLE   *phThreadToken  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3012e-105">parameters</span><span class="sxs-lookup"><span data-stu-id="3012e-105">Parameters</span></span>  
 `dwDesiredAccess`  
 <span data-ttu-id="3012e-106">[在]指定对线程令牌的请求访问类型的访问值的掩码。</span><span class="sxs-lookup"><span data-stu-id="3012e-106">[in] A mask of access values that specify the requested types of access to the thread token.</span></span> <span data-ttu-id="3012e-107">这些值在 Win32`OpenThreadToken`函数中定义。</span><span class="sxs-lookup"><span data-stu-id="3012e-107">These values are defined in the Win32 `OpenThreadToken` function.</span></span> <span data-ttu-id="3012e-108">请求的访问类型与令牌的任意访问控制列表 （DACL） 协调，以确定授予或拒绝的访问类型。</span><span class="sxs-lookup"><span data-stu-id="3012e-108">The requested access types are reconciled against the token's discretionary access control list (DACL) to determine which types of access to grant or deny.</span></span>  
  
 `bOpenAsSelf`  
 <span data-ttu-id="3012e-109">[在]`true`指定应使用调用线程的进程的安全上下文进行访问检查;`false`指定应使用调用线程本身的安全上下文执行访问检查。</span><span class="sxs-lookup"><span data-stu-id="3012e-109">[in] `true` to specify that the access check should be made using the security context of the process for the calling thread; `false` to specify that the access check should be performed using the security context for the calling thread itself.</span></span> <span data-ttu-id="3012e-110">如果线程正在模拟客户端，则安全上下文可以是客户端进程的安全上下文。</span><span class="sxs-lookup"><span data-stu-id="3012e-110">If the thread is impersonating a client, the security context can be that of a client process.</span></span>  
  
 `phThreadToken`  
 <span data-ttu-id="3012e-111">[出]指向新打开的访问令牌的指针。</span><span class="sxs-lookup"><span data-stu-id="3012e-111">[out] A pointer to the newly opened access token.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3012e-112">返回值</span><span class="sxs-lookup"><span data-stu-id="3012e-112">Return Value</span></span>  
  
|<span data-ttu-id="3012e-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="3012e-113">HRESULT</span></span>|<span data-ttu-id="3012e-114">说明</span><span class="sxs-lookup"><span data-stu-id="3012e-114">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="3012e-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="3012e-115">S_OK</span></span>|<span data-ttu-id="3012e-116">`OpenThreadToken`已成功返回。</span><span class="sxs-lookup"><span data-stu-id="3012e-116">`OpenThreadToken` returned successfully.</span></span>|  
|<span data-ttu-id="3012e-117">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="3012e-117">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="3012e-118">公共语言运行时 （CLR） 尚未加载到进程中，或者 CLR 处于无法运行托管代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="3012e-118">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="3012e-119">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="3012e-119">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="3012e-120">呼叫超时。</span><span class="sxs-lookup"><span data-stu-id="3012e-120">The call timed out.</span></span>|  
|<span data-ttu-id="3012e-121">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="3012e-121">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="3012e-122">调用方不拥有锁。</span><span class="sxs-lookup"><span data-stu-id="3012e-122">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="3012e-123">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="3012e-123">HOST_E_ABANDONED</span></span>|<span data-ttu-id="3012e-124">当阻塞的线程或光纤等待事件时，事件已被取消。</span><span class="sxs-lookup"><span data-stu-id="3012e-124">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="3012e-125">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="3012e-125">E_FAIL</span></span>|<span data-ttu-id="3012e-126">发生了未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="3012e-126">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="3012e-127">当方法返回E_FAIL时，CLR 在进程中不再可用。</span><span class="sxs-lookup"><span data-stu-id="3012e-127">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="3012e-128">对托管方法的后续调用返回HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="3012e-128">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3012e-129">备注</span><span class="sxs-lookup"><span data-stu-id="3012e-129">Remarks</span></span>  
 <span data-ttu-id="3012e-130">`IHostSecurityManager::OpenThreadToken`行为行为类似于同名的相应 Win32 函数，只不过 Win32 函数允许调用方在句柄中传递到任意线程，同时`IHostSecurityManager::OpenThreadToken`仅打开与调用线程关联的令牌。</span><span class="sxs-lookup"><span data-stu-id="3012e-130">`IHostSecurityManager::OpenThreadToken` behaves similarly to the corresponding Win32 function of the same name, except that the Win32 function allows the caller to pass in a handle to an arbitrary thread, while `IHostSecurityManager::OpenThreadToken` opens only the token associated with the calling thread.</span></span>  
  
 <span data-ttu-id="3012e-131">类型`HANDLE`不符合 COM，即其大小特定于操作系统，并且需要自定义封送。</span><span class="sxs-lookup"><span data-stu-id="3012e-131">The `HANDLE` type is not COM-compliant, that is, its size is specific to the operating system, and it requires custom marshaling.</span></span> <span data-ttu-id="3012e-132">因此，此令牌仅用于进程，在 CLR 和主机之间。</span><span class="sxs-lookup"><span data-stu-id="3012e-132">Thus, this token is for use only within the process, between the CLR and the host.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3012e-133">要求</span><span class="sxs-lookup"><span data-stu-id="3012e-133">Requirements</span></span>  
 <span data-ttu-id="3012e-134">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="3012e-134">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3012e-135">**标题：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="3012e-135">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="3012e-136">**库：** 作为资源包含在 MSCorEE.dll 中</span><span class="sxs-lookup"><span data-stu-id="3012e-136">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3012e-137">**.NET 框架版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3012e-137">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3012e-138">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3012e-138">See also</span></span>

- [<span data-ttu-id="3012e-139">IHostSecurityContext 接口</span><span class="sxs-lookup"><span data-stu-id="3012e-139">IHostSecurityContext Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md)
- [<span data-ttu-id="3012e-140">IHostSecurityManager 接口</span><span class="sxs-lookup"><span data-stu-id="3012e-140">IHostSecurityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-interface.md)
