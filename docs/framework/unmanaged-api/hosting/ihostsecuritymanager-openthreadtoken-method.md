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
ms.openlocfilehash: 68ebfdcd0ef34edec724a044791d05dd48580b12
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59144555"
---
# <a name="ihostsecuritymanageropenthreadtoken-method"></a><span data-ttu-id="5cedb-102">IHostSecurityManager::OpenThreadToken 方法</span><span class="sxs-lookup"><span data-stu-id="5cedb-102">IHostSecurityManager::OpenThreadToken Method</span></span>
<span data-ttu-id="5cedb-103">将打开与当前执行线程关联的自由访问令牌。</span><span class="sxs-lookup"><span data-stu-id="5cedb-103">Opens the discretionary access token associated with the currently executing thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5cedb-104">语法</span><span class="sxs-lookup"><span data-stu-id="5cedb-104">Syntax</span></span>  
  
```  
HRESULT OpenThreadToken (  
    [in]  DWORD    dwDesiredAccess,   
    [in]  BOOL     bOpenAsSelf,   
    [out] HANDLE   *phThreadToken  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5cedb-105">参数</span><span class="sxs-lookup"><span data-stu-id="5cedb-105">Parameters</span></span>  
 `dwDesiredAccess`  
 <span data-ttu-id="5cedb-106">[in]一个掩码，访问指定的值的线程令牌的访问权限的请求的类型。</span><span class="sxs-lookup"><span data-stu-id="5cedb-106">[in] A mask of access values that specify the requested types of access to the thread token.</span></span> <span data-ttu-id="5cedb-107">在 Win32 中定义这些值`OpenThreadToken`函数。</span><span class="sxs-lookup"><span data-stu-id="5cedb-107">These values are defined in the Win32 `OpenThreadToken` function.</span></span> <span data-ttu-id="5cedb-108">请求的访问类型已得到协调对令牌的自由访问控制列表 (DACL) 来确定哪些类型的访问权限以授予或拒绝。</span><span class="sxs-lookup"><span data-stu-id="5cedb-108">The requested access types are reconciled against the token's discretionary access control list (DACL) to determine which types of access to grant or deny.</span></span>  
  
 `bOpenAsSelf`  
 <span data-ttu-id="5cedb-109">[in]`true`来指定应为调用线程; 使用该过程的安全上下文使访问检查`false`若要指定应使用调用线程本身的安全上下文执行访问检查。</span><span class="sxs-lookup"><span data-stu-id="5cedb-109">[in] `true` to specify that the access check should be made using the security context of the process for the calling thread; `false` to specify that the access check should be performed using the security context for the calling thread itself.</span></span> <span data-ttu-id="5cedb-110">如果线程正在模拟客户端，可以是安全上下文的客户端进程。</span><span class="sxs-lookup"><span data-stu-id="5cedb-110">If the thread is impersonating a client, the security context can be that of a client process.</span></span>  
  
 `phThreadToken`  
 <span data-ttu-id="5cedb-111">[out]一个指向新打开的访问令牌。</span><span class="sxs-lookup"><span data-stu-id="5cedb-111">[out] A pointer to the newly opened access token.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5cedb-112">返回值</span><span class="sxs-lookup"><span data-stu-id="5cedb-112">Return Value</span></span>  
  
|<span data-ttu-id="5cedb-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="5cedb-113">HRESULT</span></span>|<span data-ttu-id="5cedb-114">描述</span><span class="sxs-lookup"><span data-stu-id="5cedb-114">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="5cedb-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="5cedb-115">S_OK</span></span>|`OpenThreadToken` <span data-ttu-id="5cedb-116">已成功返回。</span><span class="sxs-lookup"><span data-stu-id="5cedb-116">returned successfully.</span></span>|  
|<span data-ttu-id="5cedb-117">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="5cedb-117">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="5cedb-118">公共语言运行时 (CLR) 尚未加载到进程中，或处于不能运行托管的代码或已成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="5cedb-118">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="5cedb-119">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="5cedb-119">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="5cedb-120">呼叫已超时。</span><span class="sxs-lookup"><span data-stu-id="5cedb-120">The call timed out.</span></span>|  
|<span data-ttu-id="5cedb-121">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="5cedb-121">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="5cedb-122">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="5cedb-122">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="5cedb-123">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="5cedb-123">HOST_E_ABANDONED</span></span>|<span data-ttu-id="5cedb-124">事件已取消时被阻塞的线程或纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="5cedb-124">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="5cedb-125">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="5cedb-125">E_FAIL</span></span>|<span data-ttu-id="5cedb-126">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="5cedb-126">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="5cedb-127">如果某方法返回 E_FAIL，CLR 不再在进程内可用。</span><span class="sxs-lookup"><span data-stu-id="5cedb-127">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="5cedb-128">对托管方法的后续调用返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="5cedb-128">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5cedb-129">备注</span><span class="sxs-lookup"><span data-stu-id="5cedb-129">Remarks</span></span>  
 `IHostSecurityManager::OpenThreadToken` <span data-ttu-id="5cedb-130">行为同样具有相同名称的相应的 Win32 函数相似，Win32 函数允许调用方将句柄传递给任意线程，而`IHostSecurityManager::OpenThreadToken`打开仅与调用线程关联的标记。</span><span class="sxs-lookup"><span data-stu-id="5cedb-130">behaves similarly to the corresponding Win32 function of the same name, except that the Win32 function allows the caller to pass in a handle to an arbitrary thread, while `IHostSecurityManager::OpenThreadToken` opens only the token associated with the calling thread.</span></span>  
  
 <span data-ttu-id="5cedb-131">`HANDLE`类型不是 COM 兼容，也就是说，其大小是特定于操作系统，，它需要自定义封送处理。</span><span class="sxs-lookup"><span data-stu-id="5cedb-131">The `HANDLE` type is not COM-compliant, that is, its size is specific to the operating system, and it requires custom marshaling.</span></span> <span data-ttu-id="5cedb-132">因此，此令牌是仅在 CLR 与主机之间的流程内使用。</span><span class="sxs-lookup"><span data-stu-id="5cedb-132">Thus, this token is for use only within the process, between the CLR and the host.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5cedb-133">要求</span><span class="sxs-lookup"><span data-stu-id="5cedb-133">Requirements</span></span>  
 <span data-ttu-id="5cedb-134">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="5cedb-134">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5cedb-135">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="5cedb-135">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="5cedb-136">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="5cedb-136">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="5cedb-137">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="5cedb-137">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="5cedb-138">请参阅</span><span class="sxs-lookup"><span data-stu-id="5cedb-138">See also</span></span>

- [<span data-ttu-id="5cedb-139">IHostSecurityContext 接口</span><span class="sxs-lookup"><span data-stu-id="5cedb-139">IHostSecurityContext Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md)
- [<span data-ttu-id="5cedb-140">IHostSecurityManager 接口</span><span class="sxs-lookup"><span data-stu-id="5cedb-140">IHostSecurityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-interface.md)
