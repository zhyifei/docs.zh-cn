---
title: ICLRRuntimeHost::ExecuteInDefaultAppDomain 方法
ms.date: 03/30/2017
api_name:
- ICLRRuntimeHost.ExecuteInDefaultAppDomain
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeHost::ExecuteInDefaultAppDomain
helpviewer_keywords:
- ICLRRuntimeHost::ExecuteInDefaultAppDomain method [.NET Framework hosting]
- ExecuteInDefaultAppDomain method [.NET Framework hosting]
ms.assetid: 30b5cf9a-a762-4bd4-be12-d6c1442b78b1
topic_type:
- apiref
ms.openlocfilehash: 1a1bc7609042422de876fe167a9e61655aaf62b4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176404"
---
# <a name="iclrruntimehostexecuteindefaultappdomain-method"></a><span data-ttu-id="61d58-102">ICLRRuntimeHost::ExecuteInDefaultAppDomain 方法</span><span class="sxs-lookup"><span data-stu-id="61d58-102">ICLRRuntimeHost::ExecuteInDefaultAppDomain Method</span></span>
<span data-ttu-id="61d58-103">调用指定托管程序集中指定类型的指定方法。</span><span class="sxs-lookup"><span data-stu-id="61d58-103">Calls the specified method of the specified type in the specified managed assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="61d58-104">语法</span><span class="sxs-lookup"><span data-stu-id="61d58-104">Syntax</span></span>  
  
```cpp  
HRESULT ExecuteInDefaultAppDomain (  
    [in] LPCWSTR pwzAssemblyPath,  
    [in] LPCWSTR pwzTypeName,
    [in] LPCWSTR pwzMethodName,  
    [in] LPCWSTR pwzArgument,  
    [out] DWORD *pReturnValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="61d58-105">parameters</span><span class="sxs-lookup"><span data-stu-id="61d58-105">Parameters</span></span>  
 `pwzAssemblyPath`  
 <span data-ttu-id="61d58-106">[在]定义要调用其<xref:System.Reflection.Assembly>方法的 的<xref:System.Type>的 路径。</span><span class="sxs-lookup"><span data-stu-id="61d58-106">[in] The path to the <xref:System.Reflection.Assembly> that defines the <xref:System.Type> whose method is to be invoked.</span></span>  
  
 `pwzTypeName`  
 <span data-ttu-id="61d58-107">[在]定义要调用的方法<xref:System.Type>的名称。</span><span class="sxs-lookup"><span data-stu-id="61d58-107">[in] The name of the <xref:System.Type> that defines the method to invoke.</span></span>  
  
 `pwzMethodName`  
 <span data-ttu-id="61d58-108">[在]要调用的方法的名称。</span><span class="sxs-lookup"><span data-stu-id="61d58-108">[in] The name of the method to invoke.</span></span>  
  
 `pwzArgument`  
 <span data-ttu-id="61d58-109">[在]要传递给方法的字符串参数。</span><span class="sxs-lookup"><span data-stu-id="61d58-109">[in] The string parameter to pass to the method.</span></span>  
  
 `pReturnValue`  
 <span data-ttu-id="61d58-110">[出]被调用方法返回的整数值。</span><span class="sxs-lookup"><span data-stu-id="61d58-110">[out] The integer value returned by the invoked method.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="61d58-111">返回值</span><span class="sxs-lookup"><span data-stu-id="61d58-111">Return Value</span></span>  
  
|<span data-ttu-id="61d58-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="61d58-112">HRESULT</span></span>|<span data-ttu-id="61d58-113">说明</span><span class="sxs-lookup"><span data-stu-id="61d58-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="61d58-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="61d58-114">S_OK</span></span>|<span data-ttu-id="61d58-115">`ExecuteInDefaultAppDomain`已成功返回。</span><span class="sxs-lookup"><span data-stu-id="61d58-115">`ExecuteInDefaultAppDomain` returned successfully.</span></span>|  
|<span data-ttu-id="61d58-116">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="61d58-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="61d58-117">公共语言运行时 （CLR） 尚未加载到进程中，或者 CLR 处于无法运行托管代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="61d58-117">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="61d58-118">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="61d58-118">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="61d58-119">呼叫超时。</span><span class="sxs-lookup"><span data-stu-id="61d58-119">The call timed out.</span></span>|  
|<span data-ttu-id="61d58-120">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="61d58-120">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="61d58-121">调用方不拥有锁。</span><span class="sxs-lookup"><span data-stu-id="61d58-121">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="61d58-122">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="61d58-122">HOST_E_ABANDONED</span></span>|<span data-ttu-id="61d58-123">当阻塞的线程或光纤等待事件时，事件已被取消。</span><span class="sxs-lookup"><span data-stu-id="61d58-123">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="61d58-124">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="61d58-124">E_FAIL</span></span>|<span data-ttu-id="61d58-125">发生了未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="61d58-125">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="61d58-126">如果方法返回E_FAIL，则 CRL 在进程中不再可用。</span><span class="sxs-lookup"><span data-stu-id="61d58-126">If a method returns E_FAIL, the CRL is no longer usable within the process.</span></span> <span data-ttu-id="61d58-127">对托管方法的后续调用返回HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="61d58-127">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="61d58-128">备注</span><span class="sxs-lookup"><span data-stu-id="61d58-128">Remarks</span></span>  
 <span data-ttu-id="61d58-129">调用的方法必须具有以下签名：</span><span class="sxs-lookup"><span data-stu-id="61d58-129">The invoked method must have the following signature:</span></span>  
  
```cpp  
static int pwzMethodName (String pwzArgument)  
```  
  
 <span data-ttu-id="61d58-130">表示`pwzMethodName`被调用方法的名称，并`pwzArgument`表示作为该方法的参数传递的字符串值。</span><span class="sxs-lookup"><span data-stu-id="61d58-130">where `pwzMethodName` represents the name of the invoked method, and `pwzArgument` represents the string value passed as a parameter to that method.</span></span> <span data-ttu-id="61d58-131">如果 HRESULT 值设置为S_OK，`pReturnValue`则设置为被调用方法返回的整数值。</span><span class="sxs-lookup"><span data-stu-id="61d58-131">If the HRESULT value is set to S_OK, `pReturnValue` is set to the integer value returned by the invoked method.</span></span> <span data-ttu-id="61d58-132">否则，`pReturnValue`未设置。</span><span class="sxs-lookup"><span data-stu-id="61d58-132">Otherwise, `pReturnValue` is not set.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="61d58-133">要求</span><span class="sxs-lookup"><span data-stu-id="61d58-133">Requirements</span></span>  
 <span data-ttu-id="61d58-134">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="61d58-134">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="61d58-135">**标题：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="61d58-135">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="61d58-136">**库：** 作为资源包含在 MSCorEE.dll 中</span><span class="sxs-lookup"><span data-stu-id="61d58-136">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="61d58-137">**.NET 框架版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="61d58-137">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="61d58-138">另请参阅</span><span class="sxs-lookup"><span data-stu-id="61d58-138">See also</span></span>

- [<span data-ttu-id="61d58-139">ICLRRuntimeHost 接口</span><span class="sxs-lookup"><span data-stu-id="61d58-139">ICLRRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)
