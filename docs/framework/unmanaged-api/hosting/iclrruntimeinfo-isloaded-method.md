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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: fd1d97d9f3a44e2237cfc7a9e054a5ecfa2ebb01
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2019
ms.locfileid: "57470752"
---
# <a name="iclrruntimeinfoisloaded-method"></a><span data-ttu-id="7c0f0-102">ICLRRuntimeInfo::IsLoaded 方法</span><span class="sxs-lookup"><span data-stu-id="7c0f0-102">ICLRRuntimeInfo::IsLoaded Method</span></span>
<span data-ttu-id="7c0f0-103">指示公共语言运行时 (CLR) 是否与相关联[ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)接口加载到进程。</span><span class="sxs-lookup"><span data-stu-id="7c0f0-103">Indicates whether the common language runtime (CLR) associated with the [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interface is loaded into a process.</span></span> <span data-ttu-id="7c0f0-104">可以将运行时加载未也开始。</span><span class="sxs-lookup"><span data-stu-id="7c0f0-104">A runtime can be loaded without also being started.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7c0f0-105">语法</span><span class="sxs-lookup"><span data-stu-id="7c0f0-105">Syntax</span></span>  
  
```  
HRESULT IsLoaded(  
[in]  HANDLE hndProcess,  
[out, retval] BOOL *pbLoaded);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7c0f0-106">参数</span><span class="sxs-lookup"><span data-stu-id="7c0f0-106">Parameters</span></span>  
 `hndProcess`  
 <span data-ttu-id="7c0f0-107">[in]进程的句柄。</span><span class="sxs-lookup"><span data-stu-id="7c0f0-107">[in] A handle to the process.</span></span>  
  
 `pbLoaded`  
 <span data-ttu-id="7c0f0-108">[out]`true` CLR 加载到进程; 否则为如果`false`。</span><span class="sxs-lookup"><span data-stu-id="7c0f0-108">[out] `true` if the CLR is loaded into the process; otherwise, `false`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7c0f0-109">返回值</span><span class="sxs-lookup"><span data-stu-id="7c0f0-109">Return Value</span></span>  
 <span data-ttu-id="7c0f0-110">此方法返回以下特定 HRESULT 以及表示方法失败的 HRESULT 错误。</span><span class="sxs-lookup"><span data-stu-id="7c0f0-110">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="7c0f0-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="7c0f0-111">HRESULT</span></span>|<span data-ttu-id="7c0f0-112">描述</span><span class="sxs-lookup"><span data-stu-id="7c0f0-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="7c0f0-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="7c0f0-113">S_OK</span></span>|<span data-ttu-id="7c0f0-114">该方法已成功完成。</span><span class="sxs-lookup"><span data-stu-id="7c0f0-114">The method completed successfully.</span></span>|  
|<span data-ttu-id="7c0f0-115">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="7c0f0-115">E_POINTER</span></span>|<span data-ttu-id="7c0f0-116">`pbLoaded` 为 null。</span><span class="sxs-lookup"><span data-stu-id="7c0f0-116">`pbLoaded` is null.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7c0f0-117">备注</span><span class="sxs-lookup"><span data-stu-id="7c0f0-117">Remarks</span></span>  
 <span data-ttu-id="7c0f0-118">此方法是向后兼容使用以下函数和接口：</span><span class="sxs-lookup"><span data-stu-id="7c0f0-118">This method is backward-compatible with the following functions and interfaces:</span></span>  
  
-   <span data-ttu-id="7c0f0-119">[ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) （.NET Framework 版本 1 的托管 API) 中的接口。</span><span class="sxs-lookup"><span data-stu-id="7c0f0-119">[ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) interface (in the .NET Framework version 1 hosting API).</span></span>  
  
-   <span data-ttu-id="7c0f0-120">[ICLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)界面 （在.NET Framework 2.0 托管 API)。</span><span class="sxs-lookup"><span data-stu-id="7c0f0-120">[ICLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md) interface (in the .NET Framework 2.0 hosting API).</span></span>  
  
-   <span data-ttu-id="7c0f0-121">已弃用`CorBindTo*`函数 (请参阅[弃用的 CLR 承载函数](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)托管 API 在.NET Framework 2.0 中)。</span><span class="sxs-lookup"><span data-stu-id="7c0f0-121">Deprecated `CorBindTo*` functions (see [Deprecated CLR Hosting Functions](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md) in the .NET Framework 2.0 hosting API).</span></span>  
  
 <span data-ttu-id="7c0f0-122">主机可以调用不推荐使用之一`CorBindTo*`函数，如[CorBindToRuntime](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntime-function.md)函数来实例化特定版本的 CLR。</span><span class="sxs-lookup"><span data-stu-id="7c0f0-122">A host may call one of the deprecated `CorBindTo*` functions, such as the [CorBindToRuntime](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntime-function.md) function, to instantiate a specific version of the CLR.</span></span> <span data-ttu-id="7c0f0-123">随后可以调用主机[iclrmetahost:: Getruntime](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-getruntime-method.md)方法并指定要获取的相同版本号[ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)接口。</span><span class="sxs-lookup"><span data-stu-id="7c0f0-123">The host could then call the [ICLRMetaHost::GetRuntime](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-getruntime-method.md) method and specify the same version number to obtain a [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interface.</span></span>  
  
 <span data-ttu-id="7c0f0-124">如果主机然后调用`IsLoaded`方法返回[ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)接口，`pbLoaded`返回`true`; 否则为它将返回`false`。</span><span class="sxs-lookup"><span data-stu-id="7c0f0-124">If the host then calls the `IsLoaded` method on the returned [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interface, `pbLoaded` returns `true`; otherwise, it returns `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7c0f0-125">要求</span><span class="sxs-lookup"><span data-stu-id="7c0f0-125">Requirements</span></span>  
 <span data-ttu-id="7c0f0-126">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="7c0f0-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7c0f0-127">**标头：** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="7c0f0-127">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="7c0f0-128">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="7c0f0-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7c0f0-129">**.NET Framework 版本：**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7c0f0-129">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7c0f0-130">请参阅</span><span class="sxs-lookup"><span data-stu-id="7c0f0-130">See also</span></span>
- [<span data-ttu-id="7c0f0-131">ICLRRuntimeInfo 接口</span><span class="sxs-lookup"><span data-stu-id="7c0f0-131">ICLRRuntimeInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)
- [<span data-ttu-id="7c0f0-132">承载接口</span><span class="sxs-lookup"><span data-stu-id="7c0f0-132">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="7c0f0-133">承载</span><span class="sxs-lookup"><span data-stu-id="7c0f0-133">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
