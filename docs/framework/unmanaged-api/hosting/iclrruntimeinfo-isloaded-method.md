---
title: ICLRRuntimeInfo::IsLoaded 方法
ms.date: 03/30/2017
api_name:
- ICLRRuntimeInfo.IsLoaded
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeInfo::IsLoaded
helpviewer_keywords:
- IsLoaded method [.NET Framework hosting]
- ICLRRuntimeInfo::IsLoaded method [.NET Framework hosting]
ms.assetid: fdc5a3a7-71ff-4025-99a1-59e4ee0bfe1b
topic_type:
- apiref
ms.openlocfilehash: e0ab16348abbaff00152f2b259ccafdd331174df
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73136365"
---
# <a name="iclrruntimeinfoisloaded-method"></a><span data-ttu-id="1b28c-102">ICLRRuntimeInfo::IsLoaded 方法</span><span class="sxs-lookup"><span data-stu-id="1b28c-102">ICLRRuntimeInfo::IsLoaded Method</span></span>
<span data-ttu-id="1b28c-103">指示是否将与[ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)接口关联的公共语言运行时（CLR）加载到进程中。</span><span class="sxs-lookup"><span data-stu-id="1b28c-103">Indicates whether the common language runtime (CLR) associated with the [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interface is loaded into a process.</span></span> <span data-ttu-id="1b28c-104">可以在不启动的情况下加载运行时。</span><span class="sxs-lookup"><span data-stu-id="1b28c-104">A runtime can be loaded without also being started.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1b28c-105">语法</span><span class="sxs-lookup"><span data-stu-id="1b28c-105">Syntax</span></span>  
  
```cpp  
HRESULT IsLoaded(  
[in]  HANDLE hndProcess,  
[out, retval] BOOL *pbLoaded);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1b28c-106">参数</span><span class="sxs-lookup"><span data-stu-id="1b28c-106">Parameters</span></span>  
 `hndProcess`  
 <span data-ttu-id="1b28c-107">中进程的句柄。</span><span class="sxs-lookup"><span data-stu-id="1b28c-107">[in] A handle to the process.</span></span>  
  
 `pbLoaded`  
 <span data-ttu-id="1b28c-108">[out] `true` 是否将 CLR 加载到进程中;否则，`false`。</span><span class="sxs-lookup"><span data-stu-id="1b28c-108">[out] `true` if the CLR is loaded into the process; otherwise, `false`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1b28c-109">返回值</span><span class="sxs-lookup"><span data-stu-id="1b28c-109">Return Value</span></span>  
 <span data-ttu-id="1b28c-110">此方法返回以下特定 HRESULT 以及表示方法失败的 HRESULT 错误。</span><span class="sxs-lookup"><span data-stu-id="1b28c-110">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="1b28c-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="1b28c-111">HRESULT</span></span>|<span data-ttu-id="1b28c-112">描述</span><span class="sxs-lookup"><span data-stu-id="1b28c-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="1b28c-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="1b28c-113">S_OK</span></span>|<span data-ttu-id="1b28c-114">该方法已成功完成。</span><span class="sxs-lookup"><span data-stu-id="1b28c-114">The method completed successfully.</span></span>|  
|<span data-ttu-id="1b28c-115">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="1b28c-115">E_POINTER</span></span>|<span data-ttu-id="1b28c-116">`pbLoaded` 为 null。</span><span class="sxs-lookup"><span data-stu-id="1b28c-116">`pbLoaded` is null.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1b28c-117">备注</span><span class="sxs-lookup"><span data-stu-id="1b28c-117">Remarks</span></span>  
 <span data-ttu-id="1b28c-118">此方法与以下函数和接口向后兼容：</span><span class="sxs-lookup"><span data-stu-id="1b28c-118">This method is backward-compatible with the following functions and interfaces:</span></span>  
  
- <span data-ttu-id="1b28c-119">[ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)接口（在 .NET Framework 版本1宿主 API 中）。</span><span class="sxs-lookup"><span data-stu-id="1b28c-119">[ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) interface (in the .NET Framework version 1 hosting API).</span></span>  
  
- <span data-ttu-id="1b28c-120">[ICLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)接口（在 .NET Framework 2.0 托管 API 中）。</span><span class="sxs-lookup"><span data-stu-id="1b28c-120">[ICLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md) interface (in the .NET Framework 2.0 hosting API).</span></span>  
  
- <span data-ttu-id="1b28c-121">弃用的 `CorBindTo*` 函数（请参阅 .NET Framework 2.0 托管 API 中[弃用的 CLR 承载函数](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)）。</span><span class="sxs-lookup"><span data-stu-id="1b28c-121">Deprecated `CorBindTo*` functions (see [Deprecated CLR Hosting Functions](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md) in the .NET Framework 2.0 hosting API).</span></span>  
  
 <span data-ttu-id="1b28c-122">宿主可以调用不推荐使用的 `CorBindTo*` 函数之一（如[CorBindToRuntime](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntime-function.md)函数）来实例化特定版本的 CLR。</span><span class="sxs-lookup"><span data-stu-id="1b28c-122">A host may call one of the deprecated `CorBindTo*` functions, such as the [CorBindToRuntime](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntime-function.md) function, to instantiate a specific version of the CLR.</span></span> <span data-ttu-id="1b28c-123">然后，宿主可以调用[ICLRMetaHost：： GetRuntime](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-getruntime-method.md)方法，并指定相同的版本号以获取[ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)接口。</span><span class="sxs-lookup"><span data-stu-id="1b28c-123">The host could then call the [ICLRMetaHost::GetRuntime](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-getruntime-method.md) method and specify the same version number to obtain a [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interface.</span></span>  
  
 <span data-ttu-id="1b28c-124">如果宿主在返回的[ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)接口上调用 `IsLoaded` 方法，`pbLoaded` 返回 `true`;否则，它将返回 `false`。</span><span class="sxs-lookup"><span data-stu-id="1b28c-124">If the host then calls the `IsLoaded` method on the returned [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interface, `pbLoaded` returns `true`; otherwise, it returns `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1b28c-125">要求</span><span class="sxs-lookup"><span data-stu-id="1b28c-125">Requirements</span></span>  
 <span data-ttu-id="1b28c-126">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="1b28c-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1b28c-127">**标头：** MetaHost</span><span class="sxs-lookup"><span data-stu-id="1b28c-127">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="1b28c-128">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="1b28c-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1b28c-129">**.NET Framework 版本：** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1b28c-129">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1b28c-130">请参阅</span><span class="sxs-lookup"><span data-stu-id="1b28c-130">See also</span></span>

- [<span data-ttu-id="1b28c-131">ICLRRuntimeInfo 接口</span><span class="sxs-lookup"><span data-stu-id="1b28c-131">ICLRRuntimeInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)
- [<span data-ttu-id="1b28c-132">承载接口</span><span class="sxs-lookup"><span data-stu-id="1b28c-132">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="1b28c-133">承载</span><span class="sxs-lookup"><span data-stu-id="1b28c-133">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
