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
ms.openlocfilehash: 2ced153798355aff882f0244f3dd946c39dea2bd
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73121472"
---
# <a name="ihostsecuritymanageropenthreadtoken-method"></a><span data-ttu-id="dd255-102">IHostSecurityManager::OpenThreadToken 方法</span><span class="sxs-lookup"><span data-stu-id="dd255-102">IHostSecurityManager::OpenThreadToken Method</span></span>
<span data-ttu-id="dd255-103">打开与当前正在执行的线程关联的自由访问令牌。</span><span class="sxs-lookup"><span data-stu-id="dd255-103">Opens the discretionary access token associated with the currently executing thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dd255-104">语法</span><span class="sxs-lookup"><span data-stu-id="dd255-104">Syntax</span></span>  
  
```cpp  
HRESULT OpenThreadToken (  
    [in]  DWORD    dwDesiredAccess,   
    [in]  BOOL     bOpenAsSelf,   
    [out] HANDLE   *phThreadToken  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="dd255-105">参数</span><span class="sxs-lookup"><span data-stu-id="dd255-105">Parameters</span></span>  
 `dwDesiredAccess`  
 <span data-ttu-id="dd255-106">中访问值的掩码，指定请求的线程标记访问类型。</span><span class="sxs-lookup"><span data-stu-id="dd255-106">[in] A mask of access values that specify the requested types of access to the thread token.</span></span> <span data-ttu-id="dd255-107">这些值在 Win32 `OpenThreadToken` 函数中定义。</span><span class="sxs-lookup"><span data-stu-id="dd255-107">These values are defined in the Win32 `OpenThreadToken` function.</span></span> <span data-ttu-id="dd255-108">请求的访问类型对令牌的自由访问控制列表（DACL）进行协调，以确定要授予或拒绝的访问权限的类型。</span><span class="sxs-lookup"><span data-stu-id="dd255-108">The requested access types are reconciled against the token's discretionary access control list (DACL) to determine which types of access to grant or deny.</span></span>  
  
 `bOpenAsSelf`  
 <span data-ttu-id="dd255-109">[in] `true` 指定应使用调用线程的进程的安全上下文进行访问检查;`false` 指定应使用调用线程本身的安全上下文来执行访问检查。</span><span class="sxs-lookup"><span data-stu-id="dd255-109">[in] `true` to specify that the access check should be made using the security context of the process for the calling thread; `false` to specify that the access check should be performed using the security context for the calling thread itself.</span></span> <span data-ttu-id="dd255-110">如果线程正在模拟客户端，安全上下文可以是客户端进程的安全上下文。</span><span class="sxs-lookup"><span data-stu-id="dd255-110">If the thread is impersonating a client, the security context can be that of a client process.</span></span>  
  
 `phThreadToken`  
 <span data-ttu-id="dd255-111">弄指向新打开的访问令牌的指针。</span><span class="sxs-lookup"><span data-stu-id="dd255-111">[out] A pointer to the newly opened access token.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="dd255-112">返回值</span><span class="sxs-lookup"><span data-stu-id="dd255-112">Return Value</span></span>  
  
|<span data-ttu-id="dd255-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="dd255-113">HRESULT</span></span>|<span data-ttu-id="dd255-114">描述</span><span class="sxs-lookup"><span data-stu-id="dd255-114">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="dd255-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="dd255-115">S_OK</span></span>|<span data-ttu-id="dd255-116">`OpenThreadToken` 成功返回。</span><span class="sxs-lookup"><span data-stu-id="dd255-116">`OpenThreadToken` returned successfully.</span></span>|  
|<span data-ttu-id="dd255-117">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="dd255-117">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="dd255-118">公共语言运行时（CLR）未加载到进程中，或 CLR 处于无法运行托管代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="dd255-118">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="dd255-119">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="dd255-119">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="dd255-120">调用超时。</span><span class="sxs-lookup"><span data-stu-id="dd255-120">The call timed out.</span></span>|  
|<span data-ttu-id="dd255-121">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="dd255-121">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="dd255-122">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="dd255-122">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="dd255-123">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="dd255-123">HOST_E_ABANDONED</span></span>|<span data-ttu-id="dd255-124">已阻止的线程或纤程正在等待某个事件时，该事件被取消。</span><span class="sxs-lookup"><span data-stu-id="dd255-124">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="dd255-125">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="dd255-125">E_FAIL</span></span>|<span data-ttu-id="dd255-126">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="dd255-126">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="dd255-127">当方法返回 E_FAIL 时，CLR 在该进程内将不再可用。</span><span class="sxs-lookup"><span data-stu-id="dd255-127">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="dd255-128">对宿主方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="dd255-128">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="dd255-129">备注</span><span class="sxs-lookup"><span data-stu-id="dd255-129">Remarks</span></span>  
 <span data-ttu-id="dd255-130">`IHostSecurityManager::OpenThreadToken` 的行为类似于具有相同名称的对应 Win32 函数，不同之处在于 Win32 函数允许调用方将句柄传入任意线程，而 `IHostSecurityManager::OpenThreadToken` 只打开与调用线程关联的标记。</span><span class="sxs-lookup"><span data-stu-id="dd255-130">`IHostSecurityManager::OpenThreadToken` behaves similarly to the corresponding Win32 function of the same name, except that the Win32 function allows the caller to pass in a handle to an arbitrary thread, while `IHostSecurityManager::OpenThreadToken` opens only the token associated with the calling thread.</span></span>  
  
 <span data-ttu-id="dd255-131">`HANDLE` 类型不符合 COM 要求，也就是说，其大小特定于操作系统，并需要自定义封送处理。</span><span class="sxs-lookup"><span data-stu-id="dd255-131">The `HANDLE` type is not COM-compliant, that is, its size is specific to the operating system, and it requires custom marshaling.</span></span> <span data-ttu-id="dd255-132">因此，此令牌仅在该进程内的 CLR 和主机之间使用。</span><span class="sxs-lookup"><span data-stu-id="dd255-132">Thus, this token is for use only within the process, between the CLR and the host.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dd255-133">要求</span><span class="sxs-lookup"><span data-stu-id="dd255-133">Requirements</span></span>  
 <span data-ttu-id="dd255-134">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="dd255-134">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dd255-135">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="dd255-135">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="dd255-136">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="dd255-136">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="dd255-137">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dd255-137">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dd255-138">请参阅</span><span class="sxs-lookup"><span data-stu-id="dd255-138">See also</span></span>

- [<span data-ttu-id="dd255-139">IHostSecurityContext 接口</span><span class="sxs-lookup"><span data-stu-id="dd255-139">IHostSecurityContext Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md)
- [<span data-ttu-id="dd255-140">IHostSecurityManager 接口</span><span class="sxs-lookup"><span data-stu-id="dd255-140">IHostSecurityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-interface.md)
