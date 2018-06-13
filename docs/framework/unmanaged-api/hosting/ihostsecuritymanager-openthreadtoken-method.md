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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 35a41badd7ade016619d940880a3ace80ccf5693
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33439509"
---
# <a name="ihostsecuritymanageropenthreadtoken-method"></a><span data-ttu-id="23d27-102">IHostSecurityManager::OpenThreadToken 方法</span><span class="sxs-lookup"><span data-stu-id="23d27-102">IHostSecurityManager::OpenThreadToken Method</span></span>
<span data-ttu-id="23d27-103">将打开与当前正在执行的线程关联的自由访问令牌。</span><span class="sxs-lookup"><span data-stu-id="23d27-103">Opens the discretionary access token associated with the currently executing thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="23d27-104">语法</span><span class="sxs-lookup"><span data-stu-id="23d27-104">Syntax</span></span>  
  
```  
HRESULT OpenThreadToken (  
    [in]  DWORD    dwDesiredAccess,   
    [in]  BOOL     bOpenAsSelf,   
    [out] HANDLE   *phThreadToken  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="23d27-105">参数</span><span class="sxs-lookup"><span data-stu-id="23d27-105">Parameters</span></span>  
 `dwDesiredAccess`  
 <span data-ttu-id="23d27-106">[in]访问指定的值的访问权限的线程令牌请求的类型掩码。</span><span class="sxs-lookup"><span data-stu-id="23d27-106">[in] A mask of access values that specify the requested types of access to the thread token.</span></span> <span data-ttu-id="23d27-107">在 Win32 中定义这些值`OpenThreadToken`函数。</span><span class="sxs-lookup"><span data-stu-id="23d27-107">These values are defined in the Win32 `OpenThreadToken` function.</span></span> <span data-ttu-id="23d27-108">请求的访问类型是根据令牌的自由访问控制列表 (DACL) 来确定哪些类型的访问权限以授予或拒绝对帐。</span><span class="sxs-lookup"><span data-stu-id="23d27-108">The requested access types are reconciled against the token's discretionary access control list (DACL) to determine which types of access to grant or deny.</span></span>  
  
 `bOpenAsSelf`  
 <span data-ttu-id="23d27-109">[in]`true`以指定应与调用的线程; 使用进程的安全上下文建立访问检查`false`若要指定应使用的安全上下文适用于在调用线程执行访问检查。</span><span class="sxs-lookup"><span data-stu-id="23d27-109">[in] `true` to specify that the access check should be made using the security context of the process for the calling thread; `false` to specify that the access check should be performed using the security context for the calling thread itself.</span></span> <span data-ttu-id="23d27-110">如果线程正在模拟客户端，安全上下文可以是客户端过程。</span><span class="sxs-lookup"><span data-stu-id="23d27-110">If the thread is impersonating a client, the security context can be that of a client process.</span></span>  
  
 `phThreadToken`  
 <span data-ttu-id="23d27-111">[out]指向新打开的访问令牌的指针。</span><span class="sxs-lookup"><span data-stu-id="23d27-111">[out] A pointer to the newly opened access token.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="23d27-112">返回值</span><span class="sxs-lookup"><span data-stu-id="23d27-112">Return Value</span></span>  
  
|<span data-ttu-id="23d27-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="23d27-113">HRESULT</span></span>|<span data-ttu-id="23d27-114">描述</span><span class="sxs-lookup"><span data-stu-id="23d27-114">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="23d27-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="23d27-115">S_OK</span></span>|<span data-ttu-id="23d27-116">`OpenThreadToken` 已成功返回。</span><span class="sxs-lookup"><span data-stu-id="23d27-116">`OpenThreadToken` returned successfully.</span></span>|  
|<span data-ttu-id="23d27-117">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="23d27-117">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="23d27-118">公共语言运行时 (CLR) 尚未加载到进程中，或 CLR 处于不能运行托管的代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="23d27-118">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="23d27-119">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="23d27-119">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="23d27-120">调用操作已超时。</span><span class="sxs-lookup"><span data-stu-id="23d27-120">The call timed out.</span></span>|  
|<span data-ttu-id="23d27-121">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="23d27-121">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="23d27-122">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="23d27-122">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="23d27-123">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="23d27-123">HOST_E_ABANDONED</span></span>|<span data-ttu-id="23d27-124">事件已被取消时被阻塞的线程，或者纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="23d27-124">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="23d27-125">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="23d27-125">E_FAIL</span></span>|<span data-ttu-id="23d27-126">出现未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="23d27-126">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="23d27-127">如果某方法返回 E_FAIL，CLR 不再可用进程内。</span><span class="sxs-lookup"><span data-stu-id="23d27-127">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="23d27-128">到托管方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="23d27-128">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="23d27-129">备注</span><span class="sxs-lookup"><span data-stu-id="23d27-129">Remarks</span></span>  
 <span data-ttu-id="23d27-130">`IHostSecurityManager::OpenThreadToken` 行为同样与对应的 Win32 函数的相同的名称，只不过 Win32 函数允许调用方传入到任意线程句柄，而`IHostSecurityManager::OpenThreadToken`打开仅与调用线程关联的令牌。</span><span class="sxs-lookup"><span data-stu-id="23d27-130">`IHostSecurityManager::OpenThreadToken` behaves similarly to the corresponding Win32 function of the same name, except that the Win32 function allows the caller to pass in a handle to an arbitrary thread, while `IHostSecurityManager::OpenThreadToken` opens only the token associated with the calling thread.</span></span>  
  
 <span data-ttu-id="23d27-131">`HANDLE`类型不是 COM 兼容，也就是说，其大小是特定于操作系统，以及它要求自定义封送处理。</span><span class="sxs-lookup"><span data-stu-id="23d27-131">The `HANDLE` type is not COM-compliant, that is, its size is specific to the operating system, and it requires custom marshaling.</span></span> <span data-ttu-id="23d27-132">因此，此令牌是仅在 CLR 与主机之间的流程内使用。</span><span class="sxs-lookup"><span data-stu-id="23d27-132">Thus, this token is for use only within the process, between the CLR and the host.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="23d27-133">要求</span><span class="sxs-lookup"><span data-stu-id="23d27-133">Requirements</span></span>  
 <span data-ttu-id="23d27-134">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="23d27-134">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="23d27-135">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="23d27-135">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="23d27-136">**库：** 作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="23d27-136">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="23d27-137">**.NET framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="23d27-137">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="23d27-138">请参阅</span><span class="sxs-lookup"><span data-stu-id="23d27-138">See Also</span></span>  
 [<span data-ttu-id="23d27-139">IHostSecurityContext 接口</span><span class="sxs-lookup"><span data-stu-id="23d27-139">IHostSecurityContext Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md)  
 [<span data-ttu-id="23d27-140">IHostSecurityManager 接口</span><span class="sxs-lookup"><span data-stu-id="23d27-140">IHostSecurityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-interface.md)
