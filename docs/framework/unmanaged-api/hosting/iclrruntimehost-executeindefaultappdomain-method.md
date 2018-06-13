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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9dcddb5766894a30f1ccb2552a09abe7153c6eea
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33434947"
---
# <a name="iclrruntimehostexecuteindefaultappdomain-method"></a><span data-ttu-id="85913-102">ICLRRuntimeHost::ExecuteInDefaultAppDomain 方法</span><span class="sxs-lookup"><span data-stu-id="85913-102">ICLRRuntimeHost::ExecuteInDefaultAppDomain Method</span></span>
<span data-ttu-id="85913-103">调用中指定的托管程序集的指定类型的指定的方法。</span><span class="sxs-lookup"><span data-stu-id="85913-103">Calls the specified method of the specified type in the specified managed assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="85913-104">语法</span><span class="sxs-lookup"><span data-stu-id="85913-104">Syntax</span></span>  
  
```  
HRESULT ExecuteInDefaultAppDomain (  
    [in] LPCWSTR pwzAssemblyPath,  
    [in] LPCWSTR pwzTypeName,   
    [in] LPCWSTR pwzMethodName,  
    [in] LPCWSTR pwzArgument,  
    [out] DWORD *pReturnValue  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="85913-105">参数</span><span class="sxs-lookup"><span data-stu-id="85913-105">Parameters</span></span>  
 `pwzAssemblyPath`  
 <span data-ttu-id="85913-106">[in]路径<xref:System.Reflection.Assembly>定义<xref:System.Type>其方法是调用。</span><span class="sxs-lookup"><span data-stu-id="85913-106">[in] The path to the <xref:System.Reflection.Assembly> that defines the <xref:System.Type> whose method is to be invoked.</span></span>  
  
 `pwzTypeName`  
 <span data-ttu-id="85913-107">[in]名称<xref:System.Type>，它定义要调用的方法。</span><span class="sxs-lookup"><span data-stu-id="85913-107">[in] The name of the <xref:System.Type> that defines the method to invoke.</span></span>  
  
 `pwzMethodName`  
 <span data-ttu-id="85913-108">[in]要调用的方法的名称。</span><span class="sxs-lookup"><span data-stu-id="85913-108">[in] The name of the method to invoke.</span></span>  
  
 `pwzArgument`  
 <span data-ttu-id="85913-109">[in]要传递给方法的字符串参数。</span><span class="sxs-lookup"><span data-stu-id="85913-109">[in] The string parameter to pass to the method.</span></span>  
  
 `pReturnValue`  
 <span data-ttu-id="85913-110">[out]被调用的方法返回的整数值。</span><span class="sxs-lookup"><span data-stu-id="85913-110">[out] The integer value returned by the invoked method.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="85913-111">返回值</span><span class="sxs-lookup"><span data-stu-id="85913-111">Return Value</span></span>  
  
|<span data-ttu-id="85913-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="85913-112">HRESULT</span></span>|<span data-ttu-id="85913-113">描述</span><span class="sxs-lookup"><span data-stu-id="85913-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="85913-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="85913-114">S_OK</span></span>|<span data-ttu-id="85913-115">`ExecuteInDefaultAppDomain` 已成功返回。</span><span class="sxs-lookup"><span data-stu-id="85913-115">`ExecuteInDefaultAppDomain` returned successfully.</span></span>|  
|<span data-ttu-id="85913-116">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="85913-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="85913-117">公共语言运行时 (CLR) 尚未加载到进程中，或 CLR 处于不能运行托管的代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="85913-117">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="85913-118">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="85913-118">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="85913-119">调用操作已超时。</span><span class="sxs-lookup"><span data-stu-id="85913-119">The call timed out.</span></span>|  
|<span data-ttu-id="85913-120">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="85913-120">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="85913-121">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="85913-121">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="85913-122">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="85913-122">HOST_E_ABANDONED</span></span>|<span data-ttu-id="85913-123">事件已被取消时被阻塞的线程，或者纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="85913-123">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="85913-124">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="85913-124">E_FAIL</span></span>|<span data-ttu-id="85913-125">出现未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="85913-125">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="85913-126">如果某方法返回 E_FAIL，CRL 不再可用进程内。</span><span class="sxs-lookup"><span data-stu-id="85913-126">If a method returns E_FAIL, the CRL is no longer usable within the process.</span></span> <span data-ttu-id="85913-127">到托管方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="85913-127">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="85913-128">备注</span><span class="sxs-lookup"><span data-stu-id="85913-128">Remarks</span></span>  
 <span data-ttu-id="85913-129">调用的方法必须具有以下签名：</span><span class="sxs-lookup"><span data-stu-id="85913-129">The invoked method must have the following signature:</span></span>  
  
```  
static int pwzMethodName (String pwzArgument)  
```  
  
 <span data-ttu-id="85913-130">其中`pwzMethodName`表示所调用方法的名称和`pwzArgument`表示的字符串值作为参数传递到该方法。</span><span class="sxs-lookup"><span data-stu-id="85913-130">where `pwzMethodName` represents the name of the invoked method, and `pwzArgument` represents the string value passed as a parameter to that method.</span></span> <span data-ttu-id="85913-131">如果 HRESULT 值设置为，则为 S_OK，`pReturnValue`设置为被调用的方法返回的整数值。</span><span class="sxs-lookup"><span data-stu-id="85913-131">If the HRESULT value is set to S_OK, `pReturnValue` is set to the integer value returned by the invoked method.</span></span> <span data-ttu-id="85913-132">否则为`pReturnValue`未设置。</span><span class="sxs-lookup"><span data-stu-id="85913-132">Otherwise, `pReturnValue` is not set.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="85913-133">要求</span><span class="sxs-lookup"><span data-stu-id="85913-133">Requirements</span></span>  
 <span data-ttu-id="85913-134">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="85913-134">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="85913-135">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="85913-135">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="85913-136">**库：** 作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="85913-136">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="85913-137">**.NET framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="85913-137">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="85913-138">请参阅</span><span class="sxs-lookup"><span data-stu-id="85913-138">See Also</span></span>  
 [<span data-ttu-id="85913-139">ICLRRuntimeHost 接口</span><span class="sxs-lookup"><span data-stu-id="85913-139">ICLRRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)
